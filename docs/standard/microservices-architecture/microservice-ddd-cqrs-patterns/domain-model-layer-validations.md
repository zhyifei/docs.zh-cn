---
title: 在域模型层中设计验证
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 在域模型层中设计验证
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ce3cb0c79cbd492224ce1d4ecb25cd02062f11cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578945"
---
# <a name="designing-validations-in-the-domain-model-layer"></a>在域模型层中设计验证

在 DDD 中，验证规则可以看作不变量。 聚合的主要责任是对该聚合内所有实体跨状态更改来执行不变量。

域实体应始终为有效的实体。 应始终为 true 的对象存在一定数量的不变量。 例如，订单项对象始终得有一个必须为正整数的数量，以及项目名称和价格。 因此，执行不变量是域实体（尤其是聚合根）的职责，而实体对象应不能在无效的情况下存在。 不变量规则只需表达为协定，当它们遭违反时会引发异常或通知。

这背后的原因是，很多 bug 因对象处于它们不应处于的状态而发生。 下面是来自 Greg Young 在[联机讨论](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/)中的很好的解释：

比如说，我们现在有一个采用 UserProfile 的 SendUserCreationEmailService...我们可以如何理性解释该服务中其名称不为 null？ 是不是要再次检查？ 或者更有可能...不需要花精力检查而是“期待更好的发生”- 希望其他人在将其发送给你之前花时间进行了验证。 当然，使用 TDD 时，我们首先应该编写的一个测试是，我是否向客户发送了会引发错误的 null 名称。 但是，一旦我们开始反复编写这些类型的测试，我们认识到...“等一下，如果我们从不允许名称成为 null，我们就不会有所有这些测试”

## <a name="implementing-validations-in-the-domain-model-layer"></a>在域模型层中实现验证

验证通常在域实体构造函数或可以更改该实体的方法中实现。 有多种方法来实现验证，例如验证失败时验证数据和引发的异常。 还有更多高级的模式，例如使用验证的规范模式和通知模式来返回一系列错误，而不是在异常发生时返回每个验证的异常。

### <a name="validating-conditions-and-throwing-exceptions"></a>验证条件和引发异常

下面的代码示例通过引发异常显示域实体中最简单的验证方法。 在本部分末尾的引用表中，可以看到指向基于之前讨论的模式的更多高级实现。

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

更好的示例将演示，需要确保内部状态未更改，或者方法的所有变化都已发生。 例如，下面的实现将使对象保持处于无效状态：

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

如果状态的值无效，则第一个地址行和城市已更改。 这可能使地址无效。

类似的方法可用于实体的构造函数中，引发异常来确保实体在创建后是有效的。

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a>在基于数据注释的模型中使用验证属性

另一种方法是使用基于数据注释的验证属性。 验证属性用于配置模型验证，在概念上类似于数据库表中字段上的验证。 它包括诸如分配数据类型或必填字段之类的约束。 其他类型的验证包括向数据应用模式以强制实施业务规则，比如信用卡号、电话号码或电子邮件地址。 验证属性使执行要求变得简单。

但是，如以下代码所示，此方法在 DDD 模型中可能太具侵入性，因为它依赖 Microsoft.AspNetCore.Mvc.ModelState 的 ModelState.IsValid，Microsoft.AspNetCore.Mvc.ModelState 必须从 MVC 控制器调用。 在调用每个控制器操作之前都会执行模型验证，并且控制器方法负责检查调用 ModelState.IsValid 的结果并作出正确反应。 要不要使用它取决于你希望模型与该基础结构的耦合紧密程度。

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

但是，从 DDD 的角度来看，最好通过在实体行为方法中使用异常，或者通过实现规范和通知模式来执行验证规则，从而使域模型保持精简。 ASP.NET Core 中的数据注释等验证框架或者 FluentValidation 等任何其他验证框架带有要求来调用应用程序框架。 例如，当在数据注释中调用 ModelState.IsValid 时，需要调用 ASP.NET 控制器。

在将接受输入的 ViewModel 类（而非域实体）中在应用程序层上使用数据注释来允许 UI 层中的模型验证很有意义。 但是，这不应在域模型内排除验证时完成。

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a>通过实现规范模式和通知模式来验证实体

最后，域模型中实现验证的更复杂方法是，通过结合使用通知模式来实现规范模式，如后面列出的其他资源中所述。

值得一提的是，还可使用这些模式中一个 - 例如通过控制语句进行手动验证，但使用通知模式来堆叠并返回验证错误列表。

### <a name="using-deferred-validation-in-the-domain"></a>在域中使用延迟的验证

有数种方法来处理域中的延迟验证。 [实现域驱动设计](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577)一书中，Vaughn Vernon 在验证部分讨论了这些。

### <a name="two-step-validation"></a>双重验证

此外考虑双重验证。 在命令数据传输对象 (DTO) 上使用字段级别验证，在实体内使用域级别验证。 通过返回结果对象而非异常以使其更易于处理验证错误，可以执行此操作。

例如通过将字段验证用于数据注释，你不用重复验证定义。 然而在 DTO（例如命令和 Viewmodel）的情况下，执行可以既位于服务器端又位于客户端端。

## <a name="additional-resources"></a>其他资源

-   **Rachel Appel。ASP.NET Core MVC 模型验证简介**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)

-   **Rick Anderson。添加验证**
    [https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

-   **Martin Fowler。在验证中将引发异常替换为通知**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)

-   **规范和通知模式**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)

-   **Lev Gorodinski.域驱动设计 (DDD) 中的验证**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)

-   **Colin Jack。域模型验证**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)

-   **Jimmy Bogard。DDD 中的验证**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)


>[!div class="step-by-step"]
[上一页] (enumeration-classes-over-enum-types.md) [下一页] (client-side-validation.md)
