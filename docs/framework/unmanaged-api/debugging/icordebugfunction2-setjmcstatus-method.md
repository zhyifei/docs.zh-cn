---
title: ICorDebugFunction2::SetJMCStatus 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67959b2ebbfb62b47a1b2a770e278d043fc66d21
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754915"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="366ee-102">ICorDebugFunction2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="366ee-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="366ee-103">将标记为仅我的代码表示通过此 ICorDebugFunction2 函数单步执行。</span><span class="sxs-lookup"><span data-stu-id="366ee-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="366ee-104">语法</span><span class="sxs-lookup"><span data-stu-id="366ee-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="366ee-105">参数</span><span class="sxs-lookup"><span data-stu-id="366ee-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="366ee-106">[in]设置为`true`若要将函数标记为用户代码; 否则，将设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="366ee-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="366ee-107">返回值</span><span class="sxs-lookup"><span data-stu-id="366ee-107">Return Values</span></span>  
  
|<span data-ttu-id="366ee-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="366ee-108">HRESULT</span></span>|<span data-ttu-id="366ee-109">描述</span><span class="sxs-lookup"><span data-stu-id="366ee-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="366ee-110">该函数已成功地标记。</span><span class="sxs-lookup"><span data-stu-id="366ee-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="366ee-111">因为它不能进行调试，该函数可能未标记为用户代码中。</span><span class="sxs-lookup"><span data-stu-id="366ee-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="366ee-112">备注</span><span class="sxs-lookup"><span data-stu-id="366ee-112">Remarks</span></span>  
 <span data-ttu-id="366ee-113">仅我的代码分档器将跳过非用户代码。</span><span class="sxs-lookup"><span data-stu-id="366ee-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="366ee-114">用户代码必须是代码的可调试的子集。</span><span class="sxs-lookup"><span data-stu-id="366ee-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="366ee-115">要求</span><span class="sxs-lookup"><span data-stu-id="366ee-115">Requirements</span></span>  
 <span data-ttu-id="366ee-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="366ee-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="366ee-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="366ee-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="366ee-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="366ee-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="366ee-119">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="366ee-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
