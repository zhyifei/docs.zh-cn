---
title: "WCF 所要求的操作系统资源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31006331f5e8a71bf3f4fb9a68c31cb32d0b6f2b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="9d9cb-102">WCF 所要求的操作系统资源</span><span class="sxs-lookup"><span data-stu-id="9d9cb-102">Operating System Resources Required by WCF</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="9d9cb-103"> 的正常运行依赖于操作系统提供的几种资源。</span><span class="sxs-lookup"><span data-stu-id="9d9cb-103"> depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="9d9cb-104">下表列出了这些资源。</span><span class="sxs-lookup"><span data-stu-id="9d9cb-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="9d9cb-105">资源</span><span class="sxs-lookup"><span data-stu-id="9d9cb-105">Resource</span></span>|<span data-ttu-id="9d9cb-106">描述</span><span class="sxs-lookup"><span data-stu-id="9d9cb-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="9d9cb-107">Microsoft 分布式事务协调器 (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="9d9cb-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="9d9cb-108">支持 OleTx 事务所必需。</span><span class="sxs-lookup"><span data-stu-id="9d9cb-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="9d9cb-109">Internet 信息服务 (IIS)</span><span class="sxs-lookup"><span data-stu-id="9d9cb-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="9d9cb-110">如果希望使用 IIS 来承载应用程序，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="9d9cb-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="9d9cb-111">Windows 进程激活服务 (WAS)</span><span class="sxs-lookup"><span data-stu-id="9d9cb-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="9d9cb-112">如果希望使用 WAS 来承载应用程序，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="9d9cb-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d9cb-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d9cb-113">See Also</span></span>  
 [<span data-ttu-id="9d9cb-114">系统要求</span><span class="sxs-lookup"><span data-stu-id="9d9cb-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
