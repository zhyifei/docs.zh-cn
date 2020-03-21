---
title: 如何：检查或修改客户端的消息
ms.date: 03/30/2017
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
ms.openlocfilehash: db1a99d2ed1f765e39815e6b6c70d6ada1db1d15
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185536"
---
# <a name="how-to-inspect-or-modify-messages-on-the-client"></a><span data-ttu-id="3022c-102">如何：检查或修改客户端的消息</span><span class="sxs-lookup"><span data-stu-id="3022c-102">How to: Inspect or Modify Messages on the Client</span></span>
<span data-ttu-id="3022c-103">您可以通过实现 并将 传入<xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>或传出消息插入到客户端运行时，检查或修改 WCF 客户端的传入或传出消息。</span><span class="sxs-lookup"><span data-stu-id="3022c-103">You can inspect or modify the incoming or outgoing messages across a WCF client by implementing a <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> and inserting it into the client runtime.</span></span> <span data-ttu-id="3022c-104">有关详细信息，请参阅[扩展客户端](extending-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="3022c-104">For more information, see [Extending Clients](extending-clients.md).</span></span> <span data-ttu-id="3022c-105">服务上的等效功能为 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="3022c-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3022c-106">有关完整的代码示例，请参阅[消息检查器](../samples/message-inspectors.md)示例。</span><span class="sxs-lookup"><span data-stu-id="3022c-106">For a complete code example see the [Message Inspectors](../samples/message-inspectors.md) sample.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="3022c-107">检查或修改消息</span><span class="sxs-lookup"><span data-stu-id="3022c-107">To inspect or modify messages</span></span>  
  
1. <span data-ttu-id="3022c-108">实现 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> 接口。</span><span class="sxs-lookup"><span data-stu-id="3022c-108">Implement the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2. <span data-ttu-id="3022c-109">实现 <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> 或 <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>，具体取决于您希望在其中插入客户端消息检查器的作用域。</span><span class="sxs-lookup"><span data-stu-id="3022c-109">Implement a <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> depending upon the scope at which you want to insert the client message inspector.</span></span> <span data-ttu-id="3022c-110"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>允许您更改终结点级别的行为。</span><span class="sxs-lookup"><span data-stu-id="3022c-110"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> allows you to change behavior at the endpoint level.</span></span> <span data-ttu-id="3022c-111"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>允许您更改合同级别的行为。</span><span class="sxs-lookup"><span data-stu-id="3022c-111"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> allows you to change behavior at the contract level.</span></span>  
  
3. <span data-ttu-id="3022c-112">在 <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> 上调用 <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> 或 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> 方法前，插入行为。</span><span class="sxs-lookup"><span data-stu-id="3022c-112">Insert the behavior prior to calling the <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3022c-113">有关详细信息，请参阅[使用行为配置和扩展运行时](configuring-and-extending-the-runtime-with-behaviors.md)。</span><span class="sxs-lookup"><span data-stu-id="3022c-113">For details, see [Configuring and Extending the Runtime with Behaviors](configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3022c-114">示例</span><span class="sxs-lookup"><span data-stu-id="3022c-114">Example</span></span>  
 <span data-ttu-id="3022c-115">下面的代码示例按顺序演示以下各项：</span><span class="sxs-lookup"><span data-stu-id="3022c-115">The following code examples show, in order:</span></span>  
  
- <span data-ttu-id="3022c-116">客户端检查器实现。</span><span class="sxs-lookup"><span data-stu-id="3022c-116">A client inspector implementation.</span></span>  
  
- <span data-ttu-id="3022c-117">插入检查器的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="3022c-117">An endpoint behavior that inserts the inspector.</span></span>  
  
- <span data-ttu-id="3022c-118">一个 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> 派生类，允许您在配置文件中添加行为。</span><span class="sxs-lookup"><span data-stu-id="3022c-118">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>- derived class that allows you to add the behavior in a configuration file.</span></span>  
  
- <span data-ttu-id="3022c-119">一个配置文件，它添加终结点行为，以便在客户端运行时中插入客户端消息检查器。</span><span class="sxs-lookup"><span data-stu-id="3022c-119">A configuration file that adds the endpoint behavior which inserts the client message inspector into the client runtime.</span></span>  
  
```csharp  
// Client message inspector  
public class SimpleMessageInspector : IClientMessageInspector  
{  
    public void AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
    {  
        // Implement this method to inspect/modify messages after a message  
        // is received but prior to passing it back to the client
        Console.WriteLine("AfterReceiveReply called");  
    }  
  
    public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, IClientChannel channel)  
    {  
        // Implement this method to inspect/modify messages before they
        // are sent to the service  
        Console.WriteLine("BeforeSendRequest called");  
        return null;  
    }  
}  
```  
  
```csharp  
// Endpoint behavior  
public class SimpleEndpointBehavior : IEndpointBehavior  
{  
    public void AddBindingParameters(ServiceEndpoint endpoint, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
    {  
         // No implementation necessary  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint, ClientRuntime clientRuntime)  
    {  
        clientRuntime.MessageInspectors.Add(new SimpleMessageInspector());  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint, EndpointDispatcher endpointDispatcher)  
    {  
         // No implementation necessary  
    }  
  
    public void Validate(ServiceEndpoint endpoint)  
    {  
         // No implementation necessary  
    }  
}  
```  
  
```csharp  
// Configuration element
public class SimpleBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public override Type BehaviorType  
    {  
        get { return typeof(SimpleEndpointBehavior); }  
    }  
  
    protected override object CreateBehavior()  
    {  
         // Create the  endpoint behavior that will insert the message  
         // inspector into the client runtime  
        return new SimpleEndpointBehavior();  
    }  
}  
```  
  
```xml
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <system.serviceModel>  
        <client>  
            <endpoint address="http://localhost:8080/SimpleService/"
                      binding="wsHttpBinding"
                      behaviorConfiguration="clientInspectorsAdded"
                      contract="ServiceReference1.IService1"  
                      name="WSHttpBinding_IService1"/>  
        </client>  
  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="clientInspectorsAdded">  
            <simpleBehaviorExtension />  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <extensions>  
        <behaviorExtensions>  
          <add  
            name="simpleBehaviorExtension"  
            type="SimpleServiceLib.SimpleBehaviorExtensionElement, Host, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3022c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3022c-120">See also</span></span>

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [<span data-ttu-id="3022c-121">使用行为配置和扩展运行时</span><span class="sxs-lookup"><span data-stu-id="3022c-121">Configuring and Extending the Runtime with Behaviors</span></span>](configuring-and-extending-the-runtime-with-behaviors.md)
