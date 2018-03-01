---
title: "ICorProfilerCallback::UnmanagedToManagedTransition 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1653a92563f0031fcb4c215dd58e4e1ac73030d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="52633-102">ICorProfilerCallback::UnmanagedToManagedTransition 方法</span><span class="sxs-lookup"><span data-stu-id="52633-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="52633-103">通知探查器发生从非托管代码转换为托管代码。</span><span class="sxs-lookup"><span data-stu-id="52633-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52633-104">语法</span><span class="sxs-lookup"><span data-stu-id="52633-104">Syntax</span></span>  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52633-105">参数</span><span class="sxs-lookup"><span data-stu-id="52633-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="52633-106">[in]正在调用的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="52633-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="52633-107">[in]值为[COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)枚举，指示转换是否发生从非托管代码到托管代码的调用由于或由于从一个托管由调用非托管函数返回。</span><span class="sxs-lookup"><span data-stu-id="52633-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52633-108">备注</span><span class="sxs-lookup"><span data-stu-id="52633-108">Remarks</span></span>  
 <span data-ttu-id="52633-109">如果值`reason`是 COR_PRF_TRANSITION_RETURN 和`functionId`不为 null 的函数 ID 的非托管函数，并将永远不会编译使用实时 (JIT) 编译器。</span><span class="sxs-lookup"><span data-stu-id="52633-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="52633-110">非托管的函数具有与它们，如名称和一些元数据的一些基本信息。</span><span class="sxs-lookup"><span data-stu-id="52633-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="52633-111">如果值`reason`是 COR_PRF_TRANSITION_CALL，有可能，所调用的函数 （即，托管函数） 尚未 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="52633-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52633-112">惠?</span><span class="sxs-lookup"><span data-stu-id="52633-112">Requirements</span></span>  
 <span data-ttu-id="52633-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="52633-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52633-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52633-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52633-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52633-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52633-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52633-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52633-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="52633-117">See Also</span></span>  
 [<span data-ttu-id="52633-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="52633-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="52633-119">ManagedToUnmanagedTransition 方法</span><span class="sxs-lookup"><span data-stu-id="52633-119">ManagedToUnmanagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)  
 [<span data-ttu-id="52633-120">在 C++ 中使用显式 PInvoke（DllImport 特性）</span><span class="sxs-lookup"><span data-stu-id="52633-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)  
 [<span data-ttu-id="52633-121">使用 C++ 互操作（隐式 PInvoke）</span><span class="sxs-lookup"><span data-stu-id="52633-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
