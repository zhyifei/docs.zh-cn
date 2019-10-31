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
ms.openlocfilehash: ff393b119c349e34898b781c3185cc82f2dba11f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137555"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="96d16-102">ICorDebugStepper::SetUnmappedStopMask 方法</span><span class="sxs-lookup"><span data-stu-id="96d16-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="96d16-103">设置一个值，该值指定执行过程中将暂停的未映射代码的类型。</span><span class="sxs-lookup"><span data-stu-id="96d16-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d16-104">语法</span><span class="sxs-lookup"><span data-stu-id="96d16-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96d16-105">参数</span><span class="sxs-lookup"><span data-stu-id="96d16-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="96d16-106">中CorDebugUnmappedStop 枚举的一个值，该值指定调试器将在其中暂停执行的未映射代码的类型。</span><span class="sxs-lookup"><span data-stu-id="96d16-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="96d16-107">默认值为 STOP_OTHER_UNMAPPED。</span><span class="sxs-lookup"><span data-stu-id="96d16-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="96d16-108">值 STOP_UNMANAGED 仅适用于互操作调试。</span><span class="sxs-lookup"><span data-stu-id="96d16-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96d16-109">备注</span><span class="sxs-lookup"><span data-stu-id="96d16-109">Remarks</span></span>  
 <span data-ttu-id="96d16-110">当调试器找到了没有对应于 Microsoft 中间语言（MSIL）的映射的实时（JIT）编译时，如果指定该类型的未映射代码的标志已设置，它将暂停执行。否则，单步执行会透明地继续。</span><span class="sxs-lookup"><span data-stu-id="96d16-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="96d16-111">如果调试器不使用分档器来输入方法，则不一定要逐过程执行非映射代码。</span><span class="sxs-lookup"><span data-stu-id="96d16-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96d16-112">要求</span><span class="sxs-lookup"><span data-stu-id="96d16-112">Requirements</span></span>  
 <span data-ttu-id="96d16-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="96d16-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96d16-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96d16-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96d16-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96d16-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96d16-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96d16-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
