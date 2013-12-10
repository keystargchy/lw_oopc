LW_OOPC升级版本发布说明
=========================

* 在高焕堂先生的著作《UML+OOPC嵌入式C语言开发精讲》中介绍了高先生及其MISOO团队创作的lw_oopc宏.
* 在研读这套宏的过程中, 我发现高先生提供的这套宏还过于简陋, 不能够优雅地支持面向接口编程.
* 经过认真钻研, 我对原有的这套宏进行了扩充和改良, 得到了lw_oopc宏的升级改进版本.
* 改良后的这套宏，能够很好地支持面向对象编程，能够支持面向接口编程(甚至支持复杂的多重继承).

- 经邮件与高焕堂先生联系，征得高先生同意，以LGPL协议开源，感谢高先生以及MISOO团队的贡献!


### 原有高焕堂先生及其MISOO团队创作的宏(总共6个宏),清单如下:

高焕堂及MISOO创作的宏 | 是否存在问题? | 是否修改?
---- | ---- | ----- 
INTERFACE | 没有问题 | 否
CLASS | 无法支持继承 | 是
CTOR | 对申请不到内存的情况未保护 | 是
END_CTOR | 没有问题 | 否
FUNCTION_SETTING | 没有问题 | 否
IMPLEMENTS | 没有问题 | 否


### 为了更好的支持面向对象以及面向接口编程，金永华增加了14个宏:
创作的宏 | 创作目的()为了解决什么问题?)
---- | ----
DTOR / END_DTOR | 为了支持析构函数的概念
ABS_CLASS | 为了支持抽象类的概念
ABS_CTOR / END_ABS_CTOR | 为了支持可继承的抽象类的构造函数
EXTENDS | 为了让熟悉Java的人容易理解(与IMPLEMENTS宏等同)
SUPER_CTOR | 为了支持子类调用父类的构造函数
SUPER_PTR / SUPER_PTR_2 / SUPER_PTR_3 | 为了支持向上转型
SUB_PTR / SUB_PTR_2 / SUB_PTR_3 | 为了支持向下转型
INHERIT_FROM | 为了支持访问直接父类的数据成员

* 希望这套宏，能够真正帮助到想用C语言写出面向对象代码的C程序员们!
