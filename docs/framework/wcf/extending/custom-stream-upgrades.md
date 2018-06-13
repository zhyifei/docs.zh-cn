---
title: 自定义流升级
ms.date: 03/30/2017
ms.assetid: e3da85c8-57f3-4e32-a4cb-50123f30fea6
ms.openlocfilehash: 84edac7a4dbaaf1a01332f5c0af29319c279dd1b
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806027"
---
# <a name="custom-stream-upgrades"></a><span data-ttu-id="a4ec4-102">自定义流升级</span><span class="sxs-lookup"><span data-stu-id="a4ec4-102">Custom Stream Upgrades</span></span>
<span data-ttu-id="a4ec4-103">面向流的传输（如 TCP 和命名管道）对客户端与服务器之间的连续字节流进行操作。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-103">Stream-oriented transports such as TCP and Named Pipes operate on a continuous stream of bytes between the client and server.</span></span> <span data-ttu-id="a4ec4-104">该流通过 <xref:System.IO.Stream> 对象实现。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-104">This stream is realized by a  <xref:System.IO.Stream> object.</span></span> <span data-ttu-id="a4ec4-105">在流升级中，客户端需要向通道堆栈中添加可选的协议层，并要求通信通道的另一端也执行该操作。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-105">In a stream upgrade, the client wants to add an optional protocol layer to the channel stack, and asks the other end of the communication channel to do so.</span></span> <span data-ttu-id="a4ec4-106">流升级包括使用升级后的对象替换原始 <xref:System.IO.Stream> 对象的过程。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-106">The stream upgrade consists in replacing the original <xref:System.IO.Stream> object with an upgraded one.</span></span>  
  
 <span data-ttu-id="a4ec4-107">例如，可以直接在传输流之上生成压缩流。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-107">For example, you can build a compression stream directly on top of the transport stream.</span></span> <span data-ttu-id="a4ec4-108">在这种情况下，原始传输 <xref:System.IO.Stream> 将替换为围绕原始传输流包装压缩 <xref:System.IO.Stream> 的传输流。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-108">In this case the original transport <xref:System.IO.Stream> is replaced with one that wraps the compression <xref:System.IO.Stream> around the original one.</span></span>  
  
 <span data-ttu-id="a4ec4-109">可以应用多次流升级，每次升级都包装前一次升级。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-109">You can apply multiple stream upgrades, each wrapping the preceding one.</span></span>  
  
## <a name="how-stream-upgrades-work"></a><span data-ttu-id="a4ec4-110">流升级如何工作</span><span class="sxs-lookup"><span data-stu-id="a4ec4-110">How Stream Upgrades Work</span></span>  
 <span data-ttu-id="a4ec4-111">流升级过程包括四个部分。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-111">There are four components to the stream upgrade process.</span></span>  
  
1.  <span data-ttu-id="a4ec4-112">升级流*发起程序*开始该过程： 在运行时，它可以启动到其连接的另一端升级通道传输层的请求。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-112">An upgrade stream *Initiator* begins the process: at run-time it can initiate a request to the other end of its connection to upgrade the channel transport layer.</span></span>  
  
2.  <span data-ttu-id="a4ec4-113">升级流*接受程序*执行该升级： 在运行时接收来自其他计算机中，升级请求，并且如果可能，将接受该升级。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-113">An upgrade stream *Acceptor* carries out the upgrade: at run-time it receives the upgrade request from the other machine, and if possible, accepts the upgrade.</span></span>  
  
3.  <span data-ttu-id="a4ec4-114">升级*提供程序*创建*发起程序*客户端上与*接受程序*服务器上。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-114">An upgrade *Provider* creates the *Initiator* on the client and the *Acceptor* on the server.</span></span>  
  
4.  <span data-ttu-id="a4ec4-115">流升级*绑定元素*添加到服务和客户端上的绑定，并在运行时创建提供程序。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-115">A stream upgrade *Binding Element* is added to the bindings on the service and the client, and creates the provider at runtime.</span></span>  
  
 <span data-ttu-id="a4ec4-116">请注意，如果要进行多个升级，则发起程序和接受程序将会封装状态计算机，以便强制实施哪些升级转变对于每次“发起”都是有效的。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-116">Note that in the case of multiple upgrades, the Initiator and Acceptor encapsulate state machines to enforce which upgrade transitions are valid for each Initiation.</span></span>  
  
## <a name="how-to-implement-a-stream-upgrade"></a><span data-ttu-id="a4ec4-117">如何实现流升级</span><span class="sxs-lookup"><span data-stu-id="a4ec4-117">How to Implement a Stream Upgrade</span></span>  
 <span data-ttu-id="a4ec4-118">Windows Communication Foundation (WCF) 提供了四个`abstract`可以实现的类：</span><span class="sxs-lookup"><span data-stu-id="a4ec4-118">Windows Communication Foundation (WCF) provides four `abstract` classes that you can implement:</span></span>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeInitiator?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeProvider?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement?displayProperty=nameWithType>  
  
 <span data-ttu-id="a4ec4-119">若要实现自定义流升级，请执行下列操作。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-119">To implement a custom stream upgrade, do the following.</span></span> <span data-ttu-id="a4ec4-120">此过程在客户端计算机和服务器计算机上均实现最低流升级过程。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-120">This procedure implements a minimal stream upgrade process on both the client and server machines.</span></span>  
  
1.  <span data-ttu-id="a4ec4-121">创建用于实现 <xref:System.ServiceModel.Channels.StreamUpgradeInitiator> 的类。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-121">Create a class that implements <xref:System.ServiceModel.Channels.StreamUpgradeInitiator>.</span></span>  
  
    1.  <span data-ttu-id="a4ec4-122">重写要在所升级的流中采用的 <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.InitiateUpgrade%2A> 方法，并返回升级后的流。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-122">Override the <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.InitiateUpgrade%2A> method to take in the stream to be upgraded, and return the upgraded stream.</span></span> <span data-ttu-id="a4ec4-123">此方法同步工作；异步启动升级存在类似方法。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-123">This method works synchronously; there are analogous methods to initiate the upgrade asynchronously.</span></span>  
  
    2.  <span data-ttu-id="a4ec4-124">重写 <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> 方法以检查其他升级。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-124">Override the <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> method to check for additional upgrades.</span></span>  
  
2.  <span data-ttu-id="a4ec4-125">创建用于实现 <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor> 的类。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-125">Create a class that implements <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor>.</span></span>  
  
    1.  <span data-ttu-id="a4ec4-126">重写要在所升级的流中采用的 <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.AcceptUpgrade%2A> 方法，并返回升级后的流。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-126">Override the <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.AcceptUpgrade%2A> method to take in the stream to be upgraded, and return the upgraded stream.</span></span> <span data-ttu-id="a4ec4-127">此方法同步工作；异步接受升级存在类似方法。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-127">This method works synchronously; there are analogous methods to accept the upgrade asynchronously.</span></span>  
  
    2.  <span data-ttu-id="a4ec4-128">重写 <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> 方法，以确定在升级过程中的此时该升级接受程序是否支持请求的升级。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-128">Override the <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> method to determine if the upgrade requested is supported by this upgrade acceptor at this point in the upgrade process.</span></span>  
  
3.  <span data-ttu-id="a4ec4-129">创建用于实现 <xref:System.ServiceModel.Channels.StreamUpgradeProvider> 的类。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-129">Create a class the implements <xref:System.ServiceModel.Channels.StreamUpgradeProvider>.</span></span> <span data-ttu-id="a4ec4-130">重写 <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeAcceptor%2A> 方法和 <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeInitiator%2A> 方法，以返回步骤 2 和步骤 1 中定义的接受程序和发起程序的实例。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-130">Override the <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeAcceptor%2A> and the <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeInitiator%2A> methods to return instances of the acceptor and initiator defined in steps 2 and 1.</span></span>  
  
4.  <span data-ttu-id="a4ec4-131">创建用于实现 <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement> 的类。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-131">Create a class that implements <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>.</span></span>  
  
    1.  <span data-ttu-id="a4ec4-132">在客户端上重写 <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildClientStreamUpgradeProvider%2A> 方法，然后在服务上重写 <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildServerStreamUpgradeProvider%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-132">Override the <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildClientStreamUpgradeProvider%2A> method on the client and the <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildServerStreamUpgradeProvider%2A> method on the service.</span></span>  
  
    2.  <span data-ttu-id="a4ec4-133">在客户端上重写 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> 方法，然后在服务上重写 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> 方法，以便将升级“绑定元素”添加到 <xref:System.ServiceModel.Channels.BindingContext.BindingParameters%2A>。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-133">Override the <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> method on the client and the <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> method on the service to add the upgrade Binding Element to <xref:System.ServiceModel.Channels.BindingContext.BindingParameters%2A>.</span></span>  
  
5.  <span data-ttu-id="a4ec4-134">将新的流升级绑定元素添加到服务器计算机和客户端计算机上的绑定。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-134">Add the new stream upgrade binding element to bindings on the server and client machines.</span></span>  
  
## <a name="security-upgrades"></a><span data-ttu-id="a4ec4-135">安全升级</span><span class="sxs-lookup"><span data-stu-id="a4ec4-135">Security Upgrades</span></span>  
 <span data-ttu-id="a4ec4-136">添加安全升级是常规流升级过程的专用版本。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-136">Adding a security upgrade is a specialized version of the general stream upgrade process.</span></span>  
  
 <span data-ttu-id="a4ec4-137">WCF 已为升级流安全提供了两个绑定元素。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-137">WCF already provides two binding elements for upgrading stream security.</span></span> <span data-ttu-id="a4ec4-138">传输级安全的配置由 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement> 和 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement> 封装，可以对该两个元素进行配置并将其添加到自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-138">The configuration of transport-level security is encapsulated by the <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement> and the <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement> which can be configured and added to a custom binding.</span></span> <span data-ttu-id="a4ec4-139">这些绑定元素扩展用于生成客户端和服务器流升级提供程序的 <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement> 类。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-139">These binding elements extend the <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement> class that builds the client and server stream upgrade providers.</span></span> <span data-ttu-id="a4ec4-140">这些绑定元素包含的方法可用于创建专用的安全流升级提供程序类（不是 `public`），因此对于这两种情况，您需要做的只是将绑定元素添加到绑定。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-140">These binding elements have methods that create the specialized security stream upgrade provider classes, which are not `public`, so for these two cases all you need to do is to add the binding element to the binding.</span></span>  
  
 <span data-ttu-id="a4ec4-141">对于上述两个绑定元素都不满足的安全方案，可从上述发起程序、接受程序和提供程序的基类派生三个与安全相关的 `abstract` 类：</span><span class="sxs-lookup"><span data-stu-id="a4ec4-141">For security scenarios not met by the above two binding elements, three security-related `abstract` classes are derived from the above initiator, acceptor and provider base classes:</span></span>  
  
1.  <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator?displayProperty=nameWithType>  
  
2.  <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor?displayProperty=nameWithType>  
  
3.  <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider?displayProperty=nameWithType>  
  
 <span data-ttu-id="a4ec4-142">实现安全流升级的过程与以前的升级过程基本相同，不同的是将从这三个类进行派生。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-142">The process of implementing a security stream upgrade is the same as before, with the difference that you would derive from these three classes.</span></span> <span data-ttu-id="a4ec4-143">重写这些类中的其他属性以便为运行时提供安全信息。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-143">Override the additional properties in these classes to supply security information to the runtime.</span></span>  
  
## <a name="multiple-upgrades"></a><span data-ttu-id="a4ec4-144">多个升级</span><span class="sxs-lookup"><span data-stu-id="a4ec4-144">Multiple Upgrades</span></span>  
 <span data-ttu-id="a4ec4-145">若要创建其他升级请求，请重复上述过程：创建 <xref:System.ServiceModel.Channels.StreamUpgradeProvider> 的附加扩展和绑定元素。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-145">To create additional upgrade requests repeat the above process: create additional extensions of <xref:System.ServiceModel.Channels.StreamUpgradeProvider> and binding elements.</span></span> <span data-ttu-id="a4ec4-146">将绑定元素添加到绑定。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-146">Add the binding elements to the binding.</span></span> <span data-ttu-id="a4ec4-147">这些附加绑定元素将按顺序进行处理，首先处理添加到绑定的第一个绑定元素。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-147">The additional binding elements are processed sequentially, starting with the first binding element added to the binding.</span></span> <span data-ttu-id="a4ec4-148">在 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> 和 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> 中，每个升级提供程序均可确定如何在任何已预先存在的升级绑定参数上对自身进行分层。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-148">In <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> and <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> each upgrade provider can determine how to layer itself on any pre-existing upgrade binding parameters.</span></span> <span data-ttu-id="a4ec4-149">然后，它应使用新的复合升级绑定参数替换现有的升级绑定参数。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-149">It should then replace the existing upgrade binding parameter with a new composite upgrade binding parameter.</span></span>  
  
 <span data-ttu-id="a4ec4-150">或者，一个升级提供程序可以支持多个升级。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-150">Alternatively, one upgrade provider can support multiple upgrades.</span></span> <span data-ttu-id="a4ec4-151">例如，您可能需要实现既支持安全又支持压缩的自定义流升级提供程序。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-151">For example, you might want to implement a custom stream upgrade provider that supports both security and compression.</span></span> <span data-ttu-id="a4ec4-152">请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="a4ec4-152">Do the following steps:</span></span>  
  
1.  <span data-ttu-id="a4ec4-153">创建 <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider> 的子类，以编写用于创建发起程序和接受程序的提供程序类。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-153">Subclass <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider> to write the provider class that creates the Initiator and Acceptor.</span></span>  
  
2.  <span data-ttu-id="a4ec4-154">创建 <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator> 的子类，确保重写 <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> 方法以按顺序返回压缩流和安全流的内容类型。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-154">Subclass the <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator> making sure to override the <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> method to return the content types for the compression stream and the secure stream in order.</span></span>  
  
3.  <span data-ttu-id="a4ec4-155">创建理解其 <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor> 方法中的自定义内容类型的 <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> 的子类。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-155">Subclass the <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor> that understands the custom content types in its <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> method.</span></span>  
  
4.  <span data-ttu-id="a4ec4-156">每次调用 <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> 和 <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> 之后，都会升级该流。</span><span class="sxs-lookup"><span data-stu-id="a4ec4-156">The stream will be upgraded after each call to <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> and <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ec4-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4ec4-157">See Also</span></span>  
 <xref:System.ServiceModel.Channels.StreamUpgradeInitiator>  
 <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator>  
 <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor>  
 <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor>  
 <xref:System.ServiceModel.Channels.StreamUpgradeProvider>  
 <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider>  
 <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
