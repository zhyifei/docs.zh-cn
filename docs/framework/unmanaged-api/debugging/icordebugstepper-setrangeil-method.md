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
ms.openlocfilehash: 610225708bf990850fce73d6d7ff66c556e24e5d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760601"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="cb8e1-102">ICorDebugStepper::SetRangeIL 方法</span><span class="sxs-lookup"><span data-stu-id="cb8e1-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="cb8e1-103">设置一个值，指定是否调用[icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)传递自变量值相对于本机代码或相对于 Microsoft 中间语言 (MSIL) 代码正在单步执行的方法通过。</span><span class="sxs-lookup"><span data-stu-id="cb8e1-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb8e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb8e1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb8e1-105">参数</span><span class="sxs-lookup"><span data-stu-id="cb8e1-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="cb8e1-106">[in]设置为`true`指定的范围是相对于 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="cb8e1-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="cb8e1-107">设置为`false`指定的范围是相对于本机代码。</span><span class="sxs-lookup"><span data-stu-id="cb8e1-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="cb8e1-108">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="cb8e1-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb8e1-109">要求</span><span class="sxs-lookup"><span data-stu-id="cb8e1-109">Requirements</span></span>  
 <span data-ttu-id="cb8e1-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cb8e1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb8e1-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb8e1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb8e1-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb8e1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb8e1-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb8e1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
