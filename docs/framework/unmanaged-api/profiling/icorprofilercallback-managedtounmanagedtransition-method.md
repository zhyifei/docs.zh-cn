---
title: ICorProfilerCallback::ManagedToUnmanagedTransition 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b00394d0b08e7e4a02b95437908dd65a51d0a042
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084604"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="3ccb2-102">ICorProfilerCallback::ManagedToUnmanagedTransition 方法</span><span class="sxs-lookup"><span data-stu-id="3ccb2-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="3ccb2-103">通知探查器已发生从托管代码到非托管代码的转换。</span><span class="sxs-lookup"><span data-stu-id="3ccb2-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ccb2-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ccb2-104">Syntax</span></span>  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ccb2-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ccb2-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="3ccb2-106">[in]正在调用的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="3ccb2-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="3ccb2-107">[in]值为[COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)指示转换是否发生了由于存在从托管代码到非托管代码的调用或由于从托管函数调用的非托管一个返回的枚举。</span><span class="sxs-lookup"><span data-stu-id="3ccb2-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ccb2-108">备注</span><span class="sxs-lookup"><span data-stu-id="3ccb2-108">Remarks</span></span>  
 <span data-ttu-id="3ccb2-109">如果的值`reason`是 COR_PRF_TRANSITION_CALL，ID 是的非托管函数中，将永远不会已编译的使用中实时编译器该函数。</span><span class="sxs-lookup"><span data-stu-id="3ccb2-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="3ccb2-110">非托管的函数具有与它们，如名称和一些元数据相关联的基本信息。</span><span class="sxs-lookup"><span data-stu-id="3ccb2-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="3ccb2-111">如果通过使用隐式平台调用非托管的函数调用 (PInvoke)，运行时调用的目标和的值不能确定`functionId`将为 null。</span><span class="sxs-lookup"><span data-stu-id="3ccb2-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="3ccb2-112">有关隐式 PInvoke 的详细信息，请参阅[使用C++互操作 (隐式 PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)。</span><span class="sxs-lookup"><span data-stu-id="3ccb2-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ccb2-113">要求</span><span class="sxs-lookup"><span data-stu-id="3ccb2-113">Requirements</span></span>  
 <span data-ttu-id="3ccb2-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ccb2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ccb2-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ccb2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ccb2-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ccb2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ccb2-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ccb2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ccb2-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ccb2-118">See also</span></span>

- [<span data-ttu-id="3ccb2-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3ccb2-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="3ccb2-120">UnmanagedToManagedTransition 方法</span><span class="sxs-lookup"><span data-stu-id="3ccb2-120">UnmanagedToManagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [<span data-ttu-id="3ccb2-121">在 C++ 中使用显式 PInvoke（DllImport 特性）</span><span class="sxs-lookup"><span data-stu-id="3ccb2-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
