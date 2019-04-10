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
ms.openlocfilehash: 3b40ac5f49288f7b30018e0c8c727e3ce6b73ae8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199476"
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="cc16e-102">COR_PRF_MISC 枚举</span><span class="sxs-lookup"><span data-stu-id="cc16e-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="cc16e-103">包含指定特殊标识符的常数值。</span><span class="sxs-lookup"><span data-stu-id="cc16e-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc16e-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc16e-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="cc16e-105">成员</span><span class="sxs-lookup"><span data-stu-id="cc16e-105">Members</span></span>  
  
|<span data-ttu-id="cc16e-106">成员</span><span class="sxs-lookup"><span data-stu-id="cc16e-106">Member</span></span>|<span data-ttu-id="cc16e-107">描述</span><span class="sxs-lookup"><span data-stu-id="cc16e-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="cc16e-108">使用的默认标识符[icorprofilerinfo:: Getmoduleinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)尚未附加到程序集的模块。</span><span class="sxs-lookup"><span data-stu-id="cc16e-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="cc16e-109">默认类不属于类的全局常量的标识符。</span><span class="sxs-lookup"><span data-stu-id="cc16e-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="cc16e-110">不属于一个模块的全局对象的默认模块标识符。</span><span class="sxs-lookup"><span data-stu-id="cc16e-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc16e-111">要求</span><span class="sxs-lookup"><span data-stu-id="cc16e-111">Requirements</span></span>  
 <span data-ttu-id="cc16e-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc16e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc16e-113">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cc16e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cc16e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc16e-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="cc16e-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="cc16e-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cc16e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc16e-116">See also</span></span>

- [<span data-ttu-id="cc16e-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="cc16e-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
