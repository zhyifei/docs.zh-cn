---
title: "COR_PRF_TRANSITION_REASON 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_TRANSITION_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_TRANSITION_REASON
helpviewer_keywords: COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 498abc57e35946b2b0c8bf08cdd768bd7039c9f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="a2170-102">COR_PRF_TRANSITION_REASON 枚举</span><span class="sxs-lookup"><span data-stu-id="a2170-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="a2170-103">指示从托管代码向非托管代码转换或从非托管代码向托管代码转换的原因。</span><span class="sxs-lookup"><span data-stu-id="a2170-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2170-104">语法</span><span class="sxs-lookup"><span data-stu-id="a2170-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="a2170-105">成员</span><span class="sxs-lookup"><span data-stu-id="a2170-105">Members</span></span>  
  
|<span data-ttu-id="a2170-106">成员</span><span class="sxs-lookup"><span data-stu-id="a2170-106">Member</span></span>|<span data-ttu-id="a2170-107">描述</span><span class="sxs-lookup"><span data-stu-id="a2170-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="a2170-108">转换是由于到函数的调用。</span><span class="sxs-lookup"><span data-stu-id="a2170-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="a2170-109">转换是由于从函数返回。</span><span class="sxs-lookup"><span data-stu-id="a2170-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2170-110">备注</span><span class="sxs-lookup"><span data-stu-id="a2170-110">Remarks</span></span>  
 <span data-ttu-id="a2170-111">在探查器时，将发生转换，接收[icorprofilercallback:: Managedtounmanagedtransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)或[icorprofilercallback:: Unmanagedtomanagedtransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)回调，其中任一提供的值`COR_PRF_TRANSITION_REASON`枚举，以指示转换的原因。</span><span class="sxs-lookup"><span data-stu-id="a2170-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2170-112">惠?</span><span class="sxs-lookup"><span data-stu-id="a2170-112">Requirements</span></span>  
 <span data-ttu-id="a2170-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2170-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2170-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a2170-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a2170-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2170-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2170-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2170-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
