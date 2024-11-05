#### AWT介绍
1.包含了很多类和接口！ GUI!
2.元素：窗口，按钮，文本框
3.java.awt
4.![[Pasted image 20240830220006.png]]
早期JavaScript还没出生，由Applet来写这些东西，当时很多人因为这个而了解Java


#### 组件和内容
第一个GUI界面
首先psvm，一个main函数没得说
窗口也是一个对象
Frame，JDK，不会的看源码
CTRL加点击即可进入源码，通过源码来学习这个类，不会的看源码，
Frame frame=new Frame(“标题”)
有了界面需要设置可见性，因为它还储存在内存里
类的方法不需要看API帮助文档，直接.去查看，方法见名知意
frame.setVisible(true)
和web一样还需要这是宽高，也就是窗口大小
frame.setSize(宽，高)
设置背景颜色 Color类
frame.setBackground()
弹出的初始位置
frame.setLocation(x轴位置，y轴位置)
设置窗口是否固定
frame.setResizable(false)

public class TestFrame {  
    public static void main(String[] args) {  
        Frame frame=new Frame("第一个界面");  
        frame.setVisible(true);  
        frame.setSize(400,400);  
        frame.setBackground(Color.PINK);  
        frame.setLocation(400,400);  
        frame.setResizable(false);  
    }  
}
问题：窗口无法点击右上角关闭
尝试回顾封装，自己写一个类来封装


#### 面板panel
面板可以看成一个空间，但是不能独立存在
先写一个窗口
Frame frame=new Frame()
new一个面板
Panel panel=new Panel
设置布局，不然面板会默认置顶
frame.setLayout(null)
设置坐标，面板也要设置坐标,面板的坐标相对于frame
frame.setBounds(300,300,400.400)
frame.setBackground(new Color(40,161,35))
panel.setBounds(50,50,400,400)
panel.setBackground(new Color(193,15,60))
给界面添加面板
frame.add(panel)
设置界面可见
frame.setVisible(true)
监听事件，监听窗口关闭事件 System.exit()
适配器模式，我们需要一个类来实现这个功能但是这个类有很多重写的方法，我们不需要这么多，我们可以去寻找它的子类
frame.addWindowListener(new WindowAdapter(){
窗口点击关闭的时候需要做的事情
@Override(这是方法重写的标志)
public void windowClosing(windowEvent e){
结束程序，也就是停掉虚拟机
System.exit(0)
}
})


#### 布局管理器
1.流式布局
package com.yifan.TestFrame.lesson1;  
  
import java.awt.*;  
  
public class TestFlowLayout {  
    public static void main(String[] args) {  
        Frame frame=new Frame();  
        //组件-按钮  
        Button button1=new Button();  
        Button button2=new Button();  
        Button button3=new Button();  
        //布局设置为流式布局  
        frame.setLayout(new FlowLayout(1));  
        frame.setSize(200,200);  
        frame.add(button1);  
        frame.add(button2);  
        frame.add(button3);  
        frame.setVisible(true);  
    }  
}
通俗来说就是靠左，靠右居中
2.东西南北中(BorderLayout)
package com.yifan.TestFrame.lesson1;  
  
import java.awt.*;  
  
public class TestBorderLayout {  
    public static void main(String[] args) {  
        Frame frame=new Frame("BorderLayout");  
        //括号里面的是按钮上的文字  
        Button east=new Button("east");  
        Button west=new Button("west");  
        Button south=new Button("south");  
        Button north=new Button("north");  
        Button center=new Button("center");  
        frame.add(east,BorderLayout.EAST);  
        frame.add(west,BorderLayout.WEST);  
        frame.add(south,BorderLayout.SOUTH);  
        frame.add(north,BorderLayout.NORTH);  
        frame.add(center,BorderLayout.CENTER);  
        frame.setSize(400,400);  
        frame.setVisible(true);  
    }  
}
![[Pasted image 20240831101312.png]]
3.表格布局(GridLayout)
类似于表格的形式
package com.yifan.TestFrame.lesson1;  
  
import java.awt.*;  
  
public class TestGridLayout {  
    public static void main(String[] args) {  
        Frame frame=new Frame("GridLayout");  
        //括号里面的是按钮上的文字  
        Button btn1=new Button("east");  
        Button btn2=new Button("west");  
        Button btn3=new Button("south");  
        Button btn4=new Button("north");  
        Button btn5=new Button("center");  
        Button btn6=new Button("center");  
        frame.add(btn1);  
        frame.add(btn2);  
        frame.add(btn3);  
        frame.add(btn4);  
        frame.add(btn5);  
        frame.add(btn6);  
        frame.setLayout(new GridLayout(2,2));  
        frame.setSize(500,500);  
        frame.setVisible(true);  
    }  
}
![[Pasted image 20240831102520.png]]


#### 课堂练习
写出一个这样的布局
![[Pasted image 20240831105223.png]]

先构思再写代码
package com.yifan.TestFrame.lesson1;  
  
import java.awt.*;  
import java.awt.event.WindowAdapter;  
import java.awt.event.WindowEvent;  
  
public class Demo {  
    public static void main(String[] args) {  
        Frame frame=new Frame();  
        frame.setSize(400,400);  
        frame.setLocation(200,200);  
        frame.setLayout(new GridLayout(2,1));  
        frame.setVisible(true);  
        frame.addWindowListener(new WindowAdapter() {  
            @Override  
            public void windowClosing(WindowEvent e) {  
                System.exit(0);  
            }  
        });  
        //4个面板  
        Panel panel1=new Panel();  
        Panel panel2=new Panel();  
        Panel panel3=new Panel();  
        Panel panel4=new Panel();  
        //将面板排序布局  
        panel1.setLayout(new BorderLayout());  
        panel2.setLayout(new GridLayout(2,1));  
        panel3.setLayout(new BorderLayout());  
        panel4.setLayout(new GridLayout(2,2));  
        //在面板里面添加按钮并且布局  
        panel1.add(new Button("p1-east-1"),BorderLayout.EAST);  
        panel1.add(new Button("p1-west-1"),BorderLayout.WEST);  
        panel2.add(new Button("P2-up"));  
        panel2.add(new Button("P2-down"));  
        panel1.add(panel2,BorderLayout.CENTER);  
        
        panel3.add(new Button("p3-east-1"),BorderLayout.EAST);  
        panel3.add(new Button("p3-west-1"),BorderLayout.WEST);  
        for (int i = 0; i < 4; i++) {  
            panel4.add(new Button("p4"+(i+1)));  
        }  
        panel3.add(panel4,BorderLayout.CENTER);  
  
        //放面板进入界面  
        frame.add(panel1);  
        frame.add(panel3);  
    }  
}

#### 总结
1.Frame是一个顶级窗口
2.Panel无法单独显示，必须添加到某个容器中
3.布局管理器
 - 流式()
 - 东西南北中(BorderLayout)
 - 表格(GrimLayout)
4.大小，定位，背景颜色，可见性，监听


#### 事件监听
事件监听：当某个事件发生的时候，干什么？
```
package com.yifan.TestFrame.lesson2;  
  
import java.awt.*;  
import java.awt.event.ActionEvent;  
import java.awt.event.ActionListener;  
import java.awt.event.WindowAdapter;  
import java.awt.event.WindowEvent;  
  
public class TestActionEvent {  
    public static void main(String[] args) {  
        Frame frame=new Frame();  
        Button button = new Button();  
        //创建事件监听类然后给按钮添加事件监听效果  
        MyActionListener myActionListener=new MyActionListener();  
        button.addActionListener(myActionListener);  
        frame.add(button);  
        frame.setSize(200,200);  
        windowClose(frame);  
        frame.setVisible(true);  
    }  
    //写一个关闭窗口的方法  
    public static void windowClose(Frame frame){  
        frame.addWindowListener(new WindowAdapter() {  
            @Override  
            public void windowClosing(WindowEvent e) {  
                System.exit(1);  
            }  
        });  
  
    }  
}  
//写一个事件监听的类  
//接ActionListener接口
class MyActionListener implements ActionListener{  
    @Override  
    public void actionPerformed(ActionEvent e) {  
        System.out.println("成功");  
    }  
}
```

多个按钮共享一个事件
```
package com.yifan.TestFrame.lesson2;  
  
import java.awt.*;  
import java.awt.event.ActionEvent;  
import java.awt.event.ActionListener;  
  
public class TestActionTwo {  
    public static void main(String[] args) {  
        Frame frame=new Frame();  
        Button button1=new Button("START");  
        Button button2=new Button("END");  
        //可以显示的定义触发会返回的命令，如果不显示定义，则会走默认的值  
        //可以多个按钮只写一个监听类  
        button2.setActionCommand("按钮2");  
        MyMonitor myMonitor=new MyMonitor();  
  
        button1.addActionListener(myMonitor);  
        button2.addActionListener(myMonitor);  
  
        frame.add(button1,BorderLayout.NORTH);  
        frame.add(button2,BorderLayout.SOUTH);  
        frame.setSize(200,200);  
        frame.setVisible(true);  
    }  
}  
//写一个事件监听事件  
class MyMonitor implements ActionListener{  
  
    @Override  
    public void actionPerformed(ActionEvent e) {  
        //getActionCommand方法，获得按钮的信息  
        //e.getActionCommand();  
        System.out.println(e.getActionCommand());  
        if(e.getActionCommand().equals("按钮2")){  
            System.out.println("wow");  
        }  
    }  
}
```
#### 输入框TestField监听
```
package com.yifan.TestFrame.lesson2;  
  
import java.awt.*;  
import java.awt.event.ActionEvent;  
import java.awt.event.ActionListener;  
  
public class TestTest {  
    public static void main(String[] args) {  
        //编程思想，主函数里面只写启动函数  
        new MyFrame();  
    }  
}  
class MyFrame extends Frame{  
    public MyFrame(){  
        TextField field=new TextField();  
        TextFieldListener textFieldListener=new TextFieldListener();  
        field.addActionListener(textFieldListener);  
        add(field);  
        //设置替换代码，把文本框里面字符显示为该字符  
        field.setEchoChar('*');  
        setVisible(true);  
        //pack这个方法是让界面里的组件自适应  
        pack();  
    }  
}  
//做一个事件监听类，监听文本框里面的内容，获取里面的资源  
class TextFieldListener implements ActionListener{  
  
    @Override  
    public void actionPerformed(ActionEvent e) {  
        //getSource获得一些资源，返回一个对象  
        TextField field =(TextField) e.getSource();  
        //得到文本框里面的文本  
        System.out.println(field.getText());  
        //按下回车后把文本框里的文本设置成空字符串  
        field.setText("");  
    }  
}
```

#### 简易计算器，组合+内部类回顾复习
oop原则：组合，大于继承
旧版本(面向过程类)
```
package com.yifan.TestFrame.lesson2;  
  
import java.awt.*;  
import java.awt.event.ActionEvent;  
import java.awt.event.ActionListener;  
import java.awt.event.WindowAdapter;  
import java.awt.event.WindowEvent;  
  
public class TestCalc {  
    public static void main(String[] args) {  
        new MyCalculator();  
    }  
}  
//计算器类，继承界面  
class MyCalculator extends Frame{  
    public MyCalculator(){  
        //三个文本框，加号以及按钮  
        //加号使用标签Label类  
        TextField num1=new TextField(10);  
        Label label=new Label("+");  
        TextField num2=new TextField(10);  
        Button button=new Button("=");  
        TextField num3=new TextField(20);  
        //给按钮添加事件  
        button.addActionListener(new MyCalcListener(num1,num2,num3));  
        //流式布局  
        setLayout(new FlowLayout());  
        //自适应布局方法pack  
        setSize(500,80);  
//        pack();  
        //添加组件进入  
        add(num1);  
        add(label);  
        add(num2);  
        add(button);  
        add(num3);  
  
        setVisible(true);  
        addWindowListener(new WindowAdapter() {  
            @Override  
            public void windowClosing(WindowEvent e) {  
                System.exit(1);  
            }  
        });  
    }  
}  
//给按钮加一个事件监听  
class MyCalcListener implements ActionListener{  
    private TextField num1;  
    private TextField num2;  
    private TextField num3;  
    public MyCalcListener(TextField num1,TextField num2,TextField num3){  
        this.num1=num1;  
        this.num2=num2;  
        this.num3=num3;  
    }  
    @Override  
    public void actionPerformed(ActionEvent e) {  
        int n1=Integer.parseInt(num1.getText());  
        int n2=Integer.parseInt(num2.getText());  
        num3.setText(""+(n1+n2));  
        num1.setText("");  
        num2.setText("");  
    }  
}
```
完全改造成面向对象
```
package com.yifan.TestFrame.lesson2;  
  
import java.awt.*;  
import java.awt.event.ActionEvent;  
import java.awt.event.ActionListener;  
import java.awt.event.WindowAdapter;  
import java.awt.event.WindowEvent;  
  
public class TestCalc {  
    public static void main(String[] args) {  
        new MyCalculator().LoadFrame();  
    }  
}  
//计算器类，继承界面  
class MyCalculator extends Frame{  
    //属性  
    TextField num1;  
    TextField num2;  
    TextField num3;  
    //方法  
    public void LoadFrame(){  
        //三个文本框，加号以及按钮  
        //加号使用标签Label类  
        num1=new TextField(10);  
        Label label=new Label("+");  
        num2=new TextField(10);  
        Button button=new Button("=");  
        num3=new TextField(20);  
        //给按钮添加事件  
        button.addActionListener(new MyCalcListener(this));  
        //流式布局  
        setLayout(new FlowLayout());  
        //添加组件进入  
        add(num1);  
        add(label);  
        add(num2);  
        add(button);  
        add(num3);  
  
        //自适应布局方法pack  
        setSize(500,80);  
//        pack();  
        setVisible(true);  
        addWindowListener(new WindowAdapter() {  
            @Override  
            public void windowClosing(WindowEvent e) {  
                System.exit(1);  
            }  
        });  
    }  
}  
//给按钮加一个事件监听  
class MyCalcListener implements ActionListener{  
    MyCalculator myCalculator=null;  
    public MyCalcListener(MyCalculator myCalculator){  
        this.myCalculator=myCalculator;  
    }  
    @Override  
    public void actionPerformed(ActionEvent e) {  
        int n1=Integer.parseInt(myCalculator.num1.getText());  
        int n2=Integer.parseInt(myCalculator.num2.getText());  
        myCalculator.num3.setText(""+(n1+n2));  
        myCalculator.num1.setText("");  
        myCalculator.num2.setText("");  
    }  
}
```
内部类
更好的包装
```
package com.yifan.TestFrame.lesson2;  
  
import java.awt.*;  
import java.awt.event.ActionEvent;  
import java.awt.event.ActionListener;  
import java.awt.event.WindowAdapter;  
import java.awt.event.WindowEvent;  
  
public class TestCalc {  
    public static void main(String[] args) {  
        new MyCalculator().LoadFrame();  
    }  
}  
//计算器类，继承界面  
class MyCalculator extends Frame{  
    //属性  
    TextField num1;  
    TextField num2;  
    TextField num3;  
    //方法  
    public void LoadFrame(){  
        //三个文本框，加号以及按钮  
        //加号使用标签Label类  
        num1=new TextField(10);  
        Label label=new Label("+");  
        num2=new TextField(10);  
        Button button=new Button("=");  
        num3=new TextField(20);  
        //给按钮添加事件  
        button.addActionListener(new MyCalcListener());  
        //流式布局  
        setLayout(new FlowLayout());  
        //添加组件进入  
        add(num1);  
        add(label);  
        add(num2);  
        add(button);  
        add(num3);  
  
        //自适应布局方法pack  
        setSize(500,80);  
//        pack();  
        setVisible(true);  
        addWindowListener(new WindowAdapter() {  
            @Override  
            public void windowClosing(WindowEvent e) {  
                System.exit(1);  
            }  
        });  
    }  
    //给按钮加一个事件监听  
    //内部类最大的好处，就是可以畅通无阻的访问外部的属性和方法  
    class MyCalcListener implements ActionListener{  
        @Override  
        public void actionPerformed(ActionEvent e) {  
            int n1=Integer.parseInt(num1.getText());  
            int n2=Integer.parseInt(num2.getText());  
            num3.setText(""+(n1+n2));  
            num1.setText("");  
            num2.setText("");  
        }  
    }  
}
```


#### 画笔
```
package com.yifan.TestFrame.lesson3;  
  
import java.awt.*;  
  
public class TestPaint {  
    public static void main(String[] args) {  
        new MyPaint().LoadFrame();  
    }  
}  
class MyPaint extends Frame{  
    public void LoadFrame(){  
        setBounds(200,200,500,400);  
        setVisible(true);  
    }  
  
    @Override  
    public void paint(Graphics g) {  
        //画笔需要有颜色，画笔可以画画  
        g.setColor(Color.pink);  
        g.drawOval(100,100,100,100);  
        g.setColor(Color.cyan);  
        g.fillOval(200,200,50,50);  
        //养成习惯，画笔用完，将他还原成最初的颜色  
    }  
}
```

#### 鼠标监听
```
package com.yifan.TestFrame.lesson3;  
  
import com.yifan.TestFrame.lesson1.MyFrame;  
import jdk.swing.interop.SwingInterOpUtils;  
  
import java.awt.*;  
import java.awt.event.MouseAdapter;  
import java.awt.event.MouseEvent;  
import java.util.ArrayList;  
import java.util.Iterator;  
  
public class TestMouseListener {  
    public static void main(String[] args) {  
        new MyFrame2().CreateFrame("界面");  
    }  
}  
  
//先创建一个界面类  
class MyFrame2 extends Frame {  
    //添加一个集合来放置画出来的点  
    ArrayList points;  
  
    //弄一个方法来创建界面  
    void CreateFrame(String title) {  
        new Frame(title);  
        setBounds(200, 200, 400, 300);  
        setVisible(true);  
        points = new ArrayList();  
        //添加鼠标监听  
        addMouseListener(new MyMouseListener());  
    }  
    //写一个画点的方法  
  
    @Override  
    public void paint(Graphics g) {  
        Iterator iterator=points.iterator();  
        while (iterator.hasNext()){  
            //这里的point其实就是个坐标  
            Point point =(Point) iterator.next();  
            g.fillOval(point.x,point.y,10,10);  
        }  
    }  
}  
//事件监听类  
//适配器模式  
class MyMouseListener extends MouseAdapter {  
    //这个事件包含按下，弹起，按下不放  
    @Override  
    public void mousePressed(MouseEvent e) {  
        MyFrame2 myFrame2=(MyFrame2) e.getSource();  
        //这个点就是鼠标产生的点  
        //给集合添加点  
        myFrame2.points.add(new Point(e.getX(),e.getY()));  
        System.out.println("dianji");  
        //刷新  
        //每次点击都是重新刷新一次，这个叫做帧  
        myFrame2.repaint();  
    }  
}
```
构思图
![[Pasted image 20240901224439.png]]

#### 窗口监听
```
package com.yifan.TestFrame.lesson3;  
  
import java.awt.*;  
import java.awt.event.WindowAdapter;  
import java.awt.event.WindowEvent;  
  
public class TestWindow {  
    public static void main(String[] args) {  
        new WindowFrame();  
    }  
}  
  
class WindowFrame extends Frame {  
    public WindowFrame() {  
        setBounds(100, 100, 200, 200);  
        setBackground(Color.pink);  
        setVisible(true);  
        addWindowListener(  
                //匿名内部类  
                new WindowAdapter() {  
                    @Override  
                    public void windowClosing(WindowEvent e) {  
                        System.exit(0);  
                    }  
  
                    @Override  
                    public void windowActivated(WindowEvent e) {  
                        WindowFrame windowFrame=(WindowFrame) e.getSource();  
                        windowFrame.setTitle("hello");  
                    }  
                });  
    }  
}
```

#### 键盘监听
```
package com.yifan.TestFrame.lesson3;  
  
import java.awt.*;  
import java.awt.event.KeyAdapter;  
import java.awt.event.KeyEvent;  
  
public class TestKeyListener {  
    public static void main(String[] args) {  
        new MyKeyEventFrame();  
    }  
}  
class MyKeyEventFrame extends Frame{  
    public MyKeyEventFrame(){  
        setBounds(100,100,200,200);  
        setBackground(Color.PINK);  
        setVisible(true);  
        addKeyListener(new KeyAdapter() {  
            @Override  
            public void keyPressed(KeyEvent e) {  
                System.out.println(e.getKeyCode());  
                if(e.getKeyCode()==KeyEvent.VK_UP){  
                    System.out.println("冲刺冲刺");  
                }  
            }  
        });  
    }  
}
```