# 为什么 Git 如此复杂

> 原文：<https://javascript.plainenglish.io/why-git-is-so-complicated-7d23c1a82c46?source=collection_archive---------11----------------------->

![](img/826c252ae9587433aff7a203259c437d.png)

Illustration by the author

当你学习编程的时候，人们往往会推荐你学习 Git。理论上，这听起来很容易:一个跟踪代码变更的程序，当你需要时，它可以帮助你恢复代码的先前版本。除此之外，这是一个在行业中几乎到处都在使用的工具。实际上…至少可以说，Git 可能会令人困惑。

为什么一定要这样？

# 命令行界面

大多数日常使用电脑的人都不习惯基于文本的界面。我称之为奢侈，因为正如我之前在《T4》中写的那样，它有一些很大的优势——尽管它可能需要一些时间来适应用户体验。因此，如果您的关联与列表中的关联相符:

*   一种毛绒绒的动物，
*   `cd`-人们过去如何听音乐，以及
*   `grep`——一些拟声词，

那么您第一次使用 Git 可能会有学习命令行基础知识的额外困难。Windows 95 和它的同类从你身边夺走的东西。

# Git 的设计目标

Git 从来就不是简单的。这是出于不同的目的:更重要和更具挑战性的目的。

# 安全存储保存的数据

Git 的意思是总是将数据原样返回给您，或者让您知道存储库已损坏。它做了一件了不起的工作——你可以确信，当你检查一个提交时，你得到的状态完全是它的作者想要的。当然，这是假设他们知道自己在做什么。

Git 是如何实现这么好的数据安全性的？它用聪明的方式做到了这一点，它[存储所有的东西](https://how-to.dev/how-git-stores-data)-提交、文件夹和文件。每个对象都由其内容的加密哈希来标识，这是一个基于对象内容生成的数字，如果文件中的任何内容发生变化，该数字也会发生变化。因为对象之间的引用也是散列的，所以几乎没有办法在不被 Git 发现的情况下篡改存储库。即使在这种情况下，有意义的代码也会被长文本乱码所取代。

# 通过不安全的网络与不可信的参与者一起工作

因为一切都是由加密哈希识别的，Git 不需要太信任网络来保持数据的完整性。Git 免受中间人攻击:没有人能够在 Git 的两个节点之间注入有意义的代码。当然，如果有人可以读取他们不希望看到的提交，这也是一个问题，但比攻击者将代码注入代码库的危险后果要小。

对于额外的安全层，Git 提供了注册提交——这是确保提交是由被设置为作者的人创作的额外方法。

# 保持向后兼容性

Git 接口比它应该有的更复杂，因为它尊重用户的旧习惯。我在 2011 年学习了 Git，直到上周我才注意到有一个新的`git switch`命令被推荐来改变分支。我习惯的做法(`git checkout` +各种旗帜)还是很管用的。Git 优先考虑老用户和他们的习惯，而不是新用户的简单性——这就把我们带到了下一点。

# 超级用户的用户体验

Git 是为超级用户设计的工具。它是由 Linus Torvalds 编写的，用于管理 Linux 代码库——不是初学者的任务。Git 的主要用户开发操作系统，有几十年的编程经验，生活在命令行中。除此之外的所有使用都是偶然的，不是开发 Git 的人主要关心的。

# 简单性权衡

当你设计系统时，没有什么是免费的——包括用户的简单性。

# 隐藏复杂性

当你在处理一个本来就很复杂的问题时，你可以通过去除复杂性来简化解决方案。没了吗？不，它只是对用户隐藏。例如，在互联网连接的情况下，我和大多数人只把连接质量理解为📶：

这对于使用互联网来说已经足够了，但是这使得理解和解决任何连接问题变得很困难。

Git 专注于揭示并行更改文件和异步同步带来的所有复杂性。在另一端，您可以直接访问共享磁盘。很好用，但是两个人同时尝试编辑同一个文件会怎么样？一个会很幸运，会保留他们的变化，另一个会失去这一切。这不是一个好的工作流程，尤其是如果丢失的更改值得花费数小时的昂贵劳动。因为 Git 向用户暴露了这种情况下可能出现的所有问题，所以它使得以智能的方式解决文件中的冲突成为可能——在某些情况下，这需要用户手动完成。

# 简单与安全

Git 的另一个让用户困惑的地方是提交 id 非常长，而且不可能记住数字。即使在用户友好的缩写形式中，它们看起来也像`0828ae1`。而且全 ID 是`0828ae10b20500fbc777cc40aa88feefd123ea5e`。我们能不能只按顺序编号，或者只用分行名称？问题是提交 id 是保证数据完整性的散列——它们保证我的机器上的提交 X 与远程或你的机器上的提交 X 相同。它们之间的不匹配可能出于不同的原因:

*   故意的——改变历史的基础、修正、挤压或任何其他操作
*   无意的——错误或对代码库的攻击

简化界面并向用户隐藏提交 ID 将使用户无法理解他们在机器上运行的代码库发生了什么。因为代码根据定义是在机器上运行的，任何安全漏洞都是极其危险的。

# 这是正确的方法吗？

当我学习 g it 的时候，它还是一个新事物——我在 2011 年学习它，Git 是在 2005 年创建的(第一次提交来自[2005 年 4 月 7 日 15:13:13-0700](https://github.com/git/git/commit/e83c5163316f89bfbde7d9ab23ca2e25604af290))。那时，我在工作中使用的是 T4 SVN，而 Mercurial 通常被认为是比 Git 更友好的替代品。你最近听过这些名字吗？Git 几乎完全主宰了版本控制市场。随着 GitHub 的兴起，它变得非常受欢迎，但即使对初学者来说很粗糙，它也是一个非常有效的工具，并且它会一直存在下去。

# 作为一个初学程序员该怎么做？

我的建议是越早学越好。Git 不太可能很快变得更简单。或者永远不会。一般来说，版本控制系统可以在你编程时省去很多麻烦。如果你在代码库的各个版本之间挣扎，我无法想象如何高效地处理代码。学好 Git 将帮助您专注于代码挑战，而不是纠结于丢失的文件或修复所谓的“Git 问题”——这几乎总是人们自己搞乱他们的存储库。

除此之外，学习 Git 成了新开发人员的必经之路。作为一个开发人员，你必须使用它，如果你没有很好地理解它就试图使用它，Git 会让你的生活很痛苦。明智的选择是根据自己的条件来学习，而不是等到评审反馈或代码问题迫使你在处理其他职责的同时学习它。

# 如何学习更多？

如果你有兴趣了解更多关于 Git 的知识，请在这里注册[来获取我的 Git 相关内容的更新。](https://how-to-dev.ck.page/e92d2eb5d7)

*最初发布于*[*https://how-to . dev*](https://how-to.dev/why-git-is-so-complicated)*。*

*更多内容请看*[***plain English . io***](https://plainenglish.io/)*。报名参加我们的* [***免费周报***](http://newsletter.plainenglish.io/) *。关注我们关于*[***Twitter***](https://twitter.com/inPlainEngHQ)[***LinkedIn***](https://www.linkedin.com/company/inplainenglish/)*[***YouTube***](https://www.youtube.com/channel/UCtipWUghju290NWcn8jhyAw)*[***不和***](https://discord.gg/GtDtUAvyhW) *。对增长黑客感兴趣？检查* [***电路***](https://circuit.ooo/) *。***