---
title: "设计微服务应用程序层和 Web API"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |设计微服务应用程序层和 Web API"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7509b470a30005dd48fa88eefa91f7ed241e4e09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="41a7a-104">设计微服务应用程序层和 Web API</span><span class="sxs-lookup"><span data-stu-id="41a7a-104">Designing the microservice application layer and Web API</span></span>

## <a name="using-solid-principles-and-dependency-injection"></a><span data-ttu-id="41a7a-105">使用稳定的原则和依赖关系注入</span><span class="sxs-lookup"><span data-stu-id="41a7a-105">Using SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="41a7a-106">稳定的原则是用于任何现代和任务关键型应用程序，例如开发使用 DDD 模式 microservice 的关键技术。</span><span class="sxs-lookup"><span data-stu-id="41a7a-106">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="41a7a-107">实体是缩写该组五个基本原则：</span><span class="sxs-lookup"><span data-stu-id="41a7a-107">SOLID is an acronym that groups five fundamental principles:</span></span>

-   <span data-ttu-id="41a7a-108">单个责任原则</span><span class="sxs-lookup"><span data-stu-id="41a7a-108">Single Responsibility principle</span></span>

-   <span data-ttu-id="41a7a-109">打开/关闭原则</span><span class="sxs-lookup"><span data-stu-id="41a7a-109">Open/closed principle</span></span>

-   <span data-ttu-id="41a7a-110">Liskov 替换原则</span><span class="sxs-lookup"><span data-stu-id="41a7a-110">Liskov substitution principle</span></span>

-   <span data-ttu-id="41a7a-111">反转分隔原则</span><span class="sxs-lookup"><span data-stu-id="41a7a-111">Inversion Segregation principle</span></span>

-   <span data-ttu-id="41a7a-112">依赖项反向原则</span><span class="sxs-lookup"><span data-stu-id="41a7a-112">Dependency Inversion principle</span></span>

<span data-ttu-id="41a7a-113">实体是更多有关如何设计你的应用程序或 microservice 内部层以及分离它们之间的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="41a7a-113">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="41a7a-114">它不与加入域，但应用程序的技术设计。</span><span class="sxs-lookup"><span data-stu-id="41a7a-114">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="41a7a-115">最终的原则，依赖项反向 (DI) 原则，允许你分离的其他层，它允许的更好地分离的 DDD 层实现的基础结构层。</span><span class="sxs-lookup"><span data-stu-id="41a7a-115">The final principle, the Dependency Inversion (DI) principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="41a7a-116">DI 是一种方法实现的依赖项反向原则。</span><span class="sxs-lookup"><span data-stu-id="41a7a-116">DI is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="41a7a-117">它是一种，这些技术可以实现对象和其依赖项之间的松散耦合。</span><span class="sxs-lookup"><span data-stu-id="41a7a-117">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="41a7a-118">而不是直接实例化协作者，或使用的静态引用，需要一个类，以便执行其操作的对象是提供给 （或"注入"） 的类。</span><span class="sxs-lookup"><span data-stu-id="41a7a-118">Rather than directly instantiating collaborators, or using static references, the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="41a7a-119">大多数情况下，类将声明通过其构造函数，从而使它们可以遵循显式依赖关系原则及其依赖项。</span><span class="sxs-lookup"><span data-stu-id="41a7a-119">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="41a7a-120">DI 通常基于特定控制反向 (IoC) 容器。</span><span class="sxs-lookup"><span data-stu-id="41a7a-120">DI is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="41a7a-121">ASP.NET Core 提供简单的内置 IoC 容器中，但你也可以使用你最喜欢的 IoC 容器，如 Autofac 或 Ninject。</span><span class="sxs-lookup"><span data-stu-id="41a7a-121">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="41a7a-122">按照稳定的原则，你的类将自然往往会很小，分解，且轻松地测试。</span><span class="sxs-lookup"><span data-stu-id="41a7a-122">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="41a7a-123">但你如何知道是否正在过多的依赖关系注入到你的类？</span><span class="sxs-lookup"><span data-stu-id="41a7a-123">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="41a7a-124">如果通过构造函数使用 DI，它将轻松地检测通过只查看您的构造函数的参数的数目。</span><span class="sxs-lookup"><span data-stu-id="41a7a-124">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="41a7a-125">如果有依赖项太多，这通常是一个符号 ([代码告知](http://deviq.com/code-smells/)) 您的类尝试执行的操作过多，而且可能违反单独责任原则。</span><span class="sxs-lookup"><span data-stu-id="41a7a-125">If there are too many dependencies, this is generally a sign (a [code smell](http://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="41a7a-126">它将需要另一个指南详细介绍实线。</span><span class="sxs-lookup"><span data-stu-id="41a7a-126">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="41a7a-127">因此，本指南还要求你能够仅这些主题的最少知识。</span><span class="sxs-lookup"><span data-stu-id="41a7a-127">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="41a7a-128">其他资源</span><span class="sxs-lookup"><span data-stu-id="41a7a-128">Additional resources</span></span>

-   <span data-ttu-id="41a7a-129">**实线： 基本 OOP 原则**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span><span class="sxs-lookup"><span data-stu-id="41a7a-129">**SOLID: Fundamental OOP Principles**
[*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span></span>

-   <span data-ttu-id="41a7a-130">**反向的控件容器和依赖关系注入模式**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span><span class="sxs-lookup"><span data-stu-id="41a7a-130">**Inversion of Control Containers and the Dependency Injection pattern**
[*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span></span>

-   <span data-ttu-id="41a7a-131">**Steve Smith。新是粘附**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span><span class="sxs-lookup"><span data-stu-id="41a7a-131">**Steve Smith. New is Glue**
[*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="41a7a-132">[以前](nosql-数据库-持久性-infrastructure.md) [下一步] (microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="41a7a-132">[Previous] (nosql-database-persistence-infrastructure.md) [Next] (microservice-application-layer-implementation-web-api.md)</span></span>
