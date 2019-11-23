---
title: COR_PRF_FINALIZER_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_FINALIZER_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FINALIZER_FLAGS
helpviewer_keywords:
- COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type:
- apiref
ms.openlocfilehash: 5e718d05f033cc46fa460a81f6816a13ec32476d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428346"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="52e90-102">COR_PRF_FINALIZER_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="52e90-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="52e90-103">描述对象的终结器。</span><span class="sxs-lookup"><span data-stu-id="52e90-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52e90-104">语法</span><span class="sxs-lookup"><span data-stu-id="52e90-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="52e90-105">Members</span><span class="sxs-lookup"><span data-stu-id="52e90-105">Members</span></span>  
  
|<span data-ttu-id="52e90-106">成员</span><span class="sxs-lookup"><span data-stu-id="52e90-106">Member</span></span>|<span data-ttu-id="52e90-107">描述</span><span class="sxs-lookup"><span data-stu-id="52e90-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="52e90-108">The finalizer is critical.</span><span class="sxs-lookup"><span data-stu-id="52e90-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52e90-109">备注</span><span class="sxs-lookup"><span data-stu-id="52e90-109">Remarks</span></span>  
 <span data-ttu-id="52e90-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span><span class="sxs-lookup"><span data-stu-id="52e90-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52e90-111">要求</span><span class="sxs-lookup"><span data-stu-id="52e90-111">Requirements</span></span>  
 <span data-ttu-id="52e90-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="52e90-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52e90-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52e90-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52e90-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52e90-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52e90-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52e90-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e90-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="52e90-116">See also</span></span>

- [<span data-ttu-id="52e90-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="52e90-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
