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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9b4ee64022374cb4e1950acceb3f32925b736bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994278"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="c39de-102">ICorDebugStepper::SetRangeIL 方法</span><span class="sxs-lookup"><span data-stu-id="c39de-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="c39de-103">设置一个值，指定是否调用[icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)传递自变量值相对于本机代码或相对于 Microsoft 中间语言 (MSIL) 代码正在单步执行的方法通过。</span><span class="sxs-lookup"><span data-stu-id="c39de-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c39de-104">语法</span><span class="sxs-lookup"><span data-stu-id="c39de-104">Syntax</span></span>  
  
```  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c39de-105">参数</span><span class="sxs-lookup"><span data-stu-id="c39de-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="c39de-106">[in]设置为`true`指定的范围是相对于 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="c39de-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="c39de-107">设置为`false`指定的范围是相对于本机代码。</span><span class="sxs-lookup"><span data-stu-id="c39de-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="c39de-108">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="c39de-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c39de-109">要求</span><span class="sxs-lookup"><span data-stu-id="c39de-109">Requirements</span></span>  
 <span data-ttu-id="c39de-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c39de-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c39de-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c39de-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c39de-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c39de-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c39de-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c39de-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
