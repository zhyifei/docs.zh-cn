---
title: "客户端验证 （验证在表示层）"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |客户端验证 （验证在表示层）"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: db88a3b5c95afdc8d5a20094105f1f5991483ed6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a>客户端验证 （验证在表示层）

即使真实源是域的模型，最终你必须在域模型级别可以验证，验证仍可在域模型级别 （服务器端） 和客户端处理。

客户端验证是一个重大便利的用户。 它将保存它们需要花费时间的时间等待往返行程到的服务器，可能会返回验证错误。 在业务术语中，甚至几秒的乘积数百次每一天的秒的小数部分累加到大量的时间、 费用，并减少失败。 简单和快速验证使用户能够更有效地工作，并生成更好的质量输入和输出。

正如一样视图模型和域模型不同，视图模型验证和域模型验证可能已类似，但具有不同的用途。 如果您担心有关干 （不重复自己原则），请考虑在此情况下代码重用可能还表示耦合，而且，企业应用程序在很多重要，不以将服务器端与客户端比要遵循干原则。

即使在使用客户端验证时，应始终验证你的命令，或在服务器代码中，输入 Dto，因为服务器 Api 使用可能的攻击矢量。 因为如果你有一个客户端应用程序，从用户体验的角度，则最好主动和不允许用户输入无效的信息，执行操作都是通常情况下，最佳选择。

因此，在客户端代码中你通常验证 Viewmodel。 你还可以验证客户端输出 Dto 或命令之前将其发送给服务。

客户端验证的实现依赖于要生成哪种客户端应用程序。 如果您要验证 web MVC web 应用程序中的数据与在.NET 中，验证正在编码在 JavaScript 或 TypeScript 中的 SPA web 应用程序代码的大部分将不同或移动应用程序编码使用 Xamarin 和 C\#。

## <a name="additional-resources"></a>其他资源

### <a name="validation-in-xamarin-mobile-apps"></a>验证 Xamarin 移动应用程序

-   **验证文本输入和显示的错误**
    [*https://developer.xamarin.com/recipes/ios/standard\_控件/文本\_字段/验证\_输入 /*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)

-   **验证回调**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)

### <a name="validation-in-aspnet-core-apps"></a>ASP.NET Core 应用中的验证

-   **Rick Anderson。添加验证**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a>SPA 中的验证 Web 应用 (角度 2，TypeScript，JavaScript)

-   **Ado Kukic。角度 2 形成验证** **
     ** [ *https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)

-   **窗体验证**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)

-   **验证。** 轻松文档。
    [*http://breeze.github.io/doc-js/validation.html*](http://breeze.github.io/doc-js/validation.html)

总之，这些是关于验证的最重要概念：

-   实体和聚合应强制执行其自己的一致性，并将"始终有效"。 聚合根负责在相同的聚合内的多实体一致性。

-   如果您认为实体需要进入无效状态，请考虑使用不同的对象模型 — 例如，使用临时 DTO，直至你创建的最后一个域实体。

-   如果你需要创建多个相关的对象，例如聚合时，所有这些创建后，它们是仅有效，请考虑使用工厂模式。

-   验证框架最适用中特定层，例如表示层或应用程序/服务层中，但通常不在域模型层，因为你将需要的基础结构框架对其执行的强依赖项。

-   在大多数情况下，客户端中采用冗余验证很好的因为应用程序可以是主动。


>[!div class="step-by-step"]
[以前](域-模型-层-validations.md) [下一步] (域的事件的设计-implementation.md)
