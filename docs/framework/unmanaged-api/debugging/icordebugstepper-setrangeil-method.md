---
title: ICorDebugStepper::SetRangeIL 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
ms.openlocfilehash: 7fadffaab6eee5beed513f339ea300acef5a1c6b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378990"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="32e7f-102">ICorDebugStepper::SetRangeIL 方法</span><span class="sxs-lookup"><span data-stu-id="32e7f-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="32e7f-103">设置一个值，该值指定是否对[ICorDebugStepper：： StepRange](icordebugstepper-steprange-method.md)的调用传递与正在逐步执行的方法的本机代码或相对于 Microsoft 中间语言（MSIL）代码的参数值。</span><span class="sxs-lookup"><span data-stu-id="32e7f-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e7f-104">语法</span><span class="sxs-lookup"><span data-stu-id="32e7f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32e7f-105">参数</span><span class="sxs-lookup"><span data-stu-id="32e7f-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="32e7f-106">中如果设置为， `true` 则指定范围是相对于 MSIL 代码的。</span><span class="sxs-lookup"><span data-stu-id="32e7f-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="32e7f-107">设置为， `false` 以指定范围相对于本机代码。</span><span class="sxs-lookup"><span data-stu-id="32e7f-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="32e7f-108">默认值是 `true`。</span><span class="sxs-lookup"><span data-stu-id="32e7f-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32e7f-109">要求</span><span class="sxs-lookup"><span data-stu-id="32e7f-109">Requirements</span></span>  
 <span data-ttu-id="32e7f-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="32e7f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32e7f-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32e7f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32e7f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32e7f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32e7f-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32e7f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
