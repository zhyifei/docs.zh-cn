---
title: "GetCachePath 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: GetCachePath
helpviewer_keywords: GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 371dab83d7441681b9d6bd5723bcd8c3caadb50e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getcachepath-function"></a><span data-ttu-id="9930f-102">GetCachePath 函数</span><span class="sxs-lookup"><span data-stu-id="9930f-102">GetCachePath Function</span></span>
<span data-ttu-id="9930f-103">获取使用指定的标志的缓存程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="9930f-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9930f-104">语法</span><span class="sxs-lookup"><span data-stu-id="9930f-104">Syntax</span></span>  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9930f-105">参数</span><span class="sxs-lookup"><span data-stu-id="9930f-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="9930f-106">[in][ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)值，该值指示缓存的程序集的源。</span><span class="sxs-lookup"><span data-stu-id="9930f-106">[in] An [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="9930f-107">[out]返回的指向的路径。</span><span class="sxs-lookup"><span data-stu-id="9930f-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="9930f-108">[在中，out]将请求的最大长度的`pwzCachePath`，并在返回时的实际长度`pwzCachePath`。</span><span class="sxs-lookup"><span data-stu-id="9930f-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9930f-109">惠?</span><span class="sxs-lookup"><span data-stu-id="9930f-109">Requirements</span></span>  
 <span data-ttu-id="9930f-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9930f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9930f-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="9930f-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9930f-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9930f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9930f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="9930f-113">See Also</span></span>  
 [<span data-ttu-id="9930f-114">ASM_CACHE_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="9930f-114">ASM_CACHE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)  
 [<span data-ttu-id="9930f-115">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="9930f-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
