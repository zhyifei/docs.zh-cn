---
title: 使用消息级编程在 Json 中序列化
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: fc2777d71376cc482b715898fa81ddf618bd8284
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186935"
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="0946b-102">使用消息级编程在 Json 中序列化</span><span class="sxs-lookup"><span data-stu-id="0946b-102">Serializing in Json with Message Level Programming</span></span>
<span data-ttu-id="0946b-103">WCF 支持以 JSON 格式序列化数据。</span><span class="sxs-lookup"><span data-stu-id="0946b-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="0946b-104">本主题描述如何使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 告知 WCF 序列化您的类型。</span><span class="sxs-lookup"><span data-stu-id="0946b-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="0946b-105">类型化的消息编程</span><span class="sxs-lookup"><span data-stu-id="0946b-105">Typed Message Programming</span></span>  
 <span data-ttu-id="0946b-106"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 或 <xref:System.ServiceModel.Web.WebGetAttribute> 应用于服务操作时使用 <xref:System.ServiceModel.Web.WebInvokeAttribute>。</span><span class="sxs-lookup"><span data-stu-id="0946b-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="0946b-107">这两个属性允许您指定 `RequestFormat` 和 `ResponseFormat`。</span><span class="sxs-lookup"><span data-stu-id="0946b-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="0946b-108">要将 JSON 用于请求和响应。</span><span class="sxs-lookup"><span data-stu-id="0946b-108">To use JSON for requests and responses.</span></span> <span data-ttu-id="0946b-109">设置这两个到`WebMessageFormat.Json`。</span><span class="sxs-lookup"><span data-stu-id="0946b-109">set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="0946b-110">若要使用 JSON，必须使用<xref:System.ServiceModel.WebHttpBinding>，以自动配置<xref:System.ServiceModel.Description.WebHttpBehavior>。</span><span class="sxs-lookup"><span data-stu-id="0946b-110">In order to use JSON, you must use the <xref:System.ServiceModel.WebHttpBinding>, which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="0946b-111">有关 WCF 序列化的详细信息，请参阅[序列化和反序列化](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)。</span><span class="sxs-lookup"><span data-stu-id="0946b-111">For more information about WCF serialization, see [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).</span></span> <span data-ttu-id="0946b-112">有关 JSON 和 WCF 的详细信息，请参阅[服务站-简介到 RESTful 服务与 WCF](https://msdn.microsoft.com/magazine/dd315413.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0946b-112">For more information about JSON and WCF, see [Service Station - An Introduction To RESTful Services With WCF](https://msdn.microsoft.com/magazine/dd315413.aspx).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0946b-113">使用 JSON 需要使用 <xref:System.ServiceModel.WebHttpBinding> 和 <xref:System.ServiceModel.Description.WebHttpBehavior>，这两者不支持 SOAP 通信。</span><span class="sxs-lookup"><span data-stu-id="0946b-113">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="0946b-114">与通信的服务<xref:System.ServiceModel.WebHttpBinding>不支持公开服务元数据，因此你将无法再使用 Visual Studio 添加服务引用功能或 svcutil 命令行工具来生成客户端代理。</span><span class="sxs-lookup"><span data-stu-id="0946b-114">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="0946b-115">有关如何以编程方式调用使用服务的详细信息<xref:System.ServiceModel.WebHttpBinding>，请参阅[如何使用 REST 服务以及 WCF](https://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0946b-115">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](https://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="0946b-116">非类型化的消息编程</span><span class="sxs-lookup"><span data-stu-id="0946b-116">Untyped Message Programming</span></span>  
 <span data-ttu-id="0946b-117">当直接使用非类型化的消息对象时，您必须显式设置非类型化消息的属性，以便将其序列化为 JSON。</span><span class="sxs-lookup"><span data-stu-id="0946b-117">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="0946b-118">下面的代码段演示如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0946b-118">The following code snippet shows how to do this.</span></span>  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="0946b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="0946b-119">See also</span></span>

- [<span data-ttu-id="0946b-120">AJAX 集成和 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="0946b-120">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="0946b-121">独立 JSON 序列化</span><span class="sxs-lookup"><span data-stu-id="0946b-121">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [<span data-ttu-id="0946b-122">JSON 序列化</span><span class="sxs-lookup"><span data-stu-id="0946b-122">JSON Serialization</span></span>](../../../../docs/framework/wcf/samples/json-serialization.md)
