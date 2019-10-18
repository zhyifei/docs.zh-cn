---
title: WCF 所要求的操作系统资源
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: ac9bd5ed7c2092720c6521d0f78185c3fbf9f94b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318948"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="79561-102">WCF 所要求的操作系统资源</span><span class="sxs-lookup"><span data-stu-id="79561-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="79561-103">Windows Communication Foundation （WCF）依赖于操作系统提供的多个资源才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="79561-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="79561-104">下表列出了这些资源。</span><span class="sxs-lookup"><span data-stu-id="79561-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="79561-105">资源</span><span class="sxs-lookup"><span data-stu-id="79561-105">Resource</span></span>|<span data-ttu-id="79561-106">描述</span><span class="sxs-lookup"><span data-stu-id="79561-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="79561-107">Microsoft 分布式事务协调器 (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="79561-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="79561-108">支持 OleTx 事务所必需。</span><span class="sxs-lookup"><span data-stu-id="79561-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="79561-109">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="79561-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="79561-110">如果希望使用 IIS 来承载应用程序，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="79561-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="79561-111">Windows 进程激活服务 (WAS)</span><span class="sxs-lookup"><span data-stu-id="79561-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="79561-112">如果希望使用 WAS 来承载应用程序，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="79561-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79561-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="79561-113">See also</span></span>

- [<span data-ttu-id="79561-114">系统要求</span><span class="sxs-lookup"><span data-stu-id="79561-114">System Requirements</span></span>](wcf-system-requirements.md)
