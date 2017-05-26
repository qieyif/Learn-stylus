# CSS预处理器（**stylus**）

> - ***Stylus***是css预处理器。
> - 我们使用过***Sass*** 或者 ***Less***编写css的都知道，能够更好的管理开发css代码。Sass效率开发等是要高于less的。
> - Sass的运行环境是Ruby，而Stylus是基于Node.js的。原理就是用js操作css。这个对于前端工程师来说再熟悉不过了。所以这也是必须要改用Stylus的原因之一吧。

#### [stylus中文版参考文档](http://www.zhangxinxu.com/jq/stylus/)

#### 第一步： Stylus安装

全局安装
```ruby
	$ npm install stylus -g
```

#### 第二步：Stylus生成CSS文件

使用stylus编译css，真的是太方便了，不用你去安装ruby环境，使用什么kola软件，或者用gulp，grunt编译工具。只需要打开git bash，执行下面的代码，就可以实时编译了：
``` ruby
	$ stylus -w src/example.styl -o dist
```
`注释： 可以通过stylus -h查看所有命令。这句含义是：-w 是监测 -o 是输出 监测代码发生变化就会实时德输出到 dist这个文件夹下。`

#### stylus写法：

- 当然了你可以写css的语法，但是你不感觉，写那么多，重复的没用的，是在浪费自己的时间吗...
- 写法一：去掉花括号

```css
stylus:

	.demo1
    	width: 300px;
        height:300px;
        background-color: #00d;

变异成css：

	.demo1 {
      width: 300px;
      height: 300px;
      background-color: #00d;
    }
```
- 写法二：去掉分好

```css
stylus:

	.demo1
    	width: 300px
        height:300px
        background-color: #00d

变异成css：

	.demo1 {
      width: 300px;
      height: 300px;
      background-color: #00d;
    }
```

- 写法三：去掉冒号 这是基本的简单写法 怎么样 简单吧，是不是够劲儿！

```css
stylus:

	.demo1
    	width 300px
        height 300px
        background-color #00d

变异成css：

	.demo1 {
      width: 300px;
      height: 300px;
      background-color: #00d;
    }
```
#### stylus一般语法：

- 引入一个公共的stylus文件： 用@import 'header' ，就会插入公共的styl文件，最终将css编译到一起。

```css
	@import 'header'
    div1
    	font 12px Arial
```
`提示： 这个可以解决css的模块化的问题的，同样的css文件，不用重复的写。`

- 可以直接定义一个函数、方法

```css
    add(nums...)
      sum = 0
      sum += n for n in nums

    .demo2
      width add(12,34)px

编译后的css：
    .demo2 {
      width: 46px;
    }
```
- 可以定义一个变量

```css
    fonts = helvetica, arial, sans-serif

    body {
      padding: 50px;
      font: 14px/1.4 fonts;
    }
```
---
