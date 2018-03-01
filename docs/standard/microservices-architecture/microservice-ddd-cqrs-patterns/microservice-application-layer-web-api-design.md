---
title: "设计微服务应用层和 Web API"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 设计微服务应用层和 Web API"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c166e0286d0769e24a6361037eb6c4694fb821ae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="5e80f-104">设计微服务应用层和 Web API</span><span class="sxs-lookup"><span data-stu-id="5e80f-104">Designing the microservice application layer and Web API</span></span>

## <a name="using-solid-principles-and-dependency-injection"></a><span data-ttu-id="5e80f-105">使用 SOLID 原则和依赖关系注入</span><span class="sxs-lookup"><span data-stu-id="5e80f-105">Using SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="5e80f-106">SOLID 原则是应用于所有新式任务关键型应用的重要技术，例如使用 DDD 模式开发微服务。</span><span class="sxs-lookup"><span data-stu-id="5e80f-106">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="5e80f-107">SOLID 是五个基本原则的缩写，它们分别是：</span><span class="sxs-lookup"><span data-stu-id="5e80f-107">SOLID is an acronym that groups five fundamental principles:</span></span>

-   <span data-ttu-id="5e80f-108">单一责任原则</span><span class="sxs-lookup"><span data-stu-id="5e80f-108">Single Responsibility principle</span></span>

-   <span data-ttu-id="5e80f-109">开闭原则</span><span class="sxs-lookup"><span data-stu-id="5e80f-109">Open/closed principle</span></span>

-   <span data-ttu-id="5e80f-110">Liskov 替换原则</span><span class="sxs-lookup"><span data-stu-id="5e80f-110">Liskov substitution principle</span></span>

-   <span data-ttu-id="5e80f-111">反转分离原则</span><span class="sxs-lookup"><span data-stu-id="5e80f-111">Inversion Segregation principle</span></span>

-   <span data-ttu-id="5e80f-112">依赖关系反转原则</span><span class="sxs-lookup"><span data-stu-id="5e80f-112">Dependency Inversion principle</span></span>

<span data-ttu-id="5e80f-113">SOLID 不仅仅是关于如何设计应用程序或微服务内部层以及如何分离它们之间的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="5e80f-113">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="5e80f-114">它与域无关，而与应用程序的技术设计相关。</span><span class="sxs-lookup"><span data-stu-id="5e80f-114">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="5e80f-115">最后一个原则，依赖关系反转 (DI) 原则，让使用者能够将基础结构层从其余层中分离出来，这样便能够更好地分离 DDD 层的实现。</span><span class="sxs-lookup"><span data-stu-id="5e80f-115">The final principle, the Dependency Inversion (DI) principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="5e80f-116">DI 是实现依赖关系反转原则的一种方法。</span><span class="sxs-lookup"><span data-stu-id="5e80f-116">DI is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="5e80f-117">它是一种用于在对象与其依赖项之间实现松散耦合的技术。</span><span class="sxs-lookup"><span data-stu-id="5e80f-117">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="5e80f-118">该技术不是直接实例化协作者或使用静态引用，而是向类提供（或“注入”）该类执行其操作所需的对象。</span><span class="sxs-lookup"><span data-stu-id="5e80f-118">Rather than directly instantiating collaborators, or using static references, the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="5e80f-119">大多数情况下，类通过其构造函数声明它们的依赖项，从而允许它们遵循显式依赖关系原则。</span><span class="sxs-lookup"><span data-stu-id="5e80f-119">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="5e80f-120">DI 通常基于特定的控制反向 (IoC) 容器。</span><span class="sxs-lookup"><span data-stu-id="5e80f-120">DI is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="5e80f-121">ASP.NET Core 提供简单的内置 IoC 容器，但也可以使用其他 IoC 容器，如 Autofac 或 Ninject。</span><span class="sxs-lookup"><span data-stu-id="5e80f-121">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="5e80f-122">使用 SOLID 原则，往往会获得构造良好和易于测试的小型类。</span><span class="sxs-lookup"><span data-stu-id="5e80f-122">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="5e80f-123">但如何知道注入类的依赖关系是否将过多？</span><span class="sxs-lookup"><span data-stu-id="5e80f-123">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="5e80f-124">如果通过构造函数使用 DI，只需通过查看构造函数的参数数目便可轻松检测依赖关系的数量。</span><span class="sxs-lookup"><span data-stu-id="5e80f-124">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="5e80f-125">如果依赖关系过多，通常表明类需要做的工作太多（[代码异味](http://deviq.com/code-smells/)），而且可能违反了单一责任原则。</span><span class="sxs-lookup"><span data-stu-id="5e80f-125">If there are too many dependencies, this is generally a sign (a [code smell](http://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="5e80f-126">如果要深入了解 SOLID，需要参阅另一相关指南。</span><span class="sxs-lookup"><span data-stu-id="5e80f-126">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="5e80f-127">因此，本指南仅要求读者掌握有关这些主题的最基本的知识。</span><span class="sxs-lookup"><span data-stu-id="5e80f-127">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="5e80f-128">其他资源</span><span class="sxs-lookup"><span data-stu-id="5e80f-128">Additional resources</span></span>

-   <span data-ttu-id="5e80f-129">**SOLID: Fundamental OOP Principles**（SOLID：基本 OOP 原则）
    [http://deviq.com/solid/](http://deviq.com/solid/%20)</span><span class="sxs-lookup"><span data-stu-id="5e80f-129">**SOLID: Fundamental OOP Principles**
[*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span></span>

-   <span data-ttu-id="5e80f-130">**Inversion of Control Containers and the Dependency Injection pattern**（控制反转容器和依赖注入模式）
    [https://martinfowler.com/articles/injection.html](https://martinfowler.com/articles/injection.html)</span><span class="sxs-lookup"><span data-stu-id="5e80f-130">**Inversion of Control Containers and the Dependency Injection pattern**
[*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span></span>

-   <span data-ttu-id="5e80f-131">**Steve Smith.New is Glue**（新的即是粘的）
    [http://ardalis.com/new-is-glue](http://ardalis.com/new-is-glue)</span><span class="sxs-lookup"><span data-stu-id="5e80f-131">**Steve Smith. New is Glue**
[*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5e80f-132">[上一项] (nosql-database-persistence-infrastructure.md) [下一项] (microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="5e80f-132">[Previous] (nosql-database-persistence-infrastructure.md) [Next] (microservice-application-layer-implementation-web-api.md)</span></span>
