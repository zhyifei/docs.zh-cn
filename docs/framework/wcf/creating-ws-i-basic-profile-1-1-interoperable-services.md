---
title: 创建 WS-I 基本配置文件 1.1 可互操作服务
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: f32308a17e2934b6884140307074f97e6b51f5f9
ms.sourcegitcommit: 296183dbe35077b5c5e5e74d5fbe7f399bc507ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "50982849"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="e7cb3-102">创建 WS-I 基本配置文件 1.1 可互操作服务</span><span class="sxs-lookup"><span data-stu-id="e7cb3-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>
<span data-ttu-id="e7cb3-103">若要配置为可与互操作的 WCF 服务端点[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]Web 服务客户端：</span><span class="sxs-lookup"><span data-stu-id="e7cb3-103">To configure a WCF service endpoint to be interoperable with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients:</span></span>  
  
-   <span data-ttu-id="e7cb3-104">将 <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> 类型用作服务终结点的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="e7cb3-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
-   <span data-ttu-id="e7cb3-105">不要使用服务终结点上的回调和会话协定功能或事务行为</span><span class="sxs-lookup"><span data-stu-id="e7cb3-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
 <span data-ttu-id="e7cb3-106">您可以根据需要在该绑定上启用对 HTTPS 和传输级客户端身份验证的支持。</span><span class="sxs-lookup"><span data-stu-id="e7cb3-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
 <span data-ttu-id="e7cb3-107"><xref:System.ServiceModel.BasicHttpBinding> 类的以下特性所要求的功能超出了 WS-I 基本配置文件 1.1 的范围：</span><span class="sxs-lookup"><span data-stu-id="e7cb3-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
-   <span data-ttu-id="e7cb3-108">由 <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> 属性控制的消息传递优化机制 (MTOM) 消息编码。</span><span class="sxs-lookup"><span data-stu-id="e7cb3-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="e7cb3-109">将此属性保留为其默认值（即 <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>）以便不使用 MTOM。</span><span class="sxs-lookup"><span data-stu-id="e7cb3-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
-   <span data-ttu-id="e7cb3-110">由 <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> 值控制的消息安全提供符合 WS-I 基本安全配置文件 1.0 的 WS-Security 支持。</span><span class="sxs-lookup"><span data-stu-id="e7cb3-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="e7cb3-111">将此属性保留为其默认值（即 <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType>）以便不使用 WS-Security。</span><span class="sxs-lookup"><span data-stu-id="e7cb3-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
 <span data-ttu-id="e7cb3-112">若要使 WCF 服务的元数据可供[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]，使用 Web 服务客户端生成工具： [Web 服务描述语言工具 (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29)， [Web 服务发现工具 (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29)，和`Add Web Reference`Visual Studio 中的功能; 必须启用元数据发布。</span><span class="sxs-lookup"><span data-stu-id="e7cb3-112">To make the metadata for a WCF service available to [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), [Web Services Discovery Tool (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29), and the `Add Web Reference` feature in Visual Studio; you must enable metadata publication.</span></span> <span data-ttu-id="e7cb3-113">有关详细信息，请参阅[发布元数据终结点](../../../docs/framework/wcf/publishing-metadata-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="e7cb3-113">For more information, see [Publishing Metadata Endpoints](../../../docs/framework/wcf/publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7cb3-114">示例</span><span class="sxs-lookup"><span data-stu-id="e7cb3-114">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e7cb3-115">描述</span><span class="sxs-lookup"><span data-stu-id="e7cb3-115">Description</span></span>  
 <span data-ttu-id="e7cb3-116">下面的代码示例演示如何将与兼容的 WCF 终结点添加[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]Web 服务客户端中的代码和配置文件中。</span><span class="sxs-lookup"><span data-stu-id="e7cb3-116">The following example code demonstrates how to add a WCF endpoint that is compatible with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e7cb3-117">代码</span><span class="sxs-lookup"><span data-stu-id="e7cb3-117">Code</span></span>  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e7cb3-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7cb3-118">See Also</span></span>  
 [<span data-ttu-id="e7cb3-119">与 ASP.NET Web 服务的互操作性</span><span class="sxs-lookup"><span data-stu-id="e7cb3-119">Interoperability with ASP.NET Web Services</span></span>](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
