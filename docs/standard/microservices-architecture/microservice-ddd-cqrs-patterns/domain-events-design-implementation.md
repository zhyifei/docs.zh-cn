---
title: 域事件。 设计和实现
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 域事件、设计和实现
keywords: Docker, 微服务, ASP.NET, 容器
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bec1341df85f86d5f2aa15753a11a9c4a2d0173f
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="domain-events-design-and-implementation"></a><span data-ttu-id="66df9-105">域事件：设计和实现</span><span class="sxs-lookup"><span data-stu-id="66df9-105">Domain events: design and implementation</span></span>

<span data-ttu-id="66df9-106">使用域事件显式实现域中的更改的副作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-106">Use domain events to explicitly implement side effects of changes within your domain.</span></span> <span data-ttu-id="66df9-107">如果使用 DDD 术语表述，即使用域事件跨多个聚合显式实现副作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-107">In other words, and using DDD terminology, use domain events to explicitly implement side effects across multiple aggregates.</span></span> <span data-ttu-id="66df9-108">（可选）为了提高可伸缩性并减小对数据库锁定的影响，可在相同域的聚合之间使用最终一致性。</span><span class="sxs-lookup"><span data-stu-id="66df9-108">Optionally, for better scalability and less impact in database locks, use eventual consistency between aggregates within the same domain.</span></span>

## <a name="what-is-a-domain-event"></a><span data-ttu-id="66df9-109">什么是域事件？</span><span class="sxs-lookup"><span data-stu-id="66df9-109">What is a domain event?</span></span>

<span data-ttu-id="66df9-110">事件是过去发生的事。</span><span class="sxs-lookup"><span data-stu-id="66df9-110">An event is something that has happened in the past.</span></span> <span data-ttu-id="66df9-111">从逻辑上说，域事件是发生在特定域的事件，是你希望同一域（进程内）的其他部分识别和响应的事件。</span><span class="sxs-lookup"><span data-stu-id="66df9-111">A domain event is, logically, something that happened in a particular domain, and something you want other parts of the same domain (in-process) to be aware of and potentially react to.</span></span>

<span data-ttu-id="66df9-112">域事件的一个重要优点是，可在域中发生事件后，显式表示副作用，而不是隐式表示副作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-112">An important benefit of domain events is that side effects after something happened in a domain can be expressed explicitly instead of implicitly.</span></span> <span data-ttu-id="66df9-113">这些副作用必须保持一致性，以确保与业务任务相关的所有操作要么都发生，要么都不发生。</span><span class="sxs-lookup"><span data-stu-id="66df9-113">Those side effects must be consistent so either all the operations related to the business task happen, or none of them.</span></span> <span data-ttu-id="66df9-114">此外，域事件可优化相同域的类中的问题分离。</span><span class="sxs-lookup"><span data-stu-id="66df9-114">In addition, domain events enable a better separation of concerns among classes within the same domain.</span></span>

<span data-ttu-id="66df9-115">例如，如果只使用实体框架和实体或聚合，且用例必须引起副作用，则这些将在事件发生后作为耦合代码中的隐式概念实现。</span><span class="sxs-lookup"><span data-stu-id="66df9-115">For example, if you're just using Entity Framework and entities or even aggregates, if there have to be side effects provoked by a use case, those will be implemented as an implicit concept in the coupled code after something happened.</span></span> <span data-ttu-id="66df9-116">但是，如果只是查看代码，可能不知道代码（副作用）是主操作的一部分，还是真的副作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-116">But, if you just see that code, you might not know if that code (the side effect) is part of the main operation or if it really is a side effect.</span></span> <span data-ttu-id="66df9-117">但是，使用域事件可让概念成为显式，并属于通用语言。</span><span class="sxs-lookup"><span data-stu-id="66df9-117">On the other hand, using domain events makes the concept explicit and part of the ubiquitous language.</span></span> <span data-ttu-id="66df9-118">例如，在 eShopOnContainers 应用程序中，创建订单并不仅仅与订单相关，还需要基于原始用户更新或创建购买者聚合，因为用户在下订单前不是购买者。</span><span class="sxs-lookup"><span data-stu-id="66df9-118">For example, in the eShopOnContainers application, creating an order is not just about the order; it updates or creates a buyer aggregate based on the original user, because the user is not a buyer until there is an order in place.</span></span> <span data-ttu-id="66df9-119">如果使用域事件，可根据域专家提供的通用语言显式表示域规则。</span><span class="sxs-lookup"><span data-stu-id="66df9-119">If you use domain events, you can explicitly express that domain rule based in the ubiquitous language provided by the domain experts.</span></span>

<span data-ttu-id="66df9-120">域事件在某种程度上类似于消息样式事件，但有一个重要的区别。</span><span class="sxs-lookup"><span data-stu-id="66df9-120">Domain events are somewhat similar to messaging-style events, with one important difference.</span></span> <span data-ttu-id="66df9-121">对于真正的消息传送、消息队列、消息中转站或使用 AMPQ 的服务总线，消息始终异步发送，并跨进程和计算机传达。</span><span class="sxs-lookup"><span data-stu-id="66df9-121">With real messaging, message queuing, message brokers, or a service bus using AMPQ, a message is always sent asynchronously and communicated across processes and machines.</span></span> <span data-ttu-id="66df9-122">这对于集成多个绑定上下文、微服务或不同应用程序很有用。</span><span class="sxs-lookup"><span data-stu-id="66df9-122">This is useful for integrating multiple Bounded Contexts, microservices, or even different applications.</span></span> <span data-ttu-id="66df9-123">但是，对于域事件，需要从当前运行的域操作引发事件，但需要在相同的域中发生副作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-123">However, with domain events, you want to raise an event from the domain operation you are currently running, but you want any side effects to occur within the same domain.</span></span>

<span data-ttu-id="66df9-124">域事件和副作用（过后触发的操作，由事件处理程序管理）应几乎立即发生，通常在进程内或在相同的域中。</span><span class="sxs-lookup"><span data-stu-id="66df9-124">The domain events and their side effects (the actions triggered afterwards that are managed by event handlers) should occur almost immediately, usually in-process, and within the same domain.</span></span> <span data-ttu-id="66df9-125">因此，域事件可以是同步或异步。</span><span class="sxs-lookup"><span data-stu-id="66df9-125">Thus, domain events could be synchronous or asynchronous.</span></span> <span data-ttu-id="66df9-126">但是集成事件应始终是异步。</span><span class="sxs-lookup"><span data-stu-id="66df9-126">Integration events, however, should always be asynchronous.</span></span>

## <a name="domain-events-versus-integration-events"></a><span data-ttu-id="66df9-127">域事件和集成事件</span><span class="sxs-lookup"><span data-stu-id="66df9-127">Domain events versus integration events</span></span>

<span data-ttu-id="66df9-128">从语义上看，域事件和集成事件是相同的：都是对已发生事件的通知。</span><span class="sxs-lookup"><span data-stu-id="66df9-128">Semantically, domain and integration events are the same thing: notifications about something that just happened.</span></span> <span data-ttu-id="66df9-129">但是，它们的实现必须不同。</span><span class="sxs-lookup"><span data-stu-id="66df9-129">However, their implementation must be different.</span></span> <span data-ttu-id="66df9-130">域事件是推送到域事件调度程序的消息，可基于 IoC 容器或任何其他方法作为内存中转存进程实现。</span><span class="sxs-lookup"><span data-stu-id="66df9-130">Domain events are just messages pushed to a domain event dispatcher, which could be implemented as an in-memory mediator based on an IoC container or any other method.</span></span>

<span data-ttu-id="66df9-131">但是，集成事件的目的是将已提交事务和更新传播到其他子系统，无论它们是其他微服务、绑定上下文，还是外部应用程序。</span><span class="sxs-lookup"><span data-stu-id="66df9-131">On the other hand, the purpose of integration events is to propagate committed transactions and updates to additional subsystems, whether they are other microservices, Bounded Contexts or even external applications.</span></span> <span data-ttu-id="66df9-132">因此，它们应仅在成功保存实体时发生，因为在许多情况下，如果失败，整个操作不会发生。</span><span class="sxs-lookup"><span data-stu-id="66df9-132">Hence, they should occur only if the entity is successfully persisted, since in many scenarios if this fails, the entire operation effectively never happened.</span></span>

<span data-ttu-id="66df9-133">此外，如前所述，集成事件必须基于多个微服务（其他绑定上下文）或外部系统/应用程序之间的异步通信。</span><span class="sxs-lookup"><span data-stu-id="66df9-133">In addition, and as mentioned, integration events must be based on asynchronous communication between multiple microservices (other Bounded Contexts) or even external systems/applications.</span></span> <span data-ttu-id="66df9-134">因此，事件总线接口需要一些基础结构来实现远程服务之间的进程间和分布式通信。</span><span class="sxs-lookup"><span data-stu-id="66df9-134">Thus, the event bus interface needs some infrastructure that allows inter-process and distributed communication between potentially remote services.</span></span> <span data-ttu-id="66df9-135">可以基于商用服务总线、队列、作为邮箱的共享数据库或任何其他分布式和基于推送的消息传送系统。</span><span class="sxs-lookup"><span data-stu-id="66df9-135">It can be based on a commercial service bus, queues, a shared database used as a mailbox, or any other distributed and ideally push based messaging system.</span></span>

## <a name="domain-events-as-a-preferred-way-to-trigger-side-effects-across-multiple-aggregates-within-the-same-domain"></a><span data-ttu-id="66df9-136">域事件是在相同域中跨多个聚合触发副作用的首选方式</span><span class="sxs-lookup"><span data-stu-id="66df9-136">Domain events as a preferred way to trigger side effects across multiple aggregates within the same domain</span></span>

<span data-ttu-id="66df9-137">如果执行与一个聚合实例相关的命令需要其他域规则运行一个或多个其他聚合，应将这些副作用设计和实现为由域事件触发。</span><span class="sxs-lookup"><span data-stu-id="66df9-137">If executing a command related to one aggregate instance requires additional domain rules to be run on one or more additional aggregates, you should design and implement those side effects to be triggered by domain events.</span></span> <span data-ttu-id="66df9-138">如图 9-14 所示，这是一个最重要的用例之一，应将域事件用于在相同域模型中跨多个聚合传播状态更改。</span><span class="sxs-lookup"><span data-stu-id="66df9-138">As shown in Figure 9-14, and as one of the most important use cases, a domain event should be used to propagate state changes across multiple aggregates within the same domain model.</span></span>

![](./media/image15.png)

<span data-ttu-id="66df9-139">**图 9-14**。</span><span class="sxs-lookup"><span data-stu-id="66df9-139">**Figure 9-14**.</span></span> <span data-ttu-id="66df9-140">域事件在相同域的多个聚合之间强制执行一致性</span><span class="sxs-lookup"><span data-stu-id="66df9-140">Domain events to enforce consistency between multiple aggregates within the same domain</span></span>

<span data-ttu-id="66df9-141">在图中，当用户发起订单时，OrderStarted 域事件基于标识微服务（包含 CreateOrder 命令中提供的信息）中的原始用户信息，在订购微服务中触发购买者对象创建。</span><span class="sxs-lookup"><span data-stu-id="66df9-141">In the figure, when the user initiates an order, the OrderStarted domain event triggers creation of a Buyer object in the ordering microservice, based on the original user info from the identity microservice (with information provided in the CreateOrder command).</span></span> <span data-ttu-id="66df9-142">当最初创建时，域事件由订单聚合生成。</span><span class="sxs-lookup"><span data-stu-id="66df9-142">The domain event is generated by the order aggregate when it is created in the first place.</span></span>

<span data-ttu-id="66df9-143">或者，可以使聚合根订阅由聚合（子实体）成员引发的事件。</span><span class="sxs-lookup"><span data-stu-id="66df9-143">Alternately, you can have the aggregate root subscribed for events raised by members of its aggregates (child entities).</span></span> <span data-ttu-id="66df9-144">例如，每个 OrderItem 子实体可以在项目价格高于特定金额，或产品项目金额过高时，引发事件。</span><span class="sxs-lookup"><span data-stu-id="66df9-144">For instance, each OrderItem child entity can raise an event when the item price is higher than a specific amount, or when the product item amount is too high.</span></span> <span data-ttu-id="66df9-145">然后，聚合根可以接收这些事件，并执行全局计算或聚合。</span><span class="sxs-lookup"><span data-stu-id="66df9-145">The aggregate root can then receive those events and perform a global calculation or aggregation.</span></span>

<span data-ttu-id="66df9-146">请注意，此基于事件的通信不会直接在聚合中实现，需要实现域事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="66df9-146">It is important to understand that this event-based communication is not implemented directly within the aggregates; you need to implement domain event handlers.</span></span> <span data-ttu-id="66df9-147">处理域事件是一个应用程序问题。</span><span class="sxs-lookup"><span data-stu-id="66df9-147">Handling the domain events is an application concern.</span></span> <span data-ttu-id="66df9-148">域模型层应只关注域逻辑（域专家可理解的内容），而不应关注应用程序基础结构（如处理程序）和使用存储库的副作用持久性操作。</span><span class="sxs-lookup"><span data-stu-id="66df9-148">The domain model layer should only focus on the domain logic—things that a domain expert would understand, not application infrastructure like handlers and side-effect persistence actions using repositories.</span></span> <span data-ttu-id="66df9-149">因此，应用程序层级别是在引发域事件时应执行域事件处理程序触发操作的位置。</span><span class="sxs-lookup"><span data-stu-id="66df9-149">Therefore, the application layer level is where you should have domain event handlers triggering actions when a domain event is raised.</span></span>

<span data-ttu-id="66df9-150">域事件还可用于触发任意数量的应用程序操作，并且更重要的是，必须可在将来通过分离方式增加此数目。</span><span class="sxs-lookup"><span data-stu-id="66df9-150">Domain events can also be used to trigger any number of application actions, and what is more important, must be open to increase that number in the future in a decoupled way.</span></span> <span data-ttu-id="66df9-151">例如，发起订单时，可能需要发布域事件以将信息传播到其他聚合，或引发通知等应用程序操作。</span><span class="sxs-lookup"><span data-stu-id="66df9-151">For instance, when the order is started, you might want to publish a domain event to propagate that info to other aggregates or even to raise application actions like notifications.</span></span>

<span data-ttu-id="66df9-152">关键在于域事件发生时要执行的操作的可变数量。</span><span class="sxs-lookup"><span data-stu-id="66df9-152">The key point is the open number of actions to be executed when a domain event occurs.</span></span> <span data-ttu-id="66df9-153">最终，域中的操作和规则以及应用程序会发展。</span><span class="sxs-lookup"><span data-stu-id="66df9-153">Eventually, the actions and rules in the domain and application will grow.</span></span> <span data-ttu-id="66df9-154">事件发生时的复杂性或副作用操作的数量将增加，但如果代码被“固定”（即使用 C\# 中的新关键字实例化对象），每当需要添加新操作时，需要更改原始代码。</span><span class="sxs-lookup"><span data-stu-id="66df9-154">The complexity or number of side-effect actions when something happens will grow, but if your code were coupled with “glue” (that is, just instantiating objects with the new keyword in C\#), then every time you needed to add a new action you would need to change the original code.</span></span> <span data-ttu-id="66df9-155">这可能导致新 bug，因为对于每个新要求，需要更改原始代码流。</span><span class="sxs-lookup"><span data-stu-id="66df9-155">This could result in new bugs, because with each new requirement you would need to change the original code flow.</span></span> <span data-ttu-id="66df9-156">这违背了 [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)) 中的[开/闭原则](https://en.wikipedia.org/wiki/Open/closed_principle)。</span><span class="sxs-lookup"><span data-stu-id="66df9-156">This goes against the [Open/Closed principle](https://en.wikipedia.org/wiki/Open/closed_principle) from [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)).</span></span> <span data-ttu-id="66df9-157">不仅如此，协调操作的原始类将不断增加，这违背了[单一功能原则 (SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle)。</span><span class="sxs-lookup"><span data-stu-id="66df9-157">Not only that, the original class that was orchestrating the operations would grow and grow, which goes against the [Single Responsibility Principle (SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle).</span></span>

<span data-ttu-id="66df9-158">但是，如果使用域事件，可以通过使用以下方法分离功能来创建细化和分离的实现：</span><span class="sxs-lookup"><span data-stu-id="66df9-158">On the other hand, if you use domain events, you can create a fine-grained and decoupled implementation by segregating responsibilities using this approach:</span></span>

1.  <span data-ttu-id="66df9-159">发送命令（例如，CreateOrder）。</span><span class="sxs-lookup"><span data-stu-id="66df9-159">Send a command (for example, CreateOrder).</span></span>
2.  <span data-ttu-id="66df9-160">在命令处理程序中接收命令。</span><span class="sxs-lookup"><span data-stu-id="66df9-160">Receive the command in a command handler.</span></span>
    -   <span data-ttu-id="66df9-161">执行单个聚合的事务。</span><span class="sxs-lookup"><span data-stu-id="66df9-161">Execute a single aggregate’s transaction.</span></span>
    -   <span data-ttu-id="66df9-162">（可选）引发副作用的域事件（例如 OrderStartedDomainEvent）。</span><span class="sxs-lookup"><span data-stu-id="66df9-162">(Optional) Raise domain events for side effects (for example, OrderStartedDomainEvent).</span></span>
1.  <span data-ttu-id="66df9-163">处理域事件（在当前进程中），这些域事件会在多个聚合或应用程序操作中执行可变数量的副作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-163">Handle domain events (within the current process) that will execute an open number of side effects in multiple aggregates or application actions.</span></span> <span data-ttu-id="66df9-164">例如:</span><span class="sxs-lookup"><span data-stu-id="66df9-164">For example:</span></span>
    -   <span data-ttu-id="66df9-165">验证或创建购买者和付款方式。</span><span class="sxs-lookup"><span data-stu-id="66df9-165">Verify or create buyer and payment method.</span></span>
    -   <span data-ttu-id="66df9-166">创建相关集成事件并将其发送到事件总线，以在微服务中传播状态，或触发外部操作，例如将电子邮件发送给购买者。</span><span class="sxs-lookup"><span data-stu-id="66df9-166">Create and send a related integration event to the event bus to propagate states across microservices or trigger external actions like sending an email to the buyer.</span></span>
    -   <span data-ttu-id="66df9-167">处理其他副作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-167">Handle other side effects.</span></span>

<span data-ttu-id="66df9-168">如图 9-15 所示，从同一域事件，可以处理与域中的其他聚合相关的多个操作，或处理需要在与集成事件和事件总线相关的微服务中执行的其他应用程序操作。</span><span class="sxs-lookup"><span data-stu-id="66df9-168">As shown in Figure 9-15, starting from the same domain event, you can handle multiple actions related to other aggregates in the domain or additional application actions you need to perform across microservices connecting with integration events and the event bus.</span></span>

![](./media/image16.png)

<span data-ttu-id="66df9-169">**图 9-15**。</span><span class="sxs-lookup"><span data-stu-id="66df9-169">**Figure 9-15**.</span></span> <span data-ttu-id="66df9-170">处理每个域的多个操作</span><span class="sxs-lookup"><span data-stu-id="66df9-170">Handling multiple actions per domain</span></span>

<span data-ttu-id="66df9-171">事件处理程序通常在应用程序层中，因为会将存储库或应用程序 API 等基础结构对象用于微服务行为。</span><span class="sxs-lookup"><span data-stu-id="66df9-171">The event handlers are typically in the application layer, because you will use infrastructure objects like repositories or an application API for the microservice’s behavior.</span></span> <span data-ttu-id="66df9-172">在此意义上，事件处理程序类似于命令处理程序，因此两者都在应用程序层中。</span><span class="sxs-lookup"><span data-stu-id="66df9-172">In that sense, event handlers are similar to command handlers, so both are part of the application layer.</span></span> <span data-ttu-id="66df9-173">两者的重要区别是命令应只处理一次。</span><span class="sxs-lookup"><span data-stu-id="66df9-173">The important difference is that a command should be processed just once.</span></span> <span data-ttu-id="66df9-174">域事件可处理零或 n 次，因为它可被多个接收方或事件处理程序接收，针对每个处理程序具有不同用途。</span><span class="sxs-lookup"><span data-stu-id="66df9-174">A domain event could be processed zero or *n* times, because it can be received by multiple receivers or event handlers with a different purpose for each handler.</span></span>

<span data-ttu-id="66df9-175">借助每个域事件的可变数量的处理程序，可添加更多域规则，而不会影响当前代码。</span><span class="sxs-lookup"><span data-stu-id="66df9-175">The possibility of an open number of handlers per domain event allows you to add many more domain rules without impacting your current code.</span></span> <span data-ttu-id="66df9-176">例如，如果要实现必须在事件发生后立即发生的以下业务规则，可能只需轻松地添加一些（或者甚至是一个）事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="66df9-176">For instance, implementing the following business rule that has to happen right after an event might be as easy as adding a few event handlers (or even just one):</span></span>

<span data-ttu-id="66df9-177">如果客户在商店购买的总金额（跨任意数量订单）超过 6,000 美元，则为每个新订单提供 10% 的折扣，并通过电子邮件告知客户将来订单的折扣。</span><span class="sxs-lookup"><span data-stu-id="66df9-177">When the total amount purchased by a customer in the store, across any number of orders, exceeds $6,000, apply a 10% off discount to every new order and notify the customer with an email about that discount for future orders.</span></span>

## <a name="implementing-domain-events"></a><span data-ttu-id="66df9-178">实现域事件</span><span class="sxs-lookup"><span data-stu-id="66df9-178">Implementing domain events</span></span>

<span data-ttu-id="66df9-179">在 C# 中，域事件只是数据保留结构或类（如 DTO），包含与域中发生的事件相关的所有信息，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="66df9-179">In C#, a domain event is simply a data-holding structure or class, like a DTO, with all the information related to what just happened in the domain, as shown in the following example:</span></span>

```csharp
public class OrderStartedDomainEvent : INotification
{
    public string UserId { get; }
    public int CardTypeId { get; }
    public string CardNumber { get; }
    public string CardSecurityNumber { get; }
    public string CardHolderName { get; }
    public DateTime CardExpiration { get; }
    public Order Order { get; }

    public OrderStartedDomainEvent(Order order,
                                   int cardTypeId, string cardNumber,
                                   string cardSecurityNumber, string cardHolderName,
                                   DateTime cardExpiration)
    {
        Order = order;
        CardTypeId = cardTypeId;
        CardNumber = cardNumber;
        CardSecurityNumber = cardSecurityNumber;
        CardHolderName = cardHolderName;
        CardExpiration = cardExpiration;
    }
}
```

<span data-ttu-id="66df9-180">这实质上是一个包含与 OrderStarted 事件相关的所有数据的类。</span><span class="sxs-lookup"><span data-stu-id="66df9-180">This is essentially a class that holds all the data related to the OrderStarted event.</span></span>

<span data-ttu-id="66df9-181">关于域的通用语言，由于事件在过去发生的，事件的类名称应使用过去时态谓词表示，如 OrderStartedDomainEvent 或 OrderShippedDomainEvent。</span><span class="sxs-lookup"><span data-stu-id="66df9-181">In terms of the ubiquitous language of the domain, since an event is something that happened in the past, the class name of the event should be represented as a past-tense verb, like OrderStartedDomainEvent or OrderShippedDomainEvent.</span></span> <span data-ttu-id="66df9-182">这是域事件在 eShopOnContainers 的订购微服务中的实现方式。</span><span class="sxs-lookup"><span data-stu-id="66df9-182">That is how the domain event is implemented in the ordering microservice in eShopOnContainers.</span></span>

<span data-ttu-id="66df9-183">如前文所述，事件的一个重要特性是：由于事件是在过去发生的，所以不应发生更改。</span><span class="sxs-lookup"><span data-stu-id="66df9-183">As noted earlier, an important characteristic of events is that since an event is something that happened in the past, it should not change.</span></span> <span data-ttu-id="66df9-184">因此，它必须是一个不可变的类。</span><span class="sxs-lookup"><span data-stu-id="66df9-184">Therefore it must be an immutable class.</span></span> <span data-ttu-id="66df9-185">可以从上一个代码中看到，属性是从对象外部只读的。</span><span class="sxs-lookup"><span data-stu-id="66df9-185">You can see in the previous code that the properties are read-only from outside of the object.</span></span> <span data-ttu-id="66df9-186">更新对象的唯一方法是在创建事件对象时通过构造函数。</span><span class="sxs-lookup"><span data-stu-id="66df9-186">The only way to update the object is through the constructor when you create the event object.</span></span>

### <a name="raising-domain-events"></a><span data-ttu-id="66df9-187">引发域事件</span><span class="sxs-lookup"><span data-stu-id="66df9-187">Raising domain events</span></span>

<span data-ttu-id="66df9-188">下一个问题是如何引发域事件，使其到达相关的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="66df9-188">The next question is how to raise a domain event so it reaches its related event handlers.</span></span> <span data-ttu-id="66df9-189">可使用多个方法。</span><span class="sxs-lookup"><span data-stu-id="66df9-189">You can use multiple approaches.</span></span>

<span data-ttu-id="66df9-190">Udi Dahan 最初建议（例如在 [Domain Events – Take 2](http://udidahan.com/2008/08/25/domain-events-take-2/)（域事件 – Take 2）等一系列文章中）将静态类用于管理和引发事件。</span><span class="sxs-lookup"><span data-stu-id="66df9-190">Udi Dahan originally proposed (for example, in several related posts, such as [Domain Events – Take 2](http://udidahan.com/2008/08/25/domain-events-take-2/)) using a static class for managing and raising the events.</span></span> <span data-ttu-id="66df9-191">这可能包括名为 DomainEvents 的静态类，该类会在调用时，使用 DomainEvents.Raise(Event myEvent) 等语法立即引发域事件。</span><span class="sxs-lookup"><span data-stu-id="66df9-191">This might include a static class named DomainEvents that would raise domain events immediately when it is called, using syntax like DomainEvents.Raise(Event myEvent).</span></span> <span data-ttu-id="66df9-192">Jimmy Bogard 在其博客文章 ([Strengthening your domain: Domain Events](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/))（强化你的域：域事件）中建议使用类似方法。</span><span class="sxs-lookup"><span data-stu-id="66df9-192">Jimmy Bogard wrote a blog post ([Strengthening your domain: Domain Events](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/)) that recommends a similar approach.</span></span>

<span data-ttu-id="66df9-193">但是，如果域事件类是静态的，它也会立即调度给处理程序。</span><span class="sxs-lookup"><span data-stu-id="66df9-193">However, when the domain events class is static, it also dispatches to handlers immediately.</span></span> <span data-ttu-id="66df9-194">这使得测试和调试更加困难，因为会在引发事件后立即执行具有副作用逻辑的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="66df9-194">This makes testing and debugging more difficult, because the event handlers with side-effects logic are executed immediately after the event is raised.</span></span> <span data-ttu-id="66df9-195">测试和调试时，你希望专注于当前聚合类发生的事件；不希望突然重定向到其他事件处理程序，处理与其他聚合或应用程序逻辑相关的副作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-195">When you are testing and debugging, you want to focus on and just what is happening in the current aggregate classes; you do not want to suddenly be redirected to other event handlers for side effects related to other aggregates or application logic.</span></span> <span data-ttu-id="66df9-196">因此，其他方法应运而生，下一节将进行介绍。</span><span class="sxs-lookup"><span data-stu-id="66df9-196">This is why other approaches have evolved, as explained in the next section.</span></span>

#### <a name="the-deferred-approach-for-raising-and-dispatching-events"></a><span data-ttu-id="66df9-197">引发和调度事件的延迟方法</span><span class="sxs-lookup"><span data-stu-id="66df9-197">The deferred approach for raising and dispatching events</span></span>

<span data-ttu-id="66df9-198">一个更好的方法是将域事件添加到集合，然后在提交事务之前或之后立即调度这些域事件（正如 EF 中的 SaveChanges），而不是立即调度到域事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="66df9-198">Instead of dispatching to a domain event handler immediately, a better approach is to add the domain events to a collection and then to dispatch those domain events *right before* or *right* *after* committing the transaction (as with SaveChanges in EF).</span></span> <span data-ttu-id="66df9-199">（Jimmy Bogard 的文章 [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)（一个更好的域事件模式）中介绍了此方法。）</span><span class="sxs-lookup"><span data-stu-id="66df9-199">(This approach was described by Jimmy Bogard in this post [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/).)</span></span>

<span data-ttu-id="66df9-200">确定要在提交事务之前还是之后立即发送域事件非常重要，因为这决定了是将副作用添加到相同事务，还是不同事务中。</span><span class="sxs-lookup"><span data-stu-id="66df9-200">Deciding if you send the domain events right before or right after committing the transaction is important, since it determines whether you will include the side effects as part of the same transaction or in different transactions.</span></span> <span data-ttu-id="66df9-201">如果是将副作用添加到不同事务，需要处理跨多个聚合的最终一致性。</span><span class="sxs-lookup"><span data-stu-id="66df9-201">In the latter case, you need to deal with eventual consistency across multiple aggregates.</span></span> <span data-ttu-id="66df9-202">下一节中将对此主题进行讨论。</span><span class="sxs-lookup"><span data-stu-id="66df9-202">This topic is discussed in the next section.</span></span>

<span data-ttu-id="66df9-203">eShopOnContainers 使用延迟方法。</span><span class="sxs-lookup"><span data-stu-id="66df9-203">The deferred approach is what eShopOnContainers uses.</span></span> <span data-ttu-id="66df9-204">首先，将实体中发生的事件添加到每个实体的集合或事件列表。</span><span class="sxs-lookup"><span data-stu-id="66df9-204">First, you add the events happening in your entities into a collection or list of events per entity.</span></span> <span data-ttu-id="66df9-205">此列表应属于实体对象（或最好属于基本实体类），如以下实体基类示例所示：</span><span class="sxs-lookup"><span data-stu-id="66df9-205">That list should be part of the entity object, or even better, part of your base entity class, as shown in the following example of the Entity base class:</span></span>

```csharp
public abstract class Entity
{
     //... 
    private List<INotification> _domainEvents;
    public List<INotification> DomainEvents => _domainEvents;

    public void AddDomainEvent(INotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<INotification>();
        _domainEvents.Add(eventItem);
    }

    public void RemoveDomainEvent(INotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }
    // ...
}
```

<span data-ttu-id="66df9-206">要引发事件时，只需将其在聚合根实体的方法处添加到代码中的事件集合。</span><span class="sxs-lookup"><span data-stu-id="66df9-206">When you want to raise an event, you just add it to the event collection from code at any method of the aggregate-root entity.</span></span>

<span data-ttu-id="66df9-207">以下代码（属于 [ eShopOnContainers 的订单聚合根](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs)）演示如下示例：</span><span class="sxs-lookup"><span data-stu-id="66df9-207">The following code, part of the [Order agregate-root at eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs), shows an example:</span></span>

```csharp
var orderStartedDomainEvent = new OrderStartedDomainEvent(this, //Order object
                                                          cardTypeId, cardNumber,
                                                          cardSecurityNumber,
                                                          cardHolderName,
                                                          cardExpiration);
this.AddDomainEvent(orderStartedDomainEvent);
```

<span data-ttu-id="66df9-208">请注意 AddDomainEvent 方法的唯一功能是将事件添加到列表。</span><span class="sxs-lookup"><span data-stu-id="66df9-208">Notice that the only thing that the AddDomainEvent method is doing is adding an event to the list.</span></span> <span data-ttu-id="66df9-209">尚未调度任何事件，尚未调用任何事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="66df9-209">No event is dispatched yet, and no event handler is invoked yet.</span></span>

<span data-ttu-id="66df9-210">你需要在稍后将事务提交到数据库时调度事件。</span><span class="sxs-lookup"><span data-stu-id="66df9-210">You actually want to dispatch the events later on, when you commit the transaction to the database.</span></span> <span data-ttu-id="66df9-211">如果使用 Entity Framework Core，意味着在 EF DbContext 的 SaveChanges 方法中，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="66df9-211">If you are using Entity Framework Core, that means in the SaveChanges method of your EF DbContext, as in the following code:</span></span>

```csharp
// EF Core DbContext
public class OrderingContext : DbContext, IUnitOfWork
{
    // ...
    public async Task<bool> SaveEntitiesAsync(CancellationToken cancellationToken = default(CancellationToken))
    {
        // Dispatch Domain Events collection.
        // Choices:
        // A) Right BEFORE committing data (EF SaveChanges) into the DB. This makes
        // a single transaction including side effects from the domain event
        // handlers that are using the same DbContext with Scope lifetime
        // B) Right AFTER committing data (EF SaveChanges) into the DB. This makes
        // multiple transactions. You will need to handle eventual consistency and
        // compensatory actions in case of failures.        
        await _mediator.DispatchDomainEventsAsync(this);

        // After this line runs, all the changes (from the Command Handler and Domain
        // event handlers) performed through the DbContext will be commited
        var result = await base.SaveChangesAsync();
    }
}
```

<span data-ttu-id="66df9-212">使用此代码可将实体事件调度到相应的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="66df9-212">With this code, you dispatch the entity events to their respective event handlers.</span></span>

<span data-ttu-id="66df9-213">总体结果是将域事件引用（简单添加到内存中列表）从调度到事件处理程序中分离。</span><span class="sxs-lookup"><span data-stu-id="66df9-213">The overall result is that you have decoupled the raising of a domain event (a simple add into a list in memory) from dispatching it to an event handler.</span></span> <span data-ttu-id="66df9-214">此外，可同步或异步调度事件，具体取决于你使用的调度程序。</span><span class="sxs-lookup"><span data-stu-id="66df9-214">In addition, depending on what kind of dispatcher you are using, you could dispatch the events synchronously or asynchronously.</span></span>

<span data-ttu-id="66df9-215">请注意事务边界在此时发挥巨大作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-215">Be aware that transactional boundaries come into significant play here.</span></span> <span data-ttu-id="66df9-216">如果工作单元和事务可跨多个聚合（如使用 EF Core 和关系数据库时），这可正常运行。</span><span class="sxs-lookup"><span data-stu-id="66df9-216">If your unit of work and transaction can span more than one aggregate (as when using EF Core and a relational database), this can work well.</span></span> <span data-ttu-id="66df9-217">但是，如果事务不能跨聚合（例如使用 Azure DocumentDB 等 NoSQL 数据库时），必须执行额外步骤以实现一致性。</span><span class="sxs-lookup"><span data-stu-id="66df9-217">But if the transaction cannot span aggregates, such as when you are using a NoSQL database like Azure DocumentDB, you have to implement additional steps to achieve consistency.</span></span> <span data-ttu-id="66df9-218">这是持久性无感知不通用的另一个原因，它取决于你使用的存储系统。</span><span class="sxs-lookup"><span data-stu-id="66df9-218">This is another reason why persistence ignorance is not universal; it depends on the storage system you use.</span></span>

### <a name="single-transaction-across-aggregates-versus-eventual-consistency-across-aggregates"></a><span data-ttu-id="66df9-219">跨聚合的单个事务与跨聚合的最终一致性</span><span class="sxs-lookup"><span data-stu-id="66df9-219">Single transaction across aggregates versus eventual consistency across aggregates</span></span>

<span data-ttu-id="66df9-220">是跨聚合执行单个事务，还是依赖跨聚合的最终一致性，这一点存在争议。</span><span class="sxs-lookup"><span data-stu-id="66df9-220">The question of whether to perform a single transaction across aggregates versus relying on eventual consistency across those aggregates is a controversial one.</span></span> <span data-ttu-id="66df9-221">Eric Evans 和 Vaughn Vernon 等许多作者提倡遵循一个事务 = 一个聚合的规则，因此支持跨聚合的最终一致性。</span><span class="sxs-lookup"><span data-stu-id="66df9-221">Many DDD authors like Eric Evans and Vaughn Vernon advocate the rule that one transaction = one aggregate and therefore argue for eventual consistency across aggregates.</span></span> <span data-ttu-id="66df9-222">例如，Eric Evans 在他的著作《Domain-Driven Design》（域驱动的设计）中表示：</span><span class="sxs-lookup"><span data-stu-id="66df9-222">For example, in his book *Domain-Driven Design*, Eric Evans says this:</span></span>

<span data-ttu-id="66df9-223">跨聚合的任何规则都不会始终保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="66df9-223">Any rule that spans Aggregates will not be expected to be up-to-date at all times.</span></span> <span data-ttu-id="66df9-224">通过事件处理、批处理或其他更新机制，其他依赖项可在特定时间内解析。</span><span class="sxs-lookup"><span data-stu-id="66df9-224">Through event processing, batch processing, or other update mechanisms, other dependencies can be resolved within some specific time.</span></span> <span data-ttu-id="66df9-225">（第 128 页）</span><span class="sxs-lookup"><span data-stu-id="66df9-225">(page 128)</span></span>

<span data-ttu-id="66df9-226">Vaughn Vernon 在 [Effective Aggregate Design.Part II: Making Aggregates Work Together](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)（有效聚合设计。第二部分：让聚合共同工作）中提到：</span><span class="sxs-lookup"><span data-stu-id="66df9-226">Vaughn Vernon says the following in [Effective Aggregate Design. Part II: Making Aggregates Work Together](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf):</span></span>

<span data-ttu-id="66df9-227">因此，如果在一个聚合实例上执行命令需要在一个或多个聚合上执行其他业务规则，则使用最终一致性。\[...\]有一个实用方法可在 DDD 模型中支持最终一致性。</span><span class="sxs-lookup"><span data-stu-id="66df9-227">Thus, if executing a command on one aggregate instance requires that additional business rules execute on one or more aggregates, use eventual consistency \[...\] There is a practical way to support eventual consistency in a DDD model.</span></span> <span data-ttu-id="66df9-228">聚合方法发布及时交付到一个或多个异步订阅服务器的域事件。</span><span class="sxs-lookup"><span data-stu-id="66df9-228">An aggregate method publishes a domain event that is in time delivered to one or more asynchronous subscribers.</span></span>

<span data-ttu-id="66df9-229">此观点基于接受细化事务，而不是跨多个聚合或实体的事务。</span><span class="sxs-lookup"><span data-stu-id="66df9-229">This rationale is based on embracing fine-grained transactions instead of transactions spanning many aggregates or entities.</span></span> <span data-ttu-id="66df9-230">原理是在第二种情况下，具有高可伸缩性要求的大规模应用程序的数据库锁定的数量巨大。</span><span class="sxs-lookup"><span data-stu-id="66df9-230">The idea is that in the second case, the number of database locks will be substantial in large-scale applications with high scalability needs.</span></span> <span data-ttu-id="66df9-231">接受高可伸缩性应用程序不需要多个聚合间的即时事务一致性的事实，有助于接受最终一致性的概念。</span><span class="sxs-lookup"><span data-stu-id="66df9-231">Embracing the fact that high-scalable applications need not have instant transactional consistency between multiple aggregates helps with accepting the concept of eventual consistency.</span></span> <span data-ttu-id="66df9-232">业务通常不需要原子更改，而且确定特定操作是否需要原子事务始终是域专家的职责。</span><span class="sxs-lookup"><span data-stu-id="66df9-232">Atomic changes are often not needed by the business, and it is in any case the responsibility of the domain experts to say whether particular operations need atomic transactions or not.</span></span> <span data-ttu-id="66df9-233">如果操作始终需要多个聚合间的原子事务，应考虑聚合是否应该更大，或是否未正确设计。</span><span class="sxs-lookup"><span data-stu-id="66df9-233">If an operation always needs an atomic transaction between multiple aggregates, you might ask whether your aggregate should be larger or was not correctly designed.</span></span>

<span data-ttu-id="66df9-234">但 Jimmy Bogard 等其他开发者和架构师赞成在多个聚合中跨越单个事务 - 但仅当这些额外聚合与相同原始命令的副作用相关时。</span><span class="sxs-lookup"><span data-stu-id="66df9-234">However, other developers and architects like Jimmy Bogard are okay with spanning a single transaction across several aggregates—but only when those additional aggregates are related to side effects for the same original command.</span></span> <span data-ttu-id="66df9-235">例如，在 [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)（更好的域事件模式）中，Bogard 表示：</span><span class="sxs-lookup"><span data-stu-id="66df9-235">For instance, in [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/), Bogard says this:</span></span>

<span data-ttu-id="66df9-236">通常情况下，我希望域事件的副作用发生在相同的逻辑事务中，但不一定是在引发域事件的同一作用域 \[...\]在提交事务前，将事件调度到相应的处理程序。</span><span class="sxs-lookup"><span data-stu-id="66df9-236">Typically, I want the side effects of a domain event to occur within the same logical transaction, but not necessarily in the same scope of raising the domain event \[...\] Just before we commit our transaction, we dispatch our events to their respective handlers.</span></span>

<span data-ttu-id="66df9-237">如果在提交原始事务前调度域事件，这是因为希望在相同事务中添加这些事件的副作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-237">If you dispatch the domain events right *before* committing the original transaction, it is because you want the side effects of those events to be included in the same transaction.</span></span> <span data-ttu-id="66df9-238">例如，如果 EF DbContext SaveChanges 方法失败，事务会回退所有更改，包括由相关域事件处理程序实现的副作用操作。</span><span class="sxs-lookup"><span data-stu-id="66df9-238">For example, if the EF DbContext SaveChanges method fails, the transaction will roll back all changes, including the result of any side effect operations implemented by the related domain event handlers.</span></span> <span data-ttu-id="66df9-239">这是因为默认情况下 DbContext 生存范围定义为“已设置范围”。</span><span class="sxs-lookup"><span data-stu-id="66df9-239">This is because the DbContext life scope is by default defined as "scoped."</span></span> <span data-ttu-id="66df9-240">因此，DbContext 对象跨多个在相同范围或对象图中实例化的存储库对象共享。</span><span class="sxs-lookup"><span data-stu-id="66df9-240">Therefore, the DbContext object is shared across multiple repository objects being instantiated within the same scope or object graph.</span></span> <span data-ttu-id="66df9-241">在开发 Web API 或 MVC 应用时，这与 HttpRequest 范围一致。</span><span class="sxs-lookup"><span data-stu-id="66df9-241">This coincides with the HttpRequest scope when developing Web API or MVC apps.</span></span>

<span data-ttu-id="66df9-242">实际上，这两种方法（单个原子事务和最终一致性）都是正确的。</span><span class="sxs-lookup"><span data-stu-id="66df9-242">In reality, both approaches (single atomic transaction and eventual consistency) can be right.</span></span> <span data-ttu-id="66df9-243">实际上取决于你的域或业务要求，以及域专家的建议。</span><span class="sxs-lookup"><span data-stu-id="66df9-243">It really depends on your domain or business requirements and what the domain experts tell you.</span></span> <span data-ttu-id="66df9-244">它还取决于所需的服务可缩放性（事务越细化，对数据库锁定的影响越小）。</span><span class="sxs-lookup"><span data-stu-id="66df9-244">It also depends on how scalable you need the service to be (more granular transactions have less impact with regard to database locks).</span></span> <span data-ttu-id="66df9-245">它取决于你愿意在代码上进行的投资，由于最终一致性需要更复杂的代码以检测聚合中可能的不一致，且需要实现补偿操作。</span><span class="sxs-lookup"><span data-stu-id="66df9-245">And it depends on how much investment you are willing to make in your code, since eventual consistency requires more complex code in order to detect possible inconsistencies across aggregates and the need to implement compensatory actions.</span></span> <span data-ttu-id="66df9-246">请考虑以下情况：如果将更改提交到原始聚合，当调度事件时会发生问题，事件处理程序无法提交副作用，聚合之间将产生不一致。</span><span class="sxs-lookup"><span data-stu-id="66df9-246">Take into account that if you commit changes to the original aggregate and afterwards, when the events are being dispatched, there is an issue and the event handlers cannot commit their side effects, you will have inconsistencies between aggregates.</span></span>

<span data-ttu-id="66df9-247">若要执行补偿操作，可将域事件存储在其他数据库表格，使其属于原始事务。</span><span class="sxs-lookup"><span data-stu-id="66df9-247">A way to allow compensatory actions would be to store the domain events in additional database tables so they can be part of the original transaction.</span></span> <span data-ttu-id="66df9-248">然后，可通过批处理比较事件列表和聚合的当前状态，从而检测不一致并运行补偿操作。</span><span class="sxs-lookup"><span data-stu-id="66df9-248">Afterwards, you could have a batch process that detects inconsistencies and runs compensatory actions by comparing the list of events with the current state of the aggregates.</span></span> <span data-ttu-id="66df9-249">补偿操作属于复杂主题，需要你进行深度分析，包括与业务用户和域专家进行讨论。</span><span class="sxs-lookup"><span data-stu-id="66df9-249">The compensatory actions are part of a complex topic that will require deep analysis from your side, which includes discussing it with the business user and domain experts.</span></span>

<span data-ttu-id="66df9-250">在任何情况下，你可以选择所需的方法。</span><span class="sxs-lookup"><span data-stu-id="66df9-250">In any case, you can choose the approach you need.</span></span> <span data-ttu-id="66df9-251">但初始延迟方法（在提交前引发事件，从而使用单个事务）是使用 EF Core 和关系数据库时最简单的方法。</span><span class="sxs-lookup"><span data-stu-id="66df9-251">But the initial deferred approach—raising the events before committing, so you use a single transaction—is the simplest approach when using EF Core and a relational database.</span></span> <span data-ttu-id="66df9-252">该方法易于实现且在许多业务情景中有效。</span><span class="sxs-lookup"><span data-stu-id="66df9-252">It is easier to implement and valid in many business cases.</span></span> <span data-ttu-id="66df9-253">这也是 eShopOnContainers 的订购微服务中使用的方法。</span><span class="sxs-lookup"><span data-stu-id="66df9-253">It is also the approach used in the ordering microservice in eShopOnContainers.</span></span>

<span data-ttu-id="66df9-254">但如何将这些事件调度到相应的事件处理程序？</span><span class="sxs-lookup"><span data-stu-id="66df9-254">But how do you actually dispatch those events to their respective event handlers?</span></span> <span data-ttu-id="66df9-255">你在上一个示例中看到的\_转存进程对象是什么？</span><span class="sxs-lookup"><span data-stu-id="66df9-255">What is the \_mediator object that you see in the previous example?</span></span> <span data-ttu-id="66df9-256">它与用于在事件及其事件处理程序之间映射的技术和项目有关。</span><span class="sxs-lookup"><span data-stu-id="66df9-256">That has to do with the techniques and artifacts you can use to map between events and their event handlers.</span></span>

### <a name="the-domain-event-dispatcher-mapping-from-events-to-event-handlers"></a><span data-ttu-id="66df9-257">域事件调度程序：从事件映射到事件处理程序</span><span class="sxs-lookup"><span data-stu-id="66df9-257">The domain event dispatcher: mapping from events to event handlers</span></span>

<span data-ttu-id="66df9-258">可调度或发布事件后，需要用于发布事件的某种项目，以便每个相关处理程序可获取它，并基于该事件处理副作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-258">Once you're able to dispatch or publish the events, you need some kind of artifact that will publish the event, so that every related handler can get it and process side effects based on that event.</span></span>

<span data-ttu-id="66df9-259">一种方法是使用真正的消息传送系统或事件总线，可能基于服务总线，而不是内存中事件。</span><span class="sxs-lookup"><span data-stu-id="66df9-259">One approach is a real messaging system or even an event bus, possibly based on a service bus as opposed to in-memory events.</span></span> <span data-ttu-id="66df9-260">但是，对于第一种情况，真正的消息传送可能对于处理域事件来说用力过猛，因为你只需要处理相同进程（即相同域和应用程序层）中的事件。</span><span class="sxs-lookup"><span data-stu-id="66df9-260">However, for the first case, real messaging would be overkill for processing domain events, since you just need to process those events within the same process (that is, within the same domain and application layer).</span></span>

<span data-ttu-id="66df9-261">将事件映射到多个事件处理程序的另一种方法是使用 IoC 容器中的类型注册，以便动态推断是否调度事件。</span><span class="sxs-lookup"><span data-stu-id="66df9-261">Another way to map events to multiple event handlers is by using types registration in an IoC container so that you can dynamically infer where to dispatch the events.</span></span> <span data-ttu-id="66df9-262">换而言之，需要知道什么事件处理程序需要获得特定事件。</span><span class="sxs-lookup"><span data-stu-id="66df9-262">In other words, you need to know what event handlers need to get a specific event.</span></span> <span data-ttu-id="66df9-263">图 9-16 演示简化的方法。</span><span class="sxs-lookup"><span data-stu-id="66df9-263">Figure 9-16 shows a simplified approach for that.</span></span>

![](./media/image17.png)

<span data-ttu-id="66df9-264">**图 9-16**。</span><span class="sxs-lookup"><span data-stu-id="66df9-264">**Figure 9-16**.</span></span> <span data-ttu-id="66df9-265">使用 IoC 的域事件调度程序</span><span class="sxs-lookup"><span data-stu-id="66df9-265">Domain event dispatcher using IoC</span></span>

<span data-ttu-id="66df9-266">可以构建所有联结和项目，自行实现此方法。</span><span class="sxs-lookup"><span data-stu-id="66df9-266">You can build all the plumbing and artifacts to implement that approach by yourself.</span></span> <span data-ttu-id="66df9-267">但是还可使用 [MediatR](https://github.com/jbogard/MediatR)（MediatR 实际上使用 IoC 容器）等可用库。</span><span class="sxs-lookup"><span data-stu-id="66df9-267">However, you can also use available libraries like [MediatR](https://github.com/jbogard/MediatR), which underneath the covers uses your IoC container.</span></span> <span data-ttu-id="66df9-268">因此，可以直接使用预定义的接口和转存进程对象的发布/调度方法。</span><span class="sxs-lookup"><span data-stu-id="66df9-268">You can therefore directly use the predefined interfaces and the mediator object’s publish/dispatch methods.</span></span>

<span data-ttu-id="66df9-269">在代码中，首先需要在 IoC 容器中注册事件处理程序类型，如 [eShopOnContainers 订购服务](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/MediatorModule.cs)处的以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="66df9-269">In code, you first need to register the event handler types in your IoC container, as shown in the following example at [eShopOnContainers Ordering microservice](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/MediatorModule.cs):</span></span>

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        // Other registrations ...
        // Register the DomainEventHandler classes (they implement IAsyncNotificationHandler<>)
        // in assembly holding the Domain Events
        builder.RegisterAssemblyTypes(typeof(ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler)
                                       .GetTypeInfo().Assembly)
                                         .AsClosedTypesOf(typeof(IAsyncNotificationHandler<>));
        // Other registrations ...
    }
}
```

<span data-ttu-id="66df9-270">代码首先通过查找保留处理程序（使用 typeof(ValidateOrAddBuyerAggregateWhenXxxx)，但你可能已经选择任何其他事件处理程序来查找此程序集）的程序集，识别包含域事件处理程序的程序集。</span><span class="sxs-lookup"><span data-stu-id="66df9-270">The code first identifies the assembly that contains the domain event handlers by locating the assembly that holds any of the handlers (using typeof(ValidateOrAddBuyerAggregateWhenXxxx), but you could have chosen any other event handler to locate the assembly).</span></span> <span data-ttu-id="66df9-271">由于所有事件处理程序实现 IAsyncNotificationHandler 接口，代码仅搜索这些类型并注册所有事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="66df9-271">Since all the event handlers implement the IAsyncNotificationHandler interface, the code then just searches for those types and registers all the event handlers.</span></span>

### <a name="how-to-subscribe-to-domain-events"></a><span data-ttu-id="66df9-272">如何订阅域事件</span><span class="sxs-lookup"><span data-stu-id="66df9-272">How to subscribe to domain events</span></span>

<span data-ttu-id="66df9-273">使用 MediatR 时，每个事件处理程序必须使用 INotificationHandler 接口的通用参数上提供的事件类型，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="66df9-273">When you use MediatR, each event handler must use an event type that is provided on the generic parameter of the INotificationHandler interface, as you can see in the following code:</span></span>

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
  : IAsyncNotificationHandler<OrderStartedDomainEvent>
```

<span data-ttu-id="66df9-274">基于事件和事件处理程序之间的关系（可将其视为订阅），MediatR 项目可发现每个事件的所有事件处理程序并触发每个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="66df9-274">Based on the relationship between event and event handler, which can be considered the subscription, the MediatR artifact can discover all the event handlers for each event and trigger each of those event handlers.</span></span>

### <a name="how-to-handle-domain-events"></a><span data-ttu-id="66df9-275">如何处理域事件</span><span class="sxs-lookup"><span data-stu-id="66df9-275">How to handle domain events</span></span>

<span data-ttu-id="66df9-276">最后，事件处理程序通常实现使用基础结构存储库的应用程序层，以获取所需其他聚合并执行副作用域逻辑。</span><span class="sxs-lookup"><span data-stu-id="66df9-276">Finally, the event handler usually implements application layer code that uses infrastructure repositories to obtain the required additional aggregates and to execute side-effect domain logic.</span></span> <span data-ttu-id="66df9-277">以下[ eShopOnContainers 中的域事件处理程序代码](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/DomainEventHandlers/OrderStartedEvent/ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler.cs)演示实现示例。</span><span class="sxs-lookup"><span data-stu-id="66df9-277">The following [domain event handler code at eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/DomainEventHandlers/OrderStartedEvent/ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler.cs), shows an implementation example.</span></span>

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
                   : INotificationHandler<OrderStartedDomainEvent>
{
    private readonly ILoggerFactory _logger;
    private readonly IBuyerRepository<Buyer> _buyerRepository;
    private readonly IIdentityService _identityService;

    public ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler(
        ILoggerFactory logger,
        IBuyerRepository<Buyer> buyerRepository,
        IIdentityService identityService)
    {
        // ...Parameter validations...
    }

    public async Task Handle(OrderStartedDomainEvent orderStartedEvent)
    {
        var cardTypeId = (orderStartedEvent.CardTypeId != 0) ? orderStartedEvent.CardTypeId : 1;        
        var userGuid = _identityService.GetUserIdentity();
        var buyer = await _buyerRepository.FindAsync(userGuid);
        bool buyerOriginallyExisted = (buyer == null) ? false : true;

        if (!buyerOriginallyExisted)
        {
            buyer = new Buyer(userGuid);
        }

        buyer.VerifyOrAddPaymentMethod(cardTypeId,
                                       $"Payment Method on {DateTime.UtcNow}",
                                       orderStartedEvent.CardNumber,
                                       orderStartedEvent.CardSecurityNumber,
                                       orderStartedEvent.CardHolderName,
                                       orderStartedEvent.CardExpiration,
                                       orderStartedEvent.Order.Id);

        var buyerUpdated = buyerOriginallyExisted ? _buyerRepository.Update(buyer) 
                                                                      : _buyerRepository.Add(buyer);

        await _buyerRepository.UnitOfWork
                .SaveEntitiesAsync();

        // Logging code using buyerUpdated info, etc.
    }
}
```

<span data-ttu-id="66df9-278">前面的域事件处理程序代码被视为应用程序层代码，因为其使用基础结构存储库，如有关基础结构持久化层的下一节所述。</span><span class="sxs-lookup"><span data-stu-id="66df9-278">The previous domain event handler code is considered application layer code because it uses infrastructure repositories, as explained in the next section on the infrastructure-persistence layer.</span></span> <span data-ttu-id="66df9-279">事件处理程序还可以使用其他基础结构组件。</span><span class="sxs-lookup"><span data-stu-id="66df9-279">Event handlers could also use other infrastructure components.</span></span>

#### <a name="domain-events-can-generate-integration-events-to-be-published-outside-of-the-microservice-boundaries"></a><span data-ttu-id="66df9-280">域事件可以生成要在微服务边界之外发布的集成事件</span><span class="sxs-lookup"><span data-stu-id="66df9-280">Domain events can generate integration events to be published outside of the microservice boundaries</span></span>

<span data-ttu-id="66df9-281">最后，请注意，有时需要跨多个微服务传播事件。</span><span class="sxs-lookup"><span data-stu-id="66df9-281">Finally, it is important to mention that you might sometimes want to propagate events across multiple microservices.</span></span> <span data-ttu-id="66df9-282">这被视为集成事件，可通过特定域事件处理程序的事件总线发布它。</span><span class="sxs-lookup"><span data-stu-id="66df9-282">That is considered an integration event, and it could be published through an event bus from any specific domain event handler.</span></span>

## <a name="conclusions-on-domain-events"></a><span data-ttu-id="66df9-283">域事件的结论</span><span class="sxs-lookup"><span data-stu-id="66df9-283">Conclusions on domain events</span></span>

<span data-ttu-id="66df9-284">如前文所述，使用域事件显式实现域中的更改的副作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-284">As stated, use domain events to explicitly implement side effects of changes within your domain.</span></span> <span data-ttu-id="66df9-285">若要使用 DDD 术语表述，则是使用域事件跨一个或多个聚合显式实现副作用。</span><span class="sxs-lookup"><span data-stu-id="66df9-285">To use DDD terminology, use domain events to explicitly implement side effects across one or multiple aggregates.</span></span> <span data-ttu-id="66df9-286">此外，为了提高可伸缩性并减小对数据库锁定的影响，可在相同域的聚合之间使用最终一致性。</span><span class="sxs-lookup"><span data-stu-id="66df9-286">Additionally, and for better scalability and less impact on database locks, use eventual consistency between aggregates within the same domain.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="66df9-287">其他资源</span><span class="sxs-lookup"><span data-stu-id="66df9-287">Additional resources</span></span>

-   <span data-ttu-id="66df9-288">**Greg Young.What is a Domain Event?**
    [*http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/*](http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/)（什么是域事件？）</span><span class="sxs-lookup"><span data-stu-id="66df9-288">**Greg Young. What is a Domain Event?**
[*http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/*](http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/)</span></span>

-   <span data-ttu-id="66df9-289">**Jan Stenberg。Domain Events and Eventual Consistency**
    [*https://www.infoq.com/news/2015/09/domain-events-consistency*](https://www.infoq.com/news/2015/09/domain-events-consistency)（域事件和最终一致性）</span><span class="sxs-lookup"><span data-stu-id="66df9-289">**Jan Stenberg. Domain Events and Eventual Consistency**
[*https://www.infoq.com/news/2015/09/domain-events-consistency*](https://www.infoq.com/news/2015/09/domain-events-consistency)</span></span>

-   <span data-ttu-id="66df9-290">**Jimmy Bogard。A better domain events pattern**
    [*https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/*](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)（更好的域事件模式）</span><span class="sxs-lookup"><span data-stu-id="66df9-290">**Jimmy Bogard. A better domain events pattern**
[*https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/*](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)</span></span>

-   <span data-ttu-id="66df9-291">**Vaughn Vernon。Effective Aggregate Design Part II: Making Aggregates Work Together**
    [*http://dddcommunity.org/wp-content/uploads/files/pdf\_articles/Vernon\_2011\_2.pdf*](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)（高效聚合设计第二部：协同聚合）</span><span class="sxs-lookup"><span data-stu-id="66df9-291">**Vaughn Vernon. Effective Aggregate Design Part II: Making Aggregates Work Together**
[*http://dddcommunity.org/wp-content/uploads/files/pdf\_articles/Vernon\_2011\_2.pdf*](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)</span></span>

-   <span data-ttu-id="66df9-292">**Jimmy Bogard。Strengthening your domain: Domain Events**
    *<https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/>*（强化域：域事件）</span><span class="sxs-lookup"><span data-stu-id="66df9-292">**Jimmy Bogard. Strengthening your domain: Domain Events**
*<https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/> *</span></span>

-   <span data-ttu-id="66df9-293">**Tony Truong。Domain Events Pattern Example**
    [*https://www.tonytruong.net/domain-events-pattern-example/*](https://www.tonytruong.net/domain-events-pattern-example/)（域事件模式示例）</span><span class="sxs-lookup"><span data-stu-id="66df9-293">**Tony Truong. Domain Events Pattern Example**
[*https://www.tonytruong.net/domain-events-pattern-example/*](https://www.tonytruong.net/domain-events-pattern-example/)</span></span>

-   <span data-ttu-id="66df9-294">**Udi Dahan.How to create fully encapsulated Domain Models**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)（如何创建完全封装的域模型）</span><span class="sxs-lookup"><span data-stu-id="66df9-294">**Udi Dahan. How to create fully encapsulated Domain Models**
[*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span></span>

-   <span data-ttu-id="66df9-295">**Udi Dahan.Domain Events – Take 2**
    [*http://udidahan.com/2008/08/25/domain-events-take-2/*](http://udidahan.com/2008/08/25/domain-events-take-2/%20)（域事件 – 搞定两个问题）</span><span class="sxs-lookup"><span data-stu-id="66df9-295">**Udi Dahan. Domain Events – Take 2**
[*http://udidahan.com/2008/08/25/domain-events-take-2/*](http://udidahan.com/2008/08/25/domain-events-take-2/%20)</span></span>

-   <span data-ttu-id="66df9-296">**Udi Dahan.Domain Events – Salvation**
    [*http://udidahan.com/2009/06/14/domain-events-salvation/*](http://udidahan.com/2009/06/14/domain-events-salvation/)（域事件 – 救助）</span><span class="sxs-lookup"><span data-stu-id="66df9-296">**Udi Dahan. Domain Events – Salvation**
[*http://udidahan.com/2009/06/14/domain-events-salvation/*](http://udidahan.com/2009/06/14/domain-events-salvation/)</span></span>

-   <span data-ttu-id="66df9-297">**Jan Kronquist。Don't publish Domain Events, return them!**
    [*https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/*](https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/)（不要发布域事件，返回它们！）</span><span class="sxs-lookup"><span data-stu-id="66df9-297">**Jan Kronquist. Don't publish Domain Events, return them!**
[*https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/*](https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/)</span></span>

-   <span data-ttu-id="66df9-298">**Cesar de la Torre。Domain Events vs.Integration Events in DDD and microservices architectures**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/)（DDD 和微服务体系结构中的域事件和集成事件）</span><span class="sxs-lookup"><span data-stu-id="66df9-298">**Cesar de la Torre. Domain Events vs. Integration Events in DDD and microservices architectures**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="66df9-299">[Previous] (client-side-validation.md) [Next] (infrastructure-persistence-layer-design.md)</span><span class="sxs-lookup"><span data-stu-id="66df9-299">[Previous] (client-side-validation.md) [Next] (infrastructure-persistence-layer-design.md)</span></span>
