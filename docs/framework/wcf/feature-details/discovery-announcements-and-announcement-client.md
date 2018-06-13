---
title: 发现公告和公告客户端
ms.date: 03/30/2017
ms.assetid: 426c6437-f8d2-4968-b23a-18afd671aa4b
ms.openlocfilehash: c32aca5e6deab01423d61c516ee924d00bc041ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490280"
---
# <a name="discovery-announcements-and-announcement-client"></a><span data-ttu-id="d319a-102">发现公告和公告客户端</span><span class="sxs-lookup"><span data-stu-id="d319a-102">Discovery Announcements and Announcement Client</span></span>
<span data-ttu-id="d319a-103">WCF 发现功能使组件可以公告其可用性。</span><span class="sxs-lookup"><span data-stu-id="d319a-103">The WCF discovery feature enables components to announce their availability.</span></span> <span data-ttu-id="d319a-104">如果对某个服务进行了此配置，则该服务将发送 Hello 和 Bye 公告。</span><span class="sxs-lookup"><span data-stu-id="d319a-104">If configured to do so, a service sends Hello and Bye announcements.</span></span> <span data-ttu-id="d319a-105">客户端或其他组件可以侦听此类公告消息并据此采取操作。</span><span class="sxs-lookup"><span data-stu-id="d319a-105">Clients or other components can listen for such announcement messages and act on them.</span></span> <span data-ttu-id="d319a-106">这就向客户端提供了另一种感知服务的方法。</span><span class="sxs-lookup"><span data-stu-id="d319a-106">This provides an alternative method for clients to be aware of services.</span></span> <span data-ttu-id="d319a-107">公告功能具有多种用途，例如，如果服务频繁进入和退出网络，则相比搜索服务，公告是较好的替代方法。</span><span class="sxs-lookup"><span data-stu-id="d319a-107">Announcement functionality has several uses, for example, if the services enter and leave a network frequently, announcements may be a better alternative than searching for services.</span></span> <span data-ttu-id="d319a-108">通过此方法可以减少网络流量，并且客户端在收到公告时可立即了解到服务是进入还是退出状态。</span><span class="sxs-lookup"><span data-stu-id="d319a-108">With this approach, the network traffic is reduced and the client can learn about the presence or departure of the service as soon as announcements are received.</span></span>  
  
## <a name="discovery-announcements"></a><span data-ttu-id="d319a-109">发现公告</span><span class="sxs-lookup"><span data-stu-id="d319a-109">Discovery Announcements</span></span>  
 <span data-ttu-id="d319a-110">如果配置了公告的服务加入网络并可以被检测到，该服务将发送 Hello 消息以向侦听客户端公告其可用性。</span><span class="sxs-lookup"><span data-stu-id="d319a-110">When a service configured for announcements joins a network and becomes discoverable, it sends a Hello message announcing its availability to listening clients.</span></span> <span data-ttu-id="d319a-111">该消息包含与发现相关的服务信息，如服务的协定、终结点地址和相关范围。</span><span class="sxs-lookup"><span data-stu-id="d319a-111">The message contains discovery related information about the service, such as its contract, endpoint address and associated scopes.</span></span> <span data-ttu-id="d319a-112">可以使用 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> 类指定公告消息的发送位置。</span><span class="sxs-lookup"><span data-stu-id="d319a-112">You can specify where the announcement message is sent with the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> class.</span></span> <span data-ttu-id="d319a-113">如果公告终结点是 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>，则相应地多播 Hello 和 Bye；而如果公告终结点是单播，则消息将直接发送到指定终结点。</span><span class="sxs-lookup"><span data-stu-id="d319a-113">If the announcement endpoint is a <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> then the Hello and Bye are multicast appropriately, or if the announcement endpoint is unicast, the messages are sent directly to the specified endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d319a-114">在服务主机打开和关闭时发送公告。</span><span class="sxs-lookup"><span data-stu-id="d319a-114">Announcements are sent when the service host opens and closes.</span></span> <span data-ttu-id="d319a-115">如果这些调用没有正确完成，则可能不发出公告消息。例如，如果服务出错，则不发送 Bye 公告消息。</span><span class="sxs-lookup"><span data-stu-id="d319a-115">If these calls do not finish properly the announcement message may not be sent out. For example if the service faults, then the Bye announcement message is not sent.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="d319a-116">您可以自定义公告功能，在选择的任何时间发送公告。</span><span class="sxs-lookup"><span data-stu-id="d319a-116">You can customize the announcement functionality, allowing you to send announcements whenever you choose.</span></span>  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="d319a-117">将 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> 和 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> 定义为标准终结点，以允许服务和客户端方便地发送 Hello 和 Bye 公告。</span><span class="sxs-lookup"><span data-stu-id="d319a-117"> defines the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> and <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> as standard endpoints to allow services and clients to easily send Hello and Bye announcements.</span></span>  
  
### <a name="announcements-on-the-service"></a><span data-ttu-id="d319a-118">服务上的公告</span><span class="sxs-lookup"><span data-stu-id="d319a-118">Announcements on the Service</span></span>  
 <span data-ttu-id="d319a-119">若要将服务配置为发送公告，请添加 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> 以及公告终结点。</span><span class="sxs-lookup"><span data-stu-id="d319a-119">To configure the service to send announcements, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> with an announcement endpoint.</span></span> <span data-ttu-id="d319a-120">下面的示例演示如何以编程方式将此行为添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="d319a-120">The following example shows how to programmatically add this behavior to the service host.</span></span> <span data-ttu-id="d319a-121">此示例将使用 `UdpAnnouncementEndpoint`，这表明公告将多播到由该标准终结点指定的位置。</span><span class="sxs-lookup"><span data-stu-id="d319a-121">This example uses the `UdpAnnouncementEndpoint`, which implies that the announcements are multicast to a location specified by that standard endpoint.</span></span>  
  
```  
ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());
serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
```  
  
 <span data-ttu-id="d319a-122">在配置文件中也可配置该行为，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="d319a-122">The behavior can be configured in the configuration file as well, as shown in the following example.</span></span>  
  
```xml  
<services>
  <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">
    <!--Add Discovery Endpoint-->
    <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorBehavior">
      <!--Add Discovery behavior-->
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
 <span data-ttu-id="d319a-123">前面的示例将服务配置为自动发送公告消息。</span><span class="sxs-lookup"><span data-stu-id="d319a-123">The preceding examples configure a service to automatically send announcement messages.</span></span> <span data-ttu-id="d319a-124">您还可以使用 <xref:System.ServiceModel.Discovery.AnnouncementClient> 类显式发送公告消息。</span><span class="sxs-lookup"><span data-stu-id="d319a-124">You can also send announcement messages explicitly by using the <xref:System.ServiceModel.Discovery.AnnouncementClient> class.</span></span>  
  
### <a name="announcements-on-the-client"></a><span data-ttu-id="d319a-125">客户端上的公告</span><span class="sxs-lookup"><span data-stu-id="d319a-125">Announcements on the Client</span></span>  
 <span data-ttu-id="d319a-126">客户端应用程序必须承载公告服务，才能响应 Hello 和 Bye 消息以及订阅 <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> 和 <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived> 事件。</span><span class="sxs-lookup"><span data-stu-id="d319a-126">A client application must host an announcement service to respond to the Hello and Bye messages and subscribe to the <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> and <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived> events.</span></span> <span data-ttu-id="d319a-127">下面的示例演示如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d319a-127">The following example shows how to do this.</span></span>  
  
```  
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();
  
// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
  
// Create ServiceHost for the AnnouncementService
using (ServiceHost announcementServiceHost = new ServiceHost(announcementService))
{  
    // Listen for the announcements sent over UDP multicast
    announcementServiceHost.AddServiceEndpoint(new UdpAnnouncementEndpoint());
    announcementServiceHost.Open();
  
    Console.WriteLine("Press <ENTER> to terminate.");
    Console.ReadLine();
}  
```  
  
 <span data-ttu-id="d319a-128">在收到 Hello 或 Bye 消息时，可以通过 <xref:System.ServiceModel.Discovery.AnnouncementEventArgs> 访问终结点发现元数据，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="d319a-128">When a Hello or Bye message is received, you can access the endpoint discovery metadata through <xref:System.ServiceModel.Discovery.AnnouncementEventArgs> as shown in the following example.</span></span>  
  
```  
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine("Received an online announcement from {0}", 
e.EndpointDiscoveryMetadata.Address);
}

static void OnOfflineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine("Received an offline announcement from {0}", 
e.EndpointDiscoveryMetadata.Address);
}
```
