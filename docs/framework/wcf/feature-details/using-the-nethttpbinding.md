---
title: 使用 NetHttpBinding
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: 5090cfdfeb068acda1e1092e408f3cd747c574c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121012"
---
# <a name="using-the-nethttpbinding"></a><span data-ttu-id="7d979-102">使用 NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="7d979-102">Using the NetHttpBinding</span></span>
<xref:System.ServiceModel.NetHttpBinding> <span data-ttu-id="7d979-103">是为使用 HTTP 或 WebSocket 服务而设计的绑定，并使用默认情况下的二进制编码。</span><span class="sxs-lookup"><span data-stu-id="7d979-103">is a binding designed for consuming HTTP or WebSocket services and uses binary encoding by default.</span></span> <xref:System.ServiceModel.NetHttpBinding> <span data-ttu-id="7d979-104">将检测它是否与请求-答复协定或双工协定一起使用，并更改其行为以进行匹配-它将使用 HTTP 的请求-答复协定和 Websocket 的双工协定。</span><span class="sxs-lookup"><span data-stu-id="7d979-104">will detect whether it is used with a request-reply contract or duplex contract and change its behavior to match - it will use HTTP for request-reply contracts and WebSockets for duplex contracts.</span></span> <span data-ttu-id="7d979-105">可使用 <xref:System.ServiceModel.Channels.WebSocketTransportUsage> 设置来重写此行为：</span><span class="sxs-lookup"><span data-stu-id="7d979-105">This behavior can be overridden using the <xref:System.ServiceModel.Channels.WebSocketTransportUsage> setting:</span></span>  
  
1. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> <span data-ttu-id="7d979-106">-这会强制甚至对于请求-答复协定使用 Websocket。</span><span class="sxs-lookup"><span data-stu-id="7d979-106">- This forces WebSockets to be used even for request-reply contracts.</span></span>  
  
2. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> <span data-ttu-id="7d979-107">-这可以防止使用 Websocket。</span><span class="sxs-lookup"><span data-stu-id="7d979-107">- This prevents WebSockets from being used.</span></span> <span data-ttu-id="7d979-108">尝试使用具有此设置的双工协定将导致异常。</span><span class="sxs-lookup"><span data-stu-id="7d979-108">Attempting to use a duplex contract with this setting will result in an exception.</span></span>  
  
3. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> <span data-ttu-id="7d979-109">-这是默认值，如上文所述的行为。</span><span class="sxs-lookup"><span data-stu-id="7d979-109">- This is the default value and behaves as described above.</span></span>  
  
 <xref:System.ServiceModel.NetHttpBinding> <span data-ttu-id="7d979-110">在 HTTP 模式和 WebSocket 模式下支持可靠会话。</span><span class="sxs-lookup"><span data-stu-id="7d979-110">supports reliable sessions in both HTTP mode and WebSocket mode.</span></span> <span data-ttu-id="7d979-111">在 WebSocket 模式下，会话由传输来提供。</span><span class="sxs-lookup"><span data-stu-id="7d979-111">In WebSocket mode sessions are provided by the transport.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="7d979-112">在使用 <xref:System.ServiceModel.NetHttpBinding> 且该绑定的 TransferMode 设置为 TransferMode.Streamed 时，较大的流可能会造成死锁，调用将会超时。</span><span class="sxs-lookup"><span data-stu-id="7d979-112">When using the <xref:System.ServiceModel.NetHttpBinding> and the binding’s TransferMode is set to TransferMode.Streamed, large streams may cause a deadlock and the call will timeout.</span></span> <span data-ttu-id="7d979-113">若要解决此问题，请发送较小的流，或使用 TransferMode.Buffered。</span><span class="sxs-lookup"><span data-stu-id="7d979-113">To work around this issue send smaller messages or use TransferMode.Buffered.</span></span>  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a><span data-ttu-id="7d979-114">将服务配置为使用 NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="7d979-114">Configuring a Service to use NetHttpBinding</span></span>  
 <span data-ttu-id="7d979-115"><xref:System.ServiceModel.NetHttpBinding> 的配置方式与任何其他绑定的配置方式相同。</span><span class="sxs-lookup"><span data-stu-id="7d979-115">The <xref:System.ServiceModel.NetHttpBinding> can be configured the same as any other binding.</span></span> <span data-ttu-id="7d979-116">以下配置代码段说明了如何通过 <xref:System.ServiceModel.NetHttpBinding> 配置 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="7d979-116">The following configuration snippet illustrates how to configure a WCF service with <xref:System.ServiceModel.NetHttpBinding>.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    ...
  </system.serviceModel>  
```  
  
 <span data-ttu-id="7d979-117">下面的代码段演示如何用代码添加 <xref:System.ServiceModel.NetHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="7d979-117">The following code snippet shows how to add the <xref:System.ServiceModel.NetHttpBinding> in code.</span></span>  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d979-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d979-118">See also</span></span>

- [<span data-ttu-id="7d979-119">配置服务绑定</span><span class="sxs-lookup"><span data-stu-id="7d979-119">Configuring Bindings for Services</span></span>](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="7d979-120">绑定</span><span class="sxs-lookup"><span data-stu-id="7d979-120">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)
- [<span data-ttu-id="7d979-121">系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="7d979-121">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
- [<span data-ttu-id="7d979-122">双工服务</span><span class="sxs-lookup"><span data-stu-id="7d979-122">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)
