---
title: "传输安全"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86c94153-e48d-4539-b6cf-cd8060582e7f
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 364326e2ded11f7174adc891a5fd9bcdd3c98334
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="transport-security"></a><span data-ttu-id="3f5bc-102">传输安全</span><span class="sxs-lookup"><span data-stu-id="3f5bc-102">Transport Security</span></span>
<span data-ttu-id="3f5bc-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中的传输安全取决于所选的绑定。</span><span class="sxs-lookup"><span data-stu-id="3f5bc-103">Transport security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] depends on the binding selected.</span></span> <span data-ttu-id="3f5bc-104">绑定所实现的传输决定实际的安全机制。</span><span class="sxs-lookup"><span data-stu-id="3f5bc-104">The transport that the binding implements determines the actual security mechanism.</span></span> <span data-ttu-id="3f5bc-105">本节中的主题说明所实现的机制及其选项。</span><span class="sxs-lookup"><span data-stu-id="3f5bc-105">The topics in this section explain the mechanisms that are implemented and their options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f5bc-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="3f5bc-106">In This Section</span></span>  
 [<span data-ttu-id="3f5bc-107">传输安全性概述</span><span class="sxs-lookup"><span data-stu-id="3f5bc-107">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="3f5bc-108">说明 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中的传输安全的基本知识。</span><span class="sxs-lookup"><span data-stu-id="3f5bc-108">Explains the basics of transport security in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="3f5bc-109">HTTP 传输安全性</span><span class="sxs-lookup"><span data-stu-id="3f5bc-109">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)  
 <span data-ttu-id="3f5bc-110">说明 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 如何实现安全套接字层（SSL 或 HTTPS）。</span><span class="sxs-lookup"><span data-stu-id="3f5bc-110">Explains how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implements Secure Sockets Layer (SSL, or HTTPS).</span></span>  
  
 [<span data-ttu-id="3f5bc-111">了解 HTTP 身份验证</span><span class="sxs-lookup"><span data-stu-id="3f5bc-111">Understanding HTTP Authentication</span></span>](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md)  
 <span data-ttu-id="3f5bc-112">描述 HTTP 身份验证方案，如基本、摘要式、NT LAN Manager (NTLM) 及其他。</span><span class="sxs-lookup"><span data-stu-id="3f5bc-112">Describes HTTP authentication schemes, such as Basic, Digest, NT LAN Manager (NTLM), and others.</span></span>  
  
 [<span data-ttu-id="3f5bc-113">将模拟用于传输安全性</span><span class="sxs-lookup"><span data-stu-id="3f5bc-113">Using Impersonation with Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md)  
 <span data-ttu-id="3f5bc-114">说明传输安全模式的五个可能的模拟级别。</span><span class="sxs-lookup"><span data-stu-id="3f5bc-114">Explains the five levels of impersonation that are possible with transport security mode.</span></span>  
  
 [<span data-ttu-id="3f5bc-115">如何：使用 SSL 证书配置端口</span><span class="sxs-lookup"><span data-stu-id="3f5bc-115">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 <span data-ttu-id="3f5bc-116">浏览有关在具有用于 SSL（传输）安全的 X.509 证书的计算机上配置端口的基本知识。</span><span class="sxs-lookup"><span data-stu-id="3f5bc-116">Walks through the basics of configuring a port on a machine with an X.509 certificate for SSL (transport) security.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3f5bc-117">参考</span><span class="sxs-lookup"><span data-stu-id="3f5bc-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="3f5bc-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="3f5bc-118">Related Sections</span></span>  
 [<span data-ttu-id="3f5bc-119">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="3f5bc-119">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="3f5bc-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f5bc-120">See Also</span></span>  
 [<span data-ttu-id="3f5bc-121">WCF 安全编程</span><span class="sxs-lookup"><span data-stu-id="3f5bc-121">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
