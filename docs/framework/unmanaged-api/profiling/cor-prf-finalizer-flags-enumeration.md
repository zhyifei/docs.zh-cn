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
ms.openlocfilehash: daca2849908a7798b588ff06f6e117d412db1b33
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867264"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="2d89b-102">COR_PRF_FINALIZER_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="2d89b-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="2d89b-103">描述对象的终结器。</span><span class="sxs-lookup"><span data-stu-id="2d89b-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d89b-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d89b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="2d89b-105">Members</span><span class="sxs-lookup"><span data-stu-id="2d89b-105">Members</span></span>  
  
|<span data-ttu-id="2d89b-106">成员</span><span class="sxs-lookup"><span data-stu-id="2d89b-106">Member</span></span>|<span data-ttu-id="2d89b-107">描述</span><span class="sxs-lookup"><span data-stu-id="2d89b-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="2d89b-108">终结器至关重要。</span><span class="sxs-lookup"><span data-stu-id="2d89b-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d89b-109">备注</span><span class="sxs-lookup"><span data-stu-id="2d89b-109">Remarks</span></span>  
 <span data-ttu-id="2d89b-110">[ICorProfilerCallback2：： FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md)方法使用 `COR_PRF_FINALIZER_FLAGS` 枚举来描述对象的终结器。</span><span class="sxs-lookup"><span data-stu-id="2d89b-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d89b-111">需求</span><span class="sxs-lookup"><span data-stu-id="2d89b-111">Requirements</span></span>  
 <span data-ttu-id="2d89b-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d89b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d89b-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d89b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d89b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d89b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d89b-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d89b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d89b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d89b-116">See also</span></span>

- [<span data-ttu-id="2d89b-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="2d89b-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
