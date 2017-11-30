---
title: "域事件。 设计和实现"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |域事件、 设计和实现"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2d98b302be4ee72d8225526944fc3e41cbadcb5f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="domain-events-design-and-implementation"></a><span data-ttu-id="ce901-105">域事件： 设计和实现</span><span class="sxs-lookup"><span data-stu-id="ce901-105">Domain events: design and implementation</span></span>

<span data-ttu-id="ce901-106">使用域事件显式实现你的域中的更改的副作用。</span><span class="sxs-lookup"><span data-stu-id="ce901-106">Use domain events to explicitly implement side effects of changes within your domain.</span></span> <span data-ttu-id="ce901-107">在其他字，和使用 DDD 术语中，使用域事件显式实现跨多个聚合的副作用。</span><span class="sxs-lookup"><span data-stu-id="ce901-107">In other words, and using DDD terminology, use domain events to explicitly implement side effects across multiple aggregates.</span></span> <span data-ttu-id="ce901-108">（可选） 来更好的可伸缩性中数据库锁的影响更小，请使用在同一域中的聚合之间的最终一致性。</span><span class="sxs-lookup"><span data-stu-id="ce901-108">Optionally, for better scalability and less impact in database locks, use eventual consistency between aggregates within the same domain.</span></span>

## <a name="what-is-a-domain-event"></a><span data-ttu-id="ce901-109">什么是域事件？</span><span class="sxs-lookup"><span data-stu-id="ce901-109">What is a domain event?</span></span>

<span data-ttu-id="ce901-110">事件是发生在过去的内容。</span><span class="sxs-lookup"><span data-stu-id="ce901-110">An event is something that has happened in the past.</span></span> <span data-ttu-id="ce901-111">域事件，在逻辑上是，这发生在特定域中，并且你想同一个域 （进程内） 可以注意并可能做出响应的其他部分的内容。</span><span class="sxs-lookup"><span data-stu-id="ce901-111">A domain event is, logically, something that happened in a particular domain, and something you want other parts of the same domain (in-process) to be aware of and potentially react to.</span></span>

<span data-ttu-id="ce901-112">域事件的一个重要好处是，可以显式表示后出现了问题的域中的副作用而不是隐式。</span><span class="sxs-lookup"><span data-stu-id="ce901-112">An important benefit of domain events is that side effects after something happened in a domain can be expressed explicitly instead of implicitly.</span></span> <span data-ttu-id="ce901-113">效果必须一致，因此会发生的任何相关的所有操作的业务任务，这些端或其中任何一个。</span><span class="sxs-lookup"><span data-stu-id="ce901-113">Those side effects must be consistent so either all the operations related to the business task happen, or none of them.</span></span> <span data-ttu-id="ce901-114">此外，域事件启用在同一域中的类之间的问题的更好的隔离。</span><span class="sxs-lookup"><span data-stu-id="ce901-114">In addition, domain events enable a better separation of concerns among classes within the same domain.</span></span>

<span data-ttu-id="ce901-115">例如，如果你只需使用实体框架和实体或甚至聚合，如果必须有导致由用例的副作用，这些将作为实现耦合的代码中的一个隐式概念后出现了问题。</span><span class="sxs-lookup"><span data-stu-id="ce901-115">For example, if you are just using just Entity Framework and entities or even aggregates, if there have to be side effects provoked by a use case, those will be implemented as an implicit concept in the coupled code after something happened.</span></span> <span data-ttu-id="ce901-116">但是，如果你只需查看该代码，你可能不知道如果该代码 （副作用） 是在主系统操作的一部分，或如果它确实是会产生副作用。</span><span class="sxs-lookup"><span data-stu-id="ce901-116">But, if you just see that code, you might not know if that code (the side effect) is part of the main operation or if it really is a side effect.</span></span> <span data-ttu-id="ce901-117">另一方面，如果使用域事件使这一概念显式并无处不在的语言的一部分。</span><span class="sxs-lookup"><span data-stu-id="ce901-117">On the other hand, using domain events makes the concept explicit and part of the ubiquitous language.</span></span> <span data-ttu-id="ce901-118">例如，在 eShopOnContainers 应用程序，创建顺序是不只是关于的顺序;它更新，或创建基于原始的用户，buyer 聚合，因为直到就地没有订单后，用户不是购买者。</span><span class="sxs-lookup"><span data-stu-id="ce901-118">For example, in the eShopOnContainers application, creating an order is not just about the order; it updates or creates a buyer aggregate based on the original user, because the user is not a buyer until there is an order in place.</span></span> <span data-ttu-id="ce901-119">如果使用域事件时，你可以显式地表达无处不在提供的域专业人员的语言中基于该域规则。</span><span class="sxs-lookup"><span data-stu-id="ce901-119">If you use domain events, you can explicitly express that domain rule based in the ubiquitous language provided by the domain experts.</span></span>

<span data-ttu-id="ce901-120">域事件在某种程度上类似于消息样式事件，有一个重要的区别。</span><span class="sxs-lookup"><span data-stu-id="ce901-120">Domain events are somewhat similar to messaging-style events, with one important difference.</span></span> <span data-ttu-id="ce901-121">与实际的消息传送、 消息队列，消息代理或服务总线使用 AMPQ，一条消息会始终以异步方式发送，并跨进程和计算机进行通信。</span><span class="sxs-lookup"><span data-stu-id="ce901-121">With real messaging, message queuing, message brokers, or a service bus using AMPQ, a message is always sent asynchronously and communicated across processes and machines.</span></span> <span data-ttu-id="ce901-122">这可用于将多个绑定的上下文、 微服务或甚至不同的应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="ce901-122">This is useful for integrating multiple Bounded Contexts, microservices, or even different applications.</span></span> <span data-ttu-id="ce901-123">但是，使用域事件，你想要从当前正在运行，域操作中引发事件，但你想在同一个域内任何副作用。</span><span class="sxs-lookup"><span data-stu-id="ce901-123">However, with domain events, you want to raise an event from the domain operation you are currently running, but you want any side effects to occur within the same domain.</span></span>

<span data-ttu-id="ce901-124">域事件和其副作用 （操作之后触发管理的事件处理程序） 应几乎会立即发生，通常在进程，并在同一域中。</span><span class="sxs-lookup"><span data-stu-id="ce901-124">The domain events and their side effects (the actions triggered afterwards that are managed by event handlers) should occur almost immediately, usually in-process, and within the same domain.</span></span> <span data-ttu-id="ce901-125">因此，域事件可以同步或异步。</span><span class="sxs-lookup"><span data-stu-id="ce901-125">Thus, domain events could be synchronous or asynchronous.</span></span> <span data-ttu-id="ce901-126">集成事件，但是，应始终是异步的。</span><span class="sxs-lookup"><span data-stu-id="ce901-126">Integration events, however, should always be asynchronous.</span></span>

## <a name="domain-events-versus-integration-events"></a><span data-ttu-id="ce901-127">与集成事件域事件</span><span class="sxs-lookup"><span data-stu-id="ce901-127">Domain events versus integration events</span></span>

<span data-ttu-id="ce901-128">在语义上，域和集成事件是相同的操作： 有关某些刚刚发生的通知。</span><span class="sxs-lookup"><span data-stu-id="ce901-128">Semantically, domain and integration events are the same thing: notifications about something that just happened.</span></span> <span data-ttu-id="ce901-129">但是，其实现必须不同。</span><span class="sxs-lookup"><span data-stu-id="ce901-129">However, their implementation must be different.</span></span> <span data-ttu-id="ce901-130">域事件是只是消息推送到就可以实现基于 IoC 容器或任何其他方法中内存中介为域事件调度程序。</span><span class="sxs-lookup"><span data-stu-id="ce901-130">Domain events are just messages pushed to a domain event dispatcher, which could be implemented as an in-memory mediator based on an IoC container or any other method.</span></span>

<span data-ttu-id="ce901-131">另一方面，集成事件的目的是传播已提交的事务和更新到其他子系统，无论它们是其他微服务、 绑定上下文或甚至外部应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce901-131">On the other hand, the purpose of integration events is to propagate committed transactions and updates to additional subsystems, whether they are other microservices, Bounded Contexts or even external applications.</span></span> <span data-ttu-id="ce901-132">因此，它们应仅当成功保留该实体，因为在许多情况下如果失败，整个操作有效地永远不会发生。</span><span class="sxs-lookup"><span data-stu-id="ce901-132">Hence, they should occur only if the entity is successfully persisted, since in many scenarios if this fails, the entire operation effectively never happened.</span></span>

<span data-ttu-id="ce901-133">此外，并作为提到的那样，集成事件必须基于多个微服务 （其他绑定上下文中） 或甚至外部系统/应用程序之间进行异步通信。</span><span class="sxs-lookup"><span data-stu-id="ce901-133">In addition, and as mentioned, integration events must be based on asynchronous communication between multiple microservices (other Bounded Contexts) or even external systems/applications.</span></span> <span data-ttu-id="ce901-134">因此，事件总线接口需要一些基础结构允许间进程并分发可能远程服务之间的通信。</span><span class="sxs-lookup"><span data-stu-id="ce901-134">Thus, the event bus interface needs some infrastructure that allows inter-process and distributed communication between potentially remote services.</span></span> <span data-ttu-id="ce901-135">它可以基于商业服务总线、 队列、 应用作的邮箱的共享的数据库或任何其他分发，理想情况下推基于消息的系统。</span><span class="sxs-lookup"><span data-stu-id="ce901-135">It can be based on a commercial service bus, queues, a shared database used as a mailbox, or any other distributed and ideally push based messaging system.</span></span>

## <a name="domain-events-as-a-preferred-way-to-trigger-side-effects-across-multiple-aggregates-within-the-same-domain"></a><span data-ttu-id="ce901-136">在同一域中的多个聚合跨触发副作用的首选方法作为域事件</span><span class="sxs-lookup"><span data-stu-id="ce901-136">Domain events as a preferred way to trigger side effects across multiple aggregates within the same domain</span></span>

<span data-ttu-id="ce901-137">如果执行命令与一个聚合实例需要在一个或多个其他聚合上运行的其他域规则，你应设计和实现由域事件触发这些副作用。</span><span class="sxs-lookup"><span data-stu-id="ce901-137">If executing a command related to one aggregate instance requires additional domain rules to be run on one or more additional aggregates, you should design and implement those side effects to be triggered by domain events.</span></span> <span data-ttu-id="ce901-138">如图所示在图 9-14，以及为管理员的最重要用例，应使用域事件通过相同的域模型中的多个聚合传播状态更改。</span><span class="sxs-lookup"><span data-stu-id="ce901-138">As shown in Figure 9-14, and as one of the most important use cases, a domain event should be used to propagate state changes across multiple aggregates within the same domain model.</span></span>

![](./media/image15.png)

<span data-ttu-id="ce901-139">**图 9-14**。</span><span class="sxs-lookup"><span data-stu-id="ce901-139">**Figure 9-14**.</span></span> <span data-ttu-id="ce901-140">若要强制在同一域中的多个聚合之间的一致性的域事件</span><span class="sxs-lookup"><span data-stu-id="ce901-140">Domain events to enforce consistency between multiple aggregates within the same domain</span></span>

<span data-ttu-id="ce901-141">在图中，当用户启动顺序，OrderStarted 域事件会触发 Buyer 对象中排序 microservice，基于标识微服务构成从原始的用户信息 （与 CreateOrder 命令中提供的信息） 创建。</span><span class="sxs-lookup"><span data-stu-id="ce901-141">In the figure, when the user initiates an order, the OrderStarted domain event triggers creation of a Buyer object in the ordering microservice, based on the original user info from the identity microservice (with information provided in the CreateOrder command).</span></span> <span data-ttu-id="ce901-142">创建第一个位置时，将通过顺序聚合生成域事件。</span><span class="sxs-lookup"><span data-stu-id="ce901-142">The domain event is generated by the order aggregate when it is created in the first place.</span></span>

<span data-ttu-id="ce901-143">或者，你可以引发其聚合 （子实体） 的成员的事件订阅的聚合根。</span><span class="sxs-lookup"><span data-stu-id="ce901-143">Alternately, you can have the aggregate root subscribed for events raised by members of its aggregates (child entities).</span></span> <span data-ttu-id="ce901-144">例如，每个 OrderItem 子实体可以引发事件时项目价格高于特定量，或产品项目金额过高时。</span><span class="sxs-lookup"><span data-stu-id="ce901-144">For instance, each OrderItem child entity can raise an event when the item price is higher than a specific amount, or when the product item amount is too high.</span></span> <span data-ttu-id="ce901-145">然后，聚合根可以接收这些事件，并执行全局计算或聚合。</span><span class="sxs-lookup"><span data-stu-id="ce901-145">The aggregate root can then receive those events and perform a global calculation or aggregation.</span></span>

<span data-ttu-id="ce901-146">务必了解此基于事件的通信不直接在聚合; 内实现你需要实现域事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ce901-146">It is important to understand that this event-based communication is not implemented directly within the aggregates; you need to implement domain event handlers.</span></span> <span data-ttu-id="ce901-147">处理域事件是，一个应用程序的问题。</span><span class="sxs-lookup"><span data-stu-id="ce901-147">Handling the domain events is an application concern.</span></span> <span data-ttu-id="ce901-148">域模型层应只需关注的域逻辑-域专家理解的方面，不应用程序基础结构使用存储库的副作用的持久性操作处理程序等。</span><span class="sxs-lookup"><span data-stu-id="ce901-148">The domain model layer should only focus on the domain logic—things that a domain expert would understand, not application infrastructure like handlers and side-effect persistence actions using repositories.</span></span> <span data-ttu-id="ce901-149">因此，应用程序层级别是其中应具有域事件处理程序引发域事件时触发的操作。</span><span class="sxs-lookup"><span data-stu-id="ce901-149">Therefore, the application layer level is where you should have domain event handlers triggering actions when a domain event is raised.</span></span>

<span data-ttu-id="ce901-150">域事件还可用于触发任意数量的应用程序操作，并且更重要，必须打开要分离的方式提高该数字在将来。</span><span class="sxs-lookup"><span data-stu-id="ce901-150">Domain events can also be used to trigger any number of application actions, and what is more important, must be open to increase that number in the future in a decoupled way.</span></span> <span data-ttu-id="ce901-151">例如，当启动顺序时，你可能想要发布的域事件传播到其他聚合该信息，或甚至以引发通知之类的应用程序操作。</span><span class="sxs-lookup"><span data-stu-id="ce901-151">For instance, when the order is started, you might want to publish a domain event to propagate that info to other aggregates or even to raise application actions like notifications.</span></span>

<span data-ttu-id="ce901-152">关键在于打开域事件发生时要执行的操作的数量。</span><span class="sxs-lookup"><span data-stu-id="ce901-152">The key point is the open number of actions to be executed when a domain event occurs.</span></span> <span data-ttu-id="ce901-153">最后，将增长的操作和中的域和应用程序的规则。</span><span class="sxs-lookup"><span data-stu-id="ce901-153">Eventually, the actions and rules in the domain and application will grow.</span></span> <span data-ttu-id="ce901-154">复杂性或多个副作用的操作发生一些事情时将变大，但如果你的代码已结合"粘附"(即，只需实例化对象与在 C 中的新关键字\#)，然后，每次您需要添加新操作时你将需要更改的原始代码。</span><span class="sxs-lookup"><span data-stu-id="ce901-154">The complexity or number of side-effect actions when something happens will grow, but if your code were coupled with “glue” (that is, just instantiating objects with the new keyword in C\#), then every time you needed to add a new action you would need to change the original code.</span></span> <span data-ttu-id="ce901-155">因为与每个新的需求，你将需要更改原始代码流，这将导致新 bug 中。</span><span class="sxs-lookup"><span data-stu-id="ce901-155">This could result in new bugs, because with each new requirement you would need to change the original code flow.</span></span> <span data-ttu-id="ce901-156">这有违[打开/关闭原则](https://en.wikipedia.org/wiki/Open/closed_principle)从[纯色](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design))。</span><span class="sxs-lookup"><span data-stu-id="ce901-156">This goes against the [Open/Closed principle](https://en.wikipedia.org/wiki/Open/closed_principle) from [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)).</span></span> <span data-ttu-id="ce901-157">不仅如此，已安排操作原始类将增加和增长，这有违[单个责任原则 (SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle)。</span><span class="sxs-lookup"><span data-stu-id="ce901-157">Not only that, the original class that was orchestrating the operations would grow and grow, which goes against the [Single Responsibility Principle (SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle).</span></span>

<span data-ttu-id="ce901-158">另一方面，如果你使用域事件，你可以通过将隔开职责使用此方法创建细粒度的并且分离实现：</span><span class="sxs-lookup"><span data-stu-id="ce901-158">On the other hand, if you use domain events, you can create a fine-grained and decoupled implementation by segregating responsibilities using this approach:</span></span>

1.  <span data-ttu-id="ce901-159">发送一条命令 (例如，CreateOrder)。</span><span class="sxs-lookup"><span data-stu-id="ce901-159">Send a command (for example, CreateOrder).</span></span>
2.  <span data-ttu-id="ce901-160">命令处理程序中接收命令。</span><span class="sxs-lookup"><span data-stu-id="ce901-160">Receive the command in a command handler.</span></span>
    -   <span data-ttu-id="ce901-161">执行单个聚合的事务。</span><span class="sxs-lookup"><span data-stu-id="ce901-161">Execute a single aggregate’s transaction.</span></span>
    -   <span data-ttu-id="ce901-162">（可选）引发副作用 (例如，OrderStartedDomainDvent) 的域事件。</span><span class="sxs-lookup"><span data-stu-id="ce901-162">(Optional) Raise domain events for side effects (for example, OrderStartedDomainDvent).</span></span>
1.  <span data-ttu-id="ce901-163">句柄域 （在当前进程中） 的事件 thast 会在多个聚合或应用程序操作中执行的打开副作用数目。</span><span class="sxs-lookup"><span data-stu-id="ce901-163">Handle domain events (within the current process) thast will execute an open number of side effects in multiple aggregates or application actions.</span></span> <span data-ttu-id="ce901-164">例如: </span><span class="sxs-lookup"><span data-stu-id="ce901-164">For example:</span></span>
    -   <span data-ttu-id="ce901-165">验证或创建购买者和付款方法。</span><span class="sxs-lookup"><span data-stu-id="ce901-165">Verify or create buyer and payment method.</span></span>
    -   <span data-ttu-id="ce901-166">创建并将相关的集成事件发送到事件总线通过向买家发送一封电子邮件之类的微服务或触发器外部操作传播状态。</span><span class="sxs-lookup"><span data-stu-id="ce901-166">Create and send a related integration event to the event bus to propagate states across microservices or trigger external actions like sending an email to the buyer.</span></span>
    -   <span data-ttu-id="ce901-167">处理其他副作用。</span><span class="sxs-lookup"><span data-stu-id="ce901-167">Handle other side effects.</span></span>

<span data-ttu-id="ce901-168">如所示图 9-15，从同一域事件中，你可以处理与其他域或你需要执行跨微服务使用集成事件和事件总线连接的其他应用程序操作中的聚合相关的多个操作。</span><span class="sxs-lookup"><span data-stu-id="ce901-168">As shown in Figure 9-15, starting from the same domain event, you can handle multiple actions related to other aggregates in the domain or additional application actions you need to perform across microservices connecting with integration events and the event bus.</span></span>

![](./media/image16.png)

<span data-ttu-id="ce901-169">**图 9-15**。</span><span class="sxs-lookup"><span data-stu-id="ce901-169">**Figure 9-15**.</span></span> <span data-ttu-id="ce901-170">处理每个域的多个操作</span><span class="sxs-lookup"><span data-stu-id="ce901-170">Handling multiple actions per domain</span></span>

<span data-ttu-id="ce901-171">事件处理程序通常是在应用程序层中，因为你将使用基础结构对象，如存储库或应用程序 API 微服务的行为。</span><span class="sxs-lookup"><span data-stu-id="ce901-171">The event handlers are typically in the application layer, because you will use infrastructure objects like repositories or an application API for the microservice’s behavior.</span></span> <span data-ttu-id="ce901-172">这种意义上，事件处理程序类似于命令处理程序，因此两者都在应用程序层的一部分。</span><span class="sxs-lookup"><span data-stu-id="ce901-172">In that sense, event handlers are similar to command handlers, so both are part of the application layer.</span></span> <span data-ttu-id="ce901-173">重要的区别是，应只需一次处理多个命令。</span><span class="sxs-lookup"><span data-stu-id="ce901-173">The important difference is that a command should be processed just once.</span></span> <span data-ttu-id="ce901-174">域事件可能处理零或 *n* 超时，因为如果可由多个接收方或具有每个处理程序不同的用途的事件处理程序接收。</span><span class="sxs-lookup"><span data-stu-id="ce901-174">A domain event could be processed zero or *n* times, because if can be received by multiple receivers or event handlers with a different purpose for each handler.</span></span>

<span data-ttu-id="ce901-175">打开每个域事件处理程序数的可能性，可添加许多其他域规则而不会影响你当前的代码。</span><span class="sxs-lookup"><span data-stu-id="ce901-175">The possibility of an open number of handlers per domain event allows you to add many more domain rules without impacting your current code.</span></span> <span data-ttu-id="ce901-176">例如，实现必须发生的事件之后的右侧的以下业务规则可以是简单地添加几个事件处理程序 （或即使只是一个）：</span><span class="sxs-lookup"><span data-stu-id="ce901-176">For instance, implementing the following business rule that has to happen right after an event might be as easy as adding a few event handlers (or even just one):</span></span>

<span data-ttu-id="ce901-177">当跨任意数量的订单，通过存储中的客户购买的总金额超过 6000 美元时，适用于每个新的订单的 10%的折扣并通知该折扣将来订单有关的电子邮件的客户。</span><span class="sxs-lookup"><span data-stu-id="ce901-177">When the total amount purchased by a customer in the store, across any number of orders, exceeds $6,000, apply a 10% off discount to every new order and notify the customer with an email about that discount for future orders.</span></span>

## <a name="implementing-domain-events"></a><span data-ttu-id="ce901-178">实现域事件</span><span class="sxs-lookup"><span data-stu-id="ce901-178">Implementing domain events</span></span>

<span data-ttu-id="ce901-179">在 C# 中，域事件只是数据保持的结构或类，如 DTO，与所有相关发生在域中，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="ce901-179">In C#, a domain event is simply a data-holding structure or class, like a DTO, with all the information related to what just happened in the domain, as shown in the following example:</span></span>

```csharp
public class OrderStartedDomainEvent : IAsyncNotification
{
    public int CardTypeId { get; private set; }
    public string CardNumber { get; private set; }
    public string CardSecurityNumber { get; private set; }
    public string CardHolderName { get; private set; }
    public DateTime CardExpiration { get; private set; }
    public Order Order { get; private set; }

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

<span data-ttu-id="ce901-180">这是实质上是一个包含与 OrderStarted 事件相关的所有数据的类。</span><span class="sxs-lookup"><span data-stu-id="ce901-180">This is essentially a class that holds all the data related to the OrderStarted event.</span></span>

<span data-ttu-id="ce901-181">根据无处不在域的语言，因为事件是指发生在过去，事件的类名称应表示为过去时谓词，如 OrderStartedDomainEvent 或 OrderShippedDomainEvent。</span><span class="sxs-lookup"><span data-stu-id="ce901-181">In terms of the ubiquitous language of the domain, since an event is something that happened in the past, the class name of the event should be represented as a past-tense verb, like OrderStartedDomainEvent or OrderShippedDomainEvent.</span></span> <span data-ttu-id="ce901-182">这是如何在中 eShopOnContainers 排序微服务中实现域事件。</span><span class="sxs-lookup"><span data-stu-id="ce901-182">That is how the domain event is implemented in the ordering microservice in eShopOnContainers.</span></span>

<span data-ttu-id="ce901-183">我们前面提到，事件的一个重要特性是由于事件是发生在过去，它不应更改的内容。</span><span class="sxs-lookup"><span data-stu-id="ce901-183">As we have noted, an important characteristic of events is that since an event is something that happened in the past, it should not change.</span></span> <span data-ttu-id="ce901-184">因此，它必须是一个不可变的类。</span><span class="sxs-lookup"><span data-stu-id="ce901-184">Therefore it must be an immutable class.</span></span> <span data-ttu-id="ce901-185">你可以看到在上面的属性是只读的从外部对象的代码。</span><span class="sxs-lookup"><span data-stu-id="ce901-185">You can see in the preceding code that the properties are read-only from outside of the object.</span></span> <span data-ttu-id="ce901-186">在创建事件对象时，可以更新的对象的唯一方法是通过构造函数。</span><span class="sxs-lookup"><span data-stu-id="ce901-186">The only way to update the object is through the constructor when you create the event object.</span></span>

### <a name="raising-domain-events"></a><span data-ttu-id="ce901-187">引发域事件</span><span class="sxs-lookup"><span data-stu-id="ce901-187">Raising domain events</span></span>

<span data-ttu-id="ce901-188">下一个问题是如何引发域的事件，因此它达到其相关的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ce901-188">The next question is how to raise a domain event so it reaches its related event handlers.</span></span> <span data-ttu-id="ce901-189">你可以使用多个方法。</span><span class="sxs-lookup"><span data-stu-id="ce901-189">You can use multiple approaches.</span></span>

<span data-ttu-id="ce901-190">Udi Dahan 最初建议 (例如，在多个相关文章，如[域事件 – 执行 2](http://udidahan.com/2008/08/25/domain-events-take-2/)) 用于管理和引发事件的静态类。</span><span class="sxs-lookup"><span data-stu-id="ce901-190">Udi Dahan originally proposed (for example, in several related posts, such as [Domain Events – Take 2](http://udidahan.com/2008/08/25/domain-events-take-2/)) using a static class for managing and raising the events.</span></span> <span data-ttu-id="ce901-191">这可能包括名为 DomainEvents 将域时引发事件立即调用该实例，使用 DomainEvents.Raise (事件 myEvent) 类似的语法的静态类。</span><span class="sxs-lookup"><span data-stu-id="ce901-191">This might include a static class named DomainEvents that would raise domain events immediately when it is called, using syntax like DomainEvents.Raise(Event myEvent).</span></span> <span data-ttu-id="ce901-192">Jimmy Bogard 编写博客文章 ([增强你的域： 域事件](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/)) 建议类似的方法。</span><span class="sxs-lookup"><span data-stu-id="ce901-192">Jimmy Bogard wrote a blog post ([Strengthening your domain: Domain Events](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/)) that recommends a similar approach.</span></span>

<span data-ttu-id="ce901-193">但是，如果域事件类是静态的它还将调度给处理程序立即。</span><span class="sxs-lookup"><span data-stu-id="ce901-193">However, when the domain events class is static, it also dispatches to handlers immediately.</span></span> <span data-ttu-id="ce901-194">这使得测试和调试更加困难，因为引发该事件后立即执行负面影响逻辑的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ce901-194">This makes testing and debugging more difficult, because the event handlers with side-effects logic are executed immediately after the event is raised.</span></span> <span data-ttu-id="ce901-195">当你测试和调试时，你想专注于并仅发生了什么情况中当前聚合类;您不想要突然重定向到其他事件处理程序与其他聚合或应用程序逻辑相关的副作用。</span><span class="sxs-lookup"><span data-stu-id="ce901-195">When you are testing and debugging, you want to focus on and just what is happening in the current aggregate classes; you do not want to suddenly be redirected to other event handlers for side effects related to other aggregates or application logic.</span></span> <span data-ttu-id="ce901-196">这就是原因已演变其他方法，如在下一部分中所述。</span><span class="sxs-lookup"><span data-stu-id="ce901-196">This is why other approaches have evolved, as explained in the next section.</span></span>

#### <a name="the-deferred-approach-for-raising-and-dispatching-events"></a><span data-ttu-id="ce901-197">引发和调度事件延迟的方法</span><span class="sxs-lookup"><span data-stu-id="ce901-197">The deferred approach for raising and dispatching events</span></span>

<span data-ttu-id="ce901-198">更好的方法是将域事件添加到集合而不是立即调度给域事件处理程序，然后调度这些域事件*靠右侧*或*右* *后*（与 EF 中的 SaveChanges) 提交事务。</span><span class="sxs-lookup"><span data-stu-id="ce901-198">Instead of dispatching to a domain event handler immediately, a better approach is to add the domain events to a collection and then to dispatch those domain events *right before* or *right* *after* committing the transaction (as with SaveChanges in EF).</span></span> <span data-ttu-id="ce901-199">(这种方法中此文章 Jimmy Bogard 所述[更好的域事件模式](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)。)</span><span class="sxs-lookup"><span data-stu-id="ce901-199">(This approach was described by Jimmy Bogard in this post [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/).)</span></span>

<span data-ttu-id="ce901-200">决定你是否将域事件发送后提交事务之前或向右立即很重要，因为它将确定是否将作为同一事务的或在不同事务中的一部分包括副作用。</span><span class="sxs-lookup"><span data-stu-id="ce901-200">Deciding if you send the domain events right before or right after committing the transaction is important, since it determines whether you will include the side effects as part of the same transaction or in different transactions.</span></span> <span data-ttu-id="ce901-201">在后一种情况，你需要跨多个聚合处理最终一致性。</span><span class="sxs-lookup"><span data-stu-id="ce901-201">In the latter case, you need to deal with eventual consistency across multiple aggregates.</span></span> <span data-ttu-id="ce901-202">本主题将在下一部分中讨论。</span><span class="sxs-lookup"><span data-stu-id="ce901-202">This topic is discussed in the next section.</span></span>

<span data-ttu-id="ce901-203">延迟的方法是何种 eShopOnContainers 使用。</span><span class="sxs-lookup"><span data-stu-id="ce901-203">The deferred approach is what eShopOnContainers uses.</span></span> <span data-ttu-id="ce901-204">首先，你添加到集合或列表的每个实体的事件实体中发生的事件。</span><span class="sxs-lookup"><span data-stu-id="ce901-204">First, you add the events happening in your entities into a collection or list of events per entity.</span></span> <span data-ttu-id="ce901-205">该列表应为属于实体对象，或甚至更好地，基实体类的一部分，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="ce901-205">That list should be part of the entity object, or even better, part of your base entity class, as shown in the following example:</span></span>

```csharp
public abstract class Entity
{
    private List<IAsyncNotification> _domainEvents;

    public List<IAsyncNotification> DomainEvents => _domainEvents;

    public void AddDomainEvent(IAsyncNotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<IAsyncNotification>();
        _domainEvents.Add(eventItem);
    }

    public void RemoveDomainEvent(IAsyncNotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }
    // ...
}
```

<span data-ttu-id="ce901-206">如果你想要引发事件，你只需将其添加到要将放在聚合实体方法，如以下代码所示的事件集合：</span><span class="sxs-lookup"><span data-stu-id="ce901-206">When you want to raise an event, you just add it to the event collection to be placed within an aggregate entity method, as the following code shows:</span></span>

```csharp
var orderStartedDomainEvent = new OrderStartedDomainEvent(this, //Order object
    cardTypeId,
    cardNumber,
    cardSecurityNumber,
    cardHolderName,
    cardExpiration);
this.AddDomainEvent(orderStartedDomainEvent);
```

<span data-ttu-id="ce901-207">请注意只能执行 AddDomainEvent 方法将事件添加到列表。</span><span class="sxs-lookup"><span data-stu-id="ce901-207">Notice that the only thing that the AddDomainEvent method is doing is adding an event to the list.</span></span> <span data-ttu-id="ce901-208">尚未，会引发任何事件，并且尚未调用任何事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ce901-208">No event is raised yet, and no event handler is invoked yet.</span></span>

<span data-ttu-id="ce901-209">您确实想要更高版本上调度事件，如果提交到数据库事务。</span><span class="sxs-lookup"><span data-stu-id="ce901-209">You actually want to dispatch the events later on, when you commit the transaction to the database.</span></span> <span data-ttu-id="ce901-210">如果使用实体框架核心，这意味着你 EF DbContext，如以下代码所示的 SaveChanges 方法中：</span><span class="sxs-lookup"><span data-stu-id="ce901-210">If you are using Entity Framework Core, that means in the SaveChanges method of your EF DbContext, as in the following code:</span></span>

```csharp
// EF Core DbContext
public class OrderingContext : DbContext, IUnitOfWork
{
    // ...
    public async Task<int> SaveEntitiesAsync()
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

<span data-ttu-id="ce901-211">使用此代码中，你调度到其相应的事件处理程序的实体事件。</span><span class="sxs-lookup"><span data-stu-id="ce901-211">With this code, you dispatch the entity events to their respective event handlers.</span></span>

<span data-ttu-id="ce901-212">总结果是，你具有 （到内存中的列表添加一个简单） 域事件的引发从分离调度到事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ce901-212">The overall result is that you have decoupled the raising of a domain event (a simple add into a list in memory) from dispatching it to an event handler.</span></span> <span data-ttu-id="ce901-213">此外，具体取决于你使用哪种类型的调度程序，你无法调度事件，同步或异步。</span><span class="sxs-lookup"><span data-stu-id="ce901-213">In addition, depending on what kind of dispatcher you are using, you could dispatch the events synchronously or asynchronously.</span></span>

<span data-ttu-id="ce901-214">请注意这里扮演进入重要的事务边界。</span><span class="sxs-lookup"><span data-stu-id="ce901-214">Be aware that transactional boundaries come into significant play here.</span></span> <span data-ttu-id="ce901-215">如果你的工作和事务的单元可以跨多个聚合 （如使用 EF 核心应用程序和关系数据库时），这可以很好地。</span><span class="sxs-lookup"><span data-stu-id="ce901-215">If your unit of work and transaction can span more than one aggregate (as when using EF Core and a relational database), this can work well.</span></span> <span data-ttu-id="ce901-216">但是，如果事务不能跨越聚合，例如，当你将使用 Azure DocumentDB 等 NoSQL 数据库，你必须以实现额外的步骤，以实现一致性。</span><span class="sxs-lookup"><span data-stu-id="ce901-216">But if the transaction cannot span aggregates, such as when you are using a NoSQL database like Azure DocumentDB, you have to implement additional steps to achieve consistency.</span></span> <span data-ttu-id="ce901-217">这是为什么持久性无感知不是通用; 的另一个原因它依赖于您使用的存储系统。</span><span class="sxs-lookup"><span data-stu-id="ce901-217">This is another reason why persistence ignorance is not universal; it depends on the storage system you use.</span></span>

### <a name="single-transaction-across-aggregates-versus-eventual-consistency-across-aggregates"></a><span data-ttu-id="ce901-218">与跨聚合的最终一致性的聚合在单个事务</span><span class="sxs-lookup"><span data-stu-id="ce901-218">Single transaction across aggregates versus eventual consistency across aggregates</span></span>

<span data-ttu-id="ce901-219">这一问题是否与依赖于最终一致性跨这些聚合的聚合跨执行单个事务是一个很有争议。</span><span class="sxs-lookup"><span data-stu-id="ce901-219">The question of whether to perform a single transaction across aggregates versus relying on eventual consistency across those aggregates is a controversial one.</span></span> <span data-ttu-id="ce901-220">许多 DDD 作者像 Eric Evans 和 Vaughn Vernon 提倡规则该一个事务 = 一个聚合，因此在聚合对象需要考虑最终一致性。</span><span class="sxs-lookup"><span data-stu-id="ce901-220">Many DDD authors like Eric Evans and Vaughn Vernon advocate the rule that one transaction = one aggregate and therefore argue for eventual consistency across aggregates.</span></span> <span data-ttu-id="ce901-221">例如，在书籍*Domain-Driven 设计*，Eric Evans 的说明如下：</span><span class="sxs-lookup"><span data-stu-id="ce901-221">For example, in his book *Domain-Driven Design*, Eric Evans says this:</span></span>

<span data-ttu-id="ce901-222">跨越聚合任何规则不将需要在任何时候都保持最新。</span><span class="sxs-lookup"><span data-stu-id="ce901-222">Any rule that spans Aggregates will not be expected to be up-to-date at all times.</span></span> <span data-ttu-id="ce901-223">通过事件处理、 批处理或其他更新机制，其他依赖关系可以在某些特定的时间内进行解析。</span><span class="sxs-lookup"><span data-stu-id="ce901-223">Through event processing, batch processing, or other update mechanisms, other dependencies can be resolved within some specific time.</span></span> <span data-ttu-id="ce901-224">(pg。</span><span class="sxs-lookup"><span data-stu-id="ce901-224">(pg.</span></span> <span data-ttu-id="ce901-225">128)</span><span class="sxs-lookup"><span data-stu-id="ce901-225">128)</span></span>

<span data-ttu-id="ce901-226">Vaughn Vernon 显示以下消息的中[有效的聚合设计。第二部分： 进行聚合工作一起](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf):</span><span class="sxs-lookup"><span data-stu-id="ce901-226">Vaughn Vernon says the following in [Effective Aggregate Design. Part II: Making Aggregates Work Together](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf):</span></span>

<span data-ttu-id="ce901-227">因此，如果其中一个聚合实例需要更多的业务规则执行上一个或多个聚合上执行命令，使用最终一致性\[...\]没有切实可行的方法，以支持 DDD 模型中的最终一致性。</span><span class="sxs-lookup"><span data-stu-id="ce901-227">Thus, if executing a command on one aggregate instance requires that additional business rules execute on one or more aggregates, use eventual consistency \[...\] There is a practical way to support eventual consistency in a DDD model.</span></span> <span data-ttu-id="ce901-228">聚合方法发布时间传递到一个或多个异步订阅服务器的域事件。</span><span class="sxs-lookup"><span data-stu-id="ce901-228">An aggregate method publishes a domain event that is in time delivered to one or more asynchronous subscribers.</span></span>

<span data-ttu-id="ce901-229">持有这种观点基于接纳细化事务而不是跨越多个聚合或实体的事务。</span><span class="sxs-lookup"><span data-stu-id="ce901-229">This rationale is based on embracing fine-grained transactions instead of transactions spanning many aggregates or entities.</span></span> <span data-ttu-id="ce901-230">思路是在第二种情况，数据库锁的数目将是大量在大型应用程序具有高可伸缩性的需要。</span><span class="sxs-lookup"><span data-stu-id="ce901-230">The idea is that in the second case, the number of database locks will be substantial in large-scale applications with high scalability needs.</span></span> <span data-ttu-id="ce901-231">使用高可扩展的应用程序需要具有多个聚合之间的即时事务一致性事实帮助接受最终一致性的概念。</span><span class="sxs-lookup"><span data-stu-id="ce901-231">Embracing the fact that high-scalable applications need not have instant transactional consistency between multiple aggregates helps with accepting the concept of eventual consistency.</span></span> <span data-ttu-id="ce901-232">原子更改通常不需要由业务，而它在任何情况下是域专家说或不特定操作是否需要原子事务的责任。</span><span class="sxs-lookup"><span data-stu-id="ce901-232">Atomic changes are often not needed by the business, and it is in any case the responsibility of the domain experts to say whether particular operations need atomic transactions or not.</span></span> <span data-ttu-id="ce901-233">如果操作始终需要多个聚合之间原子事务，可能会要求你聚合是否应为更大或不正确设计。</span><span class="sxs-lookup"><span data-stu-id="ce901-233">If an operation always needs an atomic transaction between multiple aggregates, you might ask whether your aggregate should be larger or was not correctly designed.</span></span>

<span data-ttu-id="ce901-234">但是，其他开发人员和架构师如 Jimmy Bogard 被认为可以跨多个聚合跨越单个事务，但仅当这些其他的聚合相关的同一个原始命令的副作用。</span><span class="sxs-lookup"><span data-stu-id="ce901-234">However, other developers and architects like Jimmy Bogard are okay with spanning a single transaction across several aggregates—but only when those additional aggregates are related to side effects for the same original command.</span></span> <span data-ttu-id="ce901-235">例如，在[更好的域事件模式](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)，Bogard 的说明如下：</span><span class="sxs-lookup"><span data-stu-id="ce901-235">For instance, in [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/), Bogard says this:</span></span>

<span data-ttu-id="ce901-236">通常情况下，我想域事件发生在相同的逻辑事务，但不是一定引发域事件的相同作用域中的副作用\[...\]我们只需提交我们事务之前，我们将调度我们事件写入其各自的处理程序。</span><span class="sxs-lookup"><span data-stu-id="ce901-236">Typically, I want the side effects of a domain event to occur within the same logical transaction, but not necessarily in the same scope of raising the domain event \[...\] Just before we commit our transaction, we dispatch our events to their respective handlers.</span></span>

<span data-ttu-id="ce901-237">如果调度域事件右*之前*提交原来的事务，这是因为你想要在同一事务中包括这些事件的副作用。</span><span class="sxs-lookup"><span data-stu-id="ce901-237">If you dispatch the domain events right *before* committing the original transaction, it is because you want the side effects of those events to be included in the same transaction.</span></span> <span data-ttu-id="ce901-238">例如，如果 EF DbContext SaveChanges 方法失败，事务将回滚所有更改，包括由相关的域事件处理程序实现任何副作用操作的结果。</span><span class="sxs-lookup"><span data-stu-id="ce901-238">For example, if the EF DbContext SaveChanges method fails, the transaction will roll back all changes, including the result of any side effect operations implemented by the related domain event handlers.</span></span> <span data-ttu-id="ce901-239">这是因为 DbContext 生命作用域是默认情况下定义为"作用域。"</span><span class="sxs-lookup"><span data-stu-id="ce901-239">This is because the DbContext life scope is by default defined as "scoped."</span></span> <span data-ttu-id="ce901-240">因此，DbContext 对象被共享跨多个存储库对象进行实例化，在同一作用域或对象图中。</span><span class="sxs-lookup"><span data-stu-id="ce901-240">Therefore, the DbContext object is shared across multiple repository objects being instantiated within the same scope or object graph.</span></span> <span data-ttu-id="ce901-241">这与一致的 HttpRequest 作用域开发 Web API 或 MVC 的应用时。</span><span class="sxs-lookup"><span data-stu-id="ce901-241">This coincides with the HttpRequest scope when developing Web API or MVC apps.</span></span>

<span data-ttu-id="ce901-242">实际上，这两种方法 （单个原子事务和最终一致性） 可以是右。</span><span class="sxs-lookup"><span data-stu-id="ce901-242">In reality, both approaches (single atomic transaction and eventual consistency) can be right.</span></span> <span data-ttu-id="ce901-243">它实际上取决域或业务要求以及什么域专家告诉你。</span><span class="sxs-lookup"><span data-stu-id="ce901-243">It really depends on your domain or business requirements and what the domain experts tell you.</span></span> <span data-ttu-id="ce901-244">它还取决于需要要进行的服务的方式可缩放 （更精细的事务的影响较小方面数据库锁）。</span><span class="sxs-lookup"><span data-stu-id="ce901-244">It also depends on how scalable you need the service to be (more granular transactions have less impact with regard to database locks).</span></span> <span data-ttu-id="ce901-245">它依赖于多少投资您愿意为使在代码中，因为最终一致性需要更复杂的代码，以便在聚合和需要实现补偿性操作检测可能不一致。</span><span class="sxs-lookup"><span data-stu-id="ce901-245">And it depends on how much investment you are willing to make in your code, since eventual consistency requires more complex code in order to detect possible inconsistencies across aggregates and the need to implement compensatory actions.</span></span> <span data-ttu-id="ce901-246">考虑到原始的聚合，以及之后，当正在调度事件提交更改，如果没有问题并且事件处理程序无法提交其副作用，则将必须聚合之间的不一致。</span><span class="sxs-lookup"><span data-stu-id="ce901-246">Take into account that if you commit changes to the original aggregate and afterwards, when the events are being dispatched, there is an issue and the event handlers cannot commit their side effects, you will have inconsistencies between aggregates.</span></span>

<span data-ttu-id="ce901-247">若要允许补偿性操作的方式可以是事务的要在其他数据库表中存储域事件，因此它们可以是事务的原来的一部分。</span><span class="sxs-lookup"><span data-stu-id="ce901-247">A way to allow compensatory actions would be to store the domain events in additional database tables so they can be part of the original transaction.</span></span> <span data-ttu-id="ce901-248">然后，你可以检测到不一致和聚合的当前状态的事件的列表进行比较运行补偿性操作的批处理。</span><span class="sxs-lookup"><span data-stu-id="ce901-248">Afterwards, you could have a batch process that detects inconsistencies and runs compensatory actions by comparing the list of events with the current state of the aggregates.</span></span> <span data-ttu-id="ce901-249">补偿性操作属于复杂的主题，它将需要从你端，其中包括讨论与业务用户和域专家的深入分析。</span><span class="sxs-lookup"><span data-stu-id="ce901-249">The compensatory actions are part of a complex topic that will require deep analysis from your side, which includes discussing it with the business user and domain experts.</span></span>

<span data-ttu-id="ce901-250">在任何情况下，你可以选择所需的方法。</span><span class="sxs-lookup"><span data-stu-id="ce901-250">In any case, you can choose the approach you need.</span></span> <span data-ttu-id="ce901-251">但初始延迟方法-在提交之前，引发事件，因此使用单个事务-使用 EF 核心应用程序和关系数据库时，是最简单的方法。</span><span class="sxs-lookup"><span data-stu-id="ce901-251">But the initial deferred approach—raising the events before committing, so you use a single transaction—is the simplest approach when using EF Core and a relational database.</span></span> <span data-ttu-id="ce901-252">它是更加轻松地实现，在许多业务案例中有效。</span><span class="sxs-lookup"><span data-stu-id="ce901-252">It is easier to implement and valid in many business cases.</span></span> <span data-ttu-id="ce901-253">它也是在中 eShopOnContainers 排序微服务中使用的方法。</span><span class="sxs-lookup"><span data-stu-id="ce901-253">It is also the approach used in the ordering microservice in eShopOnContainers.</span></span>

<span data-ttu-id="ce901-254">但如何执行你实际调度这些事件，以便将其各自的事件处理程序？</span><span class="sxs-lookup"><span data-stu-id="ce901-254">But how do you actually dispatch those events to their respective event handlers?</span></span> <span data-ttu-id="ce901-255">什么是\_你在前面的示例中看到的中介对象？</span><span class="sxs-lookup"><span data-stu-id="ce901-255">What is the \_mediator object that you see in the previous example?</span></span> <span data-ttu-id="ce901-256">具有要使用的技术和可以使用事件和其事件处理程序之间进行映射的项目执行的操作。</span><span class="sxs-lookup"><span data-stu-id="ce901-256">That has to do with the techniques and artifacts you can use to map between events and their event handlers.</span></span>

### <a name="the-domain-event-dispatcher-mapping-from-events-to-event-handlers"></a><span data-ttu-id="ce901-257">域事件调度程序： 从事件映射到事件处理程序</span><span class="sxs-lookup"><span data-stu-id="ce901-257">The domain event dispatcher: mapping from events to event handlers</span></span>

<span data-ttu-id="ce901-258">能够调度或发布事件后，你将需要某种类型的项目，以便每个相关的处理程序可以获取和进程副作用根据该事件将发布事件。</span><span class="sxs-lookup"><span data-stu-id="ce901-258">Once you are able to dispatch or publish the events, you need some kind of artifact that will publish the event so that every related handler can get it and process side effects based on that event.</span></span>

<span data-ttu-id="ce901-259">一种方法是实际消息系统或甚至是事件总线，可以基于服务总线而不是内存中的事件。</span><span class="sxs-lookup"><span data-stu-id="ce901-259">One approach is a real messaging system or even an event bus, possibly based on a service bus as opposed to in-memory events.</span></span> <span data-ttu-id="ce901-260">但是，对于第一种情况，实际消息可能不太适用处理域事件，因为你只需处理这些事件在同一进程内的 (即，在相同的域和应用程序层内)。</span><span class="sxs-lookup"><span data-stu-id="ce901-260">However, for the first case, real messaging would be overkill for processing domain events, since you just need to process those events within the same process (that is, within the same domain and application layer).</span></span>

<span data-ttu-id="ce901-261">若要将事件映射到多个事件处理程序的另一种方法是使用 IoC 容器中的类型注册，以便你可以动态推导出调度事件的位置。</span><span class="sxs-lookup"><span data-stu-id="ce901-261">Another way to map events to multiple event handlers is by using types registration in an IoC container so that you can dynamically infer where to dispatch the events.</span></span> <span data-ttu-id="ce901-262">换而言之，你需要知道需要获取特定事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ce901-262">In other words, you need to know what event handlers need to get a specific event.</span></span> <span data-ttu-id="ce901-263">图 9-16 显示，简化的方法。</span><span class="sxs-lookup"><span data-stu-id="ce901-263">Figure 9-16 shows a simplified approach for that.</span></span>

![](./media/image17.png)

<span data-ttu-id="ce901-264">**图 9-16**。</span><span class="sxs-lookup"><span data-stu-id="ce901-264">**Figure 9-16**.</span></span> <span data-ttu-id="ce901-265">域事件调度程序使用 IoC</span><span class="sxs-lookup"><span data-stu-id="ce901-265">Domain event dispatcher using IoC</span></span>

<span data-ttu-id="ce901-266">你可以构建所有联结和要实现该方法通过自己项目。</span><span class="sxs-lookup"><span data-stu-id="ce901-266">You can build all the plumbing and artifacts to implement that approach by yourself.</span></span> <span data-ttu-id="ce901-267">但是，你还可以使用可用的库，如[MediatR](https://github.com/jbogard/MediatR)，实际上使用 IoT 容器。</span><span class="sxs-lookup"><span data-stu-id="ce901-267">However, you can also use available libraries like [MediatR](https://github.com/jbogard/MediatR), which underneath the covers uses your IoT container.</span></span> <span data-ttu-id="ce901-268">因此，可以直接使用预定义的接口和中介对象的发布/调度方法。</span><span class="sxs-lookup"><span data-stu-id="ce901-268">You can therefore directly use the predefined interfaces and the mediator object’s publish/dispatch methods.</span></span>

<span data-ttu-id="ce901-269">在代码中，你首先需要注册事件处理程序类型在 IoC 容器，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="ce901-269">In code, you first need to register the event handler types in your IoC container, as shown in the following example:</span></span>

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        // Other registrations ...
        // Register the DomainEventHandler classes (they implement
        // IAsyncNotificationHandler<>) in assembly holding the Domain Events
        builder.RegisterAssemblyTypes(
            typeof(ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler)
            .GetTypeInfo().Assembly)
            .Where(t => t.IsClosedTypeOf(typeof(IAsyncNotificationHandler<>)))
            .AsImplementedInterfaces();
        // Other registrations ...
    }
}
```

<span data-ttu-id="ce901-270">代码首先标识包含域事件处理程序通过查找程序集包含任何处理程序的程序集 （使用 typeof(ValidateOrAddBuyerAggregateWhenXxxx)，但你可能已选择任何其他事件处理程序来查找程序集）。</span><span class="sxs-lookup"><span data-stu-id="ce901-270">The code first identifies the assembly that contains the domain event handlers by locating the assembly that holds any of the handlers (using typeof(ValidateOrAddBuyerAggregateWhenXxxx), but you could have chosen any other event handler to locate the assembly).</span></span> <span data-ttu-id="ce901-271">由于所有事件处理程序都实现 IAsyncNotificationHandler 接口，然后，此代码只是搜索这些类型，注册的所有事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ce901-271">Since all the event handlers implement the IAsyncNotificationHandler interface, the code then just searches for those types and registers all the event handlers.</span></span>

### <a name="how-to-subscribe-to-domain-events"></a><span data-ttu-id="ce901-272">如何订阅域事件</span><span class="sxs-lookup"><span data-stu-id="ce901-272">How to subscribe to domain events</span></span>

<span data-ttu-id="ce901-273">当你使用 MediatR 时，每个事件处理程序必须使用对 IAsyncNotificationHandler 接口的泛型参数提供的事件类型，如你所见下面的代码中：</span><span class="sxs-lookup"><span data-stu-id="ce901-273">When you use MediatR, each event handler must use an event type that is provided on the generic parameter of the IAsyncNotificationHandler interface, as you can see in the following code:</span></span>

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
  : IAsyncNotificationHandler<OrderStartedDomainEvent>
```

<span data-ttu-id="ce901-274">基于事件和事件处理程序，可被视为订阅，之间的关系 MediatR 项目可以发现每个事件的所有事件处理程序并触发每个这些事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ce901-274">Based on the relationship between event and event handler, which can be considered the subscription, the MediatR artifact can discover all the event handlers for each event and trigger each of those event handlers.</span></span>

### <a name="how-to-handle-domain-events"></a><span data-ttu-id="ce901-275">如何处理域事件</span><span class="sxs-lookup"><span data-stu-id="ce901-275">How to handle domain events</span></span>

<span data-ttu-id="ce901-276">最后，事件处理程序通常实现使用基础结构存储库，以获取所需的其他聚合并执行负面影响域逻辑的应用程序层代码。</span><span class="sxs-lookup"><span data-stu-id="ce901-276">Finally, the event handler usually implements application layer code that uses infrastructure repositories to obtain the required additional aggregates and to execute side-effect domain logic.</span></span> <span data-ttu-id="ce901-277">以下代码显示一个示例。</span><span class="sxs-lookup"><span data-stu-id="ce901-277">The following code shows an example.</span></span>

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
    : IAsyncNotificationHandler<OrderStartedDomainEvent>
{
    private readonly ILoggerFactory _logger;
    private readonly IBuyerRepository<Buyer> _buyerRepository;
    private readonly IIdentityService _identityService;
    public ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler(
        ILoggerFactory logger,
        IBuyerRepository<Buyer> buyerRepository,
        IIdentityService identityService)
    {
        // Parameter validations
        //...
    }

    public async Task Handle(OrderStartedDomainEvent orderStartedEvent)
    {
        var cardTypeId = (orderStartedEvent.CardTypeId != 0) ?
            orderStartedEvent.CardTypeId : 1;
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
        var buyerUpdated = buyerOriginallyExisted ? _buyerRepository.Update(buyer) :
        _buyerRepository.Add(buyer);
        await _buyerRepository.UnitOfWork.SaveEntitiesAsync();
        // Logging code using buyerUpdated info, etc.
    }
}
```

<span data-ttu-id="ce901-278">此事件处理程序代码则被视为应用程序层代码因为它使用基础结构存储库下, 一节中所述基础结构持久性层上。</span><span class="sxs-lookup"><span data-stu-id="ce901-278">This event handler code is considered application layer code because it uses infrastructure repositories, as explained in the next section on the infrastructure-persistence layer.</span></span> <span data-ttu-id="ce901-279">事件处理程序还可以使用其他基础结构组件。</span><span class="sxs-lookup"><span data-stu-id="ce901-279">Event handlers could also use other infrastructure components.</span></span>

#### <a name="domain-events-can-generate-integration-events-to-be-published-outside-of-the-microservice-boundaries"></a><span data-ttu-id="ce901-280">域事件可以生成要在 microservice 边界之外发布的集成事件</span><span class="sxs-lookup"><span data-stu-id="ce901-280">Domain events can generate integration events to be published outside of the microservice boundaries</span></span>

<span data-ttu-id="ce901-281">最后，务必提及，你有时想要在多个微服务之间传播事件。</span><span class="sxs-lookup"><span data-stu-id="ce901-281">Finally, is important to mention that you might sometimes want to propagate events across multiple microservices.</span></span> <span data-ttu-id="ce901-282">认为集成事件，并可通过从任何特定域事件处理程序的事件总线发布它。</span><span class="sxs-lookup"><span data-stu-id="ce901-282">That is considered an integration event, and it could be published through an event bus from any specific domain event handler.</span></span>

## <a name="conclusions-on-domain-events"></a><span data-ttu-id="ce901-283">结论域事件</span><span class="sxs-lookup"><span data-stu-id="ce901-283">Conclusions on domain events</span></span> 

<span data-ttu-id="ce901-284">如所述，使用域事件显式实现你的域中的更改的副作用。</span><span class="sxs-lookup"><span data-stu-id="ce901-284">As stated, use domain events to explicitly implement side effects of changes within your domain.</span></span> <span data-ttu-id="ce901-285">若要使用 DDD 术语，用于域事件显式实现副作用跨一个或多个聚合。</span><span class="sxs-lookup"><span data-stu-id="ce901-285">To use DDD terminology, use domain events to explicitly implement side effects across one or multiple aggregates.</span></span> <span data-ttu-id="ce901-286">此外，和的更好的可伸缩性和有关数据库的锁的影响更小使用在同一域中的聚合之间的最终一致性。</span><span class="sxs-lookup"><span data-stu-id="ce901-286">Additionally, and for better scalability and less impact on database locks, use eventual consistency between aggregates within the same domain.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="ce901-287">其他资源</span><span class="sxs-lookup"><span data-stu-id="ce901-287">Additional resources</span></span>

-   <span data-ttu-id="ce901-288">**Greg Young。什么是域事件？** 
     [ *http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/*](http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/)</span><span class="sxs-lookup"><span data-stu-id="ce901-288">**Greg Young. What is a Domain Event?**
[*http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/*](http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/)</span></span>

-   <span data-ttu-id="ce901-289">**年 1 月 Stenberg。域事件和最终一致性**
    [*https://www.infoq.com/news/2015/09/domain-events-consistency*](https://www.infoq.com/news/2015/09/domain-events-consistency)</span><span class="sxs-lookup"><span data-stu-id="ce901-289">**Jan Stenberg. Domain Events and Eventual Consistency**
[*https://www.infoq.com/news/2015/09/domain-events-consistency*](https://www.infoq.com/news/2015/09/domain-events-consistency)</span></span>

-   <span data-ttu-id="ce901-290">**Jimmy Bogard。更好的域事件模式**
    [*https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/*](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)</span><span class="sxs-lookup"><span data-stu-id="ce901-290">**Jimmy Bogard. A better domain events pattern**
[*https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/*](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)</span></span>

-   <span data-ttu-id="ce901-291">**Vaughn Vernon。有效聚合设计第 II 部分： 进行聚合在一起工作**
    [*http://dddcommunity.org/wp-content/uploads/files/pdf\_文章/Vernon\_2011\_2.pdf*](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)</span><span class="sxs-lookup"><span data-stu-id="ce901-291">**Vaughn Vernon. Effective Aggregate Design Part II: Making Aggregates Work Together**
[*http://dddcommunity.org/wp-content/uploads/files/pdf\_articles/Vernon\_2011\_2.pdf*](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)</span></span>

-   <span data-ttu-id="ce901-292">**Jimmy Bogard。增强你的域： 域事件**
    *<https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/>*</span><span class="sxs-lookup"><span data-stu-id="ce901-292">**Jimmy Bogard. Strengthening your domain: Domain Events**
*<https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/> *</span></span>

-   <span data-ttu-id="ce901-293">**Tony Truong。域事件模式示例**
    [*http://www.tonytruong.net/domain-events-pattern-example/*](http://www.tonytruong.net/domain-events-pattern-example/)</span><span class="sxs-lookup"><span data-stu-id="ce901-293">**Tony Truong. Domain Events Pattern Example**
[*http://www.tonytruong.net/domain-events-pattern-example/*](http://www.tonytruong.net/domain-events-pattern-example/)</span></span>

-   <span data-ttu-id="ce901-294">**Udi Dahan。如何创建完全封装域模型**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span><span class="sxs-lookup"><span data-stu-id="ce901-294">**Udi Dahan. How to create fully encapsulated Domain Models**
[*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span></span>

-   <span data-ttu-id="ce901-295">**Udi Dahan。域事件 – 执行 2**
    [*http://udidahan.com/2008/08/25/domain-events-take-2/*](http://udidahan.com/2008/08/25/domain-events-take-2/%20)</span><span class="sxs-lookup"><span data-stu-id="ce901-295">**Udi Dahan. Domain Events – Take 2**
[*http://udidahan.com/2008/08/25/domain-events-take-2/*](http://udidahan.com/2008/08/25/domain-events-take-2/%20)</span></span>

-   <span data-ttu-id="ce901-296">**Udi Dahan。域事件 – Salvation**
    [*http://udidahan.com/2009/06/14/domain-events-salvation/*](http://udidahan.com/2009/06/14/domain-events-salvation/)</span><span class="sxs-lookup"><span data-stu-id="ce901-296">**Udi Dahan. Domain Events – Salvation**
[*http://udidahan.com/2009/06/14/domain-events-salvation/*](http://udidahan.com/2009/06/14/domain-events-salvation/)</span></span>

-   <span data-ttu-id="ce901-297">**年 1 月 Kronquist。不发布域的事件，将它们返回 ！** 
     [ *https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/*](https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/)</span><span class="sxs-lookup"><span data-stu-id="ce901-297">**Jan Kronquist. Don't publish Domain Events, return them!**
[*https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/*](https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/)</span></span>

-   <span data-ttu-id="ce901-298">**Cesar de la Torre。域事件 vs。DDD 和微服务体系结构中的集成事件**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/)</span><span class="sxs-lookup"><span data-stu-id="ce901-298">**Cesar de la Torre. Domain Events vs. Integration Events in DDD and microservices architectures**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ce901-299">[以前](客户端-端-validation.md) [下一步] (基础结构的持久性-层-design.md)</span><span class="sxs-lookup"><span data-stu-id="ce901-299">[Previous] (client-side-validation.md) [Next] (infrastructure-persistence-layer-design.md)</span></span>
