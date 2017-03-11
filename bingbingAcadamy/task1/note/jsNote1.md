## 慕课网javascript入门笔记 ##

### 变量命名需要遵循以下规则 ###
1. 变量必须使用字母、下划线(_)或美元符号（$）开始;
2. 可以使用任意多个英文字母、数字、下划线或美元符组成;
3. 不能使用Javascript关键词与Javascript保留字。


### 变量注意： ###
1. 在JS中区分大小写。
2. 变量虽然也可以不声明，直接使用，但不规范，需要先声明后使用。
3. 不声明直接使用的变量为全局(global)变量。


### Javascript-输出内容（document.write） ###
1. `document.write()`可用于直接在网页中输出内容。
2.	第一种输出，把要输出的内容放在引号中，然后添加到`()`里即可：
	`
	<script type="text/javascript">
		document.write("I love Javascript!");
	</script>
	`
3. 第二种：通过变量，输出内容：将内容存在变量里，然后：
	`document.write(变量名)`;

4. 第三种：输出多项内容，内容之间用+号连接：
	`<script type="text/javascript">
		var mystr = 'hello';
		document.write(mystr+ 'I love javascript');
	</script>`
5. 第四种：输出HTML标签，并起作用，标签使用""括起来。
	`<script type="javascript">
		var mystr="hello";
		document.write(mystr+"<br>");
	  	document.write("JavaScript");
	</script>`


### confirm消息对话框 ###
	对话框通常用于允许用户做选择的动作，如：“你对吗？”等。弹出对话框（包括一个确定按钮和一个取消按钮）。
	语法： confirm(str);
	参数说明：
	str:在消息对话框中要显示的文本
	返回值：Boolean值（true or false）
	
	返回值：
		当用户点击“确定”按钮时，返回true;
		当用户点击“取消”按钮时，返回false;

    `
	<script type="text/javascript">
		function sexConfirm(){
			var question = confirm("你是女士吗？");
			if(question == true){
				document.write('女士，您好');
			}else{
				document.write('先生，您好');
			}	
		}
		sexConfirm();
	</script>

	`

### prompt消对话框 ###

	prompt弹出消息对话框，通常用于询问一些需要与用户交互的信息。弹出消息对话框（包含一个确定按钮、取消按钮与一个文本输入框）。
	语法：
	prompt(str1,str2);    //str代表字符串，str2在代码中不用写，用于页面上交互填写，页面上显示为一个文本输入框
	参数说明：
	str1:要显示在消息对话框中的文本，不可修改;
	str2:文本框中的内容，可以修改。
	返回值：
		1.点击确定按钮，文本框中的内容将作为函数返回值
		2.点击取消按钮，将返回null
	案例：
		var myname = prompt('请输入你的姓名');
		if(myname != null){  //!= 不等于
			alert('hello' + myname);
		}else{
			alert('hello my friend');
		}	
 

### 打开新窗口：window.open ###

	open()方法可以查找一个已经存在或者新建的浏览器窗口。
	语法：
		window.open([URL],[窗口名称],[参数字符串])
	参数说明：
		URL：可选参数，在窗口中要显示网页的网址或路径。如果省略这个参数，或者它的值是空字符串，那么窗口就不显示任何文档。
		窗口名称：可选参数，被打开窗口的名称。
    		1.该名称由字母、数字和下划线字符组成。
    		2."_top"、"_blank"、"_self"具有特殊意义的名称。
       		_blank：在新窗口显示目标网页
       		_self：在当前窗口显示目标网页
       		_top：框架网页中在上部窗口中显示目标网页
    		3.相同 name 的窗口只能创建一个，要想创建多个窗口则 name 不能相同。
   		 4.name 不能包含有空格。
			参数字符串：可选参数，设置窗口参数，各参数用逗号隔开。

![参数图](http://i.imgur.com/UNbpzGV.jpg)
举个栗子：
打开http://www.imooc.com网站，大小为300px * 200px，无菜单，无工具栏，无状态栏，有滚动条窗口
		`<script type="text/javascript"> window.open('http://www.imooc.com','_blank','width=300,height=200,menubar=no,toolbar=no, status=no,scrollbars=yes')
		</script>`	


### 关闭窗口-window.close ###
	close()关闭窗口
	用法：
		window.close();//关闭本窗口
	或：
		<窗口对象>.close();//关闭指定窗口

	栗子：
		<script type="text/javascript">
   			var mywin=window.open('http://www.imooc.com'); //将新打的窗口对象，存储在变量mywin中
   			mywin.close();
		</script>


### DOM节点 ###

#### 获取节点 ####
 ID获取元素节点
	document.getElementById(id);

 #### innerHTML ####
	object.innerHTML
	修改元素节点的文本内容：
		obj.innerHTML = new innerHTML;

#### 改变HTML样式 ####
	语法：
		object.style.property = new style;
	如果是像background-color这样的样式，在JS里要写成
	backgroundColor.

#### 添加class样式 ####
	语法：
		object.className = new className;

#### 容易忘记的地方 ####
	<p onClick='fn()'></p>
	在行内写一定是‘onClick’