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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d20c640d6a6a43b7bde4c7d46df470c7bc8c5aa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942501"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="b6d3a-102">ICorDebugModule2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="b6d3a-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="b6d3a-103">所有类的所有方法只是我的代码 (JMC) 状态设置为指定的值，除中此 ICorDebugModule2 中`pTokens`数组，它将设置为相反值。</span><span class="sxs-lookup"><span data-stu-id="b6d3a-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d3a-104">语法</span><span class="sxs-lookup"><span data-stu-id="b6d3a-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6d3a-105">参数</span><span class="sxs-lookup"><span data-stu-id="b6d3a-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="b6d3a-106">[in]设置为`true`的代码是调试; 否则为如果设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="b6d3a-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="b6d3a-107">[in] `pTokens` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="b6d3a-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="b6d3a-108">[in]一个数组`mdToken`值，其中每个引用的方法，将具有其 JMC 状态设置为 ！`bIsJustMycode`。</span><span class="sxs-lookup"><span data-stu-id="b6d3a-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6d3a-109">备注</span><span class="sxs-lookup"><span data-stu-id="b6d3a-109">Remarks</span></span>  
 <span data-ttu-id="b6d3a-110">中指定每个方法的 JMC 状态`pTokens`数组设置为相反`bIsJustMycode`值。</span><span class="sxs-lookup"><span data-stu-id="b6d3a-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="b6d3a-111">在此模块中的所有其他方法的状态设置为`bIsJustMycode`值。</span><span class="sxs-lookup"><span data-stu-id="b6d3a-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="b6d3a-112">`SetJMCStatus`方法会清除所有以前的 JMC 设置在此模块中。</span><span class="sxs-lookup"><span data-stu-id="b6d3a-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="b6d3a-113">`SetJMCStatus`方法返回 S_OK HRESULT，如果已成功设置的所有函数。</span><span class="sxs-lookup"><span data-stu-id="b6d3a-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="b6d3a-114">它将返回标记一些函数，如果将 CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT`true`不是可调试。</span><span class="sxs-lookup"><span data-stu-id="b6d3a-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6d3a-115">要求</span><span class="sxs-lookup"><span data-stu-id="b6d3a-115">Requirements</span></span>  
 <span data-ttu-id="b6d3a-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b6d3a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6d3a-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6d3a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6d3a-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6d3a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6d3a-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6d3a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
