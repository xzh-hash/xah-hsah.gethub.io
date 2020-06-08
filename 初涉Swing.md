# Swing
* 1.swing的基础方法
* 2.swing的方法代码实现
* 3.swing的进阶方法

## Swing的基础方法<br>
  JFrame:界面类
  >>>界面还有布局要设置
  
  JPanel:固定面板类  
  JScorllPanel:滚动面板类
  >>>固定面板类和滚动面板类都是附着在JFrame上
  
  JLabel:文本标签，文字标签<br>
  JTextField:输入框的标签<br>
  JButton:按钮标签<br>
  JCombobox: 下拉列表标签<br>
  JCheckbox:选择按钮标签复选，单选）<br> 
  BottonGroup:使用<br>
  JTable:表格标签控件<br>
  JPasswordField:密码输入框<br>
  >>>这几类标签都是add在面板上的,然后再面板add到界面上,层层递进,书写代码时也要分层次写这样思路更为清晰
  
  ##Swing基础方法演示<br>
  具体见示例,需要
  
  
  
  
  
  ###示例
  ```Java
public class LoginView extends JFrame{
	Font font1=new Font("楷体",Font.BOLD,25);
	Font font2=new Font("楷体",Font.BOLD, 18);
	
	JTextField jt_user;//用户名
	JPasswordField jt_pass;//密码
	JComboBox<String> jcb_type;//用户类型

	public LoginView() {
		this.setTitle("用户登录");
		this.setBounds(200,200,450,300);
		JPanel jp1=new JPanel();
		JLabel jl_title=new JLabel(" 用 户 登 录");
		jl_title.setForeground(Color.red);
		jl_title.setFont(font1);
		jp1.add(jl_title);
		
		JPanel jp2=new JPanel();
		JLabel jl_user=new JLabel("用户名:");
		jt_user=new JTextField(20);
		jt_user.setForeground(Color.green);
		
		jl_user.setFont(font2);
		jt_user.setFont(font2);
		jp2.add(jl_user);
		jp2.add(jt_user);
		
		JPanel jp3=new JPanel();
		JLabel jl_pass=new JLabel("密　码:");
		jt_pass=new JPasswordField(20);
		jt_pass.setForeground(Color.pink);
		jl_pass.setFont(font2);
		jt_pass.setFont(font2);
		jt_pass.setEchoChar('*');//设置密码的显示符号
		jp3.add(jl_pass);
		jp3.add(jt_pass);
		
		JPanel jp4=new JPanel();
		JLabel jl_type=new JLabel("类　型:");
		jcb_type=new JComboBox<String>(new String[]{"请选择用户","普通用户","管理员"});
		jl_type.setFont(font2);
		//设置下拉列表的高度22 宽度200。。。
		jcb_type.setPreferredSize(new Dimension(200,22));
		jcb_type.setForeground(Color.GRAY);
		jp4.add(jl_type);
		jp4.add(jcb_type);
		
		JPanel jp5=new JPanel();
		JButton jb_login=new JButton("用户登录");
		JButton jb_register=new JButton("用户注册");
		
		jb_login.setPreferredSize(new Dimension(130,30));
		jb_register.setPreferredSize(new Dimension(130,30));
		jb_login.setForeground(Color.BLUE);
		jb_register.setForeground(Color.BLUE);
		
		jp5.add(jb_login);
		jp5.add(jb_register);
		this.setLayout(new GridLayout(5,1,0,0));
		this.add(jp1);
		this.add(jp2);
		this.add(jp3);
		this.add(jp4);
		this.add(jp5);
		//固定宽度的大小。。。。
		this.setResizable(false);
		//设置窗体可见
		this.setVisible(true);
		// 4.关闭界面的时候释放资源
		this.addWindowListener(new WindowAdapter() {
			@Override
			public void windowClosing(WindowEvent e) {
				JFrame jf = (JFrame) e.getSource();
				jf.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
			}
		});
}
```
写一个界面的流程应该以如下顺序较为稳妥<br>
* 1.设置界面标题,字体,位置,界面大小等<br>
* 2.创建JPanel以及设置界面布局并将JPanel加入到界面中<br>
* 3.对各个JPanel具体的设置,加上文件框,输入框,密码框等<br>
  
  

