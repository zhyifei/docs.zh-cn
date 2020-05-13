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
ms.openlocfilehash: d2fc59621cbb6752830c7a8392ce4e0c476ef9e7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210054"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="fe660-102">ICorDebugManagedCallback2::FunctionRemapOpportunity 方法</span><span class="sxs-lookup"><span data-stu-id="fe660-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="fe660-103">通知调试程序代码执行已到达已编辑函数的较早版本中的序列点。</span><span class="sxs-lookup"><span data-stu-id="fe660-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe660-104">语法</span><span class="sxs-lookup"><span data-stu-id="fe660-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe660-105">参数</span><span class="sxs-lookup"><span data-stu-id="fe660-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fe660-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含已编辑函数的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="fe660-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="fe660-107">中指向 ICorDebugThread 对象的指针，该对象表示遇到重新映射断点的线程。</span><span class="sxs-lookup"><span data-stu-id="fe660-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="fe660-108">中指向 ICorDebugFunction 对象的指针，该对象表示线程上当前正在运行的函数的版本。</span><span class="sxs-lookup"><span data-stu-id="fe660-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="fe660-109">中指向 ICorDebugFunction 对象的指针，该对象表示函数的最新版本。</span><span class="sxs-lookup"><span data-stu-id="fe660-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="fe660-110">中函数的旧版本中指令指针的 Microsoft 中间语言（MSIL）偏移量。</span><span class="sxs-lookup"><span data-stu-id="fe660-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe660-111">备注</span><span class="sxs-lookup"><span data-stu-id="fe660-111">Remarks</span></span>  
 <span data-ttu-id="fe660-112">此回调使调试器有机会通过调用[ICorDebugILFrame2：： RemapFunction](icordebugilframe2-remapfunction-method.md)方法将指令指针重新映射到指定函数的新版本中的适当位置。</span><span class="sxs-lookup"><span data-stu-id="fe660-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="fe660-113">如果在 `RemapFunction` 调用[ICorDebugController：： Continue](icordebugcontroller-continue-method.md)方法之前调试器未调用，则运行时将继续执行旧代码，并将 `FunctionRemapOpportunity` 在下一个序列点触发另一个回调。</span><span class="sxs-lookup"><span data-stu-id="fe660-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="fe660-114">对于正在执行旧版本给定函数的每个帧，将调用此回调，直到调试器返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="fe660-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe660-115">要求</span><span class="sxs-lookup"><span data-stu-id="fe660-115">Requirements</span></span>  
 <span data-ttu-id="fe660-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe660-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe660-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe660-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe660-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe660-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe660-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe660-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe660-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe660-120">See also</span></span>

- [<span data-ttu-id="fe660-121">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="fe660-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="fe660-122">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="fe660-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
