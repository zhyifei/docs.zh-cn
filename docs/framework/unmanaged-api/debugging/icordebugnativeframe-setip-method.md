---
title: ICorDebugNativeFrame::SetIP 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 604486a074c3dbe3d19b741df28499ee03e1b2e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193273"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="da7b5-102">ICorDebugNativeFrame::SetIP 方法</span><span class="sxs-lookup"><span data-stu-id="da7b5-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="da7b5-103">在本机代码中，指令指针设置为指定的偏移量位置。</span><span class="sxs-lookup"><span data-stu-id="da7b5-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da7b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="da7b5-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da7b5-105">参数</span><span class="sxs-lookup"><span data-stu-id="da7b5-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="da7b5-106">[in]本机代码中的偏移量的位置。</span><span class="sxs-lookup"><span data-stu-id="da7b5-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da7b5-107">备注</span><span class="sxs-lookup"><span data-stu-id="da7b5-107">Remarks</span></span>  
 <span data-ttu-id="da7b5-108">调用`SetIP`立即使所有帧和当前线程的链都无效。</span><span class="sxs-lookup"><span data-stu-id="da7b5-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="da7b5-109">如果调试器需要后调用的帧信息`SetIP`，则必须执行新的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="da7b5-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="da7b5-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)将尝试在有效状态中保留的堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="da7b5-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="da7b5-111">但是，即使在帧处于有效状态，就而言，运行时，仍可能有问题，例如未初始化的局部变量，依次类推。</span><span class="sxs-lookup"><span data-stu-id="da7b5-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="da7b5-112">调用方负责确保正在运行的程序的一致性。</span><span class="sxs-lookup"><span data-stu-id="da7b5-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="da7b5-113">在 64 位平台上不能共移动指令指针`catch`或`finally`块。</span><span class="sxs-lookup"><span data-stu-id="da7b5-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="da7b5-114">如果`SetIP`称为若要使这种移动 64 位平台上的，它将返回一个 HRESULT，指示失败。</span><span class="sxs-lookup"><span data-stu-id="da7b5-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da7b5-115">要求</span><span class="sxs-lookup"><span data-stu-id="da7b5-115">Requirements</span></span>  
 <span data-ttu-id="da7b5-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="da7b5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da7b5-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da7b5-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da7b5-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da7b5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da7b5-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da7b5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da7b5-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="da7b5-120">See also</span></span>
