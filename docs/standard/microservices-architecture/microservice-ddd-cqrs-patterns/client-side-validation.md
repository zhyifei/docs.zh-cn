---
title: 客户端验证（表示层中的验证）
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 客户端验证（表示层中的验证）
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 2adce39561dd2b97910155ebed595a2df7785c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="19c30-103">客户端验证（表示层中的验证）</span><span class="sxs-lookup"><span data-stu-id="19c30-103">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="19c30-104">即使真实源是域模型，最终也必须在域模型级别进行验证，验证仍然可以在域模型级别（服务器端）和客户端处理。</span><span class="sxs-lookup"><span data-stu-id="19c30-104">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the client side.</span></span>

<span data-ttu-id="19c30-105">客户端验证极大地方便了用户。</span><span class="sxs-lookup"><span data-stu-id="19c30-105">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="19c30-106">它节省了时间，让用户不必浪费时间等待服务器往返，服务器有可能返回验证错误。</span><span class="sxs-lookup"><span data-stu-id="19c30-106">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="19c30-107">从商业角度而言，即使每次只有几分之一秒，但如果每天发生几百次，也会耗费大量的时间和成本，带来很多不必要的烦恼。</span><span class="sxs-lookup"><span data-stu-id="19c30-107">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="19c30-108">简单直接的验证能够提高用户的工作效率和投入产出比。</span><span class="sxs-lookup"><span data-stu-id="19c30-108">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="19c30-109">正是因为视图模型和域模型有所不同，所以即使视图模型验证和域模型验证可能相似，也不可能用于相同目的。</span><span class="sxs-lookup"><span data-stu-id="19c30-109">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="19c30-110">如果担心 DRY（不要自我重复原则），请想想在这种情况下代码重用也可能意味着耦合，而在企业应用程序中，比起遵循 DRY 原则，不要将服务器端耦合到客户端更为重要。</span><span class="sxs-lookup"><span data-stu-id="19c30-110">If you are concerned about DRY (the Don’t Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="19c30-111">即使是使用客户端验证时，也应一直验证命令或在服务器代码中输入 DTO，因为服务器 API 可能是攻击途径。</span><span class="sxs-lookup"><span data-stu-id="19c30-111">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="19c30-112">通常情况下，最好是两项操作都进行，因为从 UX 角度，如果具有一个客户端应用程序，最好要有远见并禁止用户输入无效信息。</span><span class="sxs-lookup"><span data-stu-id="19c30-112">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="19c30-113">因此，通常要在客户端代码中验证 ViewModel。</span><span class="sxs-lookup"><span data-stu-id="19c30-113">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="19c30-114">将客户端输出的 DTO 或命令发送到服务之前，还可以对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="19c30-114">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="19c30-115">客户端验证实现取决于创建的客户端应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="19c30-115">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="19c30-116">如果使用 .NET 中的大多数代码验证 Web MVC Web 应用程序中的数据，情况便有所不同，使用该验证的 SPA Web 应用程序会在 JavaScript、TypeScript 或移动应用（编有代码 Xamarin 和 C\#）中进行编码。</span><span class="sxs-lookup"><span data-stu-id="19c30-116">It will be different if you are validating data in a web MVC web application with most of the code in .NET, an SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C\#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="19c30-117">其他资源</span><span class="sxs-lookup"><span data-stu-id="19c30-117">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="19c30-118">Xamarin 移动应用中进行的验证</span><span class="sxs-lookup"><span data-stu-id="19c30-118">Validation in Xamarin mobile apps</span></span>

-   <span data-ttu-id="19c30-119">**Validate Text Input and Show Errors**（验证文本输入并显示错误）
    [https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span><span class="sxs-lookup"><span data-stu-id="19c30-119">**Validate Text Input and Show Errors**
[*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span></span>

-   <span data-ttu-id="19c30-120">**Validation Callback**
    （验证回调）[https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span><span class="sxs-lookup"><span data-stu-id="19c30-120">**Validation Callback**
[*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span></span>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="19c30-121">ASP.NET Core 应用中进行的验证</span><span class="sxs-lookup"><span data-stu-id="19c30-121">Validation in ASP.NET Core apps</span></span>

-   <span data-ttu-id="19c30-122">**Rick Anderson。添加验证**
    [https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="19c30-122">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="19c30-123">SPA Web 应用中进行的验证（Angular 2、TypeScript、JavaScript）</span><span class="sxs-lookup"><span data-stu-id="19c30-123">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

-   <span data-ttu-id="19c30-124">**Ado Kukic.Angular 2 Form Validation**（Angular 2 窗体验证）**
    **[https://scotch.io/tutorials/angular-2-form-validation](https://scotch.io/tutorials/angular-2-form-validation)**</span><span class="sxs-lookup"><span data-stu-id="19c30-124">**Ado Kukic. Angular 2 Form Validation** **
**[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span></span>

-   <span data-ttu-id="19c30-125">**Form Validation**
    （窗体验证）[https://angular.io/docs/ts/latest/cookbook/form-validation.html](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span><span class="sxs-lookup"><span data-stu-id="19c30-125">**Form Validation**
[*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span></span>

-   <span data-ttu-id="19c30-126">**验证。**</span><span class="sxs-lookup"><span data-stu-id="19c30-126">**Validation.**</span></span> <span data-ttu-id="19c30-127">Breeze 文档。</span><span class="sxs-lookup"><span data-stu-id="19c30-127">Breeze documentation.</span></span>
    [*https://breeze.github.io/doc-js/validation.html*](https://breeze.github.io/doc-js/validation.html)

<span data-ttu-id="19c30-128">总之，与验证有关的最重要的概念有以下几条：</span><span class="sxs-lookup"><span data-stu-id="19c30-128">In summary, these are the most important concepts in regards to validation:</span></span>

-   <span data-ttu-id="19c30-129">实体和聚合应确保它们自己的一致性，并保证“始终有效”。</span><span class="sxs-lookup"><span data-stu-id="19c30-129">Entities and aggregates should enforce their own consistency and be "always valid”.</span></span> <span data-ttu-id="19c30-130">聚合根保证同一聚合内的多实体间的一致性。</span><span class="sxs-lookup"><span data-stu-id="19c30-130">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

-   <span data-ttu-id="19c30-131">如果认为实体需要进入无效状态，请考虑使用不同的对象模型 - 例如，在创建最终的域实体之前，使用临时 DTO。</span><span class="sxs-lookup"><span data-stu-id="19c30-131">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

-   <span data-ttu-id="19c30-132">如果需要创建多个相关对象（如聚合），且其只有在完成创建所有对象之后才会有效，请考虑使用工厂模式。</span><span class="sxs-lookup"><span data-stu-id="19c30-132">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

-   <span data-ttu-id="19c30-133">验证框架最适合用于特定层，如表示层或应用程序/服务层，但通常不用于域模型层，因为这需要在基础结构框架有一个强大的依赖项。</span><span class="sxs-lookup"><span data-stu-id="19c30-133">Validation frameworks are best used in specific layers, such as the presentation layer or the application/service layer, but usually not in the domain model layer, because you would need to take a strong dependency on an infrastructure framework.</span></span>

-   <span data-ttu-id="19c30-134">在大多数情况下，客户端采用冗余验证是不错的选择，因为应用程序可以是积极主动的。</span><span class="sxs-lookup"><span data-stu-id="19c30-134">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="19c30-135">[上一篇] (domain-model-layer-validations.md) [下一篇] (domain-events-design-implementation.md)</span><span class="sxs-lookup"><span data-stu-id="19c30-135">[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)</span></span>
