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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c22e3c7c04a2b85723f1c0dba4543465faccab58
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745494"
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="d26a0-102">COR_PRF_TRANSITION_REASON 枚举</span><span class="sxs-lookup"><span data-stu-id="d26a0-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="d26a0-103">指示从托管代码向非托管代码转换或从非托管代码向托管代码转换的原因。</span><span class="sxs-lookup"><span data-stu-id="d26a0-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d26a0-104">语法</span><span class="sxs-lookup"><span data-stu-id="d26a0-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="d26a0-105">成员</span><span class="sxs-lookup"><span data-stu-id="d26a0-105">Members</span></span>  
  
|<span data-ttu-id="d26a0-106">成员</span><span class="sxs-lookup"><span data-stu-id="d26a0-106">Member</span></span>|<span data-ttu-id="d26a0-107">描述</span><span class="sxs-lookup"><span data-stu-id="d26a0-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="d26a0-108">转换是由于执行某一函数的调用。</span><span class="sxs-lookup"><span data-stu-id="d26a0-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="d26a0-109">转换是由于从函数返回。</span><span class="sxs-lookup"><span data-stu-id="d26a0-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d26a0-110">备注</span><span class="sxs-lookup"><span data-stu-id="d26a0-110">Remarks</span></span>  
 <span data-ttu-id="d26a0-111">在探查器时，将发生转换，接收[icorprofilercallback:: Managedtounmanagedtransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)或[icorprofilercallback:: Unmanagedtomanagedtransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)回调，其中任一提供的值为`COR_PRF_TRANSITION_REASON`枚举来指示转换的原因。</span><span class="sxs-lookup"><span data-stu-id="d26a0-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d26a0-112">要求</span><span class="sxs-lookup"><span data-stu-id="d26a0-112">Requirements</span></span>  
 <span data-ttu-id="d26a0-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d26a0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d26a0-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d26a0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d26a0-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d26a0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d26a0-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d26a0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
