---
title: "ICorDebugModule2::SetJMCStatus 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca4b53acc69d0a56b94526de0c3b16fd1abde077
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="47108-102">ICorDebugModule2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="47108-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="47108-103">设置的所有类的所有方法的仅我的代码 (JMC) 状态中到指定的值，除中此 ICorDebugModule2`pTokens`数组，它将设置为的相反值。</span><span class="sxs-lookup"><span data-stu-id="47108-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47108-104">语法</span><span class="sxs-lookup"><span data-stu-id="47108-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47108-105">参数</span><span class="sxs-lookup"><span data-stu-id="47108-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="47108-106">[in]设置为`true`代码是调试; 否则为如果设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="47108-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="47108-107">[in] `pTokens` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="47108-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="47108-108">[in]数组`mdToken`值，其中每个是指将具有设置为其 jmc 的方法状态的方法 ！`bIsJustMycode`。</span><span class="sxs-lookup"><span data-stu-id="47108-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47108-109">备注</span><span class="sxs-lookup"><span data-stu-id="47108-109">Remarks</span></span>  
 <span data-ttu-id="47108-110">中指定每个方法的 JMC 状态`pTokens`数组设置为相反`bIsJustMycode`值。</span><span class="sxs-lookup"><span data-stu-id="47108-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="47108-111">此模块中的所有其他方法的状态设置为`bIsJustMycode`值。</span><span class="sxs-lookup"><span data-stu-id="47108-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="47108-112">`SetJMCStatus`方法清除在此模块中的所有先前 jmc 的方法设置。</span><span class="sxs-lookup"><span data-stu-id="47108-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="47108-113">`SetJMCStatus`方法返回，则为 S_OK HRESULT，如果所有函数已成功都设置。</span><span class="sxs-lookup"><span data-stu-id="47108-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="47108-114">它将返回标记一些函数，如果 CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT`true`不是可调试。</span><span class="sxs-lookup"><span data-stu-id="47108-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47108-115">要求</span><span class="sxs-lookup"><span data-stu-id="47108-115">Requirements</span></span>  
 <span data-ttu-id="47108-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47108-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47108-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47108-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47108-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47108-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47108-119">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47108-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
