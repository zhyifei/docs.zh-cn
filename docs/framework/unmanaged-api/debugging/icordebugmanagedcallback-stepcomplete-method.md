---
title: ICorDebugManagedCallback::StepComplete 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
ms.openlocfilehash: e044b1a2ad777868e33cd64bc8d09a9b76d547aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130671"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="499e4-102">ICorDebugManagedCallback::StepComplete 方法</span><span class="sxs-lookup"><span data-stu-id="499e4-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="499e4-103">通知调试器某个步骤已完成。</span><span class="sxs-lookup"><span data-stu-id="499e4-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="499e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="499e4-104">Syntax</span></span>  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="499e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="499e4-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="499e4-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含步骤已完成的线程的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="499e4-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="499e4-107">中指向 ICorDebugThread 对象的指针，该对象表示步骤已完成的线程。</span><span class="sxs-lookup"><span data-stu-id="499e4-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="499e4-108">中指向 ICorDebugStepper 对象的指针，该对象表示代码执行中的步骤。</span><span class="sxs-lookup"><span data-stu-id="499e4-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="499e4-109">中CorDebugStepReason 枚举的值，该值指示单个步骤的结果。</span><span class="sxs-lookup"><span data-stu-id="499e4-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="499e4-110">备注</span><span class="sxs-lookup"><span data-stu-id="499e4-110">Remarks</span></span>  
 <span data-ttu-id="499e4-111">如果需要，可以使用分档器继续单步执行，除非调试已终止。</span><span class="sxs-lookup"><span data-stu-id="499e4-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="499e4-112">要求</span><span class="sxs-lookup"><span data-stu-id="499e4-112">Requirements</span></span>  
 <span data-ttu-id="499e4-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="499e4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="499e4-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="499e4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="499e4-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="499e4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="499e4-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="499e4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="499e4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="499e4-117">See also</span></span>

- [<span data-ttu-id="499e4-118">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="499e4-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
