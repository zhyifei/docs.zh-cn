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
ms.openlocfilehash: b3153a88867d249aad8365bb774348fb8c9d57d5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791754"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="1f14a-102">ICorDebugStepper::SetRangeIL 方法</span><span class="sxs-lookup"><span data-stu-id="1f14a-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="1f14a-103">设置一个值，该值指定是否对[ICorDebugStepper：： StepRange](icordebugstepper-steprange-method.md)的调用传递与正在逐步执行的方法的本机代码或相对于 Microsoft 中间语言（MSIL）代码的参数值。</span><span class="sxs-lookup"><span data-stu-id="1f14a-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f14a-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f14a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f14a-105">参数</span><span class="sxs-lookup"><span data-stu-id="1f14a-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="1f14a-106">中设置为 "`true`" 指定范围相对于 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="1f14a-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="1f14a-107">设置为 "`false`" 指定范围相对于本机代码。</span><span class="sxs-lookup"><span data-stu-id="1f14a-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="1f14a-108">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="1f14a-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f14a-109">需求</span><span class="sxs-lookup"><span data-stu-id="1f14a-109">Requirements</span></span>  
 <span data-ttu-id="1f14a-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1f14a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f14a-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f14a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f14a-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f14a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f14a-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f14a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
