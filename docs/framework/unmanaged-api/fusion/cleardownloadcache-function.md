---
title: "ClearDownloadCache 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ClearDownloadCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: ClearDownloadCache
helpviewer_keywords: ClearDownloadCache function [.NET Framework fusion]
ms.assetid: df7595d1-430f-44b4-8160-4c2ba9df70b1
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d50c9c4e4bb102e94c5a5302576f623a8e04ed5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cleardownloadcache-function"></a><span data-ttu-id="7d8c3-102">ClearDownloadCache 函数</span><span class="sxs-lookup"><span data-stu-id="7d8c3-102">ClearDownloadCache Function</span></span>
<span data-ttu-id="7d8c3-103">清除下载的程序集的全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="7d8c3-103">Clears the global assembly cache of downloaded assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d8c3-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d8c3-104">Syntax</span></span>  
  
```  
HRESULT ClearDownloadCache ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="7d8c3-105">要求</span><span class="sxs-lookup"><span data-stu-id="7d8c3-105">Requirements</span></span>  
 <span data-ttu-id="7d8c3-106">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d8c3-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d8c3-107">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="7d8c3-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7d8c3-108">**库：**为 Fusion.dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="7d8c3-108">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="7d8c3-109">使用而不是 Mscorwks.dll 为 Fusion.dll 来确保面向.NET Framework 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="7d8c3-109">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="7d8c3-110">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d8c3-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d8c3-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d8c3-111">See Also</span></span>  
 [<span data-ttu-id="7d8c3-112">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="7d8c3-112">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="7d8c3-113">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="7d8c3-113">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
