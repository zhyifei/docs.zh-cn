---
title: WCF 所要求的操作系统资源
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 828d656370efd7638fa4cf367b84ee7b316b89bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100925"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="e6272-102">WCF 所要求的操作系统资源</span><span class="sxs-lookup"><span data-stu-id="e6272-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="e6272-103">Windows Communication Foundation (WCF) 取决于提供的函数将操作系统的多个资源。</span><span class="sxs-lookup"><span data-stu-id="e6272-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="e6272-104">下表列出了这些资源。</span><span class="sxs-lookup"><span data-stu-id="e6272-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="e6272-105">资源</span><span class="sxs-lookup"><span data-stu-id="e6272-105">Resource</span></span>|<span data-ttu-id="e6272-106">描述</span><span class="sxs-lookup"><span data-stu-id="e6272-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e6272-107">Microsoft 分布式事务协调器 (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="e6272-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="e6272-108">支持 OleTx 事务所必需。</span><span class="sxs-lookup"><span data-stu-id="e6272-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="e6272-109">Internet 信息服务 (IIS)</span><span class="sxs-lookup"><span data-stu-id="e6272-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="e6272-110">如果希望使用 IIS 来承载应用程序，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="e6272-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="e6272-111">Windows 进程激活服务 (WAS)</span><span class="sxs-lookup"><span data-stu-id="e6272-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="e6272-112">如果希望使用 WAS 来承载应用程序，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="e6272-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6272-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6272-113">See also</span></span>

- [<span data-ttu-id="e6272-114">系统要求</span><span class="sxs-lookup"><span data-stu-id="e6272-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
