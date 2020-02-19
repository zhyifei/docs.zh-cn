---
title: COR_PRF_REJIT_FLAGS 枚举
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: 3b4f85072b9dcf87d696b979fa6cbf4e59393f82
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453034"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="b42c3-102">COR_PRF_REJIT_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="b42c3-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="b42c3-103">包含指示[ICorProfilerInfo10：： RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API 应如何运行的值。</span><span class="sxs-lookup"><span data-stu-id="b42c3-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b42c3-104">语法</span><span class="sxs-lookup"><span data-stu-id="b42c3-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="b42c3-105">Members</span><span class="sxs-lookup"><span data-stu-id="b42c3-105">Members</span></span>  
  
|<span data-ttu-id="b42c3-106">成员</span><span class="sxs-lookup"><span data-stu-id="b42c3-106">Member</span></span>|<span data-ttu-id="b42c3-107">说明</span><span class="sxs-lookup"><span data-stu-id="b42c3-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="b42c3-108">将阻止在其他方法中内联 ReJITted 方法。</span><span class="sxs-lookup"><span data-stu-id="b42c3-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="b42c3-109">为内联 ReJITted 请求的方法的任何方法接收 `GetFunctionParameters` 回调。</span><span class="sxs-lookup"><span data-stu-id="b42c3-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="b42c3-110">要求</span><span class="sxs-lookup"><span data-stu-id="b42c3-110">Requirements</span></span>  
 <span data-ttu-id="b42c3-111">**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="b42c3-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="b42c3-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b42c3-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b42c3-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b42c3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b42c3-114">**.NET Framework 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b42c3-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b42c3-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b42c3-115">See also</span></span>

- [<span data-ttu-id="b42c3-116">分析枚举</span><span class="sxs-lookup"><span data-stu-id="b42c3-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
