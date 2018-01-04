---
title: "传输：WSE 3.0 TCP 互操作性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f7c3708-acad-4eb3-acb9-d232c77d1486
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63641f7a99b7c567e871d6a67dd72380f0c077ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="transport-wse-30-tcp-interoperability"></a><span data-ttu-id="6f894-102">传输：WSE 3.0 TCP 互操作性</span><span class="sxs-lookup"><span data-stu-id="6f894-102">Transport: WSE 3.0 TCP Interoperability</span></span>
<span data-ttu-id="6f894-103">WSE 3.0 TCP 互操作性传输示例演示如何将 TCP 双工会话作为自定义 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 传输实现，</span><span class="sxs-lookup"><span data-stu-id="6f894-103">The WSE 3.0 TCP Interoperability Transport sample demonstrates how to implement a TCP duplex session as a custom [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] transport.</span></span> <span data-ttu-id="6f894-104">还演示如何通过网络，使用通道层的扩展性与已经过部署的现有系统进行交互。</span><span class="sxs-lookup"><span data-stu-id="6f894-104">It also demonstrates how you can use the extensibility of the channel layer to interface over the wire with existing deployed systems.</span></span> <span data-ttu-id="6f894-105">下列步骤演示如何生成此自定义 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 传输：</span><span class="sxs-lookup"><span data-stu-id="6f894-105">The following steps show how to build this custom [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transport:</span></span>  
  
1.  <span data-ttu-id="6f894-106">从 TCP 套接字开始，创建 <xref:System.ServiceModel.Channels.IDuplexSessionChannel> 的客户端和服务器实现以使用 DIME 组帧来描述消息边界。</span><span class="sxs-lookup"><span data-stu-id="6f894-106">Starting with a TCP socket, create client and server implementations of <xref:System.ServiceModel.Channels.IDuplexSessionChannel> that use DIME Framing to delineate message boundaries.</span></span>  
  
2.  <span data-ttu-id="6f894-107">创建一个连接到 WSE TCP 服务并通过客户端 <xref:System.ServiceModel.Channels.IDuplexSessionChannel> 发送组帧消息的通道工厂。</span><span class="sxs-lookup"><span data-stu-id="6f894-107">Create a channel factory that connects to a WSE TCP service and sends framed messages over the client <xref:System.ServiceModel.Channels.IDuplexSessionChannel>s.</span></span>  
  
3.  <span data-ttu-id="6f894-108">创建一个通道侦听器以接受传入的 TCP 连接并生成相应的通道。</span><span class="sxs-lookup"><span data-stu-id="6f894-108">Create a channel listener to accept incoming TCP connections and produce corresponding channels.</span></span>  
  
4.  <span data-ttu-id="6f894-109">请确保将特定于网络的任何异常正常化为 <xref:System.ServiceModel.CommunicationException> 的相应派生类。</span><span class="sxs-lookup"><span data-stu-id="6f894-109">Ensure that any network-specific exceptions are normalized to the appropriate derived class of <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
5.  <span data-ttu-id="6f894-110">添加一个用来向通道堆栈中添加自定义传输的绑定元素。</span><span class="sxs-lookup"><span data-stu-id="6f894-110">Add a binding element that adds the custom transport to a channel stack.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="6f894-111">[添加绑定元素。]</span><span class="sxs-lookup"><span data-stu-id="6f894-111"> [Adding a Binding Element].</span></span>  
  
## <a name="creating-iduplexsessionchannel"></a><span data-ttu-id="6f894-112">创建 IDuplexSessionChannel</span><span class="sxs-lookup"><span data-stu-id="6f894-112">Creating IDuplexSessionChannel</span></span>  
 <span data-ttu-id="6f894-113">编写 WSE 3.0 TCP 互操作性传输的第一步是在 <xref:System.ServiceModel.Channels.IDuplexSessionChannel> 的顶部创建 <xref:System.Net.Sockets.Socket> 的实现。</span><span class="sxs-lookup"><span data-stu-id="6f894-113">The first step in writing the WSE 3.0 TCP Interoperability Transport is to create an implementation of <xref:System.ServiceModel.Channels.IDuplexSessionChannel> on top of a <xref:System.Net.Sockets.Socket>.</span></span> <span data-ttu-id="6f894-114">`WseTcpDuplexSessionChannel` 派生自 <xref:System.ServiceModel.Channels.ChannelBase>。</span><span class="sxs-lookup"><span data-stu-id="6f894-114">`WseTcpDuplexSessionChannel` derives from <xref:System.ServiceModel.Channels.ChannelBase>.</span></span> <span data-ttu-id="6f894-115">消息的发送逻辑主要由以下两个部分组成：(1) 将消息编码为字节；(2) 对这些字节进行组帧并通过网络发送它们。</span><span class="sxs-lookup"><span data-stu-id="6f894-115">The logic of sending a message consists of two main pieces: (1) Encoding the message into bytes, and (2) framing those bytes and sending them on the wire.</span></span>  
  
 `ArraySegment<byte> encodedBytes = EncodeMessage(message);`  
  
 `WriteData(encodedBytes);`  
  
 <span data-ttu-id="6f894-116">另外，设置了一个锁，以保证在调用 Send() 时可以按顺序保留 IDuplexSessionChannel，以便对基础套接字的调用能够正确地同步。</span><span class="sxs-lookup"><span data-stu-id="6f894-116">In addition, a lock is taken so that the Send() calls preserve the IDuplexSessionChannel in-order guarantee, and so that calls to the underlying socket are synchronized correctly.</span></span>  
  
 <span data-ttu-id="6f894-117">`WseTcpDuplexSessionChannel` 使用 <xref:System.ServiceModel.Channels.MessageEncoder> 在 <xref:System.ServiceModel.Channels.Message> 和 byte[] 之间相互转换。</span><span class="sxs-lookup"><span data-stu-id="6f894-117">`WseTcpDuplexSessionChannel` uses a <xref:System.ServiceModel.Channels.MessageEncoder> for translating a <xref:System.ServiceModel.Channels.Message> to and from byte[].</span></span> <span data-ttu-id="6f894-118">由于 `WseTcpDuplexSessionChannel` 为传输，因此它还负责应用通道所配置的远程地址。</span><span class="sxs-lookup"><span data-stu-id="6f894-118">Because it is a transport, `WseTcpDuplexSessionChannel` is also responsible for applying the remote address that the channel was configured with.</span></span> <span data-ttu-id="6f894-119">`EncodeMessage` 封装此转换的逻辑。</span><span class="sxs-lookup"><span data-stu-id="6f894-119">`EncodeMessage` encapsulates the logic for this conversion.</span></span>  
  
 `this.RemoteAddress.ApplyTo(message);`  
  
 `return encoder.WriteMessage(message, maxBufferSize, bufferManager);`  
  
 <span data-ttu-id="6f894-120">一旦将 <xref:System.ServiceModel.Channels.Message> 编码为字节，就必须通过线路传输它。</span><span class="sxs-lookup"><span data-stu-id="6f894-120">Once the <xref:System.ServiceModel.Channels.Message> is encoded into bytes, it must be transmitted on the wire.</span></span> <span data-ttu-id="6f894-121">这要求系统定义消息边界。</span><span class="sxs-lookup"><span data-stu-id="6f894-121">This requires a system for defining message boundaries.</span></span> <span data-ttu-id="6f894-122">WSE 3.0 使用的版本[DIME](http://go.microsoft.com/fwlink/?LinkId=94999)作为其组帧协议。</span><span class="sxs-lookup"><span data-stu-id="6f894-122">WSE 3.0 uses a version of [DIME](http://go.microsoft.com/fwlink/?LinkId=94999) as its framing protocol.</span></span> <span data-ttu-id="6f894-123">`WriteData` 封装框架逻辑以便将 byte[] 包装到一组 DIME 记录中。</span><span class="sxs-lookup"><span data-stu-id="6f894-123">`WriteData` encapsulates the framing logic to wrap a byte[] into a set of DIME records.</span></span>  
  
 <span data-ttu-id="6f894-124">用来接收消息的逻辑与组帧逻辑非常相似。</span><span class="sxs-lookup"><span data-stu-id="6f894-124">The logic for receiving messages is very similar.</span></span> <span data-ttu-id="6f894-125">其复杂性主要在于，处理读取套接字时所返回的字节数比已请求的更少这一情况。</span><span class="sxs-lookup"><span data-stu-id="6f894-125">The main complexity is handling the fact that a socket read can return less bytes than were requested.</span></span> <span data-ttu-id="6f894-126">若要接收消息，`WseTcpDuplexSessionChannel` 读取网络中的字节，对 DIME 组帧进行解码，然后使用 <xref:System.ServiceModel.Channels.MessageEncoder> 将 byte[] 转换为 <xref:System.ServiceModel.Channels.Message>。</span><span class="sxs-lookup"><span data-stu-id="6f894-126">To receive a message, `WseTcpDuplexSessionChannel` reads bytes off the wire, decodes the DIME framing, and then uses the <xref:System.ServiceModel.Channels.MessageEncoder> for turning the byte[] into a <xref:System.ServiceModel.Channels.Message>.</span></span>  
  
 <span data-ttu-id="6f894-127">基 `WseTcpDuplexSessionChannel` 假设它接收连接的套接字。</span><span class="sxs-lookup"><span data-stu-id="6f894-127">The base `WseTcpDuplexSessionChannel` assumes that it receives a connected socket.</span></span> <span data-ttu-id="6f894-128">这个基类处理套接字的关闭。</span><span class="sxs-lookup"><span data-stu-id="6f894-128">The base class handles socket shutdown.</span></span> <span data-ttu-id="6f894-129">可通过三个位置与套接字关闭进行交互：</span><span class="sxs-lookup"><span data-stu-id="6f894-129">There are three places that interface with socket closure:</span></span>  
  
-   <span data-ttu-id="6f894-130">OnAbort - 以非正常方式关闭套接字（硬关闭）。</span><span class="sxs-lookup"><span data-stu-id="6f894-130">OnAbort -- close the socket ungracefully (hard close).</span></span>  
  
-   <span data-ttu-id="6f894-131">On[Begin]Close - 正常关闭套接字（软关闭）。</span><span class="sxs-lookup"><span data-stu-id="6f894-131">On[Begin]Close -- close the socket gracefully (soft close).</span></span>  
  
-   <span data-ttu-id="6f894-132">session.CloseOutputSession - 关闭出站数据流（半关闭）。</span><span class="sxs-lookup"><span data-stu-id="6f894-132">session.CloseOutputSession -- shutdown the outbound data stream (half close).</span></span>  
  
## <a name="channel-factory"></a><span data-ttu-id="6f894-133">通道工厂</span><span class="sxs-lookup"><span data-stu-id="6f894-133">Channel Factory</span></span>  
 <span data-ttu-id="6f894-134">编写 TCP 传输的下一步是为客户端通道创建 <xref:System.ServiceModel.Channels.IChannelFactory> 的实现。</span><span class="sxs-lookup"><span data-stu-id="6f894-134">The next step in writing the TCP transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels.</span></span>  
  
-   <span data-ttu-id="6f894-135">`WseTcpChannelFactory`派生自<xref:System.ServiceModel.Channels.ChannelFactoryBase> \<IDuplexSessionChannel >。</span><span class="sxs-lookup"><span data-stu-id="6f894-135">`WseTcpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>\<IDuplexSessionChannel>.</span></span> <span data-ttu-id="6f894-136">它是一个用来重写 `OnCreateChannel` 以生成客户端通道的工厂。</span><span class="sxs-lookup"><span data-stu-id="6f894-136">It is a factory that overrides `OnCreateChannel` to produce client channels.</span></span>  
  
 `protected override IDuplexSessionChannel OnCreateChannel(EndpointAddress remoteAddress, Uri via)`  
  
 `{`  
  
 `return new ClientWseTcpDuplexSessionChannel(encoderFactory, bufferManager, remoteAddress, via, this);`  
  
 `}`  
  
-   <span data-ttu-id="6f894-137">`ClientWseTcpDuplexSessionChannel`将逻辑添加到基`WseTcpDuplexSessionChannel`以连接到 TCP 服务器在`channel.Open`时间。</span><span class="sxs-lookup"><span data-stu-id="6f894-137">`ClientWseTcpDuplexSessionChannel` adds logic to the base `WseTcpDuplexSessionChannel` to connect to a TCP server at `channel.Open` time.</span></span> <span data-ttu-id="6f894-138">首先，主机名解析为 IP 地址，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="6f894-138">First the hostname is resolved to an IP address, as shown in the following code.</span></span>  
  
 `hostEntry = Dns.GetHostEntry(Via.Host);`  
  
-   <span data-ttu-id="6f894-139">然后，主机名连接到循环中的第一个可用 IP 地址，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="6f894-139">Then the hostname is connected to the first available IP address in a loop, as shown in the following code.</span></span>  
  
 `IPAddress address = hostEntry.AddressList[i];`  
  
 `socket = new Socket(address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `socket.Connect(new IPEndPoint(address, port));`  
  
-   <span data-ttu-id="6f894-140">包装了所有特定于域的异常（如 `SocketException` 中的 <xref:System.ServiceModel.CommunicationException>），作为通道协定的一部分。</span><span class="sxs-lookup"><span data-stu-id="6f894-140">As part of the channel contract, any domain-specific exceptions are wrapped, such as `SocketException` in <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
## <a name="channel-listener"></a><span data-ttu-id="6f894-141">通道侦听器</span><span class="sxs-lookup"><span data-stu-id="6f894-141">Channel Listener</span></span>  
 <span data-ttu-id="6f894-142">编写 TCP 传输的下一步是创建用来接受服务器通道的 <xref:System.ServiceModel.Channels.IChannelListener> 实现。</span><span class="sxs-lookup"><span data-stu-id="6f894-142">The next step in writing the TCP transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelListener> for accepting server channels.</span></span>  
  
-   <span data-ttu-id="6f894-143">`WseTcpChannelListener`派生自<xref:System.ServiceModel.Channels.ChannelListenerBase> \<IDuplexSessionChannel > 和替代 [Begin] Open 和 On [Begin] Close 以控制其侦听套接字的生存期。</span><span class="sxs-lookup"><span data-stu-id="6f894-143">`WseTcpChannelListener` derives from <xref:System.ServiceModel.Channels.ChannelListenerBase>\<IDuplexSessionChannel> and overrides On[Begin]Open and On[Begin]Close to control the lifetime of its listen socket.</span></span> <span data-ttu-id="6f894-144">在 OnOpen 中，需要创建一个用来侦听 IP_ANY 的套接字。</span><span class="sxs-lookup"><span data-stu-id="6f894-144">In OnOpen, a socket is created to listen on IP_ANY.</span></span> <span data-ttu-id="6f894-145">在更高级的实现中，可以再创建一个同时侦听 IPv6 的套接字。</span><span class="sxs-lookup"><span data-stu-id="6f894-145">More advanced implementations can create a second socket to listen on IPv6 as well.</span></span> <span data-ttu-id="6f894-146">这些高级实现还允许在主机名中指定 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="6f894-146">They can also allow the IP address to be specified in the hostname.</span></span>  
  
 `IPEndPoint localEndpoint = new IPEndPoint(IPAddress.Any, uri.Port);`  
  
 `this.listenSocket = new Socket(localEndpoint.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `this.listenSocket.Bind(localEndpoint);`  
  
 `this.listenSocket.Listen(10);`  
  
 <span data-ttu-id="6f894-147">在接受了新套接字之后，将用这个套接字来初始化服务器通道。</span><span class="sxs-lookup"><span data-stu-id="6f894-147">When a new socket is accepted, a server channel is initialized with this socket.</span></span> <span data-ttu-id="6f894-148">所有的输入和输出都已经在该基类中实现，因此该通道负责初始化此套接字。</span><span class="sxs-lookup"><span data-stu-id="6f894-148">All the input and output is already implemented in the base class, so this channel is responsible for initializing the socket.</span></span>  
  
## <a name="adding-a-binding-element"></a><span data-ttu-id="6f894-149">添加绑定元素</span><span class="sxs-lookup"><span data-stu-id="6f894-149">Adding a Binding Element</span></span>  
 <span data-ttu-id="6f894-150">现在已经生成了工厂和通道，必须通过绑定将它们向 ServiceModel 运行库公开。</span><span class="sxs-lookup"><span data-stu-id="6f894-150">Now that the factories and channels are built, they must be exposed to the ServiceModel runtime through a binding.</span></span> <span data-ttu-id="6f894-151">绑定是指绑定元素的集合，该集合表示与服务地址相关联的通信堆栈。</span><span class="sxs-lookup"><span data-stu-id="6f894-151">A binding is a collection of binding elements that represents the communication stack associated with a service address.</span></span> <span data-ttu-id="6f894-152">该堆栈中的每个元素都由一个绑定元素来表示。</span><span class="sxs-lookup"><span data-stu-id="6f894-152">Each element in the stack is represented by a binding element.</span></span>  
  
 <span data-ttu-id="6f894-153">在下面的示例中，绑定元素为 `WseTcpTransportBindingElement`，它派生自 <xref:System.ServiceModel.Channels.TransportBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="6f894-153">In the sample, the binding element is `WseTcpTransportBindingElement`, which derives from <xref:System.ServiceModel.Channels.TransportBindingElement>.</span></span> <span data-ttu-id="6f894-154">它支持 <xref:System.ServiceModel.Channels.IDuplexSessionChannel> 并重写下列方法以生成与绑定相关联的工厂。</span><span class="sxs-lookup"><span data-stu-id="6f894-154">It supports <xref:System.ServiceModel.Channels.IDuplexSessionChannel> and overrides the following methods to build the factories associated with our binding.</span></span>  
  
 `public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelFactory<TChannel>)(object)new WseTcpChannelFactory(this, context);`  
  
 `}`  
  
 `public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelListener<TChannel>)(object)new WseTcpChannelListener(this, context);`  
  
 `}`  
  
 <span data-ttu-id="6f894-155">它还包含用于克隆 `BindingElement` 并返回我们自己的方案 (wse.tcp) 的成员。</span><span class="sxs-lookup"><span data-stu-id="6f894-155">It also contains members for cloning the `BindingElement` and returning our scheme (wse.tcp).</span></span>  
  
## <a name="the-wse-tcp-test-console"></a><span data-ttu-id="6f894-156">WSE TCP 测试控制台</span><span class="sxs-lookup"><span data-stu-id="6f894-156">The WSE TCP Test Console</span></span>  
 <span data-ttu-id="6f894-157">TestCode.cs 中提供了用于使用此示例传输的测试代码。</span><span class="sxs-lookup"><span data-stu-id="6f894-157">Test code for using this sample transport is available in TestCode.cs.</span></span> <span data-ttu-id="6f894-158">下面的说明演示如何设置 WSE `TcpSyncStockService` 示例。</span><span class="sxs-lookup"><span data-stu-id="6f894-158">The following instructions show how to set up the WSE `TcpSyncStockService` sample.</span></span>  
  
 <span data-ttu-id="6f894-159">该测试代码创建了一个自定义绑定，该绑定将 MTOM 用作编码并将 `WseTcpTransport` 用作传输。</span><span class="sxs-lookup"><span data-stu-id="6f894-159">The test code creates a custom binding that uses MTOM as the encoding and `WseTcpTransport` as the transport.</span></span> <span data-ttu-id="6f894-160">该测试代码还设置了与 WSE 3.0 一致的 AddressingVersion，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="6f894-160">It also sets up the AddressingVersion to be conformant with WSE 3.0, as shown in the following code.</span></span>  
  
 `CustomBinding binding = new CustomBinding();`  
  
 `MtomMessageEncodingBindingElement mtomBindingElement = new MtomMessageEncodingBindingElement();`  
  
 `mtomBindingElement.MessageVersion = MessageVersion.Soap11WSAddressingAugust2004;`  
  
 `binding.Elements.Add(mtomBindingElement);`  
  
 `binding.Elements.Add(new WseTcpTransportBindingElement());`  
  
 <span data-ttu-id="6f894-161">它由两个测试组成，第一个测试使用从 WSE 3.0 WSDL 生成的代码来设置类型化客户端，</span><span class="sxs-lookup"><span data-stu-id="6f894-161">It consists of two tests—one test sets up a typed client using code generated from the WSE 3.0 WSDL.</span></span> <span data-ttu-id="6f894-162">第二个测试通过直接在通道 API 的顶部发送消息来将 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 同时用作客户端和服务器。</span><span class="sxs-lookup"><span data-stu-id="6f894-162">The second test uses [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] as both the client and the server by sending messages directly on top of the channel APIs.</span></span>  
  
 <span data-ttu-id="6f894-163">运行此示例时，应生成下面的输出。</span><span class="sxs-lookup"><span data-stu-id="6f894-163">When running the sample, the following output is expected.</span></span>  
  
 <span data-ttu-id="6f894-164">客户端：</span><span class="sxs-lookup"><span data-stu-id="6f894-164">Client:</span></span>  
  
```  
Calling soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Symbol: FABRIKAM  
        Name: Fabrikam, Inc.  
        Last Price: 120  
  
Symbol: CONTOSO  
        Name: Contoso Corp.  
        Last Price: 50.07  
Press enter.  
  
Received Action: http://SayHello  
Received Body: to you.  
Hello to you.  
Press enter.  
  
Received Action: http://NotHello  
Received Body: to me.  
Press enter.  
```  
  
 <span data-ttu-id="6f894-165">服务器:</span><span class="sxs-lookup"><span data-stu-id="6f894-165">Server:</span></span>  
  
```  
Listening for messages at soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Press any key to exit when done...  
  
Request received.  
Symbols:  
        FABRIKAM  
        CONTOSO  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6f894-166">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="6f894-166">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6f894-167">若要运行此示例，必须安装有 WSE 3.0 和 WSE `TcpSyncStockService` 示例。</span><span class="sxs-lookup"><span data-stu-id="6f894-167">To run this sample, you must have WSE 3.0 and the WSE `TcpSyncStockService` sample installed.</span></span> <span data-ttu-id="6f894-168">你可以下载[从 MSDN 的 WSE 3.0](http://go.microsoft.com/fwlink/?LinkId=95000)。</span><span class="sxs-lookup"><span data-stu-id="6f894-168">You can download [WSE 3.0 from MSDN](http://go.microsoft.com/fwlink/?LinkId=95000).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f894-169">由于 [!INCLUDE[lserver](../../../../includes/lserver-md.md)] 上不支持 WSE 3.0，因此不能在该操作系统上安装或运行 `TcpSyncStockService` 示例。</span><span class="sxs-lookup"><span data-stu-id="6f894-169">Because WSE 3.0 is not supported on [!INCLUDE[lserver](../../../../includes/lserver-md.md)], you cannot install or run the `TcpSyncStockService` sample on that operating system.</span></span>  
  
1.  <span data-ttu-id="6f894-170">安装了 `TcpSyncStockService` 示例后，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6f894-170">Once you install the `TcpSyncStockService` sample, do the following:</span></span>  
  
    1.  <span data-ttu-id="6f894-171">在 Visual Studio 中打开 `TcpSyncStockService`。（请注意，TcpSyncStockService 示例是随 WSE 3.0 一起安装的。</span><span class="sxs-lookup"><span data-stu-id="6f894-171">Open the `TcpSyncStockService` in Visual Studio (Note that the TcpSyncStockService sample is installed with WSE 3.0.</span></span> <span data-ttu-id="6f894-172">它不属于此示例的代码。）</span><span class="sxs-lookup"><span data-stu-id="6f894-172">It is not part of this sample's code).</span></span>  
  
    2.  <span data-ttu-id="6f894-173">将 StockService 项目设置为启动项目。</span><span class="sxs-lookup"><span data-stu-id="6f894-173">Set the StockService project as the start up project.</span></span>  
  
    3.  <span data-ttu-id="6f894-174">在 StockService 项目中打开 StockService.cs，并注释掉 `StockService` 类的 [Policy] 属性。</span><span class="sxs-lookup"><span data-stu-id="6f894-174">Open StockService.cs in the StockService project and comment out the [Policy] attribute on the `StockService` class.</span></span> <span data-ttu-id="6f894-175">这会禁用该示例中的安全性。</span><span class="sxs-lookup"><span data-stu-id="6f894-175">This disables security from the sample.</span></span> <span data-ttu-id="6f894-176">尽管 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可以与 WSE 3.0 安全终结点互操作，但是为了使该示例将重点放在自定义 TCP 传输上而禁用了安全性。</span><span class="sxs-lookup"><span data-stu-id="6f894-176">While [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can interoperate with WSE 3.0 secure endpoints, security is disabled to keep this sample focused on the custom TCP transport.</span></span>  
  
    4.  <span data-ttu-id="6f894-177">按 F5 启动 `TcpSyncStockService`。</span><span class="sxs-lookup"><span data-stu-id="6f894-177">Press F5 to start the `TcpSyncStockService`.</span></span> <span data-ttu-id="6f894-178">该服务将在一个新的控制台窗口中启动。</span><span class="sxs-lookup"><span data-stu-id="6f894-178">The service starts in a new console window.</span></span>  
  
    5.  <span data-ttu-id="6f894-179">在 Visual Studio 中打开这个 TCP 传输示例。</span><span class="sxs-lookup"><span data-stu-id="6f894-179">Open this TCP transport sample in Visual Studio.</span></span>  
  
    6.  <span data-ttu-id="6f894-180">更新 TestCode.cs 中的“hostname”变量，使其与运行 `TcpSyncStockService` 的计算机的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="6f894-180">Update the "hostname" variable in TestCode.cs to match the machine name running the `TcpSyncStockService`.</span></span>  
  
    7.  <span data-ttu-id="6f894-181">按 F5 启动 TCP 传输示例。</span><span class="sxs-lookup"><span data-stu-id="6f894-181">Press F5 to start the TCP transport sample.</span></span>  
  
    8.  <span data-ttu-id="6f894-182">TCP 传输测试客户端将在一个新控制台中启动。</span><span class="sxs-lookup"><span data-stu-id="6f894-182">The TCP transport test client starts in a new console.</span></span> <span data-ttu-id="6f894-183">客户端从服务请求股票报价，然后将结果显示在其控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="6f894-183">The client requests stock quotes from the service and then displays the results in its console window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f894-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f894-184">See Also</span></span>
