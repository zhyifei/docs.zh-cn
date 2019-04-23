---
title: WCF 所要求的操作系统资源
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 828d656370efd7638fa4cf367b84ee7b316b89bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100925"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="7df98-102">WCF 所要求的操作系统资源</span><span class="sxs-lookup"><span data-stu-id="7df98-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="7df98-103">Windows Communication Foundation (WCF) 取决于提供的函数将操作系统的多个资源。</span><span class="sxs-lookup"><span data-stu-id="7df98-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="7df98-104">下表列出了这些资源。</span><span class="sxs-lookup"><span data-stu-id="7df98-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="7df98-105">资源</span><span class="sxs-lookup"><span data-stu-id="7df98-105">Resource</span></span>|<span data-ttu-id="7df98-106">描述</span><span class="sxs-lookup"><span data-stu-id="7df98-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="7df98-107">Microsoft 分布式事务协调器 (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="7df98-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="7df98-108">支持 OleTx 事务所必需。</span><span class="sxs-lookup"><span data-stu-id="7df98-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="7df98-109">Internet 信息服务 (IIS)</span><span class="sxs-lookup"><span data-stu-id="7df98-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="7df98-110">如果希望使用 IIS 来承载应用程序，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="7df98-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="7df98-111">Windows 进程激活服务 (WAS)</span><span class="sxs-lookup"><span data-stu-id="7df98-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="7df98-112">如果希望使用 WAS 来承载应用程序，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="7df98-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7df98-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="7df98-113">See also</span></span>

- [<span data-ttu-id="7df98-114">系统要求</span><span class="sxs-lookup"><span data-stu-id="7df98-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
