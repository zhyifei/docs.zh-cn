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
ms.openlocfilehash: dc4e51ec60c7526f36bbe4909bec91a527e0862c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419905"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="2e54d-102">ICorDebugStepper::SetUnmappedStopMask 方法</span><span class="sxs-lookup"><span data-stu-id="2e54d-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="2e54d-103">设置一个值，指定的顺序，则执行将暂停的非托管代码的类型。</span><span class="sxs-lookup"><span data-stu-id="2e54d-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e54d-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e54d-104">Syntax</span></span>  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e54d-105">参数</span><span class="sxs-lookup"><span data-stu-id="2e54d-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="2e54d-106">[in]CorDebugUnmappedStop 枚举，指定的顺序，则调试器将暂停执行的非托管代码的类型的值。</span><span class="sxs-lookup"><span data-stu-id="2e54d-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="2e54d-107">默认值为 STOP_OTHER_UNMAPPED。</span><span class="sxs-lookup"><span data-stu-id="2e54d-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="2e54d-108">STOP_UNMANAGED 的值才有效，且互操作调试。</span><span class="sxs-lookup"><span data-stu-id="2e54d-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e54d-109">备注</span><span class="sxs-lookup"><span data-stu-id="2e54d-109">Remarks</span></span>  
 <span data-ttu-id="2e54d-110">当调试器发现没有相应 Microsoft 中间语言 (MSIL) 到映射中实时 (JIT) 编译时，它可以暂停执行，如果已设置标志，指定该类型的非托管代码;否则，继续单步以透明方式执行。</span><span class="sxs-lookup"><span data-stu-id="2e54d-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="2e54d-111">如果调试器未使用分档器输入的方法，然后它将不一定逐过程执行未映射代码。</span><span class="sxs-lookup"><span data-stu-id="2e54d-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e54d-112">要求</span><span class="sxs-lookup"><span data-stu-id="2e54d-112">Requirements</span></span>  
 <span data-ttu-id="2e54d-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e54d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e54d-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e54d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e54d-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e54d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e54d-116">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e54d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
