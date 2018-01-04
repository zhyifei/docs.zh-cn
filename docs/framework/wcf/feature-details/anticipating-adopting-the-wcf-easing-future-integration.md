---
title: "预期采用 Windows Communication Foundation：便于以后集成"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8dbb50af9d5655a76abb3827cd2f512eab0fd662
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a><span data-ttu-id="6cc36-102">预期采用 Windows Communication Foundation：便于以后集成</span><span class="sxs-lookup"><span data-stu-id="6cc36-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>
<span data-ttu-id="6cc36-103">如果您现在使用 ASP.NET，并预期在以后使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]，则本主题所提供的指导可确保新的 ASP.NET Web 服务可与 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序一起正常工作。</span><span class="sxs-lookup"><span data-stu-id="6cc36-103">If you use ASP.NET today, and anticipate using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in the future, this topic provides guidance to ensure that new ASP.NET Web services will work well together with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="general-recommendations"></a><span data-ttu-id="6cc36-104">一般性建议</span><span class="sxs-lookup"><span data-stu-id="6cc36-104">General Recommendations</span></span>  
 <span data-ttu-id="6cc36-105">对任何新服务采用 ASP.NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="6cc36-105">Adopt ASP.NET 2.0 for any new services.</span></span> <span data-ttu-id="6cc36-106">这样做将允许新服务访问新版本中的改进和增强。</span><span class="sxs-lookup"><span data-stu-id="6cc36-106">Doing so will provide access to the improvements and enhancements of the new version.</span></span> <span data-ttu-id="6cc36-107">不过，这也允许在同一个应用程序中与 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 组件一起使用 ASP.NET 2.0 组件。</span><span class="sxs-lookup"><span data-stu-id="6cc36-107">However, it will also allow for the possibility of using ASP.NET 2.0 components together with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] components in the same application.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="6cc36-108">协议</span><span class="sxs-lookup"><span data-stu-id="6cc36-108">Protocols</span></span>  
 <span data-ttu-id="6cc36-109">使用 ASP.NET 2.0 的新工具验证与 WS-I 基本配置文件 1.1 的一致性：</span><span class="sxs-lookup"><span data-stu-id="6cc36-109">Use ASP.NET 2.0’s new facility for validating conformity to the WS-I Basic Profile 1.1:</span></span>  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="6cc36-110">通过使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 预定义的绑定 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]，符合 WS-I 基础配置文件 1.1 的 ASP.NET Web 服务将可与 <xref:System.ServiceModel.BasicHttpBinding> 客户端互操作。</span><span class="sxs-lookup"><span data-stu-id="6cc36-110">ASP.NET Web services that conform to WS-I Basic Profile 1.1 will be interoperable with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients by using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] predefined binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="6cc36-111">服务开发</span><span class="sxs-lookup"><span data-stu-id="6cc36-111">Service Development</span></span>  
 <span data-ttu-id="6cc36-112">避免使用 <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> 特性依据 SOAP 消息正文元素的完全限定名称将消息路由到方法，而应使用 SOAPAction HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="6cc36-112">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the SOAPAction HTTP header.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="6cc36-113"> 使用 SOAPAction HTTP 标头来路由消息。</span><span class="sxs-lookup"><span data-stu-id="6cc36-113"> uses the SOAPAction HTTP header for routing messages.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="6cc36-114">数据表示形式</span><span class="sxs-lookup"><span data-stu-id="6cc36-114">Data Representation</span></span>  
 <span data-ttu-id="6cc36-115">只要为 XML 显式定义了命名空间，则在默认情况下，<xref:System.Xml.Serialization.XmlSerializer> 将类型序列化为的 XML 与 <xref:System.Runtime.Serialization.DataContractSerializer> 将类型序列化为的 XML 在语义上完全相同。</span><span class="sxs-lookup"><span data-stu-id="6cc36-115">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="6cc36-116">如果预期在以后采用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]，则在定义用于 ASP.NET Web 服务的数据类型时，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6cc36-116">When defining a data type for use with ASP.NET Web services in anticipation of adopting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in the future, do the following:</span></span>  
  
1.  <span data-ttu-id="6cc36-117">使用 .NET Framework 类而不是 XML 架构来定义该类型。</span><span class="sxs-lookup"><span data-stu-id="6cc36-117">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
2.  <span data-ttu-id="6cc36-118">仅将 <xref:System.SerializableAttribute> 和 <xref:System.Xml.Serialization.XmlRootAttribute> 添加到该类，使用后者显式定义类型的命名空间。</span><span class="sxs-lookup"><span data-stu-id="6cc36-118">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="6cc36-119">不要添加 <xref:System.Xml.Serialization> 命名空间中的其他属性来控制如何将 .NET Framework 类转换为 XML。</span><span class="sxs-lookup"><span data-stu-id="6cc36-119">Do no add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
 <span data-ttu-id="6cc36-120">通过采用此方法，以后可将 .NET 类转换为附加了 <xref:System.Runtime.Serialization.DataContractAttribute> 和 <xref:System.Runtime.Serialization.DataMemberAttribute> 的数据协定，而无需为了传输而对类序列化成的 XML 进行重大更改。</span><span class="sxs-lookup"><span data-stu-id="6cc36-120">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="6cc36-121">消息中由 ASP.NET Web 服务使用的类型将能够作为数据协定由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序处理，从而使 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序具有更高的性能，同时还会有其他方面的益处。</span><span class="sxs-lookup"><span data-stu-id="6cc36-121">The types used in messages by ASP.NET Web services will be able to be processed as data contracts by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications, yielding, amongst other benefits, better performance in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="security"></a><span data-ttu-id="6cc36-122">安全性</span><span class="sxs-lookup"><span data-stu-id="6cc36-122">Security</span></span>  
 <span data-ttu-id="6cc36-123">避免使用 Internet Information Services (IIS) 提供的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="6cc36-123">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="6cc36-124"> 客户端不支持这些选项。</span><span class="sxs-lookup"><span data-stu-id="6cc36-124"> clients do not support them.</span></span> <span data-ttu-id="6cc36-125">如果必须保护某一服务，请使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供的选项，因为这些选项更丰富，并且基于标准协议。</span><span class="sxs-lookup"><span data-stu-id="6cc36-125">If a service needs to be secured, use the options provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because these options are richer and are based on standard protocols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cc36-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="6cc36-126">See Also</span></span>  
 [<span data-ttu-id="6cc36-127">预期采用 Windows Communication Foundation：便于以后迁移</span><span class="sxs-lookup"><span data-stu-id="6cc36-127">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
