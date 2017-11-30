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
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="bf326-104">客户端验证 （验证在表示层）</span><span class="sxs-lookup"><span data-stu-id="bf326-104">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="bf326-105">即使真实源是域的模型，最终你必须在域模型级别可以验证，验证仍可在域模型级别 （服务器端） 和客户端处理。</span><span class="sxs-lookup"><span data-stu-id="bf326-105">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the client side.</span></span>

<span data-ttu-id="bf326-106">客户端验证是一个重大便利的用户。</span><span class="sxs-lookup"><span data-stu-id="bf326-106">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="bf326-107">它将保存它们需要花费时间的时间等待往返行程到的服务器，可能会返回验证错误。</span><span class="sxs-lookup"><span data-stu-id="bf326-107">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="bf326-108">在业务术语中，甚至几秒的乘积数百次每一天的秒的小数部分累加到大量的时间、 费用，并减少失败。</span><span class="sxs-lookup"><span data-stu-id="bf326-108">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="bf326-109">简单和快速验证使用户能够更有效地工作，并生成更好的质量输入和输出。</span><span class="sxs-lookup"><span data-stu-id="bf326-109">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="bf326-110">正如一样视图模型和域模型不同，视图模型验证和域模型验证可能已类似，但具有不同的用途。</span><span class="sxs-lookup"><span data-stu-id="bf326-110">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="bf326-111">如果您担心有关干 （不重复自己原则），请考虑在此情况下代码重用可能还表示耦合，而且，企业应用程序在很多重要，不以将服务器端与客户端比要遵循干原则。</span><span class="sxs-lookup"><span data-stu-id="bf326-111">If you are concerned about DRY (the Don’t Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="bf326-112">即使在使用客户端验证时，应始终验证你的命令，或在服务器代码中，输入 Dto，因为服务器 Api 使用可能的攻击矢量。</span><span class="sxs-lookup"><span data-stu-id="bf326-112">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="bf326-113">因为如果你有一个客户端应用程序，从用户体验的角度，则最好主动和不允许用户输入无效的信息，执行操作都是通常情况下，最佳选择。</span><span class="sxs-lookup"><span data-stu-id="bf326-113">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="bf326-114">因此，在客户端代码中你通常验证 Viewmodel。</span><span class="sxs-lookup"><span data-stu-id="bf326-114">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="bf326-115">你还可以验证客户端输出 Dto 或命令之前将其发送给服务。</span><span class="sxs-lookup"><span data-stu-id="bf326-115">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="bf326-116">客户端验证的实现依赖于要生成哪种客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf326-116">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="bf326-117">如果您要验证 web MVC web 应用程序中的数据与在.NET 中，验证正在编码在 JavaScript 或 TypeScript 中的 SPA web 应用程序代码的大部分将不同或移动应用程序编码使用 Xamarin 和 C\#。</span><span class="sxs-lookup"><span data-stu-id="bf326-117">It will be different if you are validating data in a web MVC web application with most of the code in .NET, an SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C\#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bf326-118">其他资源</span><span class="sxs-lookup"><span data-stu-id="bf326-118">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="bf326-119">验证 Xamarin 移动应用程序</span><span class="sxs-lookup"><span data-stu-id="bf326-119">Validation in Xamarin mobile apps</span></span>

-   <span data-ttu-id="bf326-120">**验证文本输入和显示的错误**
    [*https://developer.xamarin.com/recipes/ios/standard\_控件/文本\_字段/验证\_输入 /*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span><span class="sxs-lookup"><span data-stu-id="bf326-120">**Validate Text Input and Show Errors**
[*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span></span>

-   <span data-ttu-id="bf326-121">**验证回调**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span><span class="sxs-lookup"><span data-stu-id="bf326-121">**Validation Callback**
[*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span></span>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="bf326-122">ASP.NET Core 应用中的验证</span><span class="sxs-lookup"><span data-stu-id="bf326-122">Validation in ASP.NET Core apps</span></span>

-   <span data-ttu-id="bf326-123">**Rick Anderson。添加验证**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="bf326-123">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="bf326-124">SPA 中的验证 Web 应用 (角度 2，TypeScript，JavaScript)</span><span class="sxs-lookup"><span data-stu-id="bf326-124">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

-   <span data-ttu-id="bf326-125">**Ado Kukic。角度 2 形成验证** **
     ** [ *https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span><span class="sxs-lookup"><span data-stu-id="bf326-125">**Ado Kukic. Angular 2 Form Validation** **
**[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span></span>

-   <span data-ttu-id="bf326-126">**窗体验证**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span><span class="sxs-lookup"><span data-stu-id="bf326-126">**Form Validation**
[*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span></span>

-   <span data-ttu-id="bf326-127">**验证。**</span><span class="sxs-lookup"><span data-stu-id="bf326-127">**Validation.**</span></span> <span data-ttu-id="bf326-128">轻松文档。</span><span class="sxs-lookup"><span data-stu-id="bf326-128">Breeze documentation.</span></span>
    [<span data-ttu-id="bf326-129">*http://breeze.github.io/doc-js/validation.html*</span><span class="sxs-lookup"><span data-stu-id="bf326-129">*http://breeze.github.io/doc-js/validation.html*</span></span>](http://breeze.github.io/doc-js/validation.html)

<span data-ttu-id="bf326-130">总之，这些是关于验证的最重要概念：</span><span class="sxs-lookup"><span data-stu-id="bf326-130">In summary, these are the most important concepts in regards to validation:</span></span>

-   <span data-ttu-id="bf326-131">实体和聚合应强制执行其自己的一致性，并将"始终有效"。</span><span class="sxs-lookup"><span data-stu-id="bf326-131">Entities and aggregates should enforce their own consistency and be "always valid”.</span></span> <span data-ttu-id="bf326-132">聚合根负责在相同的聚合内的多实体一致性。</span><span class="sxs-lookup"><span data-stu-id="bf326-132">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

-   <span data-ttu-id="bf326-133">如果您认为实体需要进入无效状态，请考虑使用不同的对象模型 — 例如，使用临时 DTO，直至你创建的最后一个域实体。</span><span class="sxs-lookup"><span data-stu-id="bf326-133">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

-   <span data-ttu-id="bf326-134">如果你需要创建多个相关的对象，例如聚合时，所有这些创建后，它们是仅有效，请考虑使用工厂模式。</span><span class="sxs-lookup"><span data-stu-id="bf326-134">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

-   <span data-ttu-id="bf326-135">验证框架最适用中特定层，例如表示层或应用程序/服务层中，但通常不在域模型层，因为你将需要的基础结构框架对其执行的强依赖项。</span><span class="sxs-lookup"><span data-stu-id="bf326-135">Validation frameworks are best used in specific layers, such as the presentation layer or the application/service layer, but usually not in the domain model layer, because you would need to take a strong dependency on an infrastructure framework.</span></span>

-   <span data-ttu-id="bf326-136">在大多数情况下，客户端中采用冗余验证很好的因为应用程序可以是主动。</span><span class="sxs-lookup"><span data-stu-id="bf326-136">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="bf326-137">[以前](域-模型-层-validations.md) [下一步] (域的事件的设计-implementation.md)</span><span class="sxs-lookup"><span data-stu-id="bf326-137">[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)</span></span>
