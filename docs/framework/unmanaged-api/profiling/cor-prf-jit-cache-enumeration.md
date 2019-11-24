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
ms.openlocfilehash: 57d6ba77081536eb2bce0bf62d43ac080b2f5554
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447339"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="f3bef-102">COR_PRF_JIT_CACHE 枚举</span><span class="sxs-lookup"><span data-stu-id="f3bef-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="f3bef-103">指示缓存的函数搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="f3bef-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3bef-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span><span class="sxs-lookup"><span data-stu-id="f3bef-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3bef-105">语法</span><span class="sxs-lookup"><span data-stu-id="f3bef-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="f3bef-106">Members</span><span class="sxs-lookup"><span data-stu-id="f3bef-106">Members</span></span>  
  
|<span data-ttu-id="f3bef-107">成员</span><span class="sxs-lookup"><span data-stu-id="f3bef-107">Member</span></span>|<span data-ttu-id="f3bef-108">描述</span><span class="sxs-lookup"><span data-stu-id="f3bef-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="f3bef-109">The search found the function.</span><span class="sxs-lookup"><span data-stu-id="f3bef-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="f3bef-110">The search did not find the function.</span><span class="sxs-lookup"><span data-stu-id="f3bef-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3bef-111">要求</span><span class="sxs-lookup"><span data-stu-id="f3bef-111">Requirements</span></span>  
 <span data-ttu-id="f3bef-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f3bef-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3bef-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f3bef-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f3bef-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3bef-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3bef-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3bef-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3bef-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3bef-116">See also</span></span>

- [<span data-ttu-id="f3bef-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="f3bef-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
