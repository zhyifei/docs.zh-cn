---
title: ICorDebugModule2::SetJMCStatus 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: a0b70078dee88b270d8361aa9bddcb7d80df1db1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129475"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="48aa7-102">ICorDebugModule2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="48aa7-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="48aa7-103">将此 ICorDebugModule2 中所有类的所有方法的仅我的代码（JMC）状态设置为指定的值（`pTokens` 数组中的所有方法除外），将其设置为相反值。</span><span class="sxs-lookup"><span data-stu-id="48aa7-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48aa7-104">语法</span><span class="sxs-lookup"><span data-stu-id="48aa7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48aa7-105">参数</span><span class="sxs-lookup"><span data-stu-id="48aa7-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="48aa7-106">中如果要调试代码，则设置为 `true`;否则，设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="48aa7-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="48aa7-107">[in] `pTokens` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="48aa7-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="48aa7-108">中`mdToken` 值的数组，其中每个值都引用将其 JMC 状态设置为的方法！`bIsJustMycode`。</span><span class="sxs-lookup"><span data-stu-id="48aa7-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48aa7-109">备注</span><span class="sxs-lookup"><span data-stu-id="48aa7-109">Remarks</span></span>  
 <span data-ttu-id="48aa7-110">`pTokens` 数组中指定的每个方法的 JMC 状态设置为与 `bIsJustMycode` 值相反。</span><span class="sxs-lookup"><span data-stu-id="48aa7-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="48aa7-111">此模块中所有其他方法的状态将设置为 `bIsJustMycode` 值。</span><span class="sxs-lookup"><span data-stu-id="48aa7-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="48aa7-112">`SetJMCStatus` 方法将清除此模块中的所有以前的 JMC 设置。</span><span class="sxs-lookup"><span data-stu-id="48aa7-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="48aa7-113">如果已成功设置所有函数，则 `SetJMCStatus` 方法返回 S_OK HRESULT。</span><span class="sxs-lookup"><span data-stu-id="48aa7-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="48aa7-114">如果某些标记为 `true` 的函数不可调试，它将返回 CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="48aa7-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48aa7-115">要求</span><span class="sxs-lookup"><span data-stu-id="48aa7-115">Requirements</span></span>  
 <span data-ttu-id="48aa7-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="48aa7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48aa7-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48aa7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48aa7-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48aa7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48aa7-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48aa7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
