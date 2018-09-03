---
title: 自定义生存期
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: 1946608c69401fb08f6eb458a8adabea24563963
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467741"
---
# <a name="custom-lifetime"></a><span data-ttu-id="c3b28-102">自定义生存期</span><span class="sxs-lookup"><span data-stu-id="c3b28-102">Custom lifetime</span></span>

<span data-ttu-id="c3b28-103">此示例演示如何编写一个 Windows Communication Foundation (WCF) 扩展，用于提供对共享的 WCF 服务实例的自定义生存期服务。</span><span class="sxs-lookup"><span data-stu-id="c3b28-103">This sample demonstrates how to write a Windows Communication Foundation (WCF) extension to provide custom lifetime services for shared WCF service instances.</span></span>

> [!NOTE]
> <span data-ttu-id="c3b28-104">本文的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="c3b28-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>

## <a name="shared-instancing"></a><span data-ttu-id="c3b28-105">共享实例化</span><span class="sxs-lookup"><span data-stu-id="c3b28-105">Shared instancing</span></span>

<span data-ttu-id="c3b28-106">WCF 提供了多种实例化模式的服务实例。</span><span class="sxs-lookup"><span data-stu-id="c3b28-106">WCF offers several instancing modes for your service instances.</span></span> <span data-ttu-id="c3b28-107">本文中所述的共享实例化模式提供了一种共享多个通道之间的服务实例方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-107">The shared instancing mode covered in this article provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="c3b28-108">客户端可以联系服务中的工厂方法，并创建新的通道，以启动通信。</span><span class="sxs-lookup"><span data-stu-id="c3b28-108">Clients can contact a factory method in the service and create a new channel to start communication.</span></span> <span data-ttu-id="c3b28-109">下面的代码段显示了客户端应用程序如何创建新的通道向现有服务实例：</span><span class="sxs-lookup"><span data-stu-id="c3b28-109">The following code snippet shows how a client application creates a new channel to an existing service instance:</span></span>

```csharp
// Create a header for the shared instance id
MessageHeader shareableInstanceContextHeader = MessageHeader.CreateHeader(
        CustomHeader.HeaderName,
        CustomHeader.HeaderNamespace,
        Guid.NewGuid().ToString());

// Create the channel factory
ChannelFactory<IEchoService> channelFactory =
    new ChannelFactory<IEchoService>("echoservice");

// Create the first channel
IEchoService proxy = channelFactory.CreateChannel();

// Call an operation to create shared service instance
using (new OperationContextScope((IClientChannel)proxy))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy.Echo("Apple"));
}

((IChannel)proxy).Close();

// Create the second channel
IEchoService proxy2 = channelFactory.CreateChannel();

// Call an operation using the same header that will reuse the shared service instance
using (new OperationContextScope((IClientChannel)proxy2))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy2.Echo("Apple"));
}
```

<span data-ttu-id="c3b28-110">与其他实例化模式不同，共享实例化模式拥有一种释放服务实例的独特方式。</span><span class="sxs-lookup"><span data-stu-id="c3b28-110">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="c3b28-111">默认情况下，当所有通道处于关闭都状态时<xref:System.ServiceModel.InstanceContext>，WCF 服务运行时检查以查看是否在服务<xref:System.ServiceModel.InstanceContextMode>配置为<xref:System.ServiceModel.InstanceContextMode.PerCall>或<xref:System.ServiceModel.InstanceContextMode.PerSession>，并且如果因此释放该实例并认领这些资源。</span><span class="sxs-lookup"><span data-stu-id="c3b28-111">By default, when all the channels are closed for an <xref:System.ServiceModel.InstanceContext>, the WCF service runtime checks to see if the service <xref:System.ServiceModel.InstanceContextMode> is configured to <xref:System.ServiceModel.InstanceContextMode.PerCall> or <xref:System.ServiceModel.InstanceContextMode.PerSession>, and if so releases the instance and claims the resources.</span></span> <span data-ttu-id="c3b28-112">如果自定义<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>是正在使用，WCF 调用<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>释放该实例之前的提供程序实现的方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-112">If a custom <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is being used, WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the provider implementation before releasing the instance.</span></span> <span data-ttu-id="c3b28-113">如果<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>将返回`true`释放实例，否则<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>实现负责通知`Dispatcher`处于空闲状态通过使用回调方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-113">If <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> returns `true` the instance is released, otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span> <span data-ttu-id="c3b28-114">这是通过调用<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>提供程序方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-114">This is done by calling the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method of the provider.</span></span>

<span data-ttu-id="c3b28-115">此示例演示如何延迟释放<xref:System.ServiceModel.InstanceContext>与 20 秒的空闲超时。</span><span class="sxs-lookup"><span data-stu-id="c3b28-115">This sample demonstrates how you can delay releasing the <xref:System.ServiceModel.InstanceContext> with an idle timeout of 20 seconds.</span></span>

## <a name="extending-the-instancecontext"></a><span data-ttu-id="c3b28-116">扩展 InstanceContext</span><span class="sxs-lookup"><span data-stu-id="c3b28-116">Extending the InstanceContext</span></span>

<span data-ttu-id="c3b28-117">在 WCF 中，<xref:System.ServiceModel.InstanceContext>是服务实例之间的链接和`Dispatcher`。</span><span class="sxs-lookup"><span data-stu-id="c3b28-117">In WCF, <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="c3b28-118">WCF，可通过使用其可扩展对象模式添加新状态或行为来扩展此运行时组件。</span><span class="sxs-lookup"><span data-stu-id="c3b28-118">WCF allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="c3b28-119">若要使用新功能扩展现有的运行时类，或者，或将新的状态功能添加到一个对象，WCF 中使用的可扩展对象模式。</span><span class="sxs-lookup"><span data-stu-id="c3b28-119">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="c3b28-120">可扩展对象模式中有三个接口：<xref:System.ServiceModel.IExtensibleObject%601>、<xref:System.ServiceModel.IExtension%601> 和 <xref:System.ServiceModel.IExtensionCollection%601>。</span><span class="sxs-lookup"><span data-stu-id="c3b28-120">There are three interfaces in the extensible object pattern: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, and <xref:System.ServiceModel.IExtensionCollection%601>.</span></span>

<span data-ttu-id="c3b28-121"><xref:System.ServiceModel.IExtensibleObject%601>接口由对象实现，允许使用自定义其功能的扩展。</span><span class="sxs-lookup"><span data-stu-id="c3b28-121">The <xref:System.ServiceModel.IExtensibleObject%601> interface is implemented by objects to allow extensions that customize their functionality.</span></span>

<span data-ttu-id="c3b28-122"><xref:System.ServiceModel.IExtension%601> 接口由可作为类型为 `T` 的类扩展的对象来实现。</span><span class="sxs-lookup"><span data-stu-id="c3b28-122">The <xref:System.ServiceModel.IExtension%601> interface is implemented by objects that can be extensions of classes of type `T`.</span></span>

<span data-ttu-id="c3b28-123">最后，<xref:System.ServiceModel.IExtensionCollection%601>接口是一系列<xref:System.ServiceModel.IExtension%601>实现允许检索的实现<xref:System.ServiceModel.IExtension%601>按其类型。</span><span class="sxs-lookup"><span data-stu-id="c3b28-123">And finally, the <xref:System.ServiceModel.IExtensionCollection%601> interface is a collection of <xref:System.ServiceModel.IExtension%601> implementations that allows for retrieving an implementation of <xref:System.ServiceModel.IExtension%601> by their type.</span></span>

<span data-ttu-id="c3b28-124">因此，若要将扩展<xref:System.ServiceModel.InstanceContext>，则必须实现<xref:System.ServiceModel.IExtension%601>接口。</span><span class="sxs-lookup"><span data-stu-id="c3b28-124">Therefore, in order to extend the <xref:System.ServiceModel.InstanceContext>, you must implement the <xref:System.ServiceModel.IExtension%601> interface.</span></span> <span data-ttu-id="c3b28-125">在此示例项目中，`CustomLeaseExtension`类包含此实现。</span><span class="sxs-lookup"><span data-stu-id="c3b28-125">In this sample project, the `CustomLeaseExtension` class contains this implementation.</span></span>

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

<span data-ttu-id="c3b28-126"><xref:System.ServiceModel.IExtension%601> 接口具有 <xref:System.ServiceModel.IExtension%601.Attach%2A> 和 <xref:System.ServiceModel.IExtension%601.Detach%2A> 两个方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-126">The <xref:System.ServiceModel.IExtension%601> interface has two methods <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span></span> <span data-ttu-id="c3b28-127">顾名思义，当运行时将扩展附加到 <xref:System.ServiceModel.InstanceContext> 类的实例以及将扩展从该类的实例分离时，将会调用这两个方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-127">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="c3b28-128">在此示例中，`Attach` 方法用于跟踪属于当前扩展实例的 <xref:System.ServiceModel.InstanceContext> 对象。</span><span class="sxs-lookup"><span data-stu-id="c3b28-128">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

<span data-ttu-id="c3b28-129">此外，还必须将必要的实现添加到该扩展以提供扩展的生存期支持。</span><span class="sxs-lookup"><span data-stu-id="c3b28-129">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="c3b28-130">因此，`ICustomLease`接口以所需方法声明，并且在中实现`CustomLeaseExtension`类。</span><span class="sxs-lookup"><span data-stu-id="c3b28-130">Therefore, the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>

```csharp
interface ICustomLease
{
    bool IsIdle { get; }
    InstanceContextIdleCallback Callback { get; set; }
}

class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease
{
}
```

<span data-ttu-id="c3b28-131">当调用 WCF<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>中的方法<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>实现中，此调用将路由到<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>方法的`CustomLeaseExtension`。</span><span class="sxs-lookup"><span data-stu-id="c3b28-131">When WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation, this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="c3b28-132">然后，将`CustomLeaseExtension`检查其私有状态以查看是否<xref:System.ServiceModel.InstanceContext>处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="c3b28-132">Then, the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="c3b28-133">如果它处于空闲状态，它将返回`true`。</span><span class="sxs-lookup"><span data-stu-id="c3b28-133">If it is idle, it returns `true`.</span></span> <span data-ttu-id="c3b28-134">否则，它将针对指定的扩展生存期启动一个计时器。</span><span class="sxs-lookup"><span data-stu-id="c3b28-134">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>

```csharp
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

<span data-ttu-id="c3b28-135">在该计时器的`Elapsed`事件，调度程序中的回调函数调用以启动另一个清理周期。</span><span class="sxs-lookup"><span data-stu-id="c3b28-135">In the timer’s `Elapsed` event, the callback function in the Dispatcher is called in order to start another clean-up cycle.</span></span>

```csharp
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)
{
    lock (thisLock)
    {
        StopTimer();
        isIdle = true;
        Utility.WriteMessageToConsole(
            ResourceHelper.GetString("MsgLeaseExpired"));
        callback(owner);
    }
}
```

<span data-ttu-id="c3b28-136">没有新消息到达实例对于转为空闲状态时续订正在运行的计时器的方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-136">There's no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>

<span data-ttu-id="c3b28-137">此示例实现 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 以截获对 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 方法的调用，并将这些调用路由到 `CustomLeaseExtension`。</span><span class="sxs-lookup"><span data-stu-id="c3b28-137">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="c3b28-138"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 实现包含在 `CustomLifetimeLease` 类中。</span><span class="sxs-lookup"><span data-stu-id="c3b28-138">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="c3b28-139"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> WCF 即将发布的服务实例时调用方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-139">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when WCF is about to release the service instance.</span></span> <span data-ttu-id="c3b28-140">但是，在 ServiceBehavior 的 `ISharedSessionInstance` 集合中，只有特定 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 实现的一个实例。</span><span class="sxs-lookup"><span data-stu-id="c3b28-140">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="c3b28-141">这意味着无法知道如果<xref:System.ServiceModel.InstanceContext>WCF 检查当时关闭<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-141">This means there's no way of knowing if the <xref:System.ServiceModel.InstanceContext> is closed at the time WCF checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="c3b28-142">因此，此示例使用线程锁定将请求序列化到<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-142">Therefore, this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3b28-143">由于序列化可能会严重影响应用程序的性能，因此不推荐使用线程锁定方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-143">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>

<span data-ttu-id="c3b28-144">中使用的私有成员字段`CustomLifetimeLease`类来跟踪处于空闲状态，并返回<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-144">A private member field is used in the `CustomLifetimeLease` class to track the idle state and is returned by the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="c3b28-145">每次<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>调用方法时，`isIdle`返回字段并将其重置为`false`。</span><span class="sxs-lookup"><span data-stu-id="c3b28-145">Each time the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is called, the `isIdle` field is returned and reset to `false`.</span></span>  <span data-ttu-id="c3b28-146">必须将此值设置为 `false`，以确保调度程序调用 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-146">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>

```csharp
public bool IsIdle(InstanceContext instanceContext)
{
    get
    {
        lock (thisLock)
        {
            //...
            bool idleCopy = isIdle;
            isIdle = false;
            return idleCopy;
        }
    }
}
```

<span data-ttu-id="c3b28-147">如果<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>方法将返回`false`，调度程序通过注册一个回调函数<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-147">If the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> method returns `false`, the Dispatcher registers a callback function by using the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span> <span data-ttu-id="c3b28-148">此方法将接收对所释放的 <xref:System.ServiceModel.InstanceContext> 的引用。</span><span class="sxs-lookup"><span data-stu-id="c3b28-148">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="c3b28-149">因此，可以查询的示例代码`ICustomLease`类型扩展，并检查`ICustomLease.IsIdle`属性扩展的状态。</span><span class="sxs-lookup"><span data-stu-id="c3b28-149">Therefore, the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>

```csharp
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

<span data-ttu-id="c3b28-150">之前`ICustomLease.IsIdle`属性为选中状态，需要设置，因为这是必需的回调属性`CustomLeaseExtension`进入空闲状态时通知调度程序。</span><span class="sxs-lookup"><span data-stu-id="c3b28-150">Before the `ICustomLease.IsIdle` property is checked, the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="c3b28-151">如果 `ICustomLease.IsIdle` 返回 `true`，则 `isIdle` 私有成员仅在 `CustomLifetimeLease` 中设置为 `true`，并调用该回调方法。</span><span class="sxs-lookup"><span data-stu-id="c3b28-151">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="c3b28-152">由于该代码持有锁，其他线程无法更改此私有成员的值。</span><span class="sxs-lookup"><span data-stu-id="c3b28-152">Because the code holds a lock, other threads can't change the value of this private member.</span></span> <span data-ttu-id="c3b28-153">和下一次调度程序调用<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>，它将返回`true`并让调度程序释放该实例。</span><span class="sxs-lookup"><span data-stu-id="c3b28-153">And the next time Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, it returns `true` and lets Dispatcher release the instance.</span></span>

<span data-ttu-id="c3b28-154">由于自定义扩展的基础工作已完成，因此必须将其挂钩到服务模型。</span><span class="sxs-lookup"><span data-stu-id="c3b28-154">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="c3b28-155">要挂接`CustomLeaseExtension`实现<xref:System.ServiceModel.InstanceContext>，WCF 提供了<xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer>界面来执行的引导<xref:System.ServiceModel.InstanceContext>。</span><span class="sxs-lookup"><span data-stu-id="c3b28-155">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, WCF provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="c3b28-156">在此示例中，`CustomLeaseInitializer` 类实现此接口，并将 `CustomLeaseExtension` 的一个实例从仅方法初始化添加到 <xref:System.ServiceModel.InstanceContext.Extensions%2A> 集合。</span><span class="sxs-lookup"><span data-stu-id="c3b28-156">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="c3b28-157">此方法在初始化 <xref:System.ServiceModel.InstanceContext> 时由调度程序调用。</span><span class="sxs-lookup"><span data-stu-id="c3b28-157">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 <span data-ttu-id="c3b28-158">最后<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>实现挂接到服务模型使用<xref:System.ServiceModel.Description.IServiceBehavior>实现。</span><span class="sxs-lookup"><span data-stu-id="c3b28-158">Finally the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="c3b28-159">此实现将放置在 `CustomLeaseTimeAttribute` 类中，它还派生自 `Attribute` 基类，以将此行为作为特性公开。</span><span class="sxs-lookup"><span data-stu-id="c3b28-159">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the `Attribute` base class to expose this behavior as an attribute.</span></span>

```csharp
public void ApplyDispatchBehavior(ServiceDescription description,
           ServiceHostBase serviceHostBase)
{
    CustomLifetimeLease customLease = new CustomLifetimeLease(timeout);

    foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
    {
        ChannelDispatcher cd = cdb as ChannelDispatcher;

        if (cd != null)
        {
            foreach (EndpointDispatcher ed in cd.Endpoints)
            {
                ed.DispatchRuntime.InstanceContextProvider = customLease;
            }
        }
    }
}
```

<span data-ttu-id="c3b28-160">可使用 `CustomLeaseTime` 特性对此行为进行批注，以将其添加到示例服务类中。</span><span class="sxs-lookup"><span data-stu-id="c3b28-160">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

<span data-ttu-id="c3b28-161">运行示例时，操作请求和响应将显示在服务和客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="c3b28-161">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="c3b28-162">在每个控制台窗口中按 Enter 可以关闭服务和客户端。</span><span class="sxs-lookup"><span data-stu-id="c3b28-162">Press ENTER in each console window to shut down the service and client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c3b28-163">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="c3b28-163">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="c3b28-164">请确保执行了[的 Windows Communication Foundation 示例的一次性安装过程](one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="c3b28-164">Ensure that you've performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="c3b28-165">若要生成 C# 或 Visual Basic.NET 版本的解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="c3b28-165">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="c3b28-166">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="c3b28-166">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3b28-167">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="c3b28-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c3b28-168">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="c3b28-168">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="c3b28-169">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="c3b28-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c3b28-170">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="c3b28-170">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
