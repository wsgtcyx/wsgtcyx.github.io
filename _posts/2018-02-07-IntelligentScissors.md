---
layout:     post
title:      Intelligent Scissors(6000C computer Vision project No.1)
subtitle:   So complicated!
date:       2018-02-07
author:     CHEN	Yuxiang
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    - C++
    - QT
    - Priority queue
    - Opencv
    
---
# Project Description
#### Project Details

The project detail is in [6000C Homepage](https://home.cse.ust.hk/~cktang/msbd6000c/Password_Only/projects/iscissor/index.html). 

Due to the intranet's limitation, you can click the [Washington CSE 455](https://courses.cs.washington.edu/courses/cse455/03wi/projects/project1/web/project1.htm) for temporary referrence, which is quite similar.




>最后附上GitHub：<https://github.com/wsgtcyx/qt_test>

<!--# 常见操作方法介绍


#### 操作须知

所有的信号（RACSignal）都可以进行操作处理，因为所有操作方法都定义在RACStream.h中，因此只要继承RACStream就有了操作处理方法。
#### 操作思想

运用的是Hook（钩子）思想，Hook是一种用于改变API(应用程序编程接口：方法)执行结果的技术.

Hook用处：截获API调用的技术。

有关Hook的知识可以看我的这篇博客[《Objective-C Runtime 的一些基本使用》](http://www.jianshu.com/p/ff114e69cc0a)中的 *更换代码的实现方法* 一节,

Hook原理：在每次调用一个API返回结果之前，先执行你自己的方法，改变结果的输出。

#### 操作方法

#### **bind**（绑定）- ReactiveCocoa核心方法

**ReactiveCocoa** 操作的核心方法是 **bind**（绑定）,而且也是RAC中核心开发方式。之前的开发方式是赋值，而用RAC开发，应该把重心放在绑定，也就是可以在创建一个对象的时候，就绑定好以后想要做的事情，而不是等赋值之后在去做事情。

列如，把数据展示到控件上，之前都是重写控件的 `setModel` 方法，用RAC就可以在一开始创建控件的时候，就绑定好数据。

- **作用**

	RAC底层都是调用**bind**， 在开发中很少直接使用 **bind** 方法，**bind**属于RAC中的底层方法，我们只需要调用封装好的方法，**bind**用作了解即可.

- **bind方法使用步骤**
     1. 传入一个返回值 `RACStreamBindBlock` 的 block。
     2. 描述一个 `RACStreamBindBlock` 类型的 `bindBlock`作为block的返回值。
     3. 描述一个返回结果的信号，作为 `bindBlock` 的返回值。
     
     注意：在bindBlock中做信号结果的处理。
- 	**bind方法参数**
	
	**RACStreamBindBlock**:
`typedef RACStream * (^RACStreamBindBlock)(id value, BOOL *stop);`

     `参数一(value)`:表示接收到信号的原始值，还没做处理
     
     `参数二(*stop)`:用来控制绑定Block，如果*stop = yes,那么就会结束绑定。
     
     `返回值`：信号，做好处理，在通过这个信号返回出去，一般使用 `RACReturnSignal`,需要手动导入头文件`RACReturnSignal.h`

- **使用**

	假设想监听文本框的内容，并且在每次输出结果的时候，都在文本框的内容拼接一段文字“输出：”

	- 使用封装好的方法：在返回结果后，拼接。

		```
		[_textField.rac_textSignal subscribeNext:^(id x) {
		
			// 在返回结果后，拼接 输出：
			NSLog(@"输出:%@",x);
		
		}];
		```


	- 方式二:，使用RAC中 `bind` 方法做处理，在返回结果前，拼接。
	  
		这里需要手动导入`#import <ReactiveCocoa/RACReturnSignal.h>`，才能使用`RACReturnSignal`

		```	
		[[_textField.rac_textSignal bind:^RACStreamBindBlock{
		   // 什么时候调用:
		   // block作用:表示绑定了一个信号.
		
		   return ^RACStream *(id value, BOOL *stop){
		
		       // 什么时候调用block:当信号有新的值发出，就会来到这个block。
		
		       // block作用:做返回值的处理
		
		       // 做好处理，在返回结果前，拼接 输出:
		       return [RACReturnSignal return:[NSString stringWithFormat:@"输出:%@",value]];
		   };
		
		}] subscribeNext:^(id x) {
		
		   NSLog(@"%@",x);
		
		}];

		```
-->