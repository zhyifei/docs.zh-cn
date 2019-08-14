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
ms.openlocfilehash: c616cb45eadab3a55aa76526d530cb2841e6d5fa
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974107"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="c2d85-102">COR_PRF_REJIT_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="c2d85-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="c2d85-103">包含指示[ICorProfilerInfo10:: RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) API 应如何运行的值。</span><span class="sxs-lookup"><span data-stu-id="c2d85-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2d85-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2d85-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c2d85-105">成员</span><span class="sxs-lookup"><span data-stu-id="c2d85-105">Members</span></span>  
  
|<span data-ttu-id="c2d85-106">成员</span><span class="sxs-lookup"><span data-stu-id="c2d85-106">Member</span></span>|<span data-ttu-id="c2d85-107">描述</span><span class="sxs-lookup"><span data-stu-id="c2d85-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="c2d85-108">将阻止在其他方法中内联 ReJITted 方法。</span><span class="sxs-lookup"><span data-stu-id="c2d85-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="c2d85-109">为`GetFunctionParameters`内联方法请求 ReJITted 的任何方法接收回调。</span><span class="sxs-lookup"><span data-stu-id="c2d85-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="c2d85-110">要求</span><span class="sxs-lookup"><span data-stu-id="c2d85-110">Requirements</span></span>  
 <span data-ttu-id="c2d85-111">**适用**请参阅[支持 .Net Core 的操作系统](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)。</span><span class="sxs-lookup"><span data-stu-id="c2d85-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="c2d85-112">**标头：** Corprof.idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="c2d85-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2d85-113">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2d85-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2d85-114">**.NET Framework 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2d85-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c2d85-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2d85-115">See also</span></span>

- [<span data-ttu-id="c2d85-116">分析枚举</span><span class="sxs-lookup"><span data-stu-id="c2d85-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
