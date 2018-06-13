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
ms.openlocfilehash: c8f4cffd718fffa9145e1082092ecec45b80a2ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451053"
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="5be67-102">COR_PRF_MISC 枚举</span><span class="sxs-lookup"><span data-stu-id="5be67-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="5be67-103">包含指定特殊标识符的常数值。</span><span class="sxs-lookup"><span data-stu-id="5be67-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be67-104">语法</span><span class="sxs-lookup"><span data-stu-id="5be67-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="5be67-105">成员</span><span class="sxs-lookup"><span data-stu-id="5be67-105">Members</span></span>  
  
|<span data-ttu-id="5be67-106">成员</span><span class="sxs-lookup"><span data-stu-id="5be67-106">Member</span></span>|<span data-ttu-id="5be67-107">描述</span><span class="sxs-lookup"><span data-stu-id="5be67-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="5be67-108">使用的默认标识符[icorprofilerinfo:: Getmoduleinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)尚未附加到程序集的模块。</span><span class="sxs-lookup"><span data-stu-id="5be67-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="5be67-109">不属于一个类的全局常量默认类标识符。</span><span class="sxs-lookup"><span data-stu-id="5be67-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="5be67-110">不属于模块的全局对象默认模块标识符。</span><span class="sxs-lookup"><span data-stu-id="5be67-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5be67-111">要求</span><span class="sxs-lookup"><span data-stu-id="5be67-111">Requirements</span></span>  
 <span data-ttu-id="5be67-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5be67-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5be67-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5be67-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5be67-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5be67-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5be67-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5be67-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5be67-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5be67-116">See Also</span></span>  
 [<span data-ttu-id="5be67-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="5be67-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
