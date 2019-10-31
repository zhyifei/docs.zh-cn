---
title: ICorDebugILFrame::SetIP 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 60273d7cf91be04c5fc3041260e4bb146ce9a45e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095433"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="2510c-102">ICorDebugILFrame::SetIP 方法</span><span class="sxs-lookup"><span data-stu-id="2510c-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="2510c-103">将指令指针设置为 Microsoft 中间语言（MSIL）代码中的指定偏移位置。</span><span class="sxs-lookup"><span data-stu-id="2510c-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2510c-104">语法</span><span class="sxs-lookup"><span data-stu-id="2510c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2510c-105">参数</span><span class="sxs-lookup"><span data-stu-id="2510c-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="2510c-106">MSIL 代码中的偏移位置。</span><span class="sxs-lookup"><span data-stu-id="2510c-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2510c-107">备注</span><span class="sxs-lookup"><span data-stu-id="2510c-107">Remarks</span></span>  
 <span data-ttu-id="2510c-108">对 `SetIP` 的调用会立即使当前线程的所有帧和链无效。</span><span class="sxs-lookup"><span data-stu-id="2510c-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="2510c-109">如果调试器在调用 `SetIP`之后需要帧信息，则它必须执行新的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="2510c-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="2510c-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)将尝试保持堆栈帧处于有效状态。</span><span class="sxs-lookup"><span data-stu-id="2510c-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="2510c-111">但是，即使帧处于有效状态，仍可能会出现一些问题，如未初始化的局部变量。</span><span class="sxs-lookup"><span data-stu-id="2510c-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="2510c-112">调用方负责确保正在运行的程序的一致性。</span><span class="sxs-lookup"><span data-stu-id="2510c-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="2510c-113">在64位平台上，无法将指令指针移出 `catch` 或 `finally` 块。</span><span class="sxs-lookup"><span data-stu-id="2510c-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="2510c-114">如果调用 `SetIP` 以便在64位平台上进行此类移动，则它将返回一个指示失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="2510c-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2510c-115">要求</span><span class="sxs-lookup"><span data-stu-id="2510c-115">Requirements</span></span>  
 <span data-ttu-id="2510c-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2510c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2510c-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2510c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2510c-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2510c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2510c-119">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2510c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
