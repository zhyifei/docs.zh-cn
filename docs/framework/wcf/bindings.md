---
title: "Windows Communication Foundation 绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings [WCF]
ms.assetid: 845df323-be53-4848-92ef-ba67a406484d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e878aadf1c7df6042323c008ff52a4be8a9d817f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="windows-communication-foundation-bindings"></a><span data-ttu-id="49dcd-102">Windows Communication Foundation 绑定</span><span class="sxs-lookup"><span data-stu-id="49dcd-102">Windows Communication Foundation Bindings</span></span>
<span data-ttu-id="49dcd-103">绑定指定 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 服务终结点与其他终结点进行通信的方式。</span><span class="sxs-lookup"><span data-stu-id="49dcd-103">Bindings specify how a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service endpoint communicates with other endpoints.</span></span> <span data-ttu-id="49dcd-104">绑定最起码必须指定要使用的传输（如 HTTP 或 TCP）。</span><span class="sxs-lookup"><span data-stu-id="49dcd-104">At its most basic, a binding must specify the transport (for example, HTTP or TCP) to use.</span></span> <span data-ttu-id="49dcd-105">你还可以通过绑定来设置其他特征，如安全和事务支持。</span><span class="sxs-lookup"><span data-stu-id="49dcd-105">You can also set other characteristics, such as security and transaction support, through bindings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49dcd-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="49dcd-106">In This Section</span></span>  
 [<span data-ttu-id="49dcd-107">WCF 绑定概述</span><span class="sxs-lookup"><span data-stu-id="49dcd-107">WCF Bindings Overview</span></span>](../../../docs/framework/wcf/bindings-overview.md)  
 <span data-ttu-id="49dcd-108">关于 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 绑定执行哪些功能、系统提供哪些绑定以及可以如何定义或修改这些绑定的概述。</span><span class="sxs-lookup"><span data-stu-id="49dcd-108">Overview of what [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bindings do, what bindings the system provides, and how you can define or modify them.</span></span>  
  
 [<span data-ttu-id="49dcd-109">系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="49dcd-109">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)  
 <span data-ttu-id="49dcd-110">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 附带的绑定的列表。</span><span class="sxs-lookup"><span data-stu-id="49dcd-110">A list of bindings included with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="49dcd-111">这些绑定包含大部分安全和消息模式要求。</span><span class="sxs-lookup"><span data-stu-id="49dcd-111">These bindings cover the majority of security and message pattern requirements.</span></span>  
  
 [<span data-ttu-id="49dcd-112">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="49dcd-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 <span data-ttu-id="49dcd-113">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 绑定包含重要信息，客户端必须使用这些信息连接到服务终结点。</span><span class="sxs-lookup"><span data-stu-id="49dcd-113">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] binding contains important information that clients must use to connect to service endpoints.</span></span>  
  
 [<span data-ttu-id="49dcd-114">配置服务绑定</span><span class="sxs-lookup"><span data-stu-id="49dcd-114">Configuring Bindings for Services</span></span>](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 <span data-ttu-id="49dcd-115">通过配置，管理员和安装者可以自定义服务终结点的绑定。</span><span class="sxs-lookup"><span data-stu-id="49dcd-115">Configuration enables administrators and installers to customize the bindings for service endpoints.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="49dcd-116">参考</span><span class="sxs-lookup"><span data-stu-id="49dcd-116">Reference</span></span>  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="49dcd-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="49dcd-117">Related Sections</span></span>  
 [<span data-ttu-id="49dcd-118">终结点：地址、绑定和协定</span><span class="sxs-lookup"><span data-stu-id="49dcd-118">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
  
 [<span data-ttu-id="49dcd-119">绑定</span><span class="sxs-lookup"><span data-stu-id="49dcd-119">Bindings</span></span>](../../../docs/framework/wcf/feature-details/bindings.md)  
  
## <a name="see-also"></a><span data-ttu-id="49dcd-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="49dcd-120">See Also</span></span>  
 [<span data-ttu-id="49dcd-121">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="49dcd-121">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)
