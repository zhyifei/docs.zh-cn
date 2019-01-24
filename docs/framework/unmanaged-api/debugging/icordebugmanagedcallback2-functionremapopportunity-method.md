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
ms.openlocfilehash: 86736f885e40e553195cf2a5f84575a5384e6b60
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564703"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="34236-102">ICorDebugManagedCallback2::FunctionRemapOpportunity 方法</span><span class="sxs-lookup"><span data-stu-id="34236-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="34236-103">通知调试器执行代码已达到已编辑函数的较旧版本中的序列点。</span><span class="sxs-lookup"><span data-stu-id="34236-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34236-104">语法</span><span class="sxs-lookup"><span data-stu-id="34236-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34236-105">参数</span><span class="sxs-lookup"><span data-stu-id="34236-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="34236-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含已编辑的函数的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="34236-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="34236-107">[in]指向一个 ICorDebugThread 对象，表示遇到重新映射断点的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="34236-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="34236-108">[in]指向一个 ICorDebugFunction 对象，表示当前线程运行的函数的版本的指针。</span><span class="sxs-lookup"><span data-stu-id="34236-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="34236-109">[in]指向一个 ICorDebugFunction 对象，表示该函数的最新版本的指针。</span><span class="sxs-lookup"><span data-stu-id="34236-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="34236-110">[in]指令指针中函数的旧版本的 Microsoft 中间语言 (MSIL) 偏移量。</span><span class="sxs-lookup"><span data-stu-id="34236-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34236-111">备注</span><span class="sxs-lookup"><span data-stu-id="34236-111">Remarks</span></span>  
 <span data-ttu-id="34236-112">此回调使调试器能够重新指向其正确的位置指定的函数的新版本的指令指针映射通过调用[ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="34236-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="34236-113">如果调试器不会调用`RemapFunction`之前调用[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)方法中，运行时将继续执行旧代码，并会触发另一个`FunctionRemapOpportunity`回调在下一步的序列点。</span><span class="sxs-lookup"><span data-stu-id="34236-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="34236-114">将为每个帧正在执行给定的函数的较旧版本，直到调试器返回 S_OK 调用该回调。</span><span class="sxs-lookup"><span data-stu-id="34236-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34236-115">要求</span><span class="sxs-lookup"><span data-stu-id="34236-115">Requirements</span></span>  
 <span data-ttu-id="34236-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34236-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34236-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34236-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34236-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34236-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34236-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34236-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34236-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="34236-120">See also</span></span>
- [<span data-ttu-id="34236-121">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="34236-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="34236-122">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="34236-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
