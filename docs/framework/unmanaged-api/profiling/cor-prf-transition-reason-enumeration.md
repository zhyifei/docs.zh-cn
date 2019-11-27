---
title: COR_PRF_TRANSITION_REASON 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_TRANSITION_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_TRANSITION_REASON
helpviewer_keywords:
- COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type:
- apiref
ms.openlocfilehash: 6d8b408675127cde399a8346f2b9734a0e038cb5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427137"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="07d48-102">COR_PRF_TRANSITION_REASON 枚举</span><span class="sxs-lookup"><span data-stu-id="07d48-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="07d48-103">指示从托管代码向非托管代码转换或从非托管代码向托管代码转换的原因。</span><span class="sxs-lookup"><span data-stu-id="07d48-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07d48-104">语法</span><span class="sxs-lookup"><span data-stu-id="07d48-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="07d48-105">Members</span><span class="sxs-lookup"><span data-stu-id="07d48-105">Members</span></span>  
  
|<span data-ttu-id="07d48-106">成员</span><span class="sxs-lookup"><span data-stu-id="07d48-106">Member</span></span>|<span data-ttu-id="07d48-107">说明</span><span class="sxs-lookup"><span data-stu-id="07d48-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="07d48-108">由于调用了函数，因此转换。</span><span class="sxs-lookup"><span data-stu-id="07d48-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="07d48-109">由于从函数返回，因此转换。</span><span class="sxs-lookup"><span data-stu-id="07d48-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07d48-110">备注</span><span class="sxs-lookup"><span data-stu-id="07d48-110">Remarks</span></span>  
 <span data-ttu-id="07d48-111">发生转换时，探查器会接收[ICorProfilerCallback：： ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)或[ICorProfilerCallback：： UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)回调，其中的任何一个都提供 `COR_PRF_TRANSITION_REASON` 枚举的值，以指示转换的原因。</span><span class="sxs-lookup"><span data-stu-id="07d48-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07d48-112">要求</span><span class="sxs-lookup"><span data-stu-id="07d48-112">Requirements</span></span>  
 <span data-ttu-id="07d48-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07d48-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07d48-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="07d48-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07d48-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07d48-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07d48-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07d48-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
