---
title: "NukeDownloadedCache 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: NukeDownloadedCache
helpviewer_keywords: NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31d7ba7d5f4a9268ea1e04a4c9f09cd17ebfd5bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="e986e-102">NukeDownloadedCache 函数</span><span class="sxs-lookup"><span data-stu-id="e986e-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="e986e-103">删除公共语言运行时 (CLR) 下载缓存。</span><span class="sxs-lookup"><span data-stu-id="e986e-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e986e-104">语法</span><span class="sxs-lookup"><span data-stu-id="e986e-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e986e-105">返回值</span><span class="sxs-lookup"><span data-stu-id="e986e-105">Return Value</span></span>  
 <span data-ttu-id="e986e-106">WinError.h 中定义，此方法将返回标准的 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="e986e-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e986e-107">备注</span><span class="sxs-lookup"><span data-stu-id="e986e-107">Remarks</span></span>  
 <span data-ttu-id="e986e-108">CLR 下载缓存是具有强名称程序集，从某个 URL 下载以备可能重复使用的存储位置的区域。</span><span class="sxs-lookup"><span data-stu-id="e986e-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e986e-109">惠?</span><span class="sxs-lookup"><span data-stu-id="e986e-109">Requirements</span></span>  
 <span data-ttu-id="e986e-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e986e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e986e-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e986e-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e986e-112">**库：**为 Fusion.dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="e986e-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="e986e-113">使用而不是 Mscorwks.dll 为 Fusion.dll 来确保面向.NET Framework 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="e986e-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="e986e-114">**.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e986e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e986e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e986e-115">See Also</span></span>  
 [<span data-ttu-id="e986e-116">CreateHistoryReader 函数</span><span class="sxs-lookup"><span data-stu-id="e986e-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="e986e-117">GetHistoryFileDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="e986e-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [<span data-ttu-id="e986e-118">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="e986e-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
