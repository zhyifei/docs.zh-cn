---
title: "自定义生存期"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1cbe73468e2ce1c8a4fe81a676c819b04d2ef760
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="custom-lifetime"></a><span data-ttu-id="e4b77-102">自定义生存期</span><span class="sxs-lookup"><span data-stu-id="e4b77-102">Custom Lifetime</span></span>
<span data-ttu-id="e4b77-103">此示例演示如何编写 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 扩展，以便为共享的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务实例提供自定义生存期服务。</span><span class="sxs-lookup"><span data-stu-id="e4b77-103">This sample demonstrates how to write a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] extension to provide custom lifetime services for shared [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4b77-104">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="e4b77-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="shared-instancing"></a><span data-ttu-id="e4b77-105">共享实例化</span><span class="sxs-lookup"><span data-stu-id="e4b77-105">Shared Instancing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="e4b77-106"> 为服务实例提供了多种实例化模式。</span><span class="sxs-lookup"><span data-stu-id="e4b77-106"> offers several instancing modes for your service instances.</span></span> <span data-ttu-id="e4b77-107">本主题中介绍的共享实例化模式提供了一种用于在多个通道之间共享一个服务实例的方法。</span><span class="sxs-lookup"><span data-stu-id="e4b77-107">The Shared Instancing mode covered in this topic provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="e4b77-108">客户端可以在本地解析实例的终结点地址，或与该服务中的工厂方法联系，以获取正在运行的实例的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="e4b77-108">Clients can either resolve the instance’s endpoint address locally or contact a factory method in the service to obtain the endpoint address of a running instance.</span></span> <span data-ttu-id="e4b77-109">在客户端获取终结点地址后，它就可以创建一个新通道并开始通信。</span><span class="sxs-lookup"><span data-stu-id="e4b77-109">Once it has the endpoint address, it can create a new channel and start communication.</span></span> <span data-ttu-id="e4b77-110">以下代码段演示客户端应用程序如何向现有服务实例创建一个新通道。</span><span class="sxs-lookup"><span data-stu-id="e4b77-110">The following code snippet shows how a client application creates a new channel to an existing service instance.</span></span>  
  
```  
// Create the first channel.  
IEchoService proxy = channelFactory.CreateChannel();  
  
// Resolve the instance.  
EndpointAddress epa = ((IClientChannel)proxy).ResolveInstance();  
  
// Create new channel factory with the endpoint address resolved by   
// previous statement.  
ChannelFactory<IEchoService> channelFactory2 =  
                new ChannelFactory<IEchoService>("echoservice",  
                epa);  
  
// Create the second channel to the same instance.  
IEchoService proxy2 = channelFactory2.CreateChannel();  
```  
  
 <span data-ttu-id="e4b77-111">与其他实例化模式不同，共享实例化模式拥有一种释放服务实例的独特方式。</span><span class="sxs-lookup"><span data-stu-id="e4b77-111">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="e4b77-112">当一个实例的所有通道都关闭时，服务 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 运行时将启动一个计时器。</span><span class="sxs-lookup"><span data-stu-id="e4b77-112">When all the channels are closed for an instance, the service [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime starts a timer.</span></span> <span data-ttu-id="e4b77-113">如果在超时值已到之前没有人进行连接，则 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 将释放该实例并认领这些资源。</span><span class="sxs-lookup"><span data-stu-id="e4b77-113">If nobody makes a connection before the timeout expires, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] releases the instance and claims the resources.</span></span> <span data-ttu-id="e4b77-114">作为拆卸过程的一部分，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 将在释放该实例之前调用所有 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 实现的 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 方法。</span><span class="sxs-lookup"><span data-stu-id="e4b77-114">As a part of the teardown procedure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of all <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementations before releasing the instance.</span></span> <span data-ttu-id="e4b77-115">如果它们全都返回 `true`，则释放该实例。</span><span class="sxs-lookup"><span data-stu-id="e4b77-115">If all of them return `true` the instance is released.</span></span> <span data-ttu-id="e4b77-116">否则，<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 实现负责通过回调方法来通知处于空闲状态的 `Dispatcher`。</span><span class="sxs-lookup"><span data-stu-id="e4b77-116">Otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span>  
  
 <span data-ttu-id="e4b77-117">默认情况下，<xref:System.ServiceModel.InstanceContext> 的空闲超时值为一分钟。</span><span class="sxs-lookup"><span data-stu-id="e4b77-117">By default, the idle timeout value of <xref:System.ServiceModel.InstanceContext> is one minute.</span></span> <span data-ttu-id="e4b77-118">但是，此示例演示如何使用自定义扩展来对此进行扩展。</span><span class="sxs-lookup"><span data-stu-id="e4b77-118">However this sample demonstrates how you can extend this using a custom extension.</span></span>  
  
## <a name="extending-the-instancecontext"></a><span data-ttu-id="e4b77-119">扩展 InstanceContext</span><span class="sxs-lookup"><span data-stu-id="e4b77-119">Extending the InstanceContext</span></span>  
 <span data-ttu-id="e4b77-120">在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中，<xref:System.ServiceModel.InstanceContext> 是服务实例和 `Dispatcher` 之间的链接。</span><span class="sxs-lookup"><span data-stu-id="e4b77-120">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="e4b77-121"> 允许您通过使用此运行时组件的可扩展对象模式添加新状态或行为，以扩展此组件。</span><span class="sxs-lookup"><span data-stu-id="e4b77-121"> allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="e4b77-122">在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中的可扩展对象模式下，可以用新功能来扩展现有的运行库类，或者向对象中添加新的状态功能。</span><span class="sxs-lookup"><span data-stu-id="e4b77-122">The extensible object pattern is used in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="e4b77-123">可扩展对象模式中有三个接口：`IExtensibleObject<T>`、`IExtension<T>` 和 `IExtensionCollection<T>`。</span><span class="sxs-lookup"><span data-stu-id="e4b77-123">There are three interfaces in the extensible object pattern: `IExtensibleObject<T>`, `IExtension<T>`, and `IExtensionCollection<T>`.</span></span>  
  
 <span data-ttu-id="e4b77-124">`IExtensibleObject<T>` 接口由对象实现，以允许进行自定义其功能的扩展。</span><span class="sxs-lookup"><span data-stu-id="e4b77-124">The `IExtensibleObject<T>` interface is implemented by objects to allow extensions which customize their functionality.</span></span>  
  
 <span data-ttu-id="e4b77-125">`IExtension<T>` 接口由可作为类型为 `T` 的类扩展的对象来实现。</span><span class="sxs-lookup"><span data-stu-id="e4b77-125">The `IExtension<T>` interface is implemented by objects that can be extensions of classes of type `T`.</span></span>  
  
 <span data-ttu-id="e4b77-126">最后，`IExtensionCollection<T>` 接口是允许按类型检索 `IExtensions` 的 `IExtensions` 集合。</span><span class="sxs-lookup"><span data-stu-id="e4b77-126">And finally, the `IExtensionCollection<T>` interface is a collection of `IExtensions` that allows for retrieving `IExtensions` by their type.</span></span>  
  
 <span data-ttu-id="e4b77-127">因此，为了扩展 <xref:System.ServiceModel.InstanceContext>，必须实现 `IExtension` 接口。</span><span class="sxs-lookup"><span data-stu-id="e4b77-127">Therefore in order to extend the <xref:System.ServiceModel.InstanceContext> you must implement the `IExtension` interface.</span></span> <span data-ttu-id="e4b77-128">在此示例项目中，`CustomLeaseExtension` 类包含此实现。</span><span class="sxs-lookup"><span data-stu-id="e4b77-128">In this sample project the `CustomLeaseExtension` class contains this implementation.</span></span>  
  
```  
class CustomLeaseExtension : IExtension<InstanceContext>  
{  
}  
```  
  
 <span data-ttu-id="e4b77-129">`IExtension` 接口具有 `Attach` 和 `Detach` 两个方法。</span><span class="sxs-lookup"><span data-stu-id="e4b77-129">The `IExtension` interface has two methods `Attach` and `Detach`.</span></span> <span data-ttu-id="e4b77-130">顾名思义，当运行时将扩展附加到 <xref:System.ServiceModel.InstanceContext> 类的实例以及将扩展从该类的实例分离时，将会调用这两个方法。</span><span class="sxs-lookup"><span data-stu-id="e4b77-130">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="e4b77-131">在此示例中，`Attach` 方法用于跟踪属于当前扩展实例的 <xref:System.ServiceModel.InstanceContext> 对象。</span><span class="sxs-lookup"><span data-stu-id="e4b77-131">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>  
  
```  
InstanceContext owner;  
  
public void Attach(InstanceContext owner)  
{  
  this.owner = owner;   
}  
```  
  
 <span data-ttu-id="e4b77-132">此外，还必须将必要的实现添加到该扩展以提供扩展的生存期支持。</span><span class="sxs-lookup"><span data-stu-id="e4b77-132">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="e4b77-133">因此，将使用所需的方法来声明 `ICustomLease` 接口，并在 `CustomLeaseExtension` 类中实现该接口。</span><span class="sxs-lookup"><span data-stu-id="e4b77-133">Therefore the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>  
  
```  
interface ICustomLease  
{  
    bool IsIdle { get; }          
    InstanceContextIdleCallback Callback { get; set; }  
}  
  
class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease  
{  
}  
```  
  
 <span data-ttu-id="e4b77-134">当 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 调用 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 实现中的 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 方法时，此调用将路由到 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 的 `CustomLeaseExtension` 方法。</span><span class="sxs-lookup"><span data-stu-id="e4b77-134">When [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="e4b77-135">然后，`CustomLeaseExtension` 将检查其私有状态，以查看 <xref:System.ServiceModel.InstanceContext> 是否处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="e4b77-135">Then the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="e4b77-136">如果它处于空闲状态，则返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="e4b77-136">If it is idle it returns `true`.</span></span> <span data-ttu-id="e4b77-137">否则，它将针对指定的扩展生存期启动一个计时器。</span><span class="sxs-lookup"><span data-stu-id="e4b77-137">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>  
  
```  
public bool IsIdle  
{  
  get  
  {  
    lock (thisLock)  
    {  
      if (isIdle)  
      {  
        return true;  
      }  
      else  
      {  
        StartTimer();  
        return false;  
      }  
    }  
  }  
}  
```  
  
 <span data-ttu-id="e4b77-138">在该计时器的 `Elapsed` 事件中，将调用调度程序中的回调功能以启动另一个清理周期。</span><span class="sxs-lookup"><span data-stu-id="e4b77-138">In the timer’s `Elapsed` event the callback function in the Dispatcher is called in order to start another clean up cycle.</span></span>  
  
```  
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)  
{  
    idleTimer.Stop();  
    isIdle = true;    
    callback(owner);  
}  
```  
  
 <span data-ttu-id="e4b77-139">对于转为空闲状态的实例，当有新消息到达时，将无法续订正在运行的计时器。</span><span class="sxs-lookup"><span data-stu-id="e4b77-139">There is no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>  
  
 <span data-ttu-id="e4b77-140">此示例实现 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 以截获对 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 方法的调用，并将这些调用路由到 `CustomLeaseExtension`。</span><span class="sxs-lookup"><span data-stu-id="e4b77-140">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="e4b77-141"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 实现包含在 `CustomLifetimeLease` 类中。</span><span class="sxs-lookup"><span data-stu-id="e4b77-141">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="e4b77-142"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 要释放此服务实例时，将会调用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 方法。</span><span class="sxs-lookup"><span data-stu-id="e4b77-142">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is about to release the service instance.</span></span> <span data-ttu-id="e4b77-143">但是，在 ServiceBehavior 的 `ISharedSessionInstance` 集合中，只有特定 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 实现的一个实例。</span><span class="sxs-lookup"><span data-stu-id="e4b77-143">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="e4b77-144">这意味着在 <xref:System.ServiceModel.InstanceContext> 检查 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 方法时，将无法识别关闭的 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>。</span><span class="sxs-lookup"><span data-stu-id="e4b77-144">This means there is no way of knowing the <xref:System.ServiceModel.InstanceContext> being closed at the time [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="e4b77-145">因此，此示例使用线程锁定将请求序列化到 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e4b77-145">Therefore this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e4b77-146">由于序列化可能会严重影响应用程序的性能，因此不推荐使用线程锁定方法。</span><span class="sxs-lookup"><span data-stu-id="e4b77-146">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>  
  
 <span data-ttu-id="e4b77-147">私有成员变量将在 `CustomLeaseExtension` 类中使用以跟踪 `IsIdle` 值。</span><span class="sxs-lookup"><span data-stu-id="e4b77-147">A private member variable is used in the `CustomLeaseExtension` class to track the `IsIdle` value.</span></span> <span data-ttu-id="e4b77-148">每次检索 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 的值时，`IsIdle` 私有成员都会返回并重置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="e4b77-148">Each time the value of <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is retrieved the `IsIdle` private member is returned and reset to `false`.</span></span> <span data-ttu-id="e4b77-149">必须将此值设置为 `false`，以确保调度程序调用 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e4b77-149">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>  
  
```  
public bool IsIdle  
{  
    get   
    {  
       lock (thisLock)  
       {  
           bool idleCopy = isIdle;  
           isIdle = false;  
           return idleCopy;  
       }  
    }  
}  
```  
  
 <span data-ttu-id="e4b77-150">如果 `ISharedSessionLifetime.IsIdle` 属性返回 `false`，则调度程序会使用 `NotifyIdle` 方法来注册一个回调函数。</span><span class="sxs-lookup"><span data-stu-id="e4b77-150">If the `ISharedSessionLifetime.IsIdle` property returns `false` the Dispatcher registers a callback function by using the `NotifyIdle` method.</span></span> <span data-ttu-id="e4b77-151">此方法将接收对所释放的 <xref:System.ServiceModel.InstanceContext> 的引用。</span><span class="sxs-lookup"><span data-stu-id="e4b77-151">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="e4b77-152">因此，该示例代码可查询 `ICustomLease` 类型扩展，并检查处于扩展状态的 `ICustomLease.IsIdle` 属性。</span><span class="sxs-lookup"><span data-stu-id="e4b77-152">Therefore the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>  
  
```  
public void NotifyIdle(InstanceContextIdleCallback callback,   
            InstanceContext instanceContext)  
{  
    lock (thisLock)  
    {  
       ICustomLease customLease =  
           instanceContext.Extensions.Find<ICustomLease>();  
       customLease.Callback = callback;   
       isIdle = customLease.IsIdle;  
       if (isIdle)  
       {  
             callback(instanceContext);  
       }  
    }   
}  
```  
  
 <span data-ttu-id="e4b77-153">在检查 `ICustomLease.IsIdle` 属性之前，需要设置 Callback 属性，否则，`CustomLeaseExtension` 变为空闲状态后就无法通知调度程序。</span><span class="sxs-lookup"><span data-stu-id="e4b77-153">Before the `ICustomLease.IsIdle` property is checked the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="e4b77-154">如果 `ICustomLease.IsIdle` 返回 `true`，则 `isIdle` 私有成员仅在 `CustomLifetimeLease` 中设置为 `true`，并调用该回调方法。</span><span class="sxs-lookup"><span data-stu-id="e4b77-154">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="e4b77-155">由于该代码持有一个锁，因此其他线程无法更改此私有成员的值。</span><span class="sxs-lookup"><span data-stu-id="e4b77-155">Because the code holds a lock, other threads cannot change the value of this private member.</span></span> <span data-ttu-id="e4b77-156">调度程序下次检查 `ISharedSessionLifetime.IsIdle` 时，它将返回 `true`，并让调度程序释放该实例。</span><span class="sxs-lookup"><span data-stu-id="e4b77-156">And the next time Dispatcher checks the `ISharedSessionLifetime.IsIdle`, it returns `true` and lets Dispatcher release the instance.</span></span>  
  
 <span data-ttu-id="e4b77-157">由于自定义扩展的基础工作已完成，因此必须将其挂钩到服务模型。</span><span class="sxs-lookup"><span data-stu-id="e4b77-157">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="e4b77-158">为了将 `CustomLeaseExtension` 实现挂钩到 <xref:System.ServiceModel.InstanceContext>，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供了 <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> 接口以执行 <xref:System.ServiceModel.InstanceContext> 的引导。</span><span class="sxs-lookup"><span data-stu-id="e4b77-158">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="e4b77-159">在此示例中，`CustomLeaseInitializer` 类实现此接口，并将 `CustomLeaseExtension` 的一个实例从仅方法初始化添加到 <xref:System.ServiceModel.InstanceContext.Extensions%2A> 集合。</span><span class="sxs-lookup"><span data-stu-id="e4b77-159">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="e4b77-160">此方法在初始化 <xref:System.ServiceModel.InstanceContext> 时由调度程序调用。</span><span class="sxs-lookup"><span data-stu-id="e4b77-160">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>  
  
```  
public void Initialize(InstanceContext instanceContext, Message message)  
{  
  IExtension<InstanceContext> customLeaseExtension =  
    new CustomLeaseExtension(timeout);  
  instanceContext.Extensions.Add(customLeaseExtension);  
}  
```  
  
 <span data-ttu-id="e4b77-161">最后`System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime`和<xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer>实现是已挂钩到服务模型使用<xref:System.ServiceModel.Description.IServiceBehavior>实现。</span><span class="sxs-lookup"><span data-stu-id="e4b77-161">Finally the `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` and <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> implementations are is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="e4b77-162">此实现将放置在 `CustomLeaseTimeAttribute` 类中，它还派生自 `Attribute` 基类，以将此行为作为特性公开。</span><span class="sxs-lookup"><span data-stu-id="e4b77-162">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the `Attribute` base class to expose this behavior as an attribute.</span></span> <span data-ttu-id="e4b77-163">在 `IServiceBehavior.ApplyBehavior` 方法中，<xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> 和 `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` 实现的实例分别添加到 `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes` 的 <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> 和 <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> 集合。</span><span class="sxs-lookup"><span data-stu-id="e4b77-163">In the `IServiceBehavior.ApplyBehavior` method, instances of <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> and `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` implementations are added to the `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes` and <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> collections of the <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> respectively.</span></span>  
  
```  
public void ApplyBehavior(ServiceDescription description,   
           ServiceHostBase serviceHostBase,   
           Collection<DispatchBehavior> behaviors,  
           Collection<BindingParameterCollection> parameters)  
{  
    CustomLifetimeLease customLease = new CustomLifetimeLease();  
    CustomLeaseInitializer initializer =   
                new CustomLeaseInitializer(timeout);  
  
    foreach (DispatchBehavior dispatchBehavior in behaviors)  
    {  
        dispatchBehavior.InstanceContextLifetimes.Add(customLease);  
        dispatchBehavior.InstanceContextInitializers.Add(initializer);  
    }  
}  
```  
  
 <span data-ttu-id="e4b77-164">可使用 `CustomLeaseTime` 特性对此行为进行批注，以将其添加到示例服务类中。</span><span class="sxs-lookup"><span data-stu-id="e4b77-164">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Shareable)]  
[CustomLeaseTime(Timeout = 20000)]  
public class EchoService : IEchoService  
{  
  //…  
}  
```  
  
 <span data-ttu-id="e4b77-165">运行示例时，操作请求和响应将显示在服务和客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="e4b77-165">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="e4b77-166">在每个控制台窗口中按 Enter 可以关闭服务和客户端。</span><span class="sxs-lookup"><span data-stu-id="e4b77-166">Press ENTER in each console window to shut down the service and client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e4b77-167">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="e4b77-167">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e4b77-168">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b77-168">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="e4b77-169">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e4b77-169">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="e4b77-170">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b77-170">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e4b77-171">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="e4b77-171">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e4b77-172">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="e4b77-172">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e4b77-173">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="e4b77-173">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e4b77-174">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="e4b77-174">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`  
  
## <a name="see-also"></a><span data-ttu-id="e4b77-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4b77-175">See Also</span></span>
