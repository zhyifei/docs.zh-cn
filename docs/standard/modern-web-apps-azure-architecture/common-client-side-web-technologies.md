---
title: "常见的客户端 web 技术"
description: "设计使用 ASP.NET Core 和 Azure 的现代 Web 应用程序 |常见的客户端 web 技术"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 1084aee3d81a5df6ac99d6ec0e2ef647b4173c24
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2017
---
# <a name="common-client-side-web-technologies"></a>常见的客户端 Web 技术

> "网站应显示从内部良好和 out。"  
> _-Paul Cookson_

## <a name="summary"></a>摘要

ASP.NET 核心应用程序是 web 应用程序，它们通常依赖于客户端 web 技术如 HTML、 CSS 和 JavaScript。 通过将从其布局和样式 (CSS)，其行为 （通过 JavaScript) 分离页面 (HTML) 的内容，复杂的 web 应用可以利用的关注点分离原则。 将来对结构、 设计或应用程序行为的更改可详细轻松时不缠这些问题。

虽然 HTML 和 CSS 相对稳定，JavaScript，通过应用程序框架和实用程序开发人员使用以生成基于 web 的应用程序，不断 breakneck 速度。 本章考察开发应用程序，如提供角和响应客户端库的高级概述的一部分的 web 开发人员使用 JavaScript 的几种方法。

## <a name="html"></a>HTML

HTML （超文本标记语言） 是用于创建网页和 web 应用程序的标准的标记语言。 其元素窗体页，表示带格式的文本、 图像、 窗体输入和其他结构的构建基块。 当浏览器发出请求到的 URL 是否提取一个页面或应用程序时，第一波，它是返回将是一个 HTML 文档。 此 HTML 文档可能引用或 CSS 或 JavaScript 形式的行为的形式包括有关其外观和布局的其他信息。

## <a name="css"></a>CSS

CSS （级联样式表） 用于控制的外观和布局的 HTML 元素。 CSS 样式可以直接应用于 HTML 元素、 单独定义在同一页上，或在单独的文件中定义和引用的页面。 基于如何使用它们来选择一个给定的 HTML 元素的样式 cascade。 例如，一种样式可能适用于整个文档，但将被重写被应用到特定元素的样式。 同样，将应用于已应用于反过来将重写由目标的特定实例 （通过其 id) 该元素的样式元素的 CSS 类样式的重写特定元素的样式。 图 6-1

**图 6-1。** CSS 特殊性规则，请在顺序。

![](./media/image6-1.png)

最好来保持样式在其自己单独的样式表的文件，并使用基于所选内容的级联来实现应用程序中的一致且可重用样式。 应当避免放置在 HTML 内的样式规则，并将样式应用于特定的各个元素 （而不是整个元素或已有一个特定的 CSS 类应用于它们的元素的类） 应为异常，而不是规则。

### <a name="css-preprocessors"></a>CSS 预处理器

CSS 样式表缺少对条件逻辑、 变量和其他编程语言功能的支持。 因此，大型的样式表通常包含大量重复，相同的颜色、 字体或其他设置应用于 HTML 元素和 CSS 类的许多不同变体。 CSS 预处理器可以帮助你样式表，请按照[干原则](http://deviq.com/don-t-repeat-yourself/)通过添加对变量和逻辑支持。

最常用的 CSS 预处理器是 Sass 且小于。 同时扩展 CSS 和向后兼容，这意味着是普通的 CSS 文件有效 Sass 或较少的文件。 Sass 是基于 Ruby 的和小于是 JavaScript 基于，并同时通常作为本地开发过程的一部分运行。 两个具有命令行运行这些工具在 Visual Studio 中的可用，以及内置支持使用 Gulp 或 Grunt 任务。

## <a name="javascript"></a>JavaScript

JavaScript 是已标准化 ECMAScript 语言规范中的动态、 解释型编程语言。 它是 web 的编程语言。 CSS，如 JavaScript 可以作为 HTML 元素中的属性定义为在页上，或单独的文件中的脚本块。 一样 CSS，一般而言，建议你可以将 JavaScript 组织成单独的文件，阻止将其分隔尽可能多地找到各网页或应用程序视图上的 HTML。

当 web 应用程序中使用 JavaScript，有你通常需要执行的一些任务：

-   选择 HTML 元素和检索和/或更新其值

-   查询数据 Web API

-   将命令发送到 Web API （和响应具有其结果的回调）

-   执行验证

你可以执行所有使用 JavaScript 单独出现时，这些任务，但许多库可简化了这些任务。 第一个和这些库的最成功之一是 jQuery，适合简化在网页上的这些任务将继续。 对于单页面应用程序 (Spa)，jQuery 不提供的许多角和响应提供所需功能。

### <a name="legacy-web-apps-with-jquery"></a>使用 jQuery 的传统 Web 应用

尽管由 JavaScript framework 标准远古，jQuery 仍然是一个非常常用的库用于使用 HTML/CSS 和构建应用程序 AJAX 调用 web Api。 但是，jQuery 在浏览器文档对象模型 (DOM) 级别操作，并且默认情况下提供仅的命令性，而不是声明性、 模型。

例如，想象一下这样，是否文本框的值超过 10，页面上的元素应要使其可见。 在 jQuery，这将通常可通过编写实现事件处理程序将检查文本框的值并设置基于该值的目标元素的可见性的代码。 这是一种基于代码的命令性方法。 改为其他框架可能会使用数据绑定以声明方式将元素的可见性绑定到文本框中的值。 这就不需要编写任何代码，但改为仅需要修饰所涉及的数据绑定特性的元素。 当客户端端行为增加更复杂时，数据绑定经常接近较少的代码和条件的复杂性更简单的解决方案中的结果。

### <a name="jquery-vs-a-spa-framework"></a>jQuery vs SPA Framework

| **因素** | **jQuery** | **角度**|
|--------------------------|------------|-------------|
| 将 DOM 抽离 | **是** | **是** |
| AJAX 支持 | **是** | **是** |
| 声明性数据绑定 | **否** | **是** |
| MVC 样式路由 | **否** | **是** |
| 模板化 | **否** | **是** |
| 深层链接路由 | **否** | **是** |

可以使用添加其他库添加大部分 jQuery 本质上缺少的功能。 但是，这样角的 SPA 框架提供更高的方式，这些功能，因为它已设计为具有所有这些记住从一开始。 此外，jQuery 是一个非常命令性的库，这意味着你需要调用 jQuery 函数以便使用 jQuery 执行任何操作。 其中很多工作和 SPA 框架提供的功能可以以声明方式，无需实际代码要写入。

数据绑定是一个很好的例子。 在 jQuery，通常仅需要某行代码来获取 DOM 元素的值，或设置元素的值。 但是，你必须编写此代码，你需要更改的值的元素，任何时间和有时这将在页面上的多个函数中发生。 另一个常见示例是元素可见性。 在 jQuery，可能有许多不同的位置，你将编写代码来控制某些元素是否可见。 在每个这些情况下，使用数据绑定时，不需要编写任何代码。 你只需将绑定到问题的元素的可见性的值*viewmodel*上的页上，和更改视图模型会自动反映在绑定元素中。

### <a name="angular-spas"></a>角度 Spa

AngularJS 快速变为世界上最常用的 JavaScript 框架之一。 角度 2，团队重新从零开始的 framework 生成向上 (使用[TypeScript](https://www.typescriptlang.org/)) 和 AngularJS 从变化到只需角度。 当前在版本 4 中，角仍然是可靠的框架，用于构建单页面应用程序。

从组件构建角度的应用程序。 组件将 HTML 模板与特殊对象结合起来，并控制页面的一个部分。 角的文档的简单组件如下所示：

```js
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    template: `<h1>Hello {{name}}</h1>`
})

export class AppComponent { name = 'Angular'; }
```

组件的使用定义@Component修饰器函数，其将在有关组件的元数据中。 选择器属性标识在其中将显示此组件的页面上的元素的 id。 模板属性是一个简单的 HTML 模板包含对应于该组件的名称属性，定义的最后一行的占位符。

使用组件和模板，而不是 DOM 元素，角度的应用程序可以运行更高级别的抽象和更少总体的代码比使用刚刚 （也称为"香草 JS"） 的 JavaScript 编写的应用或 jquery。 角还施加了某些上如何组织你的客户端脚本文件的顺序。 按照约定，角度应用常用文件夹结构中，使用位于应用文件夹中的模块和组件脚本文件。 角度脚本牵涉构建、 部署和测试应用程序通常位于较高级别的文件夹中的。

角还能够很好使用命令行界面 (CLI) 工具。 角度开发入门本地 （假设你已有 git 和 npm 安装） 组成只需克隆存储库从 GitHub 和运行\`npm 安装\`和\`npm 开始\`。 除此之外，角附带自己 CLI 工具，它可以创建项目、 添加文件，并帮助测试、 绑定，和部署任务。 此 CLI 工具友好性使角与 ASP.NET 核心，还提供了很好的 CLI 支持尤其兼容。

Microsoft 已开发一个引用应用程序中， [eShopOnContainers](http://aka.ms/MicroservicesArchitecture)，其中包括角度 SPA 实现。 此应用程序包含角度模块来管理在线商店购物篮、 负载和显示项从其目录和处理顺序创建。 你可以查看和下载示例应用程序从[GitHub](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebSPA)。

### <a name="react"></a>做出响应

与不同的角，它提供完整模型-视图-控制器模式实现中，响应只关心的视图。 它不是一个框架，只需一个库，因此若要生成 SPA 你将需要利用其他库。

响应的最重要功能之一是其使用虚拟的 dom。 虚拟 DOM 提供几个好处，包括 （虚拟 DOM 可以优化实际 DOM 中的哪些部分需要更新） 的性能和可测试性 （无需具有要测试响应和其虚拟 DOM 与其交互的浏览器） 的响应。

响应还很少将它与 HTML 配合方式。 而不是使代码和标记 （具有可能显示在 HTML 特性中的 JavaScript 对引用），之间做出反应的严格分隔作为 JSX 添加其 JavaScript 代码中直接 HTML。 JSX 是可编译到纯 JavaScript HTML 类似的语法。 例如: 

```js
<ul>
{ authors.map(author =>
    <li key={author.id}>{author.name}</li>
)}
</ul>
```

如果你已经知道 JavaScript，学习响应应简单。 没有几乎多学习曲线或特殊语法涉及作为角或其他受欢迎的库。

由于响应不完整框架，你通常将需要用于处理诸如路由、 web API 调用和依赖关系管理其他库。 一个好处是，你可以选择最佳的库，其中，每个但的缺点是，你需要创建所有这些决策并验证所有选定库很好地协同工作完成后。 如果你想很好的起点，你可以使用类似做出反应 Slingshot，prepackages 兼容库以及响应一组初学者工具包。

### <a name="choosing-a-spa-framework"></a>选择 SPA 框架

时考虑的 JavaScript 框架将最好地工作，以支持你的 SPA，请记住以下注意事项：

-   是你的团队熟悉框架和其依赖项 (在某些情况下包括 TypeScript)？

-   如何一时间是框架，并执行你同意其默认方式来执行操作？

-   它 （或助理库） 包含所有你的应用需要的功能？

-   是妥善制定了？

-   其社区是活跃程度？ 生成的新项目都是用它生成？

-   活跃程度是其核心团队？ 会定期传送问题已解决和新版本？

JavaScript 框架的继续发展 breakneck 速度。 使用上面列出来帮助减轻风险的选择将更高版本后悔正在依赖于框架的注意事项。 如果你特别规避风险，请考虑一个框架，它提供商业支持和/或正在开发的大型企业。

> ### <a name="references--client-web-technologies"></a>引用 – 客户端 Web 技术
> - **HTML 和 CSS**  
> <https://www.w3.org/standards/webdesign/htmlcss>
> - **Sass vs。较低**  
> <https://www.keycdn.com/blog/sass-vs-less/>
> - **小于 ASP.NET Core 应用、 Sass 和出色的字体样式**  
> <https://docs.microsoft.com/aspnet/core/client-side/less-sass-fa>
> - **在 ASP.NET 核心中的客户端开发**  
> <https://docs.microsoft.com/aspnet/core/client-side/>
> - **jQuery**  
> <https://jquery.com/>
> - **jQuery vs AngularJS**  
> <https://www.airpair.com/angularjs/posts/jquery-angularjs-comparison-migration-walkthrough>
> - **角度**  
> <https://angular.io/>
> - **做出响应**  
> <https://facebook.github.io/react/>
> - **做出反应 Slingshot**  
> <https://github.com/coryhouse/react-slingshot>
> - **做出反应 vs 角度 2 比较**  
> <https://www.codementor.io/codementorteam/react-vs-angular-2-comparison-beginners-guide-lvz5710ha>
> - **自 2017 年的 5 最佳的 JavaScript 框架**  
> <https://hackernoon.com/5-best-javascript-frameworks-in-2017-7a63b3870282>

>[!div class="step-by-step"]
[以前](常用的 web 的应用程序-architectures.md) [下一步] (develop-asp-net-core-mvc-apps.md)
