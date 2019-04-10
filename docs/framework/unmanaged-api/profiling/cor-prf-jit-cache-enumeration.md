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
ms.openlocfilehash: 0cdbe36403f830926d611ffdc655d82ea25ddeef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144789"
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="3ed3e-102">COR_PRF_JIT_CACHE 枚举</span><span class="sxs-lookup"><span data-stu-id="3ed3e-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="3ed3e-103">指示缓存的函数搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="3ed3e-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  `COR_PRF_CACHED_FUNCTION_FOUND` <span data-ttu-id="3ed3e-104">具有值为零，因此`COR_PRF_JIT_CACHE`不能用作布尔代理项。</span><span class="sxs-lookup"><span data-stu-id="3ed3e-104">has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ed3e-105">语法</span><span class="sxs-lookup"><span data-stu-id="3ed3e-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="3ed3e-106">成员</span><span class="sxs-lookup"><span data-stu-id="3ed3e-106">Members</span></span>  
  
|<span data-ttu-id="3ed3e-107">成员</span><span class="sxs-lookup"><span data-stu-id="3ed3e-107">Member</span></span>|<span data-ttu-id="3ed3e-108">描述</span><span class="sxs-lookup"><span data-stu-id="3ed3e-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="3ed3e-109">搜索找到该函数。</span><span class="sxs-lookup"><span data-stu-id="3ed3e-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="3ed3e-110">搜索未找到该函数。</span><span class="sxs-lookup"><span data-stu-id="3ed3e-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ed3e-111">要求</span><span class="sxs-lookup"><span data-stu-id="3ed3e-111">Requirements</span></span>  
 <span data-ttu-id="3ed3e-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ed3e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ed3e-113">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ed3e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ed3e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ed3e-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3ed3e-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3ed3e-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3ed3e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ed3e-116">See also</span></span>

- [<span data-ttu-id="3ed3e-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="3ed3e-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
