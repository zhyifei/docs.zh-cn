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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed6570e11008e52d4b1f97c2dc90e2ccbef2e35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750613"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="179ea-102">ICorDebugClass2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="179ea-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="179ea-103">对于类的每个方法，设置一个值，指示方法是否是用户定义的代码。</span><span class="sxs-lookup"><span data-stu-id="179ea-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="179ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="179ea-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="179ea-105">参数</span><span class="sxs-lookup"><span data-stu-id="179ea-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="179ea-106">[in]设置为`true`以指示该方法是用户定义的代码; 否则，设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="179ea-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="179ea-107">备注</span><span class="sxs-lookup"><span data-stu-id="179ea-107">Remarks</span></span>  
 <span data-ttu-id="179ea-108">仅我的代码 (JMC) 分档器将跳过用户定义的代码。</span><span class="sxs-lookup"><span data-stu-id="179ea-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="179ea-109">用户定义的代码必须是代码的可调试的子集。</span><span class="sxs-lookup"><span data-stu-id="179ea-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="179ea-110">`SetJMCStatus` 如果它无法设置的值对于任何方法，即使它已成功设置的值对于所有其他方法，则返回 S_FALSE 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="179ea-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="179ea-111">要求</span><span class="sxs-lookup"><span data-stu-id="179ea-111">Requirements</span></span>  
 <span data-ttu-id="179ea-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="179ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="179ea-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="179ea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="179ea-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="179ea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="179ea-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="179ea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
