---
title: 在域模型层中设计验证
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 在域模型层中设计验证
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 6ff325bb062da2ebff815fc847d2247707a0bf7f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188048"
---
# <a name="designing-validations-in-the-domain-model-layer"></a><span data-ttu-id="331fe-103">在域模型层中设计验证</span><span class="sxs-lookup"><span data-stu-id="331fe-103">Designing validations in the domain model layer</span></span>

<span data-ttu-id="331fe-104">在 DDD 中，验证规则可以看作不变量。</span><span class="sxs-lookup"><span data-stu-id="331fe-104">In DDD, validation rules can be thought as invariants.</span></span> <span data-ttu-id="331fe-105">聚合的主要责任是对该聚合内所有实体跨状态更改来执行不变量。</span><span class="sxs-lookup"><span data-stu-id="331fe-105">The main responsibility of an aggregate is to enforce invariants across state changes for all the entities within that aggregate.</span></span>

<span data-ttu-id="331fe-106">域实体应始终为有效的实体。</span><span class="sxs-lookup"><span data-stu-id="331fe-106">Domain entities should always be valid entities.</span></span> <span data-ttu-id="331fe-107">应始终为 true 的对象存在一定数量的不变量。</span><span class="sxs-lookup"><span data-stu-id="331fe-107">There are a certain number of invariants for an object that should always be true.</span></span> <span data-ttu-id="331fe-108">例如，订单项对象始终得有一个必须为正整数的数量，以及项目名称和价格。</span><span class="sxs-lookup"><span data-stu-id="331fe-108">For example, an order item object always has to have a quantity that must be a positive integer, plus an article name and price.</span></span> <span data-ttu-id="331fe-109">因此，执行不变量是域实体（尤其是聚合根）的职责，而实体对象应不能在无效的情况下存在。</span><span class="sxs-lookup"><span data-stu-id="331fe-109">Therefore, invariants enforcement is the responsibility of the domain entities (especially of the aggregate root) and an entity object should not be able to exist without being valid.</span></span> <span data-ttu-id="331fe-110">不变量规则只需表达为协定，当它们遭违反时会引发异常或通知。</span><span class="sxs-lookup"><span data-stu-id="331fe-110">Invariant rules are simply expressed as contracts, and exceptions or notifications are raised when they are violated.</span></span>

<span data-ttu-id="331fe-111">这背后的原因是，很多 bug 因对象处于它们不应处于的状态而发生。</span><span class="sxs-lookup"><span data-stu-id="331fe-111">The reasoning behind this is that many bugs occur because objects are in a state they should never have been in.</span></span> <span data-ttu-id="331fe-112">下面是来自 Greg Young 在[联机讨论](https://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/)中的很好的解释：</span><span class="sxs-lookup"><span data-stu-id="331fe-112">The following is a good explanation from Greg Young in an [online discussion](https://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span></span>

<span data-ttu-id="331fe-113">比如说，我们现在有一个采用 UserProfile 的 SendUserCreationEmailService...我们可以如何理性解释该服务中其名称不为 null？</span><span class="sxs-lookup"><span data-stu-id="331fe-113">Let's propose we now have a SendUserCreationEmailService that takes a UserProfile ... how can we rationalize in that service that Name is not null?</span></span> <span data-ttu-id="331fe-114">是不是要再次检查？</span><span class="sxs-lookup"><span data-stu-id="331fe-114">Do we check it again?</span></span> <span data-ttu-id="331fe-115">或者更有可能...不需要花精力检查而是“期待更好的发生”- 希望其他人在将其发送给你之前花时间进行了验证。</span><span class="sxs-lookup"><span data-stu-id="331fe-115">Or more likely ... you just don't bother to check and "hope for the best"—you hope that someone bothered to validate it before sending it to you.</span></span> <span data-ttu-id="331fe-116">当然，使用 TDD 时，我们首先应该编写的一个测试是，我是否向客户发送了会引发错误的 null 名称。</span><span class="sxs-lookup"><span data-stu-id="331fe-116">Of course, using TDD one of the first tests we should be writing is that if I send a customer with a null name that it should raise an error.</span></span> <span data-ttu-id="331fe-117">但是，一旦我们开始反复编写这些类型的测试，我们认识到...“等一下，如果我们从不允许名称成为 null，我们就不会有所有这些测试”</span><span class="sxs-lookup"><span data-stu-id="331fe-117">But once we start writing these kinds of tests over and over again we realize ... "wait if we never allowed name to become null we wouldn't have all of these tests"</span></span>

## <a name="implementing-validations-in-the-domain-model-layer"></a><span data-ttu-id="331fe-118">在域模型层中实现验证</span><span class="sxs-lookup"><span data-stu-id="331fe-118">Implementing validations in the domain model layer</span></span>

<span data-ttu-id="331fe-119">验证通常在域实体构造函数或可以更改该实体的方法中实现。</span><span class="sxs-lookup"><span data-stu-id="331fe-119">Validations are usually implemented in domain entity constructors or in methods that can update the entity.</span></span> <span data-ttu-id="331fe-120">有多种方法来实现验证，例如验证失败时验证数据和引发的异常。</span><span class="sxs-lookup"><span data-stu-id="331fe-120">There are multiple ways to implement validations, such as verifying data and raising exceptions if the validation fails.</span></span> <span data-ttu-id="331fe-121">还有更多高级的模式，例如使用验证的规范模式和通知模式来返回一系列错误，而不是在异常发生时返回每个验证的异常。</span><span class="sxs-lookup"><span data-stu-id="331fe-121">There are also more advanced patterns such as using the Specification pattern for validations, and the Notification pattern to return a collection of errors instead of returning an exception for each validation as it occurs.</span></span>

### <a name="validating-conditions-and-throwing-exceptions"></a><span data-ttu-id="331fe-122">验证条件和引发异常</span><span class="sxs-lookup"><span data-stu-id="331fe-122">Validating conditions and throwing exceptions</span></span>

<span data-ttu-id="331fe-123">下面的代码示例通过引发异常显示域实体中最简单的验证方法。</span><span class="sxs-lookup"><span data-stu-id="331fe-123">The following code example shows the simplest approach to validation in a domain entity by raising an exception.</span></span> <span data-ttu-id="331fe-124">在本部分末尾的引用表中，可以看到指向基于之前讨论的模式的更多高级实现。</span><span class="sxs-lookup"><span data-stu-id="331fe-124">In the references table at the end of this section you can see links to more advanced implementations based on the patterns we have discussed previously.</span></span>

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

<span data-ttu-id="331fe-125">更好的示例将演示，需要确保内部状态未更改，或者方法的所有变化都已发生。</span><span class="sxs-lookup"><span data-stu-id="331fe-125">A better example would demonstrate the need to ensure that either the internal state did not change, or that all the mutations for a method occurred.</span></span> <span data-ttu-id="331fe-126">例如，下面的实现将使对象保持处于无效状态：</span><span class="sxs-lookup"><span data-stu-id="331fe-126">For example, the following implementation would leave the object in an invalid state:</span></span>

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

<span data-ttu-id="331fe-127">如果状态的值无效，则第一个地址行和城市已更改。</span><span class="sxs-lookup"><span data-stu-id="331fe-127">If the value of the state is invalid, the first address line and the city have already been changed.</span></span> <span data-ttu-id="331fe-128">这可能使地址无效。</span><span class="sxs-lookup"><span data-stu-id="331fe-128">That might make the address invalid.</span></span>

<span data-ttu-id="331fe-129">类似的方法可用于实体的构造函数中，引发异常来确保实体在创建后是有效的。</span><span class="sxs-lookup"><span data-stu-id="331fe-129">A similar approach can be used in the entity’s constructor, raising an exception to make sure that the entity is valid once it is created.</span></span>

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a><span data-ttu-id="331fe-130">在基于数据注释的模型中使用验证属性</span><span class="sxs-lookup"><span data-stu-id="331fe-130">Using validation attributes in the model based on data annotations</span></span>

<span data-ttu-id="331fe-131">另一种方法是使用基于数据注释的验证属性。</span><span class="sxs-lookup"><span data-stu-id="331fe-131">Another approach is to use validation attributes based on data annotations.</span></span> <span data-ttu-id="331fe-132">验证属性用于配置模型验证，在概念上类似于数据库表中字段上的验证。</span><span class="sxs-lookup"><span data-stu-id="331fe-132">Validation attributes provide a way to configure model validation, which is similar conceptually to validation on fields in database tables.</span></span> <span data-ttu-id="331fe-133">它包括诸如分配数据类型或必填字段之类的约束。</span><span class="sxs-lookup"><span data-stu-id="331fe-133">This includes constraints such as assigning data types or required fields.</span></span> <span data-ttu-id="331fe-134">其他类型的验证包括向数据应用模式以强制实施业务规则，比如信用卡号、电话号码或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="331fe-134">Other types of validation include applying patterns to data to enforce business rules, such as a credit card number, phone number, or email address.</span></span> <span data-ttu-id="331fe-135">验证属性使执行要求变得简单。</span><span class="sxs-lookup"><span data-stu-id="331fe-135">Validation attributes make it easy to enforce requirements.</span></span>

<span data-ttu-id="331fe-136">但是，如以下代码所示，此方法在 DDD 模型中可能太具侵入性，因为它依赖 Microsoft.AspNetCore.Mvc.ModelState 的 ModelState.IsValid，Microsoft.AspNetCore.Mvc.ModelState 必须从 MVC 控制器调用。</span><span class="sxs-lookup"><span data-stu-id="331fe-136">However, as shown in the following code, this approach might be too intrusive in a DDD model, because it takes a dependency on ModelState.IsValid from Microsoft.AspNetCore.Mvc.ModelState, which you must call from your MVC controllers.</span></span> <span data-ttu-id="331fe-137">在调用每个控制器操作之前都会执行模型验证，并且控制器方法负责检查调用 ModelState.IsValid 的结果并作出正确反应。</span><span class="sxs-lookup"><span data-stu-id="331fe-137">The model validation occurs prior to each controller action being invoked, and it is the controller method’s responsibility to inspect the result of calling ModelState.IsValid and react appropriately.</span></span> <span data-ttu-id="331fe-138">要不要使用它取决于你希望模型与该基础结构的耦合紧密程度。</span><span class="sxs-lookup"><span data-stu-id="331fe-138">The decision to use it depends on how tightly coupled you want the model to be with that infrastructure.</span></span>

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

<span data-ttu-id="331fe-139">但是，从 DDD 的角度来看，最好通过在实体行为方法中使用异常，或者通过实现规范和通知模式来执行验证规则，从而使域模型保持精简。</span><span class="sxs-lookup"><span data-stu-id="331fe-139">However, from a DDD point of view, the domain model is best kept lean with the use of exceptions in your entity’s behavior methods, or by implementing the Specification and Notification patterns to enforce validation rules.</span></span> <span data-ttu-id="331fe-140">ASP.NET Core 中的数据注释等验证框架或者 FluentValidation 等任何其他验证框架带有要求来调用应用程序框架。</span><span class="sxs-lookup"><span data-stu-id="331fe-140">Validation frameworks like data annotations in ASP.NET Core or any other validation frameworks like FluentValidation carry a requirement to invoke the application framework.</span></span> <span data-ttu-id="331fe-141">例如，当在数据注释中调用 ModelState.IsValid 时，需要调用 ASP.NET 控制器。</span><span class="sxs-lookup"><span data-stu-id="331fe-141">For example, when calling the ModelState.IsValid method in data annotations, you need to invoke ASP.NET controllers.</span></span>

<span data-ttu-id="331fe-142">在将接受输入的 ViewModel 类（而非域实体）中在应用程序层上使用数据注释来允许 UI 层中的模型验证很有意义。</span><span class="sxs-lookup"><span data-stu-id="331fe-142">It can make sense to use data annotations at the application layer in ViewModel classes (instead of domain entities) that will accept input, to allow for model validation within the UI layer.</span></span> <span data-ttu-id="331fe-143">但是，这不应在域模型内排除验证时完成。</span><span class="sxs-lookup"><span data-stu-id="331fe-143">However, this should not be done at the exclusion of validation within the domain model.</span></span>

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a><span data-ttu-id="331fe-144">通过实现规范模式和通知模式来验证实体</span><span class="sxs-lookup"><span data-stu-id="331fe-144">Validating entities by implementing the Specification pattern and the Notification pattern</span></span>

<span data-ttu-id="331fe-145">最后，域模型中实现验证的更复杂方法是，通过结合使用通知模式来实现规范模式，如后面列出的其他资源中所述。</span><span class="sxs-lookup"><span data-stu-id="331fe-145">Finally, a more elaborate approach to implementing validations in the domain model is by implementing the Specification pattern in conjunction with the Notification pattern, as explained in some of the additional resources listed later.</span></span>

<span data-ttu-id="331fe-146">值得一提的是，还可使用这些模式中一个 - 例如通过控制语句进行手动验证，但使用通知模式来堆叠并返回验证错误列表。</span><span class="sxs-lookup"><span data-stu-id="331fe-146">It is worth mentioning that you can also use just one of those patterns—for example, validating manually with control statements, but using the Notification pattern to stack and return a list of validation errors.</span></span>

### <a name="using-deferred-validation-in-the-domain"></a><span data-ttu-id="331fe-147">在域中使用延迟的验证</span><span class="sxs-lookup"><span data-stu-id="331fe-147">Using deferred validation in the domain</span></span>

<span data-ttu-id="331fe-148">有数种方法来处理域中的延迟验证。</span><span class="sxs-lookup"><span data-stu-id="331fe-148">There are various approaches to deal with deferred validations in the domain.</span></span> <span data-ttu-id="331fe-149">[实现域驱动设计](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577)一书中，Vaughn Vernon 在验证部分讨论了这些。</span><span class="sxs-lookup"><span data-stu-id="331fe-149">In his book [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon discusses these in the section on validation.</span></span>

### <a name="two-step-validation"></a><span data-ttu-id="331fe-150">双重验证</span><span class="sxs-lookup"><span data-stu-id="331fe-150">Two-step validation</span></span>

<span data-ttu-id="331fe-151">此外考虑双重验证。</span><span class="sxs-lookup"><span data-stu-id="331fe-151">Also consider two-step validation.</span></span> <span data-ttu-id="331fe-152">在命令数据传输对象 (DTO) 上使用字段级别验证，在实体内使用域级别验证。</span><span class="sxs-lookup"><span data-stu-id="331fe-152">Use field-level validation on your command Data Transfer Objects (DTOs) and domain-level validation inside your entities.</span></span> <span data-ttu-id="331fe-153">通过返回结果对象而非异常以使其更易于处理验证错误，可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="331fe-153">You can do this by returning a result object instead exceptions in order to make it easier to deal with the validation errors.</span></span>

<span data-ttu-id="331fe-154">例如通过将字段验证用于数据注释，你不用重复验证定义。</span><span class="sxs-lookup"><span data-stu-id="331fe-154">Using field validation with data annotations, for example, you do not duplicate the validation definition.</span></span> <span data-ttu-id="331fe-155">然而在 DTO（例如命令和 Viewmodel）的情况下，执行可以既位于服务器端又位于客户端端。</span><span class="sxs-lookup"><span data-stu-id="331fe-155">The execution, though, can be both server-side and client-side in the case of DTOs (commands and ViewModels, for instance).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="331fe-156">其他资源</span><span class="sxs-lookup"><span data-stu-id="331fe-156">Additional resources</span></span>

-   <span data-ttu-id="331fe-157">**Rachel Appel。ASP.NET Core MVC 模型验证简介**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span><span class="sxs-lookup"><span data-stu-id="331fe-157">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC**
[*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span></span>

-   <span data-ttu-id="331fe-158">**Rick Anderson。添加验证**
    [https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="331fe-158">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

-   <span data-ttu-id="331fe-159">**Martin Fowler。在验证中将引发异常替换为通知**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span><span class="sxs-lookup"><span data-stu-id="331fe-159">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations**
[*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span></span>

-   <span data-ttu-id="331fe-160">**规范和通知模式**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span><span class="sxs-lookup"><span data-stu-id="331fe-160">**Specification and Notification Patterns**
[*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span></span>

-   <span data-ttu-id="331fe-161">**Lev Gorodinski.域驱动设计 (DDD) 中的验证**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span><span class="sxs-lookup"><span data-stu-id="331fe-161">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)**
[*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span></span>

-   <span data-ttu-id="331fe-162">**Colin Jack。域模型验证**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span><span class="sxs-lookup"><span data-stu-id="331fe-162">**Colin Jack. Domain Model Validation**
[*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span></span>

-   <span data-ttu-id="331fe-163">**Jimmy Bogard。DDD 中的验证**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span><span class="sxs-lookup"><span data-stu-id="331fe-163">**Jimmy Bogard. Validation in a DDD world**
[*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="331fe-164">[上一页](enumeration-classes-over-enum-types.md)
[下一页](client-side-validation.md)</span><span class="sxs-lookup"><span data-stu-id="331fe-164">[Previous](enumeration-classes-over-enum-types.md)
[Next](client-side-validation.md)</span></span>
