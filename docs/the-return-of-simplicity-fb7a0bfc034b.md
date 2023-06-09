# 简约的回归

> 原文：<https://javascript.plainenglish.io/the-return-of-simplicity-fb7a0bfc034b?source=collection_archive---------4----------------------->

## 我们真的需要花哨的框架来构建可行的网站吗？

![](img/732488538361a9b0368baca5af1f3a28.png)

Photo by [Dominik Schröder](https://unsplash.com/@wirhabenzeit?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com/?utm_source=medium&utm_medium=referral)

在 web 出现之初，有静态的 HTML。如果你想创建一个网站，你所要做的就是写一些标记，用 CSS 当时所提供的一些样式，然后把每个 FTP 上的所有文件放到某个服务器上。这些时代已经一去不复返了，现在我们在建立一个网站时有一个过度的复杂性。

在网络出现之初，一切都非常容易，你可以毫无困难地开始学习。但也非常有限。而且，当网络起飞时，许多人想要更多的选择来创建更强大的网站，这样他们就可以卖东西并创造一些交互性。于是就产生了 Web 2.0。

# Web 2.0

通常，短语 web 2.0 指的是用户能够与网站进行交互的 web。用户可以参与到可用的内容中，并创建新的内容。我们今天对网络的很多看法都是这个 web 2.0 的一部分。这个参与式网络的关键要素是什么？

# 服务器端开发

这场革命的发生部分是因为从服务器呈现动态 HTML 的方法更简单了。创建动态 HTML 的第一种方式是通过 CGI 脚本，设置起来很麻烦，可用的语言也不容易。

但是很快 Perl 和后来的 PHP 能够呈现动态 HTML，这些语言对初学者来说非常友好。于是，很多人开始学习编码，建立动态网站。此外，由于有一些开源数据库可用，这样做是相当便宜的。随着内容管理系统的创建，一个非技术人员甚至有可能创建一个网站并参与到这个狂野的世界中。

所有这些真的是一个巨大的进步。但这是有代价的。开发人员可以选择的选项越多，他们提供的功能越多，学习所需技能就越难。在这个交互式领域的开始，成为一个全栈开发人员真的是可能的，这意味着一个人可以非常好地了解从数据库到服务器端编程语言到客户端的整个栈。今天这几乎是不可能的，尤其是如果你必须从头开始学习一切的话。

# 客户端开发

web 2.0 的另一个因素是 JavaScript 的诞生。(由网景公司(Netscape)在 10 天之内开发出来，非常有名。)现在创建时髦的网站真的有可能了。我们可以直接在客户机上更改 DOM，而不需要重新加载所有内容。由于这发生在浏览器大战期间，不同的浏览器试图用不同的 API 相互竞争。因此，为了让开发人员的生活更轻松，一些聪明的开发人员想出了抽象出这些差异的库，jQuery 仍然以此闻名。

JavaScript 变得越强大，创建的库也越强大。第一个真正试图从客户端获得最大价值的框架是 [dojo](https://en.wikipedia.org/wiki/Dojo_Toolkit) 。在这个 [Backbone.js](https://backbonejs.org/) 创建后不久，JavaScript 框架就出现了爆炸式增长。

今天我们有过多的选择。React，Angular，Vue.js，Ember 只是几个大牌。但是有如此多的选择，真的，没有人能全部学会。而且，在我看来，这些框架中的大多数都增加了太多的复杂性，对于许多用例来说，根本不应该考虑它们。

但不幸的是，它们是，有时因为我们，作为开发者，喜欢新的闪亮的东西，有时因为相当有影响力的公司正在推动这些框架。

## 这些客户端框架是如何增加如此多的复杂性的？

所有大型框架都需要某种形式的捆绑器才可用。React 使用的是 [JSX](https://reactjs.org/docs/introducing-jsx.html) ，它甚至不再是 JavaScript，因此不能在浏览器中运行。Angular 使用了 [TypeScript](https://www.typescriptlang.org/) (这也不是 JavaScript)，Ember 是如此大的框架，具有如此多的功能，以至于它们都有自己的 CLI 和开发服务器。

当然，我们并不仅仅满足于这些框架。我们正在使用 NPM 或纱拉在额外的依赖。这让我们陷入了依赖地狱，带来了各种不良后果(参见这里的[或这里的](https://www.theregister.com/2016/03/23/npm_left_pad_chaos/))。

另一个问题是，我们用我们正在使用和依赖的所有工具在这个领域制造了一个非常大的进入壁垒。许多新来者也开始认为他们也需要这些简单网站的框架。这在大多数情况下都是多余的。

不要误解我的意思，对于一些 web 应用程序来说，这些框架确实很有帮助。没有这种工具的脸书将难以维系。但是对于一个简单的网站来说，这甚至是有害的，因为它会大大增加页面的大小。网站用户必须下载所有文件，这可能需要几兆字节。而且，由于网站使用了如此多的 JavaScript，浏览器必须解析代码，然后运行它。这就是为什么很多网站首先要花很长时间来展示任何东西。

# 那我们怎么改进呢？

为了简化开发，最近出现了一个令我兴奋的新进展——jam stack。JAMstack 代表 JavaScript、API 和标记。使用一些静态的站点生成器，如[雨果](https://gohugo.io/)或[哲基尔](https://jekyllrb.com/)，你可以创建网站，并在一些 API 的帮助下获取额外的数据。现在有如此多的 API 服务，对于一个普通的网站来说，你可以找到你需要的一切。

[这里的](https://github.com/whizkydee/Awesome-APIs)只是其中的几个！这些网站甚至不需要花哨的 CMS——简单的 CMS 就足够了。大多数时候，用例甚至不需要 WordPress、 [NetlifyCMS](https://www.netlifycms.org/) 或其他基于 Git 的 CMS 对很多很多网站来说就足够了。

这种方法的另一个优点是(几乎)没有安全问题。(我现在唯一能想到的是一个简单的管理员密码。)没有需要维护的服务器，也没有数据库。因此，有了这个，我们摆脱了所有后端的复杂性。

SSG 如何摆脱前端的复杂性？嗯，这个掌握在开发商手里。当然，*有可能使用一些花哨的 JavaScript 框架并引入大量的依赖项。但是，如果你只关注网站的设计和可用性，你会发现你并不需要这些工具。SSG 让这变得更容易，因为它可以快速启动和运行。当你开始写网站的框架时，你会发现所有的东西都很好地结合在一起。*

# 结论

我认为所有这些框架都是浪费时间吗？当然不是！我想说的是，对于一个简单的网站来说，如果客户想展示一个产品、一家公司或者他自己，你可以用 SSG/jam stack 创造出更好的结果。这将为开发商节省完成项目的时间。该网站将更快，因此在谷歌的定位会更好，这也会让你的客户高兴。

一如既往，我们需要为正确的工作使用正确的工具。不是所有的东西都需要一个大的框架。当我们坐下来，提前考虑这些选择，可能会节省我们一些时间。或者，当我们决定确实需要一个框架时，我们可以确定我们使用了正确的工具。

为什么网站仍然相关？如果你仅仅依赖大型科技公司来维持你的在线形象，你将受到他们规则的支配。而且，正如许多人所见，这些规则相当武断。例如，最近一家名为 Meta 的澳大利亚公司被脸书禁止进入。最终，这个问题得到了解决，但在很多情况下，情况并非如此。

*不是中等会员？* [*在这里报名*](https://grnt-grdwhl.medium.com/membership) *并支持我的写作过程！*

*更多内容看* [***说白了。报名参加我们的***](http://plainenglish.io/) **[***免费周报***](http://newsletter.plainenglish.io/) *。在我们的* [***社区不和谐***](https://discord.gg/GtDtUAvyhW) *获得独家获取写作机会和建议。***