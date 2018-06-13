---
title: ICorDebugManagedCallback2::FunctionRemapOpportunity 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc900ca20ac87ddecfd8f7adf0894af21ca5d2f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418085"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="3707c-102">ICorDebugManagedCallback2::FunctionRemapOpportunity 方法</span><span class="sxs-lookup"><span data-stu-id="3707c-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="3707c-103">通知调试器执行代码已达到经过编辑的函数的早期版本中的序列点。</span><span class="sxs-lookup"><span data-stu-id="3707c-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3707c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3707c-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3707c-105">参数</span><span class="sxs-lookup"><span data-stu-id="3707c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3707c-106">[in]指向一个表示包含编辑过的函数的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="3707c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="3707c-107">[in]指向一个 ICorDebugThread 对象，表示遇到重新映射断点的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="3707c-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="3707c-108">[in]指向一个 ICorDebugFunction 对象，表示在线程当前运行的函数的版本的指针。</span><span class="sxs-lookup"><span data-stu-id="3707c-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="3707c-109">[in]指向一个 ICorDebugFunction 对象，表示函数的最新版本的指针。</span><span class="sxs-lookup"><span data-stu-id="3707c-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="3707c-110">[in]函数的旧版本中的指令指针 Microsoft 中间语言 (MSIL) 偏移量。</span><span class="sxs-lookup"><span data-stu-id="3707c-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3707c-111">备注</span><span class="sxs-lookup"><span data-stu-id="3707c-111">Remarks</span></span>  
 <span data-ttu-id="3707c-112">此回调，调试器能够通过调用重新映射到其正确的位置指定的函数的新版本中的指令指针[icordebugilframe2:: Remapfunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3707c-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="3707c-113">如果调试器不会调用`RemapFunction`之前调用[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)方法，运行时将继续执行的旧代码，并且会触发另一个`FunctionRemapOpportunity`拨到下一个序列点。</span><span class="sxs-lookup"><span data-stu-id="3707c-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="3707c-114">将为每个帧正在执行给定的函数的较旧版本，直到调试器返回，则为 S_OK 调用此回调。</span><span class="sxs-lookup"><span data-stu-id="3707c-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3707c-115">要求</span><span class="sxs-lookup"><span data-stu-id="3707c-115">Requirements</span></span>  
 <span data-ttu-id="3707c-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3707c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3707c-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3707c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3707c-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3707c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3707c-119">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3707c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3707c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="3707c-120">See Also</span></span>  
 [<span data-ttu-id="3707c-121">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="3707c-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="3707c-122">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3707c-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
