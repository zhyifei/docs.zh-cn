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
ms.openlocfilehash: 758364b2d63343e464b727d5a1c1817533a6acea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137784"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="9a2f1-102">ICorDebugFunction2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="9a2f1-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="9a2f1-103">为仅我的代码步进标记此 ICorDebugFunction2 所表示的函数。</span><span class="sxs-lookup"><span data-stu-id="9a2f1-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a2f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="9a2f1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a2f1-105">参数</span><span class="sxs-lookup"><span data-stu-id="9a2f1-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="9a2f1-106">中设置为 `true` 将函数标记为用户代码;否则，设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="9a2f1-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="9a2f1-107">返回值</span><span class="sxs-lookup"><span data-stu-id="9a2f1-107">Return Values</span></span>  
  
|<span data-ttu-id="9a2f1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a2f1-108">HRESULT</span></span>|<span data-ttu-id="9a2f1-109">描述</span><span class="sxs-lookup"><span data-stu-id="9a2f1-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9a2f1-110">已成功标记函数。</span><span class="sxs-lookup"><span data-stu-id="9a2f1-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="9a2f1-111">函数无法标记为用户代码，因为无法对其进行调试。</span><span class="sxs-lookup"><span data-stu-id="9a2f1-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a2f1-112">备注</span><span class="sxs-lookup"><span data-stu-id="9a2f1-112">Remarks</span></span>  
 <span data-ttu-id="9a2f1-113">仅我的代码分档器将跳过非用户代码。</span><span class="sxs-lookup"><span data-stu-id="9a2f1-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="9a2f1-114">用户代码必须是可调试代码的子集。</span><span class="sxs-lookup"><span data-stu-id="9a2f1-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a2f1-115">要求</span><span class="sxs-lookup"><span data-stu-id="9a2f1-115">Requirements</span></span>  
 <span data-ttu-id="9a2f1-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9a2f1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a2f1-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a2f1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a2f1-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a2f1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a2f1-119">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a2f1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
