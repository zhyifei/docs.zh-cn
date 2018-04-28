---
title: 创建 WS-I 基本配置文件 1.1 可互操作服务
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fd08dca74ddb3f77e37a3aa4d67cf6d495bf5d16
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="5ee85-102">创建 WS-I 基本配置文件 1.1 可互操作服务</span><span class="sxs-lookup"><span data-stu-id="5ee85-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>
<span data-ttu-id="5ee85-103">将 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务终结点配置为可与 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web 服务客户端互操作：</span><span class="sxs-lookup"><span data-stu-id="5ee85-103">To configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service endpoint to be interoperable with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients:</span></span>  
  
-   <span data-ttu-id="5ee85-104">将 <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> 类型用作服务终结点的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="5ee85-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
-   <span data-ttu-id="5ee85-105">不要使用服务终结点上的回调和会话协定功能或事务行为</span><span class="sxs-lookup"><span data-stu-id="5ee85-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
 <span data-ttu-id="5ee85-106">您可以根据需要在该绑定上启用对 HTTPS 和传输级客户端身份验证的支持。</span><span class="sxs-lookup"><span data-stu-id="5ee85-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
 <span data-ttu-id="5ee85-107"><xref:System.ServiceModel.BasicHttpBinding> 类的以下特性所要求的功能超出了 WS-I 基本配置文件 1.1 的范围：</span><span class="sxs-lookup"><span data-stu-id="5ee85-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
-   <span data-ttu-id="5ee85-108">由 <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> 属性控制的消息传递优化机制 (MTOM) 消息编码。</span><span class="sxs-lookup"><span data-stu-id="5ee85-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="5ee85-109">将此属性保留为其默认值（即 <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>）以便不使用 MTOM。</span><span class="sxs-lookup"><span data-stu-id="5ee85-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
-   <span data-ttu-id="5ee85-110">由 <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> 值控制的消息安全提供符合 WS-I 基本安全配置文件 1.0 的 WS-Security 支持。</span><span class="sxs-lookup"><span data-stu-id="5ee85-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="5ee85-111">将此属性保留为其默认值（即 <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType>）以便不使用 WS-Security。</span><span class="sxs-lookup"><span data-stu-id="5ee85-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
 <span data-ttu-id="5ee85-112">若要使元数据[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]适用于服务[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]，使用 Web 服务客户端生成工具： [Web 服务描述语言工具 (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88)， [Web 服务发现工具 (Disco.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979)，和`Add Web Reference`Visual Studio 中的功能; 必须启用元数据发布。</span><span class="sxs-lookup"><span data-stu-id="5ee85-112">To make the metadata for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service available to [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [Web Services Discovery Tool (Disco.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979), and the `Add Web Reference` feature in Visual Studio; you must enable metadata publication.</span></span> <span data-ttu-id="5ee85-113">有关详细信息，请参阅[发布元数据终结点](../../../docs/framework/wcf/publishing-metadata-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="5ee85-113">For more information, see [Publishing Metadata Endpoints](../../../docs/framework/wcf/publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ee85-114">示例</span><span class="sxs-lookup"><span data-stu-id="5ee85-114">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="5ee85-115">描述</span><span class="sxs-lookup"><span data-stu-id="5ee85-115">Description</span></span>  
 <span data-ttu-id="5ee85-116">下面的代码示例演示如何添加[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]与兼容的终结点[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]Web 服务客户端在代码和配置文件中。</span><span class="sxs-lookup"><span data-stu-id="5ee85-116">The following example code demonstrates how to add a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] endpoint that is compatible with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5ee85-117">代码</span><span class="sxs-lookup"><span data-stu-id="5ee85-117">Code</span></span>  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5ee85-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ee85-118">See Also</span></span>  
 [<span data-ttu-id="5ee85-119">与 ASP.NET Web 服务的互操作性</span><span class="sxs-lookup"><span data-stu-id="5ee85-119">Interoperability with ASP.NET Web Services</span></span>](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
