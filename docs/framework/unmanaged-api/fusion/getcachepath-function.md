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
ms.openlocfilehash: 13e1468ef5a48f18910c1f8082cdd7c4849da14a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132695"
---
# <a name="getcachepath-function"></a><span data-ttu-id="e09f9-102">GetCachePath 函数</span><span class="sxs-lookup"><span data-stu-id="e09f9-102">GetCachePath Function</span></span>
<span data-ttu-id="e09f9-103">使用指定的标志获取缓存的程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="e09f9-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e09f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="e09f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e09f9-105">参数</span><span class="sxs-lookup"><span data-stu-id="e09f9-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="e09f9-106">中指示缓存的程序集的源的[ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="e09f9-106">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="e09f9-107">弄指向路径的返回指针。</span><span class="sxs-lookup"><span data-stu-id="e09f9-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="e09f9-108">[in，out]请求的 `pwzCachePath`的最大长度，返回时为 `pwzCachePath`的实际长度。</span><span class="sxs-lookup"><span data-stu-id="e09f9-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e09f9-109">要求</span><span class="sxs-lookup"><span data-stu-id="e09f9-109">Requirements</span></span>  
 <span data-ttu-id="e09f9-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e09f9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e09f9-111">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="e09f9-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e09f9-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e09f9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e09f9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e09f9-113">See also</span></span>

- [<span data-ttu-id="e09f9-114">ASM_CACHE_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="e09f9-114">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="e09f9-115">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="e09f9-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
