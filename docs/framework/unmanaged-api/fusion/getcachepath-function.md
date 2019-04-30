---
title: GetCachePath 函数
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf23a8f1893aa0f992d554d3c7533c3dc42f4e95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985889"
---
# <a name="getcachepath-function"></a><span data-ttu-id="38ce1-102">GetCachePath 函数</span><span class="sxs-lookup"><span data-stu-id="38ce1-102">GetCachePath Function</span></span>
<span data-ttu-id="38ce1-103">获取使用指定的标志的缓存程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="38ce1-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ce1-104">语法</span><span class="sxs-lookup"><span data-stu-id="38ce1-104">Syntax</span></span>  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="38ce1-105">参数</span><span class="sxs-lookup"><span data-stu-id="38ce1-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="38ce1-106">[in][ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)值，该值指示将缓存程序集的源。</span><span class="sxs-lookup"><span data-stu-id="38ce1-106">[in] An [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="38ce1-107">[out]返回的指针到路径。</span><span class="sxs-lookup"><span data-stu-id="38ce1-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="38ce1-108">[in、 out]请求的最大长度`pwzCachePath`，并在返回时，实际长度`pwzCachePath`。</span><span class="sxs-lookup"><span data-stu-id="38ce1-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38ce1-109">要求</span><span class="sxs-lookup"><span data-stu-id="38ce1-109">Requirements</span></span>  
 <span data-ttu-id="38ce1-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="38ce1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38ce1-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="38ce1-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="38ce1-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38ce1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38ce1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="38ce1-113">See also</span></span>

- [<span data-ttu-id="38ce1-114">ASM_CACHE_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="38ce1-114">ASM_CACHE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)
- [<span data-ttu-id="38ce1-115">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="38ce1-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
