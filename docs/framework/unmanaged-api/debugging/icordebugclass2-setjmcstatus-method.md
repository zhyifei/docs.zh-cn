---
title: ICorDebugClass2::SetJMCStatus 方法
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: a862dd3f6a9c10c6b3a5a0bb41208d351c4ca9f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125689"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="89ebb-102">ICorDebugClass2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="89ebb-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="89ebb-103">对于类的每个方法，设置一个值，该值指示该方法是否为用户定义的代码。</span><span class="sxs-lookup"><span data-stu-id="89ebb-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89ebb-104">语法</span><span class="sxs-lookup"><span data-stu-id="89ebb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89ebb-105">参数</span><span class="sxs-lookup"><span data-stu-id="89ebb-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="89ebb-106">中设置为 `true` 以指示该方法是用户定义的代码;否则，设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="89ebb-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89ebb-107">备注</span><span class="sxs-lookup"><span data-stu-id="89ebb-107">Remarks</span></span>  
 <span data-ttu-id="89ebb-108">仅我的代码（JMC）分档器将跳过非用户定义的代码。</span><span class="sxs-lookup"><span data-stu-id="89ebb-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="89ebb-109">用户定义的代码必须是可调试代码的子集。</span><span class="sxs-lookup"><span data-stu-id="89ebb-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="89ebb-110">如果为任何方法设置了值，则 `SetJMCStatus` 返回 S_FALSE 值 S_FALSE，即使它成功设置了所有其他方法的值也是如此。</span><span class="sxs-lookup"><span data-stu-id="89ebb-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89ebb-111">要求</span><span class="sxs-lookup"><span data-stu-id="89ebb-111">Requirements</span></span>  
 <span data-ttu-id="89ebb-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89ebb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89ebb-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89ebb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89ebb-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89ebb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89ebb-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89ebb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
