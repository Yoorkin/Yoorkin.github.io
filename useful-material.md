# 资料与链接汇编

一些关于编程语言理论、逻辑以及编译器工具链实现的阅读材料。放在这里不代表我全都读过，我的学习习惯是各种相关材料穿插阅读学习，所以记录下来以免读到一半忘记了（在写这篇汇编的时候就发现一些资料给弄丢了，有一篇是关于使用coq证明助理的教程）。如果可以也能够帮助到一些对这些主题感兴趣的人，很多资料都是我在学习过程中偶然遇到的。

以下内容会逐渐修改和增加。

## 论文

- Implementation Strategies for Mutable Value Semantics: 宣称找到纯函数(haskell的方案)以及borrow checker(rust的方案)之外的第三种避开指针别名以利于编译器优化的方案
- A Functional Perspective on SSA Optimisation Algorithms：还没读，一看标题很有意思，可以再顺便探究下和monad以及call/cc的联系
- Propositions as Types (Philip Wadler)：计算机与数学发展历史以及重要思想工具介绍，计算机科学到逻辑的漂亮一跃
- A Fast Verified Liveness Analysis
- A Simple, Fast Dominance： 与SSA生成有关
- A History of Haskell - Being Lazy With Class
- Fundamental Concepts in Programming Languages: 早期记录参数化多态的论文
- Dependent Types: Level Up Your Types (Marco Syfrig)：Dependent Type的重要性和它的未来。宣称它能够通过PAT的思想证明代码的正确性，完全替代只保证极端值正确性的单元测试
- [The GHC Runtime System](https://www.google.com.hk/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjG4KirtrH8AhX2FLcAHRpiAXYQFnoECAsQAQ&url=http%3A%2F%2Fezyang.com%2Fjfp-ghc-rts-draft.pdf&usg=AOvVaw1iTzx7FYymZoQlCS5Ku5lz): Haskell运行时实现，没看
- Applicative programming with effects： 给Haskell引入了Applicative的概念，从此用parsec写parser方便又愉快
- Haskell’s overlooked object system (Oleg Kiselyov, Ralf L¨ammel): 在Haskell98中实现面向对象编程范式特性
- [[文献导读] Borrow checker 的形式化 - Patina: A Formalization of the Rust Programming Language](https://zhuanlan.zhihu.com/p/23603637)

## 书籍 & 系列教程

- Programming Languages and Lambda Calculi：lambda演算，学习PL的基础。Church-Rosser定理证明杀我；后面不知道写啥。
- Type Theory and Formal Proof An Introduction：介绍种种Lambda扩展类型系统，systemF,lambda cube,dependent type基础概念等等，抽象黑话。
- [知乎 - 类型论入门笔记](https://zhuanlan.zhihu.com/p/112024185)：《Type Theory and Formal Proof》的笔记，无证明过程
- Logic in Computer Science (M. Huth, M. Ryan): 前面介绍了一些自然演绎，浅显易懂。对阅读TAPL有帮助。
- Category Theory for Programmers (Bartosz Milewski)：无抽象黑话，但口语化的解释啰嗦又含糊的吓人，需要Haskell基础。书中提过一嘴“单元测试只是一个相比证明要差得多的保证”印象深刻。
- Categories for the Working Mathematician (Saunders Mac Lane)：范畴论抽象话，没读过
- Conceptual Mathematics A First Introduction to Categories (F. William Lawvere Stephen H. Schanuel)：同上
- A Gentle Introduction to Category Theory：同上
- Modern Compiler Implementation in C (Andrew W. Appel,  Maia Ginsburg)：编译原理虎书，个人觉得比龙书好读且介绍的方法可操作性强
- Types and Programming Languages：PL入门
- Static Program Analysis (Anders Møller and Michael I. Schwartzbach): 丹麦某大学的程序静态分析课程讲义
- [南京大学《软件分析》课程](https://www.bilibili.com/video/BV1b7411K7P4/?spm_id_from=333.337.search-card.all.click): 前几节课内容和上面的讲义高度重合，讲的更加详细易懂；后面几节课没看

- [Advanced Programming Languages (2022)](https://www.cs.cornell.edu/courses/cs6110/2022sp/)： 康奈尔PL大杂烩

- [Advanced Programming Languages (2016)](https://www.cs.cornell.edu/courses/cs6110/2017sp/schedule.html)： 同上

- Type-driven Development with Idris (Edwin Brady)：不好看
- Advanced Design and Implementation of Virtual Machines by Xiao Feng Li：虚拟机实现，没耐心看，光顾着自己写了
- Expert .NET 2.0 IL Assembler (Serge Lidin): CLR内部设计与IL表示。内容有点过时但入门有用
- The Java virtual machine specification Java SE by Bracha, GiladBuckley, AlexLindholm, TimYellin, Frank：虚拟机、ISA和编译器设计的抄作业对象。~~try..catch..finally一个finally块拷贝n次的设计就算了，真垃圾~~
- 深入解析Java编译器：源码剖析与实例详解 (马智)： 还行，字有点大
- antlr4权威指南：同上

# 博客杂谈

- [Purely Functional Languages and Monads](https://yinwang0.substack.com/p/pure-fp-and-monads): 王垠怼纯函数式，总感觉哪里不对

# 其他

- [RednaxelaFx](https://www.zhihu.com/people/rednaxelafx): 虚拟机与编程语言巨牛，写了很多干货；据本人所说是玩gal game才开始对游戏背后的虚拟机感兴趣

- [what-is-the-question-that-programming-language-theory-is-trying-to-answer](https://cstheory.stackexchange.com/questions/42724/what-is-the-question-that-programming-language-theory-is-trying-to-answer)：stack exchange关于PLT的疑问

- [what-is-the-question-that-programming-language-theory-is-trying-to-answer](https://cstheory.stackexchange.com/a/42728)：PL相关研究和从业者的回答。早期面试的时候试图说服Anders Heijlsberg给C#添加泛型被拒绝

- [PKU《程序设计语言原理》文献汇编](https://www.math.pku.edu.cn/teachers/qiuzy/plan/lits/index.htm)

- [bidirectional typechecking, nlab](https://ncatlab.org/nlab/show/bidirectional+typechecking)

- [如何开始学习CoreCLR源代码? - RednaxelaFX的回答 - 知乎](https://www.zhihu.com/question/28554410/answer/41486461)