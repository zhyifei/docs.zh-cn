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
ms.openlocfilehash: a56b5c31c26dbe5c5371fdb7a10c13ad11847117
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419467"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="16c56-102">ICorDebugModule2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="16c56-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="16c56-103">设置的所有类的所有方法的仅我的代码 (JMC) 状态中到指定的值，除中此 ICorDebugModule2`pTokens`数组，它将设置为的相反值。</span><span class="sxs-lookup"><span data-stu-id="16c56-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16c56-104">语法</span><span class="sxs-lookup"><span data-stu-id="16c56-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16c56-105">参数</span><span class="sxs-lookup"><span data-stu-id="16c56-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="16c56-106">[in]设置为`true`代码是调试; 否则为如果设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="16c56-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="16c56-107">[in] `pTokens` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="16c56-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="16c56-108">[in]数组`mdToken`值，其中每个是指将具有设置为其 jmc 的方法状态的方法 ！`bIsJustMycode`。</span><span class="sxs-lookup"><span data-stu-id="16c56-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16c56-109">备注</span><span class="sxs-lookup"><span data-stu-id="16c56-109">Remarks</span></span>  
 <span data-ttu-id="16c56-110">中指定每个方法的 JMC 状态`pTokens`数组设置为相反`bIsJustMycode`值。</span><span class="sxs-lookup"><span data-stu-id="16c56-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="16c56-111">此模块中的所有其他方法的状态设置为`bIsJustMycode`值。</span><span class="sxs-lookup"><span data-stu-id="16c56-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="16c56-112">`SetJMCStatus`方法清除在此模块中的所有先前 jmc 的方法设置。</span><span class="sxs-lookup"><span data-stu-id="16c56-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="16c56-113">`SetJMCStatus`方法返回，则为 S_OK HRESULT，如果所有函数已成功都设置。</span><span class="sxs-lookup"><span data-stu-id="16c56-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="16c56-114">它将返回标记一些函数，如果 CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT`true`不是可调试。</span><span class="sxs-lookup"><span data-stu-id="16c56-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16c56-115">要求</span><span class="sxs-lookup"><span data-stu-id="16c56-115">Requirements</span></span>  
 <span data-ttu-id="16c56-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="16c56-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16c56-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16c56-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16c56-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16c56-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16c56-119">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16c56-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
