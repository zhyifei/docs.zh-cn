---
title: 使用行为配置和扩展运行时
ms.date: 03/30/2017
helpviewer_keywords:
- attaching extensions using behaviors [WCF]
ms.assetid: 149b99b6-6eb6-4f45-be22-c967279677d9
ms.openlocfilehash: af95fa01fc9caffb8a4f0e85d3457c7f3fa60320
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33808307"
---
# <a name="configuring-and-extending-the-runtime-with-behaviors"></a><span data-ttu-id="a3d20-102">使用行为配置和扩展运行时</span><span class="sxs-lookup"><span data-stu-id="a3d20-102">Configuring and Extending the Runtime with Behaviors</span></span>
<span data-ttu-id="a3d20-103">行为可用于修改默认行为和添加自定义扩展的检查和验证服务配置或修改 Windows Communication Foundation (WCF) 客户端和服务应用程序中的运行时行为。</span><span class="sxs-lookup"><span data-stu-id="a3d20-103">Behaviors enable you to modify default behavior and add custom extensions that inspect and validate service configuration or modify runtime behavior in Windows Communication Foundation (WCF) client and service applications.</span></span> <span data-ttu-id="a3d20-104">本主题说明行为接口、如何实现这些接口以及如何以编程方式将它们添加到服务说明（在服务应用程序中）或终结点（在客户端应用程序中）或配置文件中。</span><span class="sxs-lookup"><span data-stu-id="a3d20-104">This topic describes the behavior interfaces, how to implement them, and how to add them to the service description (in a service application) or endpoint (in a client application) programmatically or in a configuration file.</span></span> <span data-ttu-id="a3d20-105">有关使用系统提供的行为的详细信息，请参阅[指定服务运行时行为](../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)和[指定客户端运行时行为](../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d20-105">For more information about using system-provided behaviors, see [Specifying Service Run-Time Behavior](../../../../docs/framework/wcf/specifying-service-run-time-behavior.md) and [Specifying Client Run-Time Behavior](../../../../docs/framework/wcf/specifying-client-run-time-behavior.md).</span></span>  
  
## <a name="behaviors"></a><span data-ttu-id="a3d20-106">行为</span><span class="sxs-lookup"><span data-stu-id="a3d20-106">Behaviors</span></span>  
 <span data-ttu-id="a3d20-107">行为类型将添加到服务或服务终结点说明对象 (客户端，在服务上分别) 这些对象用于通过 Windows Communication Foundation (WCF) 中创建运行时执行 WCF 服务或 WCF 客户端之前。</span><span class="sxs-lookup"><span data-stu-id="a3d20-107">Behavior types are added to the service or service endpoint description objects (on the service or client, respectively) before those objects are used by Windows Communication Foundation (WCF) to create a runtime that executes a WCF service or a WCF client.</span></span> <span data-ttu-id="a3d20-108">在运行时构造过程中调用这些行为时，这些行为可以访问运行时属性和方法以修改由协定、绑定和地址构造的运行时。</span><span class="sxs-lookup"><span data-stu-id="a3d20-108">When these behaviors are called during the runtime construction process they are then able to access runtime properties and methods that modify the runtime constructed by the contract, bindings, and addresses.</span></span>  
  
### <a name="behavior-methods"></a><span data-ttu-id="a3d20-109">行为方法</span><span class="sxs-lookup"><span data-stu-id="a3d20-109">Behavior Methods</span></span>  
 <span data-ttu-id="a3d20-110">所有行为都具有一个 `AddBindingParameters` 方法、一个 `ApplyDispatchBehavior` 方法、一个 `Validate` 方法和一个 `ApplyClientBehavior` 方法，但有一个例外：因为 <xref:System.ServiceModel.Description.IServiceBehavior> 无法在客户端中执行，因此该行为不实现 `ApplyClientBehavior`。</span><span class="sxs-lookup"><span data-stu-id="a3d20-110">All behaviors have an `AddBindingParameters` method, an `ApplyDispatchBehavior` method, a `Validate` method, and an `ApplyClientBehavior` method with one exception: Because <xref:System.ServiceModel.Description.IServiceBehavior> cannot execute in a client, it does not implement `ApplyClientBehavior`.</span></span>  
  
-   <span data-ttu-id="a3d20-111">使用 `AddBindingParameters` 方法可修改自定义对象或将自定义对象添加到集合，在构造运行时时，自定义绑定可以访问该集合以使这些对象。</span><span class="sxs-lookup"><span data-stu-id="a3d20-111">Use the `AddBindingParameters` method to modify or add custom objects to a collection that custom bindings can access for their use when the runtime is constructed.</span></span> <span data-ttu-id="a3d20-112">例如，可能会指定影响通道生成方式的保护要求，但通道开发人员可能并不知道这些保护要求。</span><span class="sxs-lookup"><span data-stu-id="a3d20-112">For example, this how protection requirements are specified that affect the way the channel is built, but are not known by the channel developer.</span></span>  
  
-   <span data-ttu-id="a3d20-113">使用 `Validate` 方法可检查说明树和相应的运行时对象以确保符合某一条件集。</span><span class="sxs-lookup"><span data-stu-id="a3d20-113">Use the `Validate` method to examine the description tree and corresponding runtime object to ensure it conforms to some set of criteria.</span></span>  
  
-   <span data-ttu-id="a3d20-114">使用 `ApplyDispatchBehavior` 和 `ApplyClientBehavior` 方法可检查说明树并在服务或客户端上修改特定范围的运行时。</span><span class="sxs-lookup"><span data-stu-id="a3d20-114">Use the `ApplyDispatchBehavior` and `ApplyClientBehavior` methods to examine the description tree and modify the runtime for a particular scope on either the service or the client.</span></span> <span data-ttu-id="a3d20-115">也可以插入扩展对象。</span><span class="sxs-lookup"><span data-stu-id="a3d20-115">You can also insert extension objects as well.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a3d20-116">尽管在这些方法中提供了说明树，但它仅限用于检查。</span><span class="sxs-lookup"><span data-stu-id="a3d20-116">Although a description tree is provided in these methods, it is for examination only.</span></span> <span data-ttu-id="a3d20-117">如果修改了说明树，则行为将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="a3d20-117">If a description tree is modified, the behavior is undefined.</span></span>  
  
 <span data-ttu-id="a3d20-118">可以修改的属性和可以实现的自定义接口可通过服务和客户端运行时类访问。</span><span class="sxs-lookup"><span data-stu-id="a3d20-118">The properties you can modify and the customization interfaces you can implement are accessed through the service and client runtime classes.</span></span> <span data-ttu-id="a3d20-119">服务类型为 <xref:System.ServiceModel.Dispatcher.DispatchRuntime> 和 <xref:System.ServiceModel.Dispatcher.DispatchOperation> 类。</span><span class="sxs-lookup"><span data-stu-id="a3d20-119">The service types are the <xref:System.ServiceModel.Dispatcher.DispatchRuntime> and  <xref:System.ServiceModel.Dispatcher.DispatchOperation> classes.</span></span> <span data-ttu-id="a3d20-120">客户端类型为 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 和 <xref:System.ServiceModel.Dispatcher.ClientOperation> 类。</span><span class="sxs-lookup"><span data-stu-id="a3d20-120">The client types are the <xref:System.ServiceModel.Dispatcher.ClientRuntime> and <xref:System.ServiceModel.Dispatcher.ClientOperation> classes.</span></span> <span data-ttu-id="a3d20-121"><xref:System.ServiceModel.Dispatcher.ClientRuntime> 和 <xref:System.ServiceModel.Dispatcher.DispatchRuntime> 类是分别访问客户端范围和服务范围运行时属性和扩展集合的扩展入口点。</span><span class="sxs-lookup"><span data-stu-id="a3d20-121">The <xref:System.ServiceModel.Dispatcher.ClientRuntime> and <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes are the extensibility entry points to access client-wide and service-wide runtime properties and extension collections, respectively.</span></span> <span data-ttu-id="a3d20-122">同样，<xref:System.ServiceModel.Dispatcher.ClientOperation> 和 <xref:System.ServiceModel.Dispatcher.DispatchOperation> 类分别公开客户端操作和服务操作运行时属性和扩展集合。</span><span class="sxs-lookup"><span data-stu-id="a3d20-122">Similarly, the <xref:System.ServiceModel.Dispatcher.ClientOperation> and  <xref:System.ServiceModel.Dispatcher.DispatchOperation> classes expose client operation and service operation runtime properties and extension collections, respectively.</span></span> <span data-ttu-id="a3d20-123">但您可以从操作运行时对象访问更广范围的运行时对象，如果需要，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a3d20-123">You can, however, access the wider scoped runtime object from the operation runtime object and vice versa if need be.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3d20-124">有关运行时属性和可用于修改客户端的执行行为的扩展类型的讨论，请参阅[扩展客户端](../../../../docs/framework/wcf/extending/extending-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d20-124">For a discussion of runtime properties and extension types that you can use to modify the execution behavior of a client, see [Extending Clients](../../../../docs/framework/wcf/extending/extending-clients.md).</span></span> <span data-ttu-id="a3d20-125">有关运行时属性和可用于修改服务调度程序的执行行为的扩展类型的讨论，请参阅[扩展调度程序](../../../../docs/framework/wcf/extending/extending-dispatchers.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d20-125">For a discussion of runtime properties and extension types that you can use to modify the execution behavior of a service dispatcher, see [Extending Dispatchers](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span></span>  
  
 <span data-ttu-id="a3d20-126">大多数 WCF 用户并不与运行时直接交互;而是使用核心编程模型结构，比如终结点、 协定、 绑定、 地址和行为属性对类或行为配置文件中。</span><span class="sxs-lookup"><span data-stu-id="a3d20-126">Most WCF users do not interact with the runtime directly; instead they use core programming model constructs like endpoints, contracts, bindings, addresses, and behavior attributes on classes or behaviors in configuration files.</span></span> <span data-ttu-id="a3d20-127">这些结构构成*说明树*，这是用于构造运行时以支持服务的完整规范，或者客户端所述由说明树。</span><span class="sxs-lookup"><span data-stu-id="a3d20-127">These constructs make up the *description tree*, which is the complete specification for constructing a runtime to support a service or client described by the description tree.</span></span>  
  
 <span data-ttu-id="a3d20-128">有四种类型的 WCF 中的行为：</span><span class="sxs-lookup"><span data-stu-id="a3d20-128">There are four kinds of behaviors in WCF:</span></span>  
  
-   <span data-ttu-id="a3d20-129">服务行为（<xref:System.ServiceModel.Description.IServiceBehavior> 类型）启用整个服务运行时（包括 <xref:System.ServiceModel.ServiceHostBase>）的自定义。</span><span class="sxs-lookup"><span data-stu-id="a3d20-129">Service behaviors (<xref:System.ServiceModel.Description.IServiceBehavior> types) enable the customization of the entire service runtime including <xref:System.ServiceModel.ServiceHostBase>.</span></span>  
  
-   <span data-ttu-id="a3d20-130">终结点行为（<xref:System.ServiceModel.Description.IEndpointBehavior> 类型）启用服务终结点及其关联 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> 对象的自定义。</span><span class="sxs-lookup"><span data-stu-id="a3d20-130">Endpoint behaviors (<xref:System.ServiceModel.Description.IEndpointBehavior> types) enable the customization of service endpoints and their associated <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> objects.</span></span>  
  
-   <span data-ttu-id="a3d20-131">协定行为（<xref:System.ServiceModel.Description.IContractBehavior> 类型）分别启用客户端和服务应用程序中 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 和 <xref:System.ServiceModel.Dispatcher.DispatchRuntime> 类的自定义。</span><span class="sxs-lookup"><span data-stu-id="a3d20-131">Contract behaviors (<xref:System.ServiceModel.Description.IContractBehavior> types) enable the customization of both the <xref:System.ServiceModel.Dispatcher.ClientRuntime> and <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes in client and service applications, respectively.</span></span>  
  
-   <span data-ttu-id="a3d20-132">操作行为（<xref:System.ServiceModel.Description.IOperationBehavior> 类型）也启用客户端和服务中 <xref:System.ServiceModel.Dispatcher.ClientOperation> 和 <xref:System.ServiceModel.Dispatcher.DispatchOperation> 类的自定义。</span><span class="sxs-lookup"><span data-stu-id="a3d20-132">Operation behaviors (<xref:System.ServiceModel.Description.IOperationBehavior> types) enable the customization of the <xref:System.ServiceModel.Dispatcher.ClientOperation> and <xref:System.ServiceModel.Dispatcher.DispatchOperation> classes, again, on the client and service.</span></span>  
  
 <span data-ttu-id="a3d20-133">您可以通过实现自定义属性、使用应用程序配置文件或直接将行为添加到相应说明对象上的行为集合，将这些行为添加到各个说明对象。</span><span class="sxs-lookup"><span data-stu-id="a3d20-133">You can add these behaviors to the various description objects by implementing custom attributes, using application configuration files, or directly by adding them to the behaviors collection on the appropriate description object.</span></span> <span data-ttu-id="a3d20-134">但在对 <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> 或 <xref:System.ServiceModel.ServiceHost> 调用 <xref:System.ServiceModel.ChannelFactory%601> 之前，必须将这些行为添加到服务说明或服务终结点说明对象。</span><span class="sxs-lookup"><span data-stu-id="a3d20-134">The must, however, be added to a service description or service endpoint description object prior to calling <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> on the <xref:System.ServiceModel.ServiceHost> or a <xref:System.ServiceModel.ChannelFactory%601>.</span></span>  
  
### <a name="behavior-scopes"></a><span data-ttu-id="a3d20-135">行为范围</span><span class="sxs-lookup"><span data-stu-id="a3d20-135">Behavior Scopes</span></span>  
 <span data-ttu-id="a3d20-136">有四种行为类型，每种类型各对应于特定范围的运行时访问。</span><span class="sxs-lookup"><span data-stu-id="a3d20-136">There are four behavior types, each of which corresponds to a particular scope of runtime access.</span></span>  
  
#### <a name="service-behaviors"></a><span data-ttu-id="a3d20-137">服务行为</span><span class="sxs-lookup"><span data-stu-id="a3d20-137">Service Behaviors</span></span>  
 <span data-ttu-id="a3d20-138">服务行为实现 <xref:System.ServiceModel.Description.IServiceBehavior>，它是赖以修改整个服务运行时的主要机制。</span><span class="sxs-lookup"><span data-stu-id="a3d20-138">Service behaviors, which implement <xref:System.ServiceModel.Description.IServiceBehavior>, are the primary mechanism by which you modify the entire service runtime.</span></span> <span data-ttu-id="a3d20-139">向服务中添加服务行为有三种方式。</span><span class="sxs-lookup"><span data-stu-id="a3d20-139">There are three mechanisms for adding service behaviors to a service.</span></span>  
  
1.  <span data-ttu-id="a3d20-140">在服务类上使用属性。</span><span class="sxs-lookup"><span data-stu-id="a3d20-140">Using an attribute on the service class.</span></span>  <span data-ttu-id="a3d20-141">在构造 <xref:System.ServiceModel.ServiceHost> 时，<xref:System.ServiceModel.ServiceHost> 实现使用反射来发现服务类型上的属性集。</span><span class="sxs-lookup"><span data-stu-id="a3d20-141">When a <xref:System.ServiceModel.ServiceHost> is constructed, the <xref:System.ServiceModel.ServiceHost> implementation uses reflection to discover the set of attributes on the type of the service.</span></span> <span data-ttu-id="a3d20-142">如果这些属性中的任何属性是 <xref:System.ServiceModel.Description.IServiceBehavior> 的实现，则会将其添加到 <xref:System.ServiceModel.Description.ServiceDescription> 上的行为集合中。</span><span class="sxs-lookup"><span data-stu-id="a3d20-142">If any of those attributes are implementations of <xref:System.ServiceModel.Description.IServiceBehavior>, they are added to the behaviors collection on <xref:System.ServiceModel.Description.ServiceDescription>.</span></span> <span data-ttu-id="a3d20-143">这允许这些行为参与服务运行时的构造。</span><span class="sxs-lookup"><span data-stu-id="a3d20-143">This allows those behaviors to participate in the construction of the service run time.</span></span>  
  
2.  <span data-ttu-id="a3d20-144">以编程方式将行为添加到 <xref:System.ServiceModel.Description.ServiceDescription> 上的行为集合中。</span><span class="sxs-lookup"><span data-stu-id="a3d20-144">Programmatically adding the behavior to the behaviors collection on <xref:System.ServiceModel.Description.ServiceDescription>.</span></span> <span data-ttu-id="a3d20-145">这可以通过以下几行代码实现：</span><span class="sxs-lookup"><span data-stu-id="a3d20-145">This can be accomplished with the following lines of code:</span></span>  
  
    ```  
    ServiceHost host = new ServiceHost(/* Parameters */);  
    host.Description.Behaviors.Add(/* Service Behavior */);  
    ```  
  
3.  <span data-ttu-id="a3d20-146">实现用于扩展配置的自定义 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>。</span><span class="sxs-lookup"><span data-stu-id="a3d20-146">Implementing a custom <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> that extends configuration.</span></span> <span data-ttu-id="a3d20-147">这将允许在应用程序配置文件中使用服务行为。</span><span class="sxs-lookup"><span data-stu-id="a3d20-147">This enables the use of the service behavior from application configuration files.</span></span>  
  
 <span data-ttu-id="a3d20-148">在 WCF 中的服务行为的示例包括<xref:System.ServiceModel.ServiceBehaviorAttribute>属性， <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>，和<xref:System.ServiceModel.Description.ServiceMetadataBehavior>行为。</span><span class="sxs-lookup"><span data-stu-id="a3d20-148">Examples of service behaviors in WCF include the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute, the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>, and the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
#### <a name="contract-behaviors"></a><span data-ttu-id="a3d20-149">协定行为</span><span class="sxs-lookup"><span data-stu-id="a3d20-149">Contract Behaviors</span></span>  
 <span data-ttu-id="a3d20-150">协定行为实现 <xref:System.ServiceModel.Description.IContractBehavior> 接口，它用于在协定范围内扩展客户端和服务运行时。</span><span class="sxs-lookup"><span data-stu-id="a3d20-150">Contract behaviors, which implement the <xref:System.ServiceModel.Description.IContractBehavior> interface, are used to extend both the client and service runtime across a contract.</span></span>  
  
 <span data-ttu-id="a3d20-151">向协定中添加协定行为有两种方式。</span><span class="sxs-lookup"><span data-stu-id="a3d20-151">There are two mechanisms for adding contract behaviors to a contract.</span></span>  <span data-ttu-id="a3d20-152">第一种方式是创建要在协定接口上使用的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="a3d20-152">The first mechanism is to create a custom attribute to be used on the contract interface.</span></span> <span data-ttu-id="a3d20-153">当协定接口传递给<xref:System.ServiceModel.ServiceHost>或<xref:System.ServiceModel.ChannelFactory%601>，WCF 检查接口上的属性。</span><span class="sxs-lookup"><span data-stu-id="a3d20-153">When a contract interface is passed to either a <xref:System.ServiceModel.ServiceHost> or a <xref:System.ServiceModel.ChannelFactory%601>, WCF examines the attributes on the interface.</span></span> <span data-ttu-id="a3d20-154">如果任何属性是 <xref:System.ServiceModel.Description.IContractBehavior> 的实现，则会将其添加到为该接口创建的 <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType> 上的行为集合中。</span><span class="sxs-lookup"><span data-stu-id="a3d20-154">If any attributes are implementations of <xref:System.ServiceModel.Description.IContractBehavior>, those are added to the behaviors collection on the <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType> created for that interface.</span></span>  
  
 <span data-ttu-id="a3d20-155">也可以在自定义协定行为属性上实现 <xref:System.ServiceModel.Description.IContractBehaviorAttribute?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a3d20-155">You can also implement the <xref:System.ServiceModel.Description.IContractBehaviorAttribute?displayProperty=nameWithType> on the custom contract behavior attribute.</span></span> <span data-ttu-id="a3d20-156">在这种情况下，当应用于以下对象时，行为如下所述：</span><span class="sxs-lookup"><span data-stu-id="a3d20-156">In this case, the behavior is as follows when applied to:</span></span>  
  
 <span data-ttu-id="a3d20-157">• 协定接口。</span><span class="sxs-lookup"><span data-stu-id="a3d20-157">•A contract interface.</span></span> <span data-ttu-id="a3d20-158">在这种情况下，该行为应用到任何终结点中该类型的所有协定和 WCF 将忽略的值<xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="a3d20-158">In this case, the behavior is applied to all contracts of that type in any endpoint and WCF ignores the value of the <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="a3d20-159">• 服务类。</span><span class="sxs-lookup"><span data-stu-id="a3d20-159">•A service class.</span></span> <span data-ttu-id="a3d20-160">在此情况下，该行为只应用到其协定是 <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A> 属性的值的终结点。</span><span class="sxs-lookup"><span data-stu-id="a3d20-160">In this case, the behavior is applied only to endpoints the contract of which is the value of the <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A> property.</span></span>  
  
 <span data-ttu-id="a3d20-161">• 回调类。</span><span class="sxs-lookup"><span data-stu-id="a3d20-161">•A callback class.</span></span> <span data-ttu-id="a3d20-162">在这种情况下，该行为将应用到双工客户端的终结点和 WCF 将忽略的值<xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="a3d20-162">In this case, the behavior is applied to the duplex client's endpoint and WCF ignores the value of the <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A> property.</span></span>  
  
 <span data-ttu-id="a3d20-163">第二种方式是将该行为添加到 <xref:System.ServiceModel.Description.ContractDescription> 上的行为集合中。</span><span class="sxs-lookup"><span data-stu-id="a3d20-163">The second mechanism is to add the behavior to the behaviors collection on a <xref:System.ServiceModel.Description.ContractDescription>.</span></span>  
  
 <span data-ttu-id="a3d20-164">在 WCF 中的协定行为的示例包括<xref:System.ServiceModel.DeliveryRequirementsAttribute?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="a3d20-164">Examples of contract behaviors in WCF include the <xref:System.ServiceModel.DeliveryRequirementsAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="a3d20-165">有关更多信息和示例，请参见参考主题。</span><span class="sxs-lookup"><span data-stu-id="a3d20-165">For more information and an example, see the reference topic.</span></span>  
  
#### <a name="endpoint-behaviors"></a><span data-ttu-id="a3d20-166">终结点行为</span><span class="sxs-lookup"><span data-stu-id="a3d20-166">Endpoint Behaviors</span></span>  
 <span data-ttu-id="a3d20-167">终结点行为实现 <xref:System.ServiceModel.Description.IEndpointBehavior>，它是赖以修改特定终结点的整个服务或客户端运行时的主要机制。</span><span class="sxs-lookup"><span data-stu-id="a3d20-167">Endpoint behaviors, which implement <xref:System.ServiceModel.Description.IEndpointBehavior>, are the primary mechanism by which you modify the entire service or client run time for a specific endpoint.</span></span>  
  
 <span data-ttu-id="a3d20-168">向服务中添加终结点行为有两种方式。</span><span class="sxs-lookup"><span data-stu-id="a3d20-168">There are two mechanisms for adding endpoint behaviors to a service.</span></span>  
  
1.  <span data-ttu-id="a3d20-169">将行为添加到 <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="a3d20-169">Add the behavior to the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property.</span></span>  
  
2.  <span data-ttu-id="a3d20-170">实现用于扩展配置的自定义 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>。</span><span class="sxs-lookup"><span data-stu-id="a3d20-170">Implement a custom <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> that extends configuration.</span></span>  
  
 <span data-ttu-id="a3d20-171">有关更多信息和示例，请参见参考主题。</span><span class="sxs-lookup"><span data-stu-id="a3d20-171">For more information and an example, see the reference topic.</span></span>  
  
#### <a name="operation-behaviors"></a><span data-ttu-id="a3d20-172">操作行为</span><span class="sxs-lookup"><span data-stu-id="a3d20-172">Operation Behaviors</span></span>  
 <span data-ttu-id="a3d20-173">操作行为实现 <xref:System.ServiceModel.Description.IOperationBehavior> 接口，用于扩展每个操作的客户端和服务运行时。</span><span class="sxs-lookup"><span data-stu-id="a3d20-173">Operation behaviors, which implement the <xref:System.ServiceModel.Description.IOperationBehavior> interface, are used to extend both the client and service runtime for each operation.</span></span>  
  
 <span data-ttu-id="a3d20-174">向操作中添加操作行为有两种方式。</span><span class="sxs-lookup"><span data-stu-id="a3d20-174">There are two mechanisms for adding operation behaviors to an operation.</span></span> <span data-ttu-id="a3d20-175">第一种方式是创建要在对操作建模的方法上使用的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="a3d20-175">The first mechanism is to create a custom attribute to be used on the method that models the operation.</span></span> <span data-ttu-id="a3d20-176">当操作添加到<xref:System.ServiceModel.ServiceHost>或<xref:System.ServiceModel.ChannelFactory>，WCF 将所有<xref:System.ServiceModel.Description.IOperationBehavior>上特性的行为集合以<xref:System.ServiceModel.Description.OperationDescription>创建为该操作。</span><span class="sxs-lookup"><span data-stu-id="a3d20-176">When an operation is added to either a <xref:System.ServiceModel.ServiceHost> or a <xref:System.ServiceModel.ChannelFactory>, WCF adds any  <xref:System.ServiceModel.Description.IOperationBehavior> attributes to the behaviors collection on the <xref:System.ServiceModel.Description.OperationDescription> created for that operation.</span></span>  
  
 <span data-ttu-id="a3d20-177">第二种方式是直接将该行为添加到所构造的 <xref:System.ServiceModel.Description.OperationDescription> 上的行为集合中。</span><span class="sxs-lookup"><span data-stu-id="a3d20-177">The second mechanism is by directly adding the behavior to the behaviors collection on a constructed <xref:System.ServiceModel.Description.OperationDescription>.</span></span>  
  
 <span data-ttu-id="a3d20-178">在 WCF 中的操作行为的示例包括<xref:System.ServiceModel.OperationBehaviorAttribute>和<xref:System.ServiceModel.TransactionFlowAttribute>。</span><span class="sxs-lookup"><span data-stu-id="a3d20-178">Examples of operation behaviors in WCF include the <xref:System.ServiceModel.OperationBehaviorAttribute> and the <xref:System.ServiceModel.TransactionFlowAttribute>.</span></span>  
  
 <span data-ttu-id="a3d20-179">有关更多信息和示例，请参见参考主题。</span><span class="sxs-lookup"><span data-stu-id="a3d20-179">For more information and an example, see the reference topic.</span></span>  
  
### <a name="using-configuration-to-create-behaviors"></a><span data-ttu-id="a3d20-180">使用配置创建行为</span><span class="sxs-lookup"><span data-stu-id="a3d20-180">Using Configuration to Create Behaviors</span></span>  
 <span data-ttu-id="a3d20-181">服务和终结点以及协定行为可以设计成使用代码或属性进行指定；只有服务和终结点行为才可以使用应用程序或 Web 配置文件进行配置。</span><span class="sxs-lookup"><span data-stu-id="a3d20-181">Service and endpoint, and contract behaviors can by designed to be specified in code or using attributes; only service and endpoint behaviors can be configured using application or Web configuration files.</span></span> <span data-ttu-id="a3d20-182">使用属性来公开行为可以让开发人员在编辑时指定行为，而该行为在运行时是无法添加、删除或修改的。</span><span class="sxs-lookup"><span data-stu-id="a3d20-182">Exposing behaviors using attributes allows developers to specify a behavior at compilation-time that cannot be added, removed, or modified at runtime.</span></span> <span data-ttu-id="a3d20-183">这种方式通常适合于服务的正确操作始终需要的那些行为（例如 <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType> 属性的事务相关参数）。</span><span class="sxs-lookup"><span data-stu-id="a3d20-183">This is often suitable for behaviors that are always required for the correct operation of a service (for example, the transaction-related parameters to the <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType> attribute).</span></span> <span data-ttu-id="a3d20-184">使用配置来公开行为可以让开发人员将这些行为的指定和配置留给部署服务的那些人去完成。</span><span class="sxs-lookup"><span data-stu-id="a3d20-184">Exposing behaviors using configuration allows developers to leave the specification and configuration of those behaviors to those who deploy the service.</span></span> <span data-ttu-id="a3d20-185">这种方式适合于作为可选组件或其他特定于部署的配置的行为，比如是否为服务或服务的特定授权配置公开元数据。</span><span class="sxs-lookup"><span data-stu-id="a3d20-185">This is suitable for behaviors that are optional components or other deployment-specific configuration, such as whether metadata is exposed for the service or the particular authorization configuration for a service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3d20-186">也可以使用支持配置的行为，并通过将这些行为插入到 machine.config 配置文件并锁定这些项来强制执行公司的应用程序策略。</span><span class="sxs-lookup"><span data-stu-id="a3d20-186">You can also use behaviors that support configuration to enforce company application policies by inserting them into the machine.config configuration file and locking those items down.</span></span> <span data-ttu-id="a3d20-187">有关说明和示例，请参阅[如何： 在企业中锁定下终结点](../../../../docs/framework/wcf/extending/how-to-lock-down-endpoints-in-the-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d20-187">For a description and an example, see [How to: Lock Down Endpoints in the Enterprise](../../../../docs/framework/wcf/extending/how-to-lock-down-endpoints-in-the-enterprise.md).</span></span>  
  
 <span data-ttu-id="a3d20-188">若要使用配置来公开行为，开发人员必须创建 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> 的派生类，然后向配置注册该扩展。</span><span class="sxs-lookup"><span data-stu-id="a3d20-188">To expose a behavior using configuration, a developer must create a derived class of <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> and then register that extension with configuration.</span></span>  
  
 <span data-ttu-id="a3d20-189">下面的代码示例演示 <xref:System.ServiceModel.Description.IEndpointBehavior> 如何实现 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>：</span><span class="sxs-lookup"><span data-stu-id="a3d20-189">The following code example shows how an  <xref:System.ServiceModel.Description.IEndpointBehavior> implements <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>:</span></span>  
  
```  
// BehaviorExtensionElement members  
    public override Type BehaviorType  
    {  
      get { return typeof(EndpointBehaviorMessageInspector); }  
    }  
  
    protected override object CreateBehavior()  
    {  
      return new EndpointBehaviorMessageInspector();  
    }  
```  
  
 <span data-ttu-id="a3d20-190">若要让配置系统加载自定义 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>，必须将该类注册为扩展。</span><span class="sxs-lookup"><span data-stu-id="a3d20-190">In order for the configuration system to load a custom <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, it must be registered as an extension.</span></span> <span data-ttu-id="a3d20-191">下面的代码示例演示前一个终结点行为的配置文件：</span><span class="sxs-lookup"><span data-stu-id="a3d20-191">The following code example shows the configuration file for the preceding endpoint behavior:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        name="Microsoft.WCF.Documentation.SampleService"  
        behaviorConfiguration="metadataSupport"  
      >  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8080/ServiceMetadata" />  
          </baseAddresses>  
        </host>  
        <endpoint  
          address="/SampleService"  
          binding="wsHttpBinding"  
          behaviorConfiguration="withMessageInspector"   
          contract="Microsoft.WCF.Documentation.ISampleService"  
        />  
        <endpoint  
           address="mex"  
           binding="mexHttpBinding"  
           contract="IMetadataExchange"  
        />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="metadataSupport">  
        <serviceMetadata httpGetEnabled="true" httpGetUrl=""/>  
      </behavior>  
      </serviceBehaviors>  
      <endpointBehaviors>  
        <behavior name="withMessageInspector">  
          <endpointMessageInspector />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <extensions>  
      <behaviorExtensions>  
        <add   
          name="endpointMessageInspector"  
          type="Microsoft.WCF.Documentation.EndpointBehaviorMessageInspector, HostApplication, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"  
        />  
      </behaviorExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a3d20-192">其中`Microsoft.WCF.Documentation.EndpointBehaviorMessageInspector`是行为扩展类型和`HostApplication`是该类编译到程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="a3d20-192">Where `Microsoft.WCF.Documentation.EndpointBehaviorMessageInspector` is the behavior extension type and `HostApplication` is the name of the assembly into which that class has been compiled.</span></span>  
  
### <a name="evaluation-order"></a><span data-ttu-id="a3d20-193">计算顺序</span><span class="sxs-lookup"><span data-stu-id="a3d20-193">Evaluation Order</span></span>  
 <span data-ttu-id="a3d20-194"><xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> 和 <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> 负责从编程模型和说明生成运行时。</span><span class="sxs-lookup"><span data-stu-id="a3d20-194">The <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> and the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> are responsible for building the runtime from the programming model and description.</span></span> <span data-ttu-id="a3d20-195">如前面所述，行为可在服务、终结点、协定和操作中参与该生成过程。</span><span class="sxs-lookup"><span data-stu-id="a3d20-195">Behaviors, as previously described, contribute to that build process at the service, endpoint, contract, and operation.</span></span>  
  
 <span data-ttu-id="a3d20-196"><xref:System.ServiceModel.ServiceHost> 按以下顺序应用行为：</span><span class="sxs-lookup"><span data-stu-id="a3d20-196">The <xref:System.ServiceModel.ServiceHost> applies behaviors in the following order:</span></span>  
  
1.  <span data-ttu-id="a3d20-197">服务</span><span class="sxs-lookup"><span data-stu-id="a3d20-197">Service</span></span>  
  
2.  <span data-ttu-id="a3d20-198">协定</span><span class="sxs-lookup"><span data-stu-id="a3d20-198">Contract</span></span>  
  
3.  <span data-ttu-id="a3d20-199">终结点</span><span class="sxs-lookup"><span data-stu-id="a3d20-199">Endpoint</span></span>  
  
4.  <span data-ttu-id="a3d20-200">操作</span><span class="sxs-lookup"><span data-stu-id="a3d20-200">Operation</span></span>  
  
 <span data-ttu-id="a3d20-201">在任何行为集合内，不保证任何顺序。</span><span class="sxs-lookup"><span data-stu-id="a3d20-201">Within any collection of behaviors, no order is guaranteed.</span></span>  
  
 <span data-ttu-id="a3d20-202"><xref:System.ServiceModel.ChannelFactory%601> 按以下顺序应用行为：</span><span class="sxs-lookup"><span data-stu-id="a3d20-202">The <xref:System.ServiceModel.ChannelFactory%601> applies behaviors in the following order:</span></span>  
  
1.  <span data-ttu-id="a3d20-203">协定</span><span class="sxs-lookup"><span data-stu-id="a3d20-203">Contract</span></span>  
  
2.  <span data-ttu-id="a3d20-204">终结点</span><span class="sxs-lookup"><span data-stu-id="a3d20-204">Endpoint</span></span>  
  
3.  <span data-ttu-id="a3d20-205">操作</span><span class="sxs-lookup"><span data-stu-id="a3d20-205">Operation</span></span>  
  
 <span data-ttu-id="a3d20-206">在任何行为集合内，同样不保证任何顺序。</span><span class="sxs-lookup"><span data-stu-id="a3d20-206">Within any collection of behaviors, again, no order is guaranteed.</span></span>  
  
### <a name="adding-behaviors-programmatically"></a><span data-ttu-id="a3d20-207">以编程方式添加行为</span><span class="sxs-lookup"><span data-stu-id="a3d20-207">Adding Behaviors Programmatically</span></span>  
 <span data-ttu-id="a3d20-208">服务应用程序中 <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> 的属性不能在 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A?displayProperty=nameWithType> 上的 <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType> 方法之后进行修改。</span><span class="sxs-lookup"><span data-stu-id="a3d20-208">Properties of the <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> in the service application must not be modified subsequent to the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A?displayProperty=nameWithType> method on <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a3d20-209">有些成员（如 <xref:System.ServiceModel.ServiceHostBase.Credentials%2A?displayProperty=nameWithType> 属性以及 `AddServiceEndpoint` 和 <xref:System.ServiceModel.ServiceHostBase> 上的 <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> 方法）在此时点后修改时会引发异常。</span><span class="sxs-lookup"><span data-stu-id="a3d20-209">Some members, like the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A?displayProperty=nameWithType> property and the `AddServiceEndpoint` methods on <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>, throw an exception if modified past that point.</span></span> <span data-ttu-id="a3d20-210">允许修改其他成员，但结果不可确定。</span><span class="sxs-lookup"><span data-stu-id="a3d20-210">Others permit you to modify them, but the result is undefined.</span></span>  
  
 <span data-ttu-id="a3d20-211">同样，在调用 <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType> 上的 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> 之后不能在客户端上修改 <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> 值。</span><span class="sxs-lookup"><span data-stu-id="a3d20-211">Similarly, on the client the <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType> values must not be modified after the call to <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> on the <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a3d20-212"><xref:System.ServiceModel.ChannelFactory.Credentials%2A?displayProperty=nameWithType> 属性在此时点后修改时会引发异常，但其他客户端说明值可以正常修改而不会出现错误。</span><span class="sxs-lookup"><span data-stu-id="a3d20-212">The <xref:System.ServiceModel.ChannelFactory.Credentials%2A?displayProperty=nameWithType> property throws an exception if modified past that point, but the other client description values can be modified without error.</span></span> <span data-ttu-id="a3d20-213">但结果不可确定。</span><span class="sxs-lookup"><span data-stu-id="a3d20-213">The result, however, is undefined.</span></span>  
  
 <span data-ttu-id="a3d20-214">无论是对于服务还是客户端，建议您在调用 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> 之前修改说明。</span><span class="sxs-lookup"><span data-stu-id="a3d20-214">Whether for the service or client, it is recommended that you modify the description prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="inheritance-rules-for-behavior-attributes"></a><span data-ttu-id="a3d20-215">行为属性的继承规则</span><span class="sxs-lookup"><span data-stu-id="a3d20-215">Inheritance Rules for Behavior Attributes</span></span>  
 <span data-ttu-id="a3d20-216">所有四种类型的行为都可以使用属性进行填充 – 服务行为和协定行为。</span><span class="sxs-lookup"><span data-stu-id="a3d20-216">All four types of behaviors can be populated using attributes – service behaviors and contract behaviors.</span></span> <span data-ttu-id="a3d20-217">由于属性是在托管对象和成员上定义的，而托管对象和成员支持继承，因此有必要定义行为属性在继承上下文中的工作方式。</span><span class="sxs-lookup"><span data-stu-id="a3d20-217">Because attributes are defined on managed objects and members, and managed objects and members support inheritance, it is necessary to define how behavior attributes work in the context of inheritance.</span></span>  
  
 <span data-ttu-id="a3d20-218">总的来说，规则是这样的：对于特定范围（例如服务、协定或操作），该范围的继承层次结构中的所有行为属性均适用。</span><span class="sxs-lookup"><span data-stu-id="a3d20-218">At a high level, the rule is that for a particular scope (for example, service, contract, or operation), all behavior attributes in the inheritance hierarchy for that scope are applied.</span></span> <span data-ttu-id="a3d20-219">如果两个行为属性具有相同的类型，则使用派生程度最高的类型。</span><span class="sxs-lookup"><span data-stu-id="a3d20-219">If there are two behavior attributes of the same type, only the most-derived type is used.</span></span>  
  
#### <a name="service-behaviors"></a><span data-ttu-id="a3d20-220">服务行为</span><span class="sxs-lookup"><span data-stu-id="a3d20-220">Service Behaviors</span></span>  
 <span data-ttu-id="a3d20-221">对于给定的服务类，该类及该类的父类上的所有服务行为属性均适用。</span><span class="sxs-lookup"><span data-stu-id="a3d20-221">For a given service class, all service behavior attributes on that class, and on parents of that class, are applied.</span></span> <span data-ttu-id="a3d20-222">如果在继承层次结构中的多个位置应用同种属性类型，则使用派生程度最高的类型。</span><span class="sxs-lookup"><span data-stu-id="a3d20-222">If the same type of attribute is applied at multiple places in the inheritance hierarchy, the most-derived type is used.</span></span>  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple)]  
[AspNetCompatibilityRequirementsAttribute(  
    AspNetCompatibilityRequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
public class A { /* … */ }  
  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
public class B : A { /* … */}  
```  
  
 <span data-ttu-id="a3d20-223">例如在上例中，服务 B 结束时，其 <xref:System.ServiceModel.InstanceContextMode> 为 <xref:System.ServiceModel.InstanceContextMode.Single>、<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> 模式为 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> 且 <xref:System.ServiceModel.ConcurrencyMode> 为 <xref:System.ServiceModel.ConcurrencyMode.Single>。</span><span class="sxs-lookup"><span data-stu-id="a3d20-223">For example, in the preceding case, the service B ends up with an <xref:System.ServiceModel.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.Single>, an <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> mode of <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>, and a <xref:System.ServiceModel.ConcurrencyMode> of <xref:System.ServiceModel.ConcurrencyMode.Single>.</span></span> <span data-ttu-id="a3d20-224"><xref:System.ServiceModel.ConcurrencyMode> 为 <xref:System.ServiceModel.ConcurrencyMode.Single>，这是因为服务 B 上的 <xref:System.ServiceModel.ServiceBehaviorAttribute> 属性比服务 A 上的该属性“派生程度更高”。</span><span class="sxs-lookup"><span data-stu-id="a3d20-224">The <xref:System.ServiceModel.ConcurrencyMode> is <xref:System.ServiceModel.ConcurrencyMode.Single>, because <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute on service B is on "more derived" than that on service A.</span></span>  
  
#### <a name="contract-behaviors"></a><span data-ttu-id="a3d20-225">协定行为</span><span class="sxs-lookup"><span data-stu-id="a3d20-225">Contract Behaviors</span></span>  
 <span data-ttu-id="a3d20-226">对于给定的协定，该接口及该接口的父接口上的所有协定行为属性均适用。</span><span class="sxs-lookup"><span data-stu-id="a3d20-226">For a given contract, all contract behavior attributes on that interface and on parents of that interface, are applied.</span></span> <span data-ttu-id="a3d20-227">如果在继承层次结构中的多个位置应用同种属性类型，则使用派生程度最高的类型。</span><span class="sxs-lookup"><span data-stu-id="a3d20-227">If the same type of attribute is applied at multiple places in the inheritance hierarchy, the most-derived type is used.</span></span>  
  
#### <a name="operation-behaviors"></a><span data-ttu-id="a3d20-228">操作行为</span><span class="sxs-lookup"><span data-stu-id="a3d20-228">Operation Behaviors</span></span>  
 <span data-ttu-id="a3d20-229">如果给定操作不重写现有抽象或虚拟操作，则继承规则不适用。</span><span class="sxs-lookup"><span data-stu-id="a3d20-229">If a given operation does not override an existing abstract or virtual operation, no inheritance rules apply.</span></span>  
  
 <span data-ttu-id="a3d20-230">如果操作重写现有操作，则该操作及该操作的父操作上的所有操作行为属性均适用。</span><span class="sxs-lookup"><span data-stu-id="a3d20-230">If an operation does override an existing operation, then all operation behavior attributes on that operation and on parents of that operation, are applied.</span></span>  <span data-ttu-id="a3d20-231">如果在继承层次结构中的多个位置应用同种属性类型，则使用派生程度最高的类型。</span><span class="sxs-lookup"><span data-stu-id="a3d20-231">If the same type of attribute is applied at multiple places in the inheritance hierarchy, the most-derived type is used.</span></span>
