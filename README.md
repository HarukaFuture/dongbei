# dongbei - 东北方言编程语言

* [引言](#引言)
* [系统要求](#系统要求)
* [安装](#安装)
* [你好，世界](#你好世界)
* [语言定义](#语言定义)
  * [词法](#词法)
    * [字符串常量](#字符串常量)
    * [注释](#注释)
    * [分词](#分词)
    * [标识符](#标识符)
    * [常数](#常数)
  
## 引言

dongbei是啥？它是一门*以东北方言词汇为基本关键字的以人为本的编程语言。*

这玩意儿可是填补了世界方言编程地图上的一大片儿空地啊！
这么说吧，谁要是看了 dongbei 程序能忍住了不笑，我敬他是纯爷们儿！

那它有啥特点咧？多了去了：

*  简单啊！小学文化程度就行。您能看懂春晚不？能？那就没问题。
*  好读啊！看着看着包您不由自主地念出声儿来。
*  开心啊！呃，做人嘛，最重要的是要开心。
*  开源啊！不但不要钱，而且不要脸 -- 随时随地欢迎东北话高手打脸指正。

dongbei 编程语言的开发采用了业界领先的 **TDD（TreeNewBee-Driven Development）**方式。
具体地说，就是每个功能都是先把文案写好，八字没一撇牛皮就吹起来了，然后根据牛皮写测试案例，最后再实现功能让牛皮不被吹破。
这样做有两大好处：第一每个功能都是有的放矢，不值得 tree new bee 的功能一概没有。
第二确保了每个功能都有文案负责吹嘘，开发者的辛劳绝对不会被埋没。

不扯犊子了。翠花，上酸菜～～～

## 系统要求

dongbei 语言是基于 Python 二次开发的。
只要能跑 Python 的旮旯儿都能跑。
像 Mac OS 啦、Windows 啦、Linux 啦，等等等等，都成！

## 安装

甭麻烦了！直接跑 src/dongbei.py 就成。

## 你好，世界

创建一个名字叫 hello-world.dongbei 的文本文件，内容如下：

```
唠唠：“这旮旯儿嗷嗷美好哇！”。
```

用 utf-8 编码保存。
要是编辑器因为编码错误埋汰你，那就把文件内容改成

```
# -*- coding: utf-8 -*-

唠唠：“这旮旯儿嗷嗷美好哇！”。
```

再试，应该就成了。

然后在命令行窗口运行：

```
src/dongbei.py hello-world.dongbei
```

你应该看到执行结果：

```
这旮旯儿嗷嗷美好哇！
```

## 语言定义

学习一门语言，先得了解它的**词法**（怎么从一串串的字符组成词），然后是**语法**（怎么把词组成句子）和**语义**（这些句子都啥意思啊？）。
所以，咱们先讲讲 dongbei 语言词汇的构成。

### 词法

#### 字符串常量

一行代码当中，要是出现配对的中文全角双引号，比如

```
...“我是一个字符串”...
```

那么引号当中的内容（*我是一个字符串*）会被当成一个字符串常量。

#### 注释

一行代码当中，如果在字符串常量*外面*出现 **#** 字符，所有从 # 开始的字符都会被当成注释被忽略掉。
比如

```
唠唠：  # 我是一个注释。
    “嘎哈#？”。  # 我还是一个注释。
```
跟
```
唠唠：“嘎哈#？”。
```
是一样一样的。

#### 分词

大部分的西方语言在书写的时候要用空白字符或者标点把单词隔开，要不就会产生歧义。
比如 therapist（理疗师）和 the rapist（强X犯）就有很大的不同！

所以，西人开发的编程语言也一样啰嗦，动不动就要加空格，忒麻烦了。

dongbei 语言以人为本，适应华人的书写习惯，*加不加空格换行都无所谓。*
反正加了也白加（除非加在一个字符串常量的内部）。
所以对 dongbei 来说，

```
唠
  唠
    ：
      “嘎哈？”
        。
```
跟
```
唠唠：“嘎哈？”。
```
是一样一样的。

#### 标识符

代码里面除了各种有特俗意义的关键词（keyword），还会有各种用户定义的**标识符**（变量名、函数名、类型名，等等）。
在 dongbei 语言里面，除了关键词、标点符号和常数，剩下的都是标识符。
比如，在“张三乘李四”这个 dongbei 语言表达式里，“乘”是一个关键词，“张三”和“李四”是两个不同的标识符，

那么问题来了：dongbei 语言是不尿空格的，标识符和关键词之间没有明显的隔离。
要是标识符里包含关键词怎么办？
比如，我们知道“乘”是一个关键词，那还能用“阶乘”做函数名吗？
系统会不会把它理解成标识符“阶”和关键词“乘”？

不要方！
dongbei 语言允许你用中文全角方括号【】把一串字符标注为标识符。
比方说，“【阶乘】”就明明白白地是一个名字叫“阶乘”的标识符，绝对不会被当成是标识符“阶”加关键词“乘”。

#### 常数

除了用阿拉伯数字表示的十进制整数（比如 2、42、250，等等），0 到 10 的常数也可以用中文表达：

```
零一二三四五六七八九十
```

其中 `二` 也可以写成 `两`。

比如，
```
五加二
```
的意思就是 5 + 2。
