---
title: 创建使用 UDP 传输的多播应用程序
ms.date: 03/30/2017
ms.assetid: 7485154a-6e85-4a67-a9d4-9008e741d4df
ms.openlocfilehash: 89ac99ffec614eeebd076f9868568dcf2c7b04fd
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44264789"
---
# <a name="creating-multicasting-applications-using-the-udp-transport"></a><span data-ttu-id="3c493-102">创建使用 UDP 传输的多播应用程序</span><span class="sxs-lookup"><span data-stu-id="3c493-102">Creating Multicasting Applications using the UDP Transport</span></span>
<span data-ttu-id="3c493-103">多播应用程序同时向大量收件人发送小消息，而无需建立点到点连接。</span><span class="sxs-lookup"><span data-stu-id="3c493-103">Multicasting applications send small messages to a large number of recipients at the same time without the need to establish point to point connections.</span></span> <span data-ttu-id="3c493-104">对于此类应用程序而言，速度比可靠性更重要。</span><span class="sxs-lookup"><span data-stu-id="3c493-104">The emphasis of such applications is speed over reliability.</span></span> <span data-ttu-id="3c493-105">换句话说，更重要的是发送及时的数据，而不是确保确实收到任何特定的消息。</span><span class="sxs-lookup"><span data-stu-id="3c493-105">In other words, it is more important to send timely data than to ensure any specific message is actually received.</span></span> <span data-ttu-id="3c493-106">现在，WCF 支持使用 <xref:System.ServiceModel.UdpBinding> 编写多播应用程序。</span><span class="sxs-lookup"><span data-stu-id="3c493-106">WCF now supports writing multicasting applications using the <xref:System.ServiceModel.UdpBinding>.</span></span> <span data-ttu-id="3c493-107">此传输在服务需要将小消息同时发出到大量客户端的方案中非常有用。</span><span class="sxs-lookup"><span data-stu-id="3c493-107">This transport is useful in scenarios where a service needs to send out small messages to a number of clients simultaneously.</span></span> <span data-ttu-id="3c493-108">股票行情自动收录器应用程序是这类服务的一个示例。</span><span class="sxs-lookup"><span data-stu-id="3c493-108">A stock ticker application is an example of such a service.</span></span>  
  
## <a name="implementing-a-multicast-application"></a><span data-ttu-id="3c493-109">实现多播应用程序</span><span class="sxs-lookup"><span data-stu-id="3c493-109">Implementing a Multicast Application</span></span>  
 <span data-ttu-id="3c493-110">要实现多播应用程序，请定义服务协定，并对需要响应多播消息的每个软件组件实现该服务协定。</span><span class="sxs-lookup"><span data-stu-id="3c493-110">To implement a multicast application, define a service contract and for each software component that needs to respond to the multicast messages, implement the service contract.</span></span> <span data-ttu-id="3c493-111">例如，股票行情自动收录器应用程序可以定义服务协定：</span><span class="sxs-lookup"><span data-stu-id="3c493-111">For example, a stock ticker application might define a service contract:</span></span>  
  
```  
// Shared contracts between the client and the service  
[ServiceContract]
interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void SendStockInfo(StockInfo[] stockInfo);
}

[DataContract]
class StockInfo
{
    [DataMember]
    public string Symbol;

    [DataMember]
    public float Price;

    public StockInfo(string symbol, float price)
    {
        this.Symbol = symbol;
        this.Price = price;
    }
}
```  
  
 <span data-ttu-id="3c493-112">每个想要接收多播消息的应用程序必须承载公开此接口的服务。</span><span class="sxs-lookup"><span data-stu-id="3c493-112">Each application that wants to receive multicast messages must host a service that exposes this interface.</span></span>  <span data-ttu-id="3c493-113">例如，下面的代码示例演示如何接收多播消息：</span><span class="sxs-lookup"><span data-stu-id="3c493-113">For example, here is a code sample that illustrates how to receive multicast messages:</span></span>  
  
```  
// Service Address
string serviceAddress = "soap.udp://224.0.0.1:40000";
// Binding
UdpBinding myBinding = new UdpBinding();
// Host
ServiceHost host = new ServiceHost(typeof(StockTickerService), new Uri(serviceAddress));
// Add service endpoint
host.AddServiceEndpoint(typeof(IStockTicker), myBinding, string.Empty);
// Openup the service host
host.Open();

Console.WriteLine("Start receiving stock information");
Console.ReadLine();
```  
  
 <span data-ttu-id="3c493-114">应用程序指定所有服务都将侦听的 UDP 地址。</span><span class="sxs-lookup"><span data-stu-id="3c493-114">The application specifies the UDP address that all services will be listening on.</span></span> <span data-ttu-id="3c493-115">将创建一个新的 <xref:System.ServiceModel.ServiceHost>，并使用 <xref:System.ServiceModel.UdpBinding> 公开一个服务终结点。</span><span class="sxs-lookup"><span data-stu-id="3c493-115">A new <xref:System.ServiceModel.ServiceHost> is created and a service endpoint is exposed using the <xref:System.ServiceModel.UdpBinding>.</span></span> <span data-ttu-id="3c493-116">然后，<xref:System.ServiceModel.ServiceHost> 打开并开始侦听传入消息。</span><span class="sxs-lookup"><span data-stu-id="3c493-116">The <xref:System.ServiceModel.ServiceHost> is then opened and will start listening for incoming messages.</span></span>  
  
 <span data-ttu-id="3c493-117">在这种类型的方案中，它是实际发出多播消息的客户端。</span><span class="sxs-lookup"><span data-stu-id="3c493-117">In this type of a scenario it is the client that actually sends out multicast messages.</span></span> <span data-ttu-id="3c493-118">正在正确的 UDP 地址上侦听的每个服务都将接收多播消息。</span><span class="sxs-lookup"><span data-stu-id="3c493-118">Each service that is listening at the correct UDP address will receive the multicast messages.</span></span> <span data-ttu-id="3c493-119">下面是发出多播消息的客户端的一个示例：</span><span class="sxs-lookup"><span data-stu-id="3c493-119">Here is an example of a client that sends out multicast messages:</span></span>  
  
```  
// Multicast Address
string serviceAddress = "soap.udp://224.0.0.1:40000";

// Binding
UdpBinding myBinding = new UdpBinding();

// Channel factory
ChannelFactory<IStockTicker> factory 
    = new ChannelFactory<IStockTicker>(myBinding,
                new EndpointAddress(serviceAddress));

// Call service
IStockTicker proxy = factory.CreateChannel();

while (true)
{
    // This will continue to mulicast stock information
    proxy.SendStockInfo(GetStockInfo());
    Console.WriteLine(String.Format("sent stock info at {0}", DateTime.Now));
    // Wait for one second before sending another update
    System.Threading.Thread.Sleep(new TimeSpan(0, 0, 1));
}
```  
  
 <span data-ttu-id="3c493-120">此代码将生成股票信息，然后使用服务协定 IStockTicker 发送多播消息，以调用在正确的 UDP 地址上侦听的服务。</span><span class="sxs-lookup"><span data-stu-id="3c493-120">This code generates stock information and then uses the service contract IStockTicker to send multicast messages to call services listening on the correct UDP address.</span></span>  
  
### <a name="udp-and-reliable-messaging"></a><span data-ttu-id="3c493-121">UDP 和可靠的消息传送</span><span class="sxs-lookup"><span data-stu-id="3c493-121">UDP and Reliable Messaging</span></span>  
 <span data-ttu-id="3c493-122">UDP 绑定不支持可靠的消息传送，原因在于 UDP 协议的轻型性质。</span><span class="sxs-lookup"><span data-stu-id="3c493-122">The UDP binding does not support reliable messaging because of the lightweight nature of the UDP protocol.</span></span> <span data-ttu-id="3c493-123">如果您需要确认某个远程终结点接收到了消息，请使用支持可靠消息传送的传输，如 HTTP 或 TCP。</span><span class="sxs-lookup"><span data-stu-id="3c493-123">If you need to confirm that messages are received by a remote endpoint, use a transport that supports reliable messaging like  HTTP or TCP.</span></span> <span data-ttu-id="3c493-124">可靠消息传送，请参阅有关详细信息 https://go.microsoft.com/fwlink/?LinkId=231830</span><span class="sxs-lookup"><span data-stu-id="3c493-124">For more information about reliable messaging see https://go.microsoft.com/fwlink/?LinkId=231830</span></span>  
  
### <a name="two-way-multicast-messaging"></a><span data-ttu-id="3c493-125">双向多播消息传送</span><span class="sxs-lookup"><span data-stu-id="3c493-125">Two-way Multicast Messaging</span></span>  
 <span data-ttu-id="3c493-126">尽管多播消息通常是单向的，但 UdpBinding 的确支持请求/答复消息交换。</span><span class="sxs-lookup"><span data-stu-id="3c493-126">While multicast messages are generally one-way, the UdpBinding does support request/reply message exchange.</span></span> <span data-ttu-id="3c493-127">使用 UDP 传输发送的消息同时包含发件人地址和收件人地址。</span><span class="sxs-lookup"><span data-stu-id="3c493-127">Messages sent using the UDP transport contain both a From and To address.</span></span> <span data-ttu-id="3c493-128">使用发件人地址时必须小心，因为它可能在路由过程中被恶意更改。</span><span class="sxs-lookup"><span data-stu-id="3c493-128">Care must be taken when using the From address as it could be maliciously changed en-route.</span></span>  <span data-ttu-id="3c493-129">可以使用下面的代码来检查地址：</span><span class="sxs-lookup"><span data-stu-id="3c493-129">The address can be checked using the following code:</span></span>  
  
```  
if (address.AddressFamily == AddressFamily.InterNetwork)
{
    // IPv4
    byte[] addressBytes = address.GetAddressBytes();
    return ((addressBytes[0] & 0xE0) == 0xE0);
}
else
{
    // IPv6
    return address.IsIPv6Multicast;
}
```  
  
 <span data-ttu-id="3c493-130">此代码检查发件人地址的第一个字节，以查看它是否包含 0xE0，这标志着该地址是一个多播地址。</span><span class="sxs-lookup"><span data-stu-id="3c493-130">This code checks the first byte of the From address to see if it contains 0xE0 which signifies that the address is a multi-cast address.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="3c493-131">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="3c493-131">Security Considerations</span></span>  
 <span data-ttu-id="3c493-132">侦听多播消息时，ICMP 数据包发送到路由器，通知它您正在多播地址上侦听。</span><span class="sxs-lookup"><span data-stu-id="3c493-132">When listening for multicast messages an ICMP packet is sent to the router notifying it you are listening on the multicast address.</span></span> <span data-ttu-id="3c493-133">本地子网上具有权限的任何人都可以侦听这些类型的数据包，并确定您正在侦听的多播地址和端口。</span><span class="sxs-lookup"><span data-stu-id="3c493-133">Anyone on the local subnet who has permissions could listen for these types of packets and determine which multicast address and port you are listening on.</span></span>  
  
 <span data-ttu-id="3c493-134">请勿出于任何安全目的使用发件人的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3c493-134">Do not use the IP address of the sender for any security purposes.</span></span> <span data-ttu-id="3c493-135">此信息可以伪造，并可以导致应用程序将响应发送到错误的计算机。</span><span class="sxs-lookup"><span data-stu-id="3c493-135">This information can be spoofed and can cause an application to send responses to the wrong machine.</span></span> <span data-ttu-id="3c493-136">缓解这种威胁的一种方法是启用消息级别安全性。</span><span class="sxs-lookup"><span data-stu-id="3c493-136">One way to mitigate this threat is to enable message level security.</span></span> <span data-ttu-id="3c493-137">在网络级，还可使用 IPSec（Internet 协议安全性）和/或 NAP（网络访问保护）。</span><span class="sxs-lookup"><span data-stu-id="3c493-137">At the network level IPSec  (Internet Protocol Security) and/or NAP (Network Access Protection) could also be used.</span></span>
