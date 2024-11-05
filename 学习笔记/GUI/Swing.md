#### 窗口，面板
其实Swing只是有些类名字前面加了一个J，其本质是继承Frame类，是Frame类的子类
```
package com.yifan.TestFrame.lesson4;  
  
import javax.swing.*;  
import java.awt.*;  
  
public class JFrameDemo {  
    //init()初始化的方法  
    public void init(){  
        JFrame jFrame=new JFrame("JFrame");  
        jFrame.setBounds(200,200,200,200);  
        jFrame.setBackground(Color.PINK);  
        //添加标签  
        JLabel jLabel=new JLabel("java学习");  
        jFrame.add(jLabel);  
        //给标签设置水平居中  
        jLabel.setHorizontalAlignment(SwingConstants.CENTER);  
        //JFrame不能直接设置颜色  
        //JFrame本质是一个容器，给JFrame设置颜色先获取container对象，给它设置颜色  
        Container contentPane = jFrame.getContentPane();  
        contentPane.setBackground(Color.pink);  
  
        jFrame.setVisible(true);  
        //关闭事件  
        jFrame.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
    }  
    public static void main(String[] args) {  
        new JFrameDemo().init();  
    }  
}
```


#### JDialog弹窗
点击某处能触发弹窗(弹出另外一个界面)
```
package com.yifan.TestFrame.lesson4;  
  
import javax.swing.*;  
import java.awt.*;  
import java.awt.event.ActionEvent;  
import java.awt.event.ActionListener;  
  
public class DialogDemo {  
    public void init(){  
        JFrame jFrame=new JFrame();  
        jFrame.setBounds(200,200,400,400);  
        //设置界面绝对布局  
        //参数填null就是绝对布局  
        //设置了绝对布局之后需要设置所有组件的大小，否则它们将保持默认的零大小，并且不会出现
        jFrame.setLayout(null);  
  
        jFrame.setVisible(true);  
        //设置一个按钮来触发弹窗事件  
        JButton jButton=new JButton("点我触发弹窗");  
        jButton.setBounds(80,80,200,200);  
        jFrame.add(jButton);  
        //给按钮添加事件  
        jButton.addActionListener(new ActionListener() {  
            @Override  
            public void actionPerformed(ActionEvent e) {  
                new MyDialogFrame().CreateMyDialogFrame();  
            }  
        });  
    }  
  
    public static void main(String[] args) {  
        new DialogDemo().init();  
    }  
}  
class MyDialogFrame extends JDialog{  
    void CreateMyDialogFrame(){  
        setBounds(400,400,400,400);  
        setVisible(true);  
        Container contentPane = getContentPane();  
        contentPane.setLayout(null);  
        JLabel jLabel=new JLabel("听话喵");  
        jLabel.setBounds(100,100,100,100);  
        contentPane.add(jLabel);  
    }  
}
```


#### 标签
lable
```
package com.yifan.TestFrame.lesson4;  
  
import javax.swing.*;  
import java.awt.*;  
  
//图标，需要实现类，JFrame继承  
public class IconDemo extends JFrame implements Icon{  
    private int width;  
    private int height;  
    //无参构造，带参构造  
    public IconDemo(){}  
    public IconDemo(int width,int height){  
        this.width=width;  
        this.height=height;  
    }  
    public void init(){  
        IconDemo iconDemo=new IconDemo(15,15);  
        JLabel jLabel=new JLabel("tub",iconDemo,SwingConstants.CENTER);  
        Container contentPane =getContentPane();  
        contentPane.add(jLabel);  
        setVisible(true);  
        setBounds(200,200,200,200);  
        setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
    }  
    @Override  
    public void paintIcon(Component c, Graphics g, int x, int y) {  
        g.fillOval(x,y,width,height);  
    }  
  
    @Override  
    public int getIconWidth() {  
        return width;  
    }  
  
    @Override  
    public int getIconHeight() {  
        return height;  
    }  
  
    public static void main(String[] args) {  
        new IconDemo().init();  
    }  
}
```

图标ICON
```
package com.yifan.TestFrame.lesson4;  
  
import javax.swing.*;  
import java.awt.*;  
import java.net.URL;  
  
public class ImageIconDemo extends JFrame {  
    public ImageIconDemo(){  
        //获取图片地址  
        JLabel jLabel=new JLabel(":D");  
        //ImageIconDemo.class.getResource("crossing.png")表示找这个类同一级的文件  
        URL resource = ImageIconDemo.class.getResource("crossing.png");  
        ImageIcon imageIcon=new ImageIcon(resource);  
        //给标签添加图片  
        jLabel.setIcon(imageIcon);  
        jLabel.setHorizontalAlignment(SwingConstants.CENTER);  
  
        Container contentPane = getContentPane();  
        contentPane.add(jLabel);  
        setVisible(true);  
        setBounds(200,200,200,200);  
        setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
    }  
  
  
    public static void main(String[] args) {  
        new ImageIconDemo();  
    }  
}
```

#### JPanel面板
```
package com.yifan.TestFrame.lesson4;  
  
import javax.swing.*;  
import java.awt.*;  
  
public class JPanelDemo extends JFrame {  
    public JPanelDemo(){  
//        Container contentPane = getContentPane();  
////        contentPane.setLayout();  
//        JLabel jLabel=new JLabel();  
//        jLabel.setLayout(new GridLayout(1,3));  
//        jLabel.add(new JButton("1"));  
//        jLabel.add(new JButton("1"));  
//        jLabel.add(new JButton("1"));  
//        contentPane.add(jLabel);  
//        setVisible(true);  
//        setSize(200,200);  
    }  
    void init(){  
        JFrame jFrame=new JFrame("hello");  
//        contentPane.setLayout();  
        JLabel jLabel=new JLabel();  
        jLabel.setLayout(new GridLayout(1,3));  
        jLabel.add(new JButton("1"));  
        jLabel.add(new JButton("1"));  
        jLabel.add(new JButton("1"));  
        jFrame.add(jLabel);  
        jFrame.setVisible(true);  
        jFrame.setSize(200,200);  
    }  
    public static void main(String[] args) {  
        new JPanelDemo().init();  
    }  
}
```


#### JScroll
```
package com.yifan.TestFrame.lesson4;  
  
import javax.swing.*;  
import java.awt.*;  
  
public class JScrollDemo extends JFrame {  
    public JScrollDemo(){  
        Container contentPane = getContentPane();  
  
        JScrollPane jScrollPane = new JScrollPane(new TextArea("hello", 20, 30));  
        contentPane.add(jScrollPane);  
  
        setBounds(200,200,200,150);  
        setVisible(true);  
    }  
    public static void main(String[] args) {  
        new JScrollDemo();  
    }  
}
```

#### 图片按钮
```
package com.yifan.TestFrame.lesson5;  
  
import javax.swing.*;  
import java.awt.*;  
import java.net.URL;  
  
public class JButtonDemo1 extends JFrame {  
    public JButtonDemo1(){  
        Container contentPane = this.getContentPane();  
        //获得图片路径  
        URL resource = JButtonDemo1.class.getResource("crossing.png");  
        Icon icon = new ImageIcon(resource);  
        JButton jButton = new JButton();  
        jButton.setIcon(icon);  
        contentPane.add(jButton);  
  
        setBounds(200,200,200,200);  
        setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
        setVisible(true);  
    }  
    public static void main(String[] args) {  
        new JButtonDemo1();  
    }  
}
```

#### 单选框
```
package com.yifan.TestFrame.lesson5;  
  
import javax.swing.*;  
import java.awt.*;  
  
public class JRationButtonDemo extends JFrame {  
    void init(){  
        JFrame jFrame = new JFrame("hello");  
        //三个单选框  
        JRadioButton jRadioButton1 = new JRadioButton("111");  
        JRadioButton jRadioButton2 = new JRadioButton("222");  
        JRadioButton jRadioButton3 = new JRadioButton("333");  
  
  
        //单选框只能选一个，给它们分组,一个组只能选一个  
        ButtonGroup buttonGroup = new ButtonGroup();  
        buttonGroup.add(jRadioButton1);  
        buttonGroup.add(jRadioButton2);  
        buttonGroup.add(jRadioButton3);  
  
        //添加按钮进入面板，再添加面板入界面  
        JPanel jPanel = new JPanel();  
        jPanel.add(jRadioButton1);  
        jPanel.add(jRadioButton2);  
        jPanel.add(jRadioButton3);  
        jFrame.add(jPanel);  
  
        jFrame.setVisible(true);  
        jFrame.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
        jFrame.setBounds(200,200,200,200);  
    }  
  
    public static void main(String[] args) {  
        new JRationButtonDemo().init();  
    }  
}
```

#### 多选框
```
package com.yifan.TestFrame.lesson5;  
  
import javax.swing.*;  
import java.awt.*;  
  
public class JCheckBoxDemo extends JFrame {  
    void init(){  
        JFrame jf = new JFrame("hello");  
        //两个多选框  
        JCheckBox jCheckBox1 = new JCheckBox("111");  
        JCheckBox jCheckBox2 = new JCheckBox("222");  
        JCheckBox jCheckBox3 = new JCheckBox("333");  
  
        JPanel jPanel = new JPanel();  
        jPanel.add(jCheckBox1);  
        jPanel.add(jCheckBox2);  
        jPanel.add(jCheckBox3);  
        jf.add(jPanel);  
  
        jf.setVisible(true);  
        jf.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
        jf.setBounds(200,200,200,200);  
    }  
    public static void main(String[] args) {  
        new JCheckBoxDemo().init();  
    }  
}
```


#### 下拉框
```
package com.yifan.TestFrame.lesson6;  
  
import javax.swing.*;  
import java.awt.*;  
import java.awt.event.*;  
  
public class JComboDemo extends JFrame {  
    void init(){  
        JFrame jFrame = new JFrame();  
        jFrame.setLayout(null);  
  
        //创建下拉框对象  
        JComboBox jComboBox = new JComboBox();  
  
        //添加下拉框选项  
        jComboBox.addItem("hello");  
        jComboBox.addItem("sorry");  
        jComboBox.addItem("GoodMorning");  
        jComboBox.addItem("GoodAfternoon");  
        jComboBox.addItem("GoodEvening");  
  
        //给下拉框添加监听  
        jComboBox.addItemListener(new JComboListener() );  
  
  
        jComboBox.setBounds(0,0,285,30);  
        jFrame.add(jComboBox);  
  
  
        jFrame.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
        jFrame.setVisible(true);  
        jFrame.setBounds(300,300,300,300);  
    }  
      
    public static void main(String[] args) {  
        new JComboDemo().init();  
    }  
    class JComboListener implements ItemListener {  
  
        @Override  
        public void itemStateChanged(ItemEvent e) {  
            JComboBox jComboBox =(JComboBox) e.getSource();  
//            String selectedItem =(String) jComboBox.getSelectedItem();  
//            System.out.println(selectedItem);  
            //不懂这里为啥打印两次  
            System.out.println(jComboBox.getSelectedItem());  
        }  
    }  
}
```


#### 列表框
```
package com.yifan.TestFrame.lesson6;  
  
import javax.swing.*;  
import java.awt.*;  
  
public class JListDemo extends JFrame {  
  
    public JListDemo() {  
        Container contentPane = getContentPane();  
  
        //生成列表需要对象  
        String[] contents={"1","2","3"};  
  
  
        //创建列表对象  
        JList jList = new JList(contents);  
  
  
        contentPane.add(jList);  
  
        setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
        setVisible(true);  
        setBounds(300,300,300,300);  
  
  
    }  
  
  
    void init(){  
        JFrame jFrame = new JFrame();  
  
        //创建列表对象  
        JList jList=new JList();  
        jFrame.add(jList);  
  
        //生成列表需要对象  
        String[] contents={"sayori","yuri"};  
  
//        DefaultListModel defaultListModel = new DefaultListModel();  
//        defaultListModel.add(0,contents);  
  
  
  
        jFrame.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
        jFrame.setVisible(true);  
        jFrame.setBounds(300,300,300,300);  
    }  
  
    public static void main(String[] args) {  
        new JListDemo();  
    }  
}
```


#### 文本域
```
package com.yifan.TestFrame.lesson6;  
  
import javax.swing.*;  
  
public class JTextFieldDemo extends JFrame {  
  
  
    void init(){  
        JFrame jFrame = new JFrame();  
        jFrame.setLayout(null);  
  
        //创建文本域对象  
        JTextField jTextField=new JTextField(10);  
        JTextArea jTextArea = new JTextArea(3,3);  
  
        jTextField.setBounds(0,0,300,100);  
        jTextArea.setBounds(0,160,300,30);  
  
        jFrame.add(jTextField);  
        jFrame.add(jTextArea);  
  
  
  
        jFrame.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
        jFrame.setVisible(true);  
        jFrame.setBounds(300,300,300,300);  
    }  
  
    public static void main(String[] args) {  
        new JTextFieldDemo().init();  
    }  
}
```


#### 密码框
```
package com.yifan.TestFrame.lesson5;  
  
import javax.swing.*;  
  
public class JPasswordDemo extends JFrame {  
  
    void init(){  
        JFrame jFrame = new JFrame();  
  
        JPasswordField jPasswordField = new JPasswordField();  
  
        jFrame.add(jPasswordField);  
  
  
        jFrame.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
        jFrame.setVisible(true);  
        jFrame.setBounds(300,300,300,300);  
    }  
    public static void main(String[] args) {  
        new JPasswordDemo().init();  
    }  
}
```


#### 文本域
```
package com.yifan.TestFrame.lesson5;  
  
import javax.swing.*;  
import java.awt.*;  
  
public class JScrollDemo extends JFrame {  
    public JScrollDemo(){  
        Container contentPane = getContentPane();  
  
        JScrollPane jScrollPane = new JScrollPane(new TextArea("hello", 20, 30));  
        contentPane.add(jScrollPane);  
  
        setBounds(200,200,200,150);  
        setVisible(true);  
        setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
    }  
    public static void main(String[] args) {  
        new JScrollDemo();  
    }  
}
```