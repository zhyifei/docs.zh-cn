---
title: "设计域模型层中的验证"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |设计域模型层中的验证"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f4870d0568c3539f296bcb3f577291cb0250cfca
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="designing-validations-in-the-domain-model-layer"></a>设计域模型层中的验证

在 DDD，验证规则都可以看作固定协定。 聚合的主要责任是在该聚合内的所有实体的状态更改之间强制实施固定协定。

域实体应始终为有效的实体。 有一定数量的固定条件应始终为 true 的对象。 例如，订单项对象始终必须拥有的数量必须为正整数，加上项目名称和价格。 因此，固定协定强制负责 （尤其是的聚合根） 的域实体的和的实体对象时应不能存在不是有效。 固定规则只需表达为协定，而它们违反时引发异常或通知。

这背后的原因是因为对象在它们永远不会已在进行的状态，则出现 bug 都很多。 下面是从在 Greg Young 详细讲解[联机讨论](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):

让我们建议我们现在有 SendUserCreationEmailService 采用 UserProfile...如何可以我们合理利用在该名称不为 null 的服务中？ 我们它再次检查？ 或更有可能...你只是你不必费神以检查并"最佳希望"— 您却希望人担忧若要发送到你之前验证它。 当然，使用 TDD 应，如果发送具有空名称的客户也应引发错误编写我们的第一个测试。 但是，一旦我们开始反复编写这些类型的测试我们认识到..."请稍等如果我们永远不会允许名称成为 null 我们就不会所有这些测试"

## <a name="implementing-validations-in-the-domain-model-layer"></a>在域模型层中实现验证

在域实体构造函数中或可以更新实体的方法中，通常被实现验证。 有多种方法来实现验证，例如验证数据和在验证失败时引发的异常。 还有更高级的模式，例如，验证，使用的规范模式和通知模式，以返回而不是返回每个验证异常，所发生的错误的集合。

### <a name="validating-conditions-and-throwing-exceptions"></a>验证条件并引发异常

下面的代码示例通过引发异常，在域实体中显示验证的最简单方法。 在本部分末尾的引用表中，你可以看到指向更高级的实现根据我们前面讨论的模式。

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

更好的示例将演示，需要确保，内部状态未更改，或者在方法的所有变化都时发生。 例如，下面的实现将使对象保持处于无效状态：

```csharp
public void SetAddress(string line1, string line2,
    string city, string state, int zip)
{
    _shipingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

如果状态的值无效，第一个地址行和城市已更改。 可能使的地址无效。

引发异常以确保在创建后的实体是有效的实体的构造函数中，可以使用类似的方法。

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a>在基于数据批注的模型中使用验证属性

另一种方法是使用基于数据注释的验证属性。 验证特性提供了如何配置从概念上讲到验证对数据库表中的字段类似的模型验证。 这包括如将数据类型或必填的字段分配的约束。 其他类型的验证包括将模式应用于数据以强制实施业务规则，如信用卡号码，电话号码或电子邮件地址。 验证特性，可以方便以强制执行需求。

但是，下面的代码中所示，此方法可能太彻底在 DDD 模型中，因为它将依赖关系 ModelState.IsValid 从 Microsoft.AspNetCore.Mvc.ModelState，必须从你的 MVC 控制器调用。 在正在调用的每个控制器操作之前，将执行模型验证和控制器方法负责检查的结果调用 ModelState.IsValid 并相应地作出反应。 若要使用它的决策取决于如何紧密耦合你想要与该基础结构的模型。

```csharp
using System.ComponentModel.DataAnnotations;
// Other using statements ...
// Entity is a custom base class which has the ID
public class Product : Entity
{
    [Required]
    [StringLength(100)]
    public string Title { get; private set; }

    [Required]
    [Range(0, 999.99)]
    public decimal Price { get; private set; }

    [Required]
    [VintageProduct(1970)]
    [DataType(DataType.Date)]
    public DateTime ReleaseDate { get; private set; }

    [Required]
    [StringLength(1000)]
    public string Description { get; private set; }

    // Constructor...
    // Additional methods for entity logic and constructor...
}
```

但是，从 DDD 的角度来看，域模型最好保存精益异常使用在实体的行为方法中，或通过实现的规范和通知模式，以强制执行验证规则。 验证框架，如在 ASP.NET 核心数据注释或任何其他验证框架如 FluentValidation 执行需要调用应用程序框架。 例如，当调用 ModelState.IsValid 方法中数据注释时，你需要调用 ASP.NET 控制器。

它很有意义，要在将接受输入，以允许 UI 层中的模型验证的 ViewModel 类 （而不是域实体） 的应用程序层使用数据注释。 但是，这不应在验证域模型中排除。

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a>通过实现规范模式和通知模式验证实体

最后，在域模型中实现验证的更复杂方法是通过结合使用通知模式中，实现规范模式中更高版本列出的其他资源的某些所述。

值得一提的是，你还可以使用这些模式的其中一个 — 例如，验证手动控制语句中，但它使用的通知模式以堆栈并返回验证错误的列表。

### <a name="using-deferred-validation-in-the-domain"></a>使用的域中的延迟的验证

有各种方法来处理域中的延迟验证。 在书籍[Implementing Domain-Driven 设计](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577)，Vaughn Vernon 讨论这些部分中的验证。

### <a name="two-step-validation"></a>双重验证

此外考虑双重验证。 使用命令数据传输对象 (Dto) 和域级别验证在你的实体上的字段级别验证。 通过返回结果对象改为异常以使其更轻松地处理验证错误，可以执行此操作。

使用数据注释字段验证，例如，你不重复的验证定义。 执行，但是，可以是服务器端和客户端在 Dto 的情况下 (命令和 Viewmodel 实例)。

## <a name="additional-resources"></a>其他资源

-   **Rachel Appel。ASP.NET 核心 mvc 模型验证简介**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)

-   **Rick Anderson。添加验证**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

-   **Martin Fowler。替换在验证中引发异常通知**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)

-   **规范和通知模式**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)

-   **列弗 Gorodinski。域驱动设计 (DDD) 中的验证**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)

-   **Colin 上插座。域模型验证**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)

-   **Jimmy Bogard。DDD 生活中的验证**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)


>[!div class="step-by-step"]
[以前](枚举-类-转移-枚举-types.md) [下一步] (客户端端 validation.md)
