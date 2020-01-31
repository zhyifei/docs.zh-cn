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
ms.openlocfilehash: fe27c0fca6d38b4cff6cac2b9778cf2be68903a3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867121"
---
# <a name="cor_prf_misc-enumeration"></a><span data-ttu-id="5a488-102">COR_PRF_MISC 枚举</span><span class="sxs-lookup"><span data-stu-id="5a488-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="5a488-103">包含指定特殊标识符的常数值。</span><span class="sxs-lookup"><span data-stu-id="5a488-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a488-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a488-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="5a488-105">Members</span><span class="sxs-lookup"><span data-stu-id="5a488-105">Members</span></span>  
  
|<span data-ttu-id="5a488-106">成员</span><span class="sxs-lookup"><span data-stu-id="5a488-106">Member</span></span>|<span data-ttu-id="5a488-107">描述</span><span class="sxs-lookup"><span data-stu-id="5a488-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="5a488-108">[ICorProfilerInfo：： GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md)用于尚未附加到程序集的模块的默认标识符。</span><span class="sxs-lookup"><span data-stu-id="5a488-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="5a488-109">不属于类的全局常数的默认类标识符。</span><span class="sxs-lookup"><span data-stu-id="5a488-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="5a488-110">不属于模块的全局对象的默认模块标识符。</span><span class="sxs-lookup"><span data-stu-id="5a488-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a488-111">需求</span><span class="sxs-lookup"><span data-stu-id="5a488-111">Requirements</span></span>  
 <span data-ttu-id="5a488-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5a488-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a488-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a488-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a488-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a488-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a488-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a488-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a488-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a488-116">See also</span></span>

- [<span data-ttu-id="5a488-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="5a488-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
