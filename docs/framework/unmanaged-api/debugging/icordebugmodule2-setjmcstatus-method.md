---
title: "ICorDebugModule2::SetJMCStatus 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a461a9c05b18de45426247743c6e4ffca775025a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="b6190-102">ICorDebugModule2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="b6190-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="b6190-103">设置的所有类的所有方法的仅我的代码 (JMC) 状态中到指定的值，除中此 ICorDebugModule2`pTokens`数组，它将设置为的相反值。</span><span class="sxs-lookup"><span data-stu-id="b6190-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6190-104">语法</span><span class="sxs-lookup"><span data-stu-id="b6190-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6190-105">参数</span><span class="sxs-lookup"><span data-stu-id="b6190-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="b6190-106">[in]设置为`true`代码是调试; 否则为如果设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="b6190-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="b6190-107">[in] `pTokens` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="b6190-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="b6190-108">[in]数组`mdToken`值，其中每个是指将具有设置为其 jmc 的方法状态的方法 ！`bIsJustMycode`。</span><span class="sxs-lookup"><span data-stu-id="b6190-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6190-109">备注</span><span class="sxs-lookup"><span data-stu-id="b6190-109">Remarks</span></span>  
 <span data-ttu-id="b6190-110">中指定每个方法的 JMC 状态`pTokens`数组设置为相反`bIsJustMycode`值。</span><span class="sxs-lookup"><span data-stu-id="b6190-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="b6190-111">此模块中的所有其他方法的状态设置为`bIsJustMycode`值。</span><span class="sxs-lookup"><span data-stu-id="b6190-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="b6190-112">`SetJMCStatus`方法清除在此模块中的所有先前 jmc 的方法设置。</span><span class="sxs-lookup"><span data-stu-id="b6190-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="b6190-113">`SetJMCStatus`方法返回，则为 S_OK HRESULT，如果所有函数已成功都设置。</span><span class="sxs-lookup"><span data-stu-id="b6190-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="b6190-114">它将返回标记一些函数，如果 CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT`true`不是可调试。</span><span class="sxs-lookup"><span data-stu-id="b6190-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6190-115">惠?</span><span class="sxs-lookup"><span data-stu-id="b6190-115">Requirements</span></span>  
 <span data-ttu-id="b6190-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b6190-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6190-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6190-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6190-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6190-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6190-119">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6190-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
