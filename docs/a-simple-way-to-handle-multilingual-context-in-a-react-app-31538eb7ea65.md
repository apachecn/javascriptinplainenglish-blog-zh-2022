# React 应用中处理多语言上下文的简单方法

> 原文：<https://javascript.plainenglish.io/a-simple-way-to-handle-multilingual-context-in-a-react-app-31538eb7ea65?source=collection_archive---------3----------------------->

## React 应用程序中处理多语言上下文的指南。

![](img/970b30838d3e754251f5b8fac178399d.png)

Photo by [Matteo Vistocco](https://unsplash.com/@mrsunflower94?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/rosetta-stone?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

我最近一直在开发一个需要阿拉伯语和英语版本的应用程序。我研究了一些教程和样板文件，了解如何在网上做到这一点。它们在开始时很有帮助，但一旦我明白了我在做什么，我意识到有一种更简单的方法来管理 React 应用程序中不同语言的上下文。所以这就是这篇文章的内容！

如果你想直接跳到代码，你可以在这里看到我是如何在一个应用[中实现的。](https://github.com/osintalex/sudan-art/tree/6415bdaebf85747d4a62b8aa1b4dbf5cad68830d)

# 概观

以下是设置和运行该系统所需的所有东西:

1.  用`React.createContext`创建的上下文；
2.  您的应用程序的所有翻译；
3.  在`App.js`中把语言环境注入到你的应用程序中；
4.  一个工具组件，根据传递给它的标识符返回不同语言的文本。我把这个叫做`multilingualContent.js`；
5.  一个按钮，你的用户可以点击切换整个应用程序的语言；
6.  一种利用您创建的多语言环境来测试组件的方法。

我将一个一个地检查这些。

## 1.如何创建上下文

首先，使用`React.createContext`创建上下文。这非常简单，因为您只是利用了 React 库中已经存在的东西，所以您可以创建一个像这样简单的文件:

## 2.存储所有翻译

现在，将所有翻译保存在一个名为`translations.js`的文件中的 JSON 对象中。你应该确保这些关键字对每个文本值给出了清晰而简明的描述，这样你就可以很容易地在你的应用程序中引用它们。

现在，这里有一个简单的例子，只是利用文本说“你好”。

## 3.将语言上下文注入 App.js

您现在可以利用您在第一步中创建的上下文实例将语言上下文注入到您的`App.js`的顶部。我这样做的原因是它让我在`App.js`中将状态提升到应用程序的顶部。

这样，您可以将`toggleLanguage`函数传递到应用程序中的任何地方，比如您可能希望让用户单击一个 navbar 组件来切换整个应用程序的语言。

你可以忽略这里所有的路由内容，我只是从我正在做的一个项目中复制了这个例子，因为我认为它更接近大多数真实应用程序的样子。主要的一点是，你需要将你的应用程序的所有部分包装在`LanguageContext.Provider`组件中。

## 4.制作多语言实用程序组件

现在，您可以利用 React `useContext`钩子创建一个通用组件来处理您的应用程序中的多语言内容。

该组件的要点是，您可以创建一次，然后在应用程序中需要不同语言的文本内容的任何地方使用它。

现在，您可以在应用程序中的任何地方使用该组件，如下所示:

```
<p>
<MultiLingualContent contentID="hello" />
</p>
```

例如，您可以将该组件导入到您的应用程序中，并像上面的示例一样进行呈现，以创建一个段落 HTML 标记，如果您的应用程序上下文是英语，该标记将呈现“hello ”,如果上下文是阿拉伯语，则呈现“mrhaba”。

这是因为`contentID`道具被赋予了值 hello，该值映射到`translations.js`中的‘hello’键。

## 5.制作一个按钮，以便用户可以更改应用程序语言

现在，您可以制作一个按钮，在这里您可以像这样切换应用程序的语言:

因为我将语言状态注入到应用程序树顶部的`App.js`中，如果你点击这个按钮来切换语言，它会将语言状态传递回应用程序树的顶部，并将在整个应用程序中切换语言。

## 6.测试使用该语言上下文的组件

最后但同样重要的是，您必须弄清楚如何测试使用语言上下文的组件。

幸运的是，这对于 React 测试库来说非常简单。例如，要测试下面的组件，您可以像这样编写一个测试:

就是这样！现在您有了一个可以测试的多语言 React 应用程序。:-)

*更多内容看* [***说白了就是 io***](http://plainenglish.io/) *。报名参加我们的* [***免费周报***](http://newsletter.plainenglish.io/) *。在我们的* [***社区不和谐***](https://discord.gg/GtDtUAvyhW) *获得独家获取写作机会和建议。*