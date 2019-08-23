---
title: COR_PRF_JIT_CACHE 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 30500e8ea55f8298b9a980e34dc611b58a51bdcc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916401"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="76e45-102">COR_PRF_JIT_CACHE 枚举</span><span class="sxs-lookup"><span data-stu-id="76e45-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="76e45-103">指示缓存的函数搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="76e45-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76e45-104">`COR_PRF_CACHED_FUNCTION_FOUND`的值为零, 因此`COR_PRF_JIT_CACHE`不能用作布尔代理项。</span><span class="sxs-lookup"><span data-stu-id="76e45-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e45-105">语法</span><span class="sxs-lookup"><span data-stu-id="76e45-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="76e45-106">成员</span><span class="sxs-lookup"><span data-stu-id="76e45-106">Members</span></span>  
  
|<span data-ttu-id="76e45-107">成员</span><span class="sxs-lookup"><span data-stu-id="76e45-107">Member</span></span>|<span data-ttu-id="76e45-108">描述</span><span class="sxs-lookup"><span data-stu-id="76e45-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="76e45-109">搜索找到函数。</span><span class="sxs-lookup"><span data-stu-id="76e45-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="76e45-110">搜索找不到函数。</span><span class="sxs-lookup"><span data-stu-id="76e45-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76e45-111">要求</span><span class="sxs-lookup"><span data-stu-id="76e45-111">Requirements</span></span>  
 <span data-ttu-id="76e45-112">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="76e45-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76e45-113">**标头：** Corprof.idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="76e45-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="76e45-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76e45-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76e45-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76e45-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e45-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="76e45-116">See also</span></span>

- [<span data-ttu-id="76e45-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="76e45-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
