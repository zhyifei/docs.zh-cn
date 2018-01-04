---
title: "与 ASP.NET Web 服务的互操作性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef174f457114003e5b2783b50040424d9a96945c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="interoperability-with-aspnet-web-services"></a><span data-ttu-id="8fa0a-102">与 ASP.NET Web 服务的互操作性</span><span class="sxs-lookup"><span data-stu-id="8fa0a-102">Interoperability with ASP.NET Web Services</span></span>
<span data-ttu-id="8fa0a-103">确保使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web 服务技术和 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务技术实现的服务符合 WS-I Basic Profile 1.1 规范，便可以实现这两种 Web 服务之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-103">Interoperability between [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services and [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web services can be achieved by ensuring that services implemented using both technologies conform to the WS-I Basic Profile 1.1 specification.</span></span> <span data-ttu-id="8fa0a-104">通过使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 系统提供的绑定 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]，符合 WS-I Basic Profile 1.1 的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web 服务可与 <xref:System.ServiceModel.BasicHttpBinding> 客户端进行互操作。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-104">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services that conform to WS-I Basic Profile 1.1 are interoperable with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients by using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
 <span data-ttu-id="8fa0a-105">使用 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] 选项，即将 <xref:System.Web.Services.WebService> 和 <xref:System.Web.Services.WebMethodAttribute> 属性添加到接口而不是添加到类，并编写实现该接口的类，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-105">Use [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] option of adding the <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> attributes to an interface rather than to a class, and writing a class to implement the interface, as shown in the following sample code.</span></span>  
  
```  
[WebService]  
public interface IEcho  
{  
    [WebMethod]  
    string Echo(string input);  
}  
  
public class Service : IEcho  
{  
  
   public string Echo(string input)  
   {  
        return input;  
    }  
}  
```  
  
 <span data-ttu-id="8fa0a-106">使用此选项是首选方法，因为具有 <xref:System.Web.Services.WebService> 属性的接口为服务所执行的操作构成了一个协定，在以不同方式实现该协定的各个类中，都可重用该协定。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-106">Using this option is preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="8fa0a-107">避免使用 <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> 特性依据 SOAP 消息正文元素的完全限定名称将消息路由到方法，而应使用 `SOAPAction` 标头。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-107">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the `SOAPAction` HTTP header.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8fa0a-108"> 使用 `SOAPAction` 标头来路由消息。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-108"> uses the `SOAPAction` HTTP header for routing messages.</span></span>  
  
 <span data-ttu-id="8fa0a-109">只要为 XML 显式定义了命名空间，则在默认情况下，<xref:System.Xml.Serialization.XmlSerializer> 将类型序列化为的 XML 与 <xref:System.Runtime.Serialization.DataContractSerializer> 将类型序列化为的 XML 在语义上完全相同。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-109">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="8fa0a-110">定义与一起使用的数据类型时[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web 服务，并且预期采用[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8fa0a-110">When defining a data type for use with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web services in anticipation of adopting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], do the following:</span></span>  
  
-   <span data-ttu-id="8fa0a-111">使用 .NET Framework 类而不是 XML 架构来定义该类型。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-111">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
-   <span data-ttu-id="8fa0a-112">仅将 <xref:System.SerializableAttribute> 和 <xref:System.Xml.Serialization.XmlRootAttribute> 添加到该类，使用后者显式定义类型的命名空间。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-112">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="8fa0a-113">不要添加 <xref:System.Xml.Serialization> 命名空间中的其他属性来控制如何将 .NET Framework 类转换为 XML。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-113">Do not add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
-   <span data-ttu-id="8fa0a-114">通过采用此方法，以后可将 .NET 类转换为附加了 <xref:System.Runtime.Serialization.DataContractAttribute> 和 <xref:System.Runtime.Serialization.DataMemberAttribute> 的数据协定，而无需为了传输而对类序列化成的 XML 进行重大更改。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-114">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="8fa0a-115">消息中由 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web 服务使用的类型可作为数据协定由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序处理，这样做的好处之一是，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序的性能会更好。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-115">The types used in messages by [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services can be processed as data contracts by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications, yielding, among other benefits, better performance in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
 <span data-ttu-id="8fa0a-116">避免使用 Internet Information Services (IIS) 提供的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-116">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8fa0a-117"> 客户端不支持这些选项。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-117"> clients do not support them.</span></span> <span data-ttu-id="8fa0a-118">如果必须保护服务，请使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供的选项，因为这些选项是可靠的，它们基于标准协议。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-118">If a service must be secured, use the options provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because these options are robust and are based on standard protocols.</span></span>  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a><span data-ttu-id="8fa0a-119">由加载 ServiceModel HttpModule 而导致的性能影响</span><span class="sxs-lookup"><span data-stu-id="8fa0a-119">Performance impact caused by loading the ServiceModel HttpModule</span></span>  
 <span data-ttu-id="8fa0a-120">在 .NET Framework 3.0 中，WCF `HttpModule` 安装在根 Web.config 文件中，因此，每个 ASP.NET 应用程序都启用了 WCF。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-120">In the .NET Framework 3.0, the WCF `HttpModule` was installed in the root Web.config file such that every ASP.NET application was WCF enabled.</span></span> <span data-ttu-id="8fa0a-121">这可能会影响性能，因此，可以移除 Web.config 文件的 `ServiceModel`，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="8fa0a-121">This might affect performance, so you can remove `ServiceModel` for the Web.config file as shown in the following example.</span></span>  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8fa0a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fa0a-122">See Also</span></span>  
 [<span data-ttu-id="8fa0a-123">如何：配置 WCF 服务以便与 ASP.NET Web 服务客户端进行互操作</span><span class="sxs-lookup"><span data-stu-id="8fa0a-123">How to: Configure WCF Service to Interoperate with ASP.NET Web Service Clients</span></span>](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
