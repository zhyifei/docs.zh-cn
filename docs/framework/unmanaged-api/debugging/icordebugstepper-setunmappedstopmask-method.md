---
title: ICorDebugStepper::SetUnmappedStopMask 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da799b0d4f4e5e4b281445baa35d95f992ba0b63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987449"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="c6f55-102">ICorDebugStepper::SetUnmappedStopMask 方法</span><span class="sxs-lookup"><span data-stu-id="c6f55-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="c6f55-103">设置一个值，指定在其中执行都将停止的代码未映射的类型。</span><span class="sxs-lookup"><span data-stu-id="c6f55-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f55-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6f55-104">Syntax</span></span>  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6f55-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6f55-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="c6f55-106">[in]CorDebugUnmappedStop 枚举，用于指定在其中调试程序将终止执行的代码未映射的类型的值。</span><span class="sxs-lookup"><span data-stu-id="c6f55-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="c6f55-107">默认值为 STOP_OTHER_UNMAPPED。</span><span class="sxs-lookup"><span data-stu-id="c6f55-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="c6f55-108">STOP_UNMANAGED 的值才有效，且互操作调试。</span><span class="sxs-lookup"><span data-stu-id="c6f55-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6f55-109">备注</span><span class="sxs-lookup"><span data-stu-id="c6f55-109">Remarks</span></span>  
 <span data-ttu-id="c6f55-110">当调试器发现没有对应到 Microsoft 中间语言 (MSIL) 映射中实时 (JIT) 编译时，它暂停执行，如果已设置标志，指定该类型的非托管代码;否则，以透明方式单步执行将继续。</span><span class="sxs-lookup"><span data-stu-id="c6f55-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="c6f55-111">如果调试器不使用分档器输入一个方法，它不一定是逐未映射代码。</span><span class="sxs-lookup"><span data-stu-id="c6f55-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6f55-112">要求</span><span class="sxs-lookup"><span data-stu-id="c6f55-112">Requirements</span></span>  
 <span data-ttu-id="c6f55-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6f55-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6f55-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6f55-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6f55-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6f55-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6f55-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6f55-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
