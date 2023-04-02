# 如何给你的代码命名？

> 原文：<https://javascript.plainenglish.io/how-to-name-your-code-e2cba14a7b3b?source=collection_archive---------3----------------------->

## 干净代码的命名约定。

![](img/fb3ca2b24b924d86909b49dae649c529.png)

Photo by [James Harrison](https://unsplash.com/@jstrippa?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

你有多少次第一眼就看懂别人写的代码？

可能不经常。您需要深入研究代码，了解发生了什么，并多次检查。

尽管如此，您可能不理解代码的功能。

你能做些什么来避免这种情况？

这时，干净的代码来拯救我们了。

> 干净的代码鼓励你去写那些有效的并且容易被其他开发者理解的代码。

例如:

```
function city(a, b) {
    print('I am moving from city', a,'to', b)
}
```

乍一看，您对该函数正在执行的任务了解多少？

这个函数的名字不足以描述它的意图。变量名也没有意义。

将上面的代码片段与下面的代码片段进行比较:

```
function printCity(fromCity, toCity) {
    print('I am moving from city', fromCity ,'to', toCity)
}
```

在这里，函数的名字是不言自明的，变量名给了我们线索，城市代表了事物的开始和结束。

仅仅通过改变名字，这种神秘的代码就变得更加易读了。

这种易于阅读的代码使其他开发人员的工作变得更容易，也有助于您进行调试。

如果你想让你的代码有意义，可维护和易读，下面是一些命名时要记住的规则。

# 干净代码的命名约定

既然我们已经讨论了干净代码的重要性，那么让我们来看看一些命名约定，以帮助您编写可读的代码。

这里描述的约定与你使用的编程语言无关。

这些与为您编写代码的编程语言描述的约定并行工作。

## 规则 1:使用名词或带形容词的短语来命名变量

大多数编程语言中的变量只不过是数据容器。

它们保存一些数据用于存储或处理。

建议用名词或带形容词的短语来命名它们，以阐明所存储数据的含义。

例如:

```
let f = {};
```

这里，变量名‘f’没有告诉我们任何关于存储数据的信息。

这里的 f 是什么？客户详情、产品详情还是其他？

我们没有线索。

但是，如果我们要在其中存储一些用户详细信息，我们可以将其命名为:

```
let user = {};
```

我们也可以使用像“userData”这样的名字，但是，当我们使用对象来存储数据时，在名字后面加上“Data”并没有增加任何价值。

> 目的是尽可能避免名字的冗余。

理解在名字后面加一个额外的单词是否会增加价值。

## 规则 2:布尔函数的名字必须有是或否的答案

让我们看一个例子，

```
if(login) {
// do something
}
```

在这里，login 是一个布尔值，但是变量的名称不够清楚，无法从其名称中推导出含义。

“登录”是什么意思？登录的动作？用户登录了吗？

我们无法理解。

相反，我们可以把它命名为，

```
if(isLoggedIn){
// do something
}
```

在这里，变量的名称足够有意义，可以断定它表示用户是否登录。“用户登录了吗？”这个问题的答案可能是也可能不是。

> 布尔有开/关的特性。因此，他们的名字必须反映他们的性格。

## 规则 3:使用动词或带有形容词的短语来命名函数或方法

函数是编程语言中的实干家。

它们充当执行某些事情的命令，并可能返回一个结果。

语言中的动词是动作词。

所以用动词命名函数是有意义的，因为它们应该描述它们需要执行的动作。

例如:

```
function getUser() {
// do something and 
return user;
}
```

这里的动词“get”告诉我们该函数将获取用户的详细信息。

它可以通过网络请求或通过数据库获取请求来实现。

无论哪种方式，我们都可以得出结论，该功能将“获取”用户的详细信息。

我们也可以在这里使用“fetchUser”。唯一的条件是对所有函数使用相同的动词，即“fetch”，这意味着它获取数据。为了更好地理解这一点，让我们看一个代码片段。

```
function getUser(){
// do something
return user;
}
function fetchAdmin(){
// do something
return admin;
}
```

在上面的代码示例中，我们有函数“getUser”和“fetchAdmin”。

两者都执行获取用户详细信息的相同任务，但使用不同的动词。

在这种情况下，使用“get”或“fetch”作为两个函数的动作词以避免混淆是很重要的。

> 使用动词命名函数时避免不一致，坚持使用相同的动词来命名相同的动作。

## 规则 4:使用名词或带名词的短语来命名类

大多数编程语言中的类都会实例化一些东西。

它可以是用户、产品、评论等。

用名词描述实例化的事物来命名类是可取的。

让我们看一个例子:

```
class User {
const firstName;
const age;
const email;
}
```

上面的代码片段定义了一个类 User，它的实例化如下:

```
let user = new User();
```

在这里,‘User’这个名字的含义足以理解它是一个用户的实例。

我们可以使用“AppUser”这样的名字，但是“App”这个词并不能增加价值。每个用户都是应用用户，那么‘AppUser’是什么意思？

遵循前面提到的规则，在命名变量、函数或类时避免任何冗余。

另一个例子，

如果某个类负责连接到数据库，则将该类命名为 database，而不要使用 DatabaseManager 之类的名称。

“经理”这个词歪曲了班级数据库的意思。

什么的经理？用户是“数据库管理员”吗？

> 为了避免任何混淆，请确保使用名词，并在名称中添加额外的单词之前进行思考。
> 
> 它增加了什么价值，还是使意思更加模糊了？

我希望所提供的提示能帮助你在将来写出更干净的代码，让你的生活更轻松。

如果您有任何问题或意见，请在下面的评论区随意添加。

到那时，快乐的编码！

***参考文献:***

[清洁码](https://pro.academind.com/p/clean-code)

*更多内容请看*[***plain English . io***](http://plainenglish.io/)*。报名参加我们的* [***免费周报***](http://newsletter.plainenglish.io/) *。在我们的* [***社区***](https://discord.gg/GtDtUAvyhW) *获得独家获得写作机会和建议。*