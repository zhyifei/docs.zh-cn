---
title: "ICorDebugILFrame::SetIP 方法"
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
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: daffbbd9e961f4fdc7ff2e3c9be57e41e8fa3f78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="6409d-102">ICorDebugILFrame::SetIP 方法</span><span class="sxs-lookup"><span data-stu-id="6409d-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="6409d-103">将指令指针设置为 Microsoft 中间语言 (MSIL) 代码中的指定偏移位置。</span><span class="sxs-lookup"><span data-stu-id="6409d-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6409d-104">语法</span><span class="sxs-lookup"><span data-stu-id="6409d-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6409d-105">参数</span><span class="sxs-lookup"><span data-stu-id="6409d-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="6409d-106">中的 MSIL 代码的偏移的位置。</span><span class="sxs-lookup"><span data-stu-id="6409d-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6409d-107">备注</span><span class="sxs-lookup"><span data-stu-id="6409d-107">Remarks</span></span>  
 <span data-ttu-id="6409d-108">调用`SetIP`立即使所有帧和当前线程的链都无效。</span><span class="sxs-lookup"><span data-stu-id="6409d-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="6409d-109">如果调试器需要后调用的帧信息`SetIP`，则必须执行新的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="6409d-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="6409d-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)将尝试保留堆栈帧中的有效状态。</span><span class="sxs-lookup"><span data-stu-id="6409d-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="6409d-111">但是，即使的框架是处于有效状态，仍可能有问题，如未初始化的局部变量。</span><span class="sxs-lookup"><span data-stu-id="6409d-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="6409d-112">调用方负责确保正在运行的程序的一致性。</span><span class="sxs-lookup"><span data-stu-id="6409d-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="6409d-113">在 64 位平台上的指令指针不能移动外`catch`或`finally`块。</span><span class="sxs-lookup"><span data-stu-id="6409d-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="6409d-114">如果`SetIP`称为若要使此类移动在 64 位平台上的，它将返回 HRESULT，指示失败。</span><span class="sxs-lookup"><span data-stu-id="6409d-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6409d-115">惠?</span><span class="sxs-lookup"><span data-stu-id="6409d-115">Requirements</span></span>  
 <span data-ttu-id="6409d-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6409d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6409d-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6409d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6409d-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6409d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6409d-119">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6409d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
