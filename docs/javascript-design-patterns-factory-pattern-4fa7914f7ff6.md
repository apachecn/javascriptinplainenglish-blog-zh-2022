# JavaScript 设计模式:工厂模式

> 原文：<https://javascript.plainenglish.io/javascript-design-patterns-factory-pattern-4fa7914f7ff6?source=collection_archive---------2----------------------->

## 工厂模式是什么？工厂模式是用于创建对象的最常见的设计模式之一。

![](img/d2ba6a509bb7a01e1c8fd8efd149af8c.png)

## 工厂模式是什么？

工厂模式是用于创建对象的最常见的设计模式之一。我们没有公开创建对象的具体逻辑，而是将逻辑封装在一个函数中，这个函数可以被认为是一个工厂。工厂模式可以根据抽象的层次进行分类:简单工厂、工厂方法和抽象工厂。

如果你只接触过 JavaScript 这种编程语言，抽象的概念可能会有点模糊，因为 JavaScript 一直把抽象作为保留词，并没有实现它。没有很好的理解抽象概念，就很难理解工厂模式中三种方法的异同。所以，让我们从一个场景开始，简单的说一下抽象和工厂的概念。

**下面我们用一个小故事来帮你理解工厂模式:**

> 你女朋友的生日快到了，你想知道她想要什么生日礼物，于是出现了下面的对话:
> 
> **你**:“亲爱的，今天是你的生日，你想要什么生日礼物？”
> 
> (刚好你女朋友是个爱猫人士，大多在抖音上爱上了一只超级可爱的苏格兰折耳猫，她也想要一只和网络名人一样风格的猫。)
> 
> **你女朋友**:“亲爱的，我想要一只动物。”
> 
> **你**:“你想要什么动物？”
> 
> 你女朋友说:“我想要猫科动物。”
> 
> (这时候你就纳闷了，猫科动物包括老虎，狮子，豹子，猞猁，各种猫。我怎么知道你想要什么？)
> 
> **你**:“你想要什么样的猫科动物？”
> 
> **你女朋友**:“真傻，你还要什么，肯定是小猫，我们还能像迪拜的土豪一样养虎吗！
> 
> **你**:“好吧，那你想要哪个品种的猫？
> 
> **你女朋友**:“我要外国品种”
> 
> (讲到这里，你就要崩溃了，作为一个程序员，你再也受不了这种挤牙膏的问题了)
> 
> 于是你央求道:“亲爱的，你就告诉我你想要什么品种，什么颜色，多大的猫？”
> 
> 你的女朋友想了想抖音上的猫，回答说:“我想要一只不超过一岁的灰色苏格兰短耳猫！”
> 
> 于是，在女朋友生日那天，你去宠物店挑了一只“不超过一岁的灰色苏格兰短耳猫”送给女朋友。同一个红猫的梦！

上面你最后买的送给女朋友的猫可以看做是一个实例对象，宠物店可以看做是一个工厂，我们可以把它看成是一个函数，这个工厂函数里面有各种动物，那么你是怎么得到实例的呢？因为你把正确的参数传给宠物店，“颜色:灰色”，“年龄:不超过 1 岁”，“品种:苏格兰短耳”，“类别”。猫”。
在之前的对话中，你的女朋友回答“动物”、“猫科动物”、“外国品种”，你不明白她想要什么，因为她太抽象了。她回答的是一大群动物而不是具体动物的共同特征，这种提取复杂事物的一个或多个共同特征的思维过程就是抽象。

现在我们理解了抽象的概念，让我们来看看前面提到的工厂模式的三种实现:**简单工厂模式**、**工厂方法模式**、**抽象工厂模式**。

## **简单工厂模式**

简单工厂模式也称为静态工厂模式。工厂对象决定创建某个产品对象类的实例。主要用于创建同一类的对象。

在实际项目中，我们经常需要根据用户的权限来渲染不同的页面。拥有高级权限的用户所拥有的某些页面不能被拥有低级权限的用户查看。因此，我们可以将用户可以看到的页面保存在具有不同权限级别的用户的构造函数中。基于权限实例化用户。代码显示如下:

UserFactory 是一个简单的工厂，在这个函数中有 3 个构造函数对应不同权限的用户。当我们调用工厂函数时，只需要传递`superAdmin`、`admin`、`user` 三个可选参数中的一个，就可以得到对应的实例对象。你可能会发现我们三类用户的构造函数内部都比较熟悉，我们也可以优化。

简单工厂的优点是，您只需要一个正确的参数就可以获得您需要的对象，而不需要知道它的创建细节。但是，函数包含所有对象的创建逻辑(构造函数)和判断逻辑代码。每增加一个新的构造函数，都需要修改判断逻辑代码。当我们的对象不是以上 3 个而是 30 个以上的时候，这个功能就会变成一个巨大的超级功能，很难维护。因此，只有在创建的对象数量较少且对象创建逻辑不复杂的情况下，才能使用简单的工厂。

**工厂方法模式**

工厂方法模式的初衷是将对象的实际创建委托给子类，这样核心类就变成了抽象类。但是在 JavaScript 中，很难像传统的面向对象那样创建抽象类。所以在 JavaScript 中我们只需要参考它的核心思想。我们可以把工厂方法想象成实例化对象的工厂类。

在简单工厂模式中，每次添加构造函数时，我们都需要修改两段代码。现在我们使用工厂方法模式来转换上面的代码。如前所述，我们只把工厂方法当作实例化对象的工厂，它只做实例化对象一件事！我们在安全模式下创建对象。

上面的代码解决了每次添加构造函数都需要修改两次代码的问题。如果我们需要添加一个新的角色，我们只需要在`UserFactory.prototype`中添加即可。例如，我们需要添加一个`VipUser`:

在上面的代码中，使用的安全模式可能一时难以理解。

因为我们保存了`SuperAdmin`、`Admin`、`NormalUser` 等构造函数到`UserFactory.prototype`，这意味着我们必须实例化`UserFactory` 函数才能实例化以上对象。如下面的代码所示。

在上面调用函数的过程中，一旦我们在任何阶段忘记使用 new，就无法正确获取`superAdmin` 对象。但是一旦使用安全模式实例化，就可以很好的解决上述问题。

**抽象工厂模式**

上面描述了简单工厂模式和工厂方法模式，这两种模式都是直接生成实例，但是抽象工厂模式是不同的。抽象工厂模式不直接生成实例，而是用于创建产品类集群。

在上面的例子中，有三个用户角色:`superAdmin`、`admin`和`user`，其中`user` 可能注册了不同的社交媒体账户，比如 facebook、twitter、linkedin。那么这三类社交媒体账号就是对应的集群。在抽象工厂中，类簇一般由父类定义，在父类中定义一些抽象方法，然后子类通过抽象工厂继承父类。所以抽象工厂其实是子类从超类继承的方法。

上面提到的抽象方法是声明了但不能使用的方法。在其他传统的面向对象语言中，通常使用 abstract 进行声明，但是在 JavaScript 中，abstract 是一个保留字，但是我们可以通过抛出类方法中的错误来模拟抽象类。

上面代码中的`getPrice` 是一个抽象方法，我们定义了它但没有实现它。如果子类继承了`FacebookUser` 但没有覆盖`getName`，子类的实例化对象将调用超类的`getName` 方法并抛出错误消息。

让我们分别实现帐户管理的抽象工厂方法:

AccountAbstractFactory 是一个抽象工厂方法，在参数中传递子类和超类，在方法体中实现子类对超类的继承。将抽象类添加到抽象工厂方法的方法是通过点语法添加的。

让我们定义一个普通用户的子类:

在上面的代码中，我们定义了三类`UserOfFacebook`、`UserOfTwitter`和`UserOfLinkedin`。这三个类通过抽象工厂方法作为子类实现继承。特别需要注意的是，调用抽象工厂方法后，不要忘记重写抽象方法，否则在子类的实例中调用抽象方法时会报错。

让我们分别实例化这三个类别，并检查抽象工厂方法是否实现了类集群的管理。

从打印结果来看，抽象工厂`AccountAbstractFactory` 很好地完成了它的角色，根据社交媒体集群对不同的用户账户进行分类。这就是抽象工厂的作用。它不直接创建实例，而是通过类继承来管理类簇。抽象工厂模式一般用于多人协作的超大型项目，严格要求项目以面向对象的思维完成。

## 工厂**模式**的项目实际应用

在实际的前端业务中，最常用的简单工厂模式。如果不是非常大的项目，很难有机会使用工厂方法模式和抽象工厂方法模式。下面我将介绍 Vue 项目中实际使用的简单工厂模式的应用。

在一个普通的 vue + vue-router 项目中，我们通常会将所有路由写入 router/index.js 文件。下面这段代码我相信 vue 开发者会非常熟悉，一共 5 个页面路由:

谈到权限管理页面，通常需要在用户登录时根据权限打开一个固定的访问页面，并使用相应的权限进行页面跳转。但是如果我们仍然遵循旧的方法，将所有的路径写入`router/index.js`文件，那么低特权用户可以通过在浏览器上输入 url 跳转到高特权页面，如果他们知道高特权路径的话。。因此，登录时必须使用`vue-router`提供的`addRoutes` 方式，根据权限给用户相应的路由权限。此时，您可以使用简单的工厂方法来转换上面的代码。

在`router/index.js`文件中，我们只提供了`/login`路由页面。

我们在`router/`文件夹中创建新的`routerFactory.js`文件，并导出`routerFactory` 简单工厂功能，根据用户权限提供路由权限。代码如下:

在登录页面导入该方法，在请求登录界面后根据权限添加路由:

在实际项目中，由于使用`this.$router.addRoutes`方法添加的路由刷新后无法保存，路由将无法访问。通常的做法是在本地加密和保存用户信息，获取本地权限并在刷新后解密，然后根据权限重新添加路由。我不想在这里详述，因为这和工厂模式没有什么关系。

## 总结

上面提到的三种工厂模式，就像上面的单例模式一样，都是创造性的设计模式。简单工厂模式也被称为静态工厂方法，用于创建特定产品对象的实例，该实例用于创建单个对象；工厂方法模式是将实例的创建推迟到子类；抽象工厂模式用于抽象类的工厂。创建产品类集群，并不负责创建某一类产品的实例。在实际业务中，有必要根据实际业务的复杂程度选择合适的模式。对于非大型前端应用程序，灵活使用简单的工厂实际上可以解决大多数问题。

关于设计模式的其他文章，请阅读以下文章，如果你对我的文章感兴趣，你可以在[media](https://hyhwell.medium.com/)或 [Twitter](https://twitter.com/Maxwell_hyh) 上关注我。

[](https://levelup.gitconnected.com/javascript-design-patterns-observer-pattern-1cf90cffb1e2) [## JavaScript 设计模式:观察者模式

### 观察者

Observerlevelup.gitconnected.com 模式](https://levelup.gitconnected.com/javascript-design-patterns-observer-pattern-1cf90cffb1e2) [](https://levelup.gitconnected.com/javascript-design-patterns-strategy-pattern-c013d3dbc059) [## JavaScript 设计模式:策略模式

### 学习设计模式的目的是代码的可重用性，使代码更容易被其他人理解，并且…

levelup.gitconnected.com](https://levelup.gitconnected.com/javascript-design-patterns-strategy-pattern-c013d3dbc059) [](https://levelup.gitconnected.com/javascript-design-patterns-singleton-pattern-7ada98be9a10) [## JavaScript 设计模式:单例模式

### Singleton 模式:将类实例化的次数限制为一次，一个类只有一个实例，并且…

levelup.gitconnected.com](https://levelup.gitconnected.com/javascript-design-patterns-singleton-pattern-7ada98be9a10) 

*更多内容请看*[***plain English . io***](https://plainenglish.io/)*。报名参加我们的* [***免费周报***](http://newsletter.plainenglish.io/) *。关注我们关于*[***Twitter***](https://twitter.com/inPlainEngHQ)[***LinkedIn***](https://www.linkedin.com/company/inplainenglish/)*[***YouTube***](https://www.youtube.com/channel/UCtipWUghju290NWcn8jhyAw)*[***不和***](https://discord.gg/GtDtUAvyhW) *。对增长黑客感兴趣？检查* [***电路***](https://circuit.ooo/) *。***