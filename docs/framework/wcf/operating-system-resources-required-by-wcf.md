---
title: WCF 所要求的操作系统资源
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 4522f1c59c8f74281a0e197338c6206ab29c229b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498639"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="b2c4b-102">WCF 所要求的操作系统资源</span><span class="sxs-lookup"><span data-stu-id="b2c4b-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="b2c4b-103">Windows Communication Foundation (WCF) 取决于几个资源，由操作系统正常工作。</span><span class="sxs-lookup"><span data-stu-id="b2c4b-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="b2c4b-104">下表列出了这些资源。</span><span class="sxs-lookup"><span data-stu-id="b2c4b-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="b2c4b-105">资源</span><span class="sxs-lookup"><span data-stu-id="b2c4b-105">Resource</span></span>|<span data-ttu-id="b2c4b-106">描述</span><span class="sxs-lookup"><span data-stu-id="b2c4b-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="b2c4b-107">Microsoft 分布式事务协调器 (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="b2c4b-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="b2c4b-108">支持 OleTx 事务所必需。</span><span class="sxs-lookup"><span data-stu-id="b2c4b-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="b2c4b-109">Internet 信息服务 (IIS)</span><span class="sxs-lookup"><span data-stu-id="b2c4b-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="b2c4b-110">如果希望使用 IIS 来承载应用程序，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="b2c4b-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="b2c4b-111">Windows 进程激活服务 (WAS)</span><span class="sxs-lookup"><span data-stu-id="b2c4b-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="b2c4b-112">如果希望使用 WAS 来承载应用程序，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="b2c4b-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2c4b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2c4b-113">See Also</span></span>  
 [<span data-ttu-id="b2c4b-114">系统要求</span><span class="sxs-lookup"><span data-stu-id="b2c4b-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
