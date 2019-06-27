![](https://upload-images.jianshu.io/upload_images/57036-a656f3cb7ab534cd.jpg)

# Rx钥匙：为无聊而生的 Android 开发者工具
`更新动态 | 2019.4.25`

很高兴又和大家见面啦！

有不少热心网友关心，上一期的 Rx钥匙 后来怎么样了，再次谢谢大家的期待，原本目标只是给大家一把钥匙，方便大家意会 RxJava 操作符的本质，想不到有不少网友对 Rx钥匙 的期待远远超出了其本身，期望那是一把能够解决无聊、带给自己更多的魔法棒。

![](https://upload-images.jianshu.io/upload_images/57036-d64787fa6df74e62.png)

再加上，我自己也因为“拿 SQL 来隐喻操作符”的那番见解，而心生灵感：

不如做一件史上最无聊的事吧 —— **像设计师一样将每个像素都抠到极致，像工程师一样将工程设计模式和原则应用到每一个功能的编写，用无聊的方式来对抗无聊** —— 这是一款为无聊而生的面向 Android 开发者的操作符练习工具。

![](https://upload-images.jianshu.io/upload_images/57036-832073b8b7f9801d.gif?imageMogr2/auto-orient/strip)

![](https://upload-images.jianshu.io/upload_images/57036-77454b962bfc9d09.gif?imageMogr2/auto-orient/strip)

![](https://upload-images.jianshu.io/upload_images/57036-4dfd67d168698644.gif?imageMogr2/auto-orient/strip)

除了提供“解决无聊”这一最核心功能之外，你还可以从这个开源项目获得的内容包括：

1. 整洁的代码风格和标准的资源命名规范。
2. 基于前沿的、遵循关注点分离的 JetPack MVVM 架构。
3. 使用 RxJava 和 lambda 表达式。
4. AndroidX 和 Material Design 2 的全面使用。
5. ConstraintLayout 约束布局的最佳实践。
6. 为提升手机桌面的逼格做贡献，让知识与美观并存，即使从不打开。
7. 绝不使用 Dagger，绝不使用奇技淫巧、编写艰深晦涩的代码。
8. 长期更新。

如你所见，Rx钥匙的界面效果大体已经出来了，我的目标是，将首页先打磨好，这样 Rx钥匙 Apk 最快可能下周就能正式和大家见面了。

鉴于目前在 RxOperatorAdapter 的 EditText 读写缓存逻辑上存有一些问题，如果你对此十分熟悉，请不吝参与进来，这个项目会因为你的参与而变得更好！

![blank](https://upload-images.jianshu.io/upload_images/57036-f59799c18ddccf9f.png)

# Rx钥匙：本周读者留言回复
`更新动态 | 2019.4.20`

上周我在掘金发布了 Rx钥匙，没想到在评论区收到 40 多条留言。

有的读者因为豁然开朗而喜出望外，不吝留下夸张的赞美；也有读者觉得意犹未尽，表达了对见证更多的愿望。

![](https://upload-images.jianshu.io/upload_images/57036-0c2e1cc89253dc22.png)

![](https://upload-images.jianshu.io/upload_images/57036-ed92fc17cc7284e6.png)

![](https://upload-images.jianshu.io/upload_images/57036-f960ade1565fa041.png)

从留言中我看到了大家对 Rx钥匙的期待 和 各自内心世界的丰富多彩，这些期待甚至远远超出了 Rx钥匙本身，期望它是一把能够解决无聊、带给自己更多的 魔法棒。

![](https://upload-images.jianshu.io/upload_images/57036-23325e335e96987e.jpeg)

如你所愿，我在 GitHub 开源了这套操作符示例项目，该项目的计划分三步走：

1.收集业内关于操作符的 代码案例 和 最佳实践，以便随时查阅。

2.设计一款操作符组合工具，让人们可以直观而简便地组合操作符。

3.在组合工具的基础上映射代码，让代码可以自由复制。

![](https://upload-images.jianshu.io/upload_images/57036-07df9019c086acd0.png)

我会不定期地 **只在公众号公布** Rx钥匙 研发的最新动态，并固定于每周三或周四下午3点 在公众号或掘金 推送新的短平快文章。

公众号刚开通，文章留言功能暂无法使用，欢迎在公众号中与 KunMinX（可以叫我坤哥）交流，消息我一般看到了就会回复。

我的微信公众号

![公众号](https://upload-images.jianshu.io/upload_images/57036-dc3af94a5daf478c.jpg)

![blank](https://upload-images.jianshu.io/upload_images/57036-f59799c18ddccf9f.png)

![](https://upload-images.jianshu.io/upload_images/57036-550b81d8d77c687d.jpg)

# 你用不惯 RxJava，只因缺了这把钥匙
`更新动态 | 2019.4.18`

## 前言

本文最初是为部门内部培训而准备的，但经过一番调研发现，同事们用不惯 RxJava，并不是因为网上介绍 “怎么用” 的教程不够多，恰恰是因为，一上来就急着发车的教程无数、却从未有过哪篇教程 **舍得用几句话的功夫点破 RxJava 操作符究竟为何方神圣**、我们为什么要用、为什么要那样用。

```java
Observable.just(1, 3, 5, 7, 9)
    .map(i -> i + 1)
    .filter(i -> i < 5)
    .subscribe(getObserve());
```

事实上，在相当长的一段时间里，我也和大部分人一样，只知道使用 RxJava 来完成异步回调，至于那些操作符，则是能不用尽量不用，因为不知道葫芦里卖的什么药，看不懂、不会用。

![RxJava三连](https://upload-images.jianshu.io/upload_images/57036-a20c7618a0416530.png)

因此，本文的初衷绝不是翻译官方文档、教大家怎么用，而是旨在帮助大家对 RxJava 操作符 **完成感性上的认识**。鉴于本次培训的效果还不错、同事们听了都说好，我便在 GitHub 开源了全套操作符示例代码（不要慌，链接文末已给出）。如果你在阅读本文后觉得恍然大悟，原来 RxJava 操作符是这么回事，那么我的愿望也就达到了。

![然而我并不发车](https://upload-images.jianshu.io/upload_images/57036-4a1585f97c9876a4.png)


## 编程语言包含多种编程范式

我对操作符本质的顿悟，始于我对编程语言的理解。和你一样，我是做安卓开发，但有一天，我决定跳出 Java，从整个计算机科学的角度来学习和理解编程语言的本质，在这过程中，我接触了“编程范式”这个概念，了解到原来每个编程语言大都包含多种编程范式。

常见的编程范式有：命令式编程、声明式编程等。

![编程范式](https://upload-images.jianshu.io/upload_images/57036-d09589d947e65251.png)

以 Java 为例，咱们 Java 最主要的编程范式是命令式编程。命令式编程 即按顺序执行具体的命令，这些命令**不仅交待了做什么，还详细交待了每一步怎么做**。

SQL 也是种编程语言，是一种典型的声明式编程。声明式编程的特点是，**只交待做什么，但无须交待怎么做**。


## 操作符的本质是声明式编程

下面回到我们最初的问题上来。你之所以用不惯 RxJava 操作符，是因为你习惯性地使用命令式编程思维 来理解实际上是声明式编程的操作符。
学习操作符，就和你在大学里接受的 SQL 语句一样理所当然。

SQL 你是理解的，就是按一定的规则，向数据库中的数据声明你要做什么。

![SQL代码示例](https://upload-images.jianshu.io/upload_images/57036-da21d86723997dd8.png)

同理，RxJava 也是按一定的规则，向数据流声明你要做什么。

![操作符伪代码示例](https://upload-images.jianshu.io/upload_images/57036-4dd92d6d426660d5.png)


转换成代码，便成为以下这样。

```java
Observable.just(1, 3, 5, 7, 9)
    .map(i -> i + 1)
    .filter(i -> i < 5)
    .subscribe(getObserve());
```
这样说，你理解了吗？

![请点赞 ~](https://upload-images.jianshu.io/upload_images/57036-3e15111b4263be48.png)

![blank](https://upload-images.jianshu.io/upload_images/57036-f59799c18ddccf9f.png)

# Thanks to

[RxJava2](https://github.com/ReactiveX/RxJava)

[RxJava2-Android-Samples](https://github.com/amitshekhariitbhu/RxJava2-Android-Samples)

[material-components-android](https://github.com/material-components/material-components-android)

[LicenseAdapter](https://github.com/yshrsmz/LicenseAdapter)

[JetPack :](https://developer.android.google.cn/jetpack/)

[AndroidX](https://developer.android.google.cn/jetpack/androidx)

[DataBinding](https://developer.android.google.cn/topic/libraries/data-binding)

[Room](https://developer.android.google.cn/topic/libraries/architecture/room)

# My Pages

Email：[kunminx@gmail.com](mailto:kunminx@gmail.com)

JianShu：[kunminx@jianshu](https://www.jianshu.com/u/5d956b6dcf1f)

Juejin：[kunminx@juejin](https://juejin.im/user/58ab0de9ac502e006975d757/posts)

My WeChat Public Account：

![公众号](https://upload-images.jianshu.io/upload_images/57036-dc3af94a5daf478c.jpg)

# License

```
Copyright 2018-2019 KunMinX

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```