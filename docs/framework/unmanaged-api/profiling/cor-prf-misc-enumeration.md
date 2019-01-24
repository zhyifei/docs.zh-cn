---
title: COR_PRF_MISC 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11b36fa4636dd55e539c198a260dcf93da02a237
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728955"
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="2c29d-102">COR_PRF_MISC 枚举</span><span class="sxs-lookup"><span data-stu-id="2c29d-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="2c29d-103">包含指定特殊标识符的常数值。</span><span class="sxs-lookup"><span data-stu-id="2c29d-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c29d-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c29d-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="2c29d-105">成员</span><span class="sxs-lookup"><span data-stu-id="2c29d-105">Members</span></span>  
  
|<span data-ttu-id="2c29d-106">成员</span><span class="sxs-lookup"><span data-stu-id="2c29d-106">Member</span></span>|<span data-ttu-id="2c29d-107">描述</span><span class="sxs-lookup"><span data-stu-id="2c29d-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="2c29d-108">使用的默认标识符[icorprofilerinfo:: Getmoduleinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)尚未附加到程序集的模块。</span><span class="sxs-lookup"><span data-stu-id="2c29d-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="2c29d-109">默认类不属于类的全局常量的标识符。</span><span class="sxs-lookup"><span data-stu-id="2c29d-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="2c29d-110">不属于一个模块的全局对象的默认模块标识符。</span><span class="sxs-lookup"><span data-stu-id="2c29d-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c29d-111">要求</span><span class="sxs-lookup"><span data-stu-id="2c29d-111">Requirements</span></span>  
 <span data-ttu-id="2c29d-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c29d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c29d-113">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c29d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c29d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c29d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c29d-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c29d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c29d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c29d-116">See also</span></span>
- [<span data-ttu-id="2c29d-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="2c29d-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
