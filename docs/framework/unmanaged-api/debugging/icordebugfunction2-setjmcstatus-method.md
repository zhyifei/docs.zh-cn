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
ms.openlocfilehash: 7da12554ba1db9a467aa03c01bfb3b584125b129
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213187"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="0806c-102">ICorDebugFunction2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="0806c-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="0806c-103">为仅我的代码步进标记此 ICorDebugFunction2 所表示的函数。</span><span class="sxs-lookup"><span data-stu-id="0806c-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0806c-104">语法</span><span class="sxs-lookup"><span data-stu-id="0806c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0806c-105">参数</span><span class="sxs-lookup"><span data-stu-id="0806c-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="0806c-106">中设置为将 `true` 函数标记为用户代码; 否则设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="0806c-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="0806c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="0806c-107">Return Values</span></span>  
  
|<span data-ttu-id="0806c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0806c-108">HRESULT</span></span>|<span data-ttu-id="0806c-109">描述</span><span class="sxs-lookup"><span data-stu-id="0806c-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0806c-110">已成功标记函数。</span><span class="sxs-lookup"><span data-stu-id="0806c-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="0806c-111">函数无法标记为用户代码，因为无法对其进行调试。</span><span class="sxs-lookup"><span data-stu-id="0806c-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0806c-112">备注</span><span class="sxs-lookup"><span data-stu-id="0806c-112">Remarks</span></span>  
 <span data-ttu-id="0806c-113">仅我的代码分档器将跳过非用户代码。</span><span class="sxs-lookup"><span data-stu-id="0806c-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="0806c-114">用户代码必须是可调试代码的子集。</span><span class="sxs-lookup"><span data-stu-id="0806c-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0806c-115">要求</span><span class="sxs-lookup"><span data-stu-id="0806c-115">Requirements</span></span>  
 <span data-ttu-id="0806c-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0806c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0806c-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0806c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0806c-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0806c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0806c-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0806c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
