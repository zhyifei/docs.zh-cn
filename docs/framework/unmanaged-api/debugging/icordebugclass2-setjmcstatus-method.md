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
ms.openlocfilehash: 23f248625753c15a4798ea69a1eb3b377b79f95d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747749"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="f0663-102">ICorDebugClass2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="f0663-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="f0663-103">对于类的每个方法，设置一个值，指示方法是否是用户定义的代码。</span><span class="sxs-lookup"><span data-stu-id="f0663-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0663-104">语法</span><span class="sxs-lookup"><span data-stu-id="f0663-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0663-105">参数</span><span class="sxs-lookup"><span data-stu-id="f0663-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="f0663-106">[in]设置为`true`以指示该方法是用户定义的代码; 否则，设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="f0663-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0663-107">备注</span><span class="sxs-lookup"><span data-stu-id="f0663-107">Remarks</span></span>  
 <span data-ttu-id="f0663-108">仅我的代码 (JMC) 分档器将跳过用户定义的代码。</span><span class="sxs-lookup"><span data-stu-id="f0663-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="f0663-109">用户定义的代码必须是代码的可调试的子集。</span><span class="sxs-lookup"><span data-stu-id="f0663-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="f0663-110">`SetJMCStatus` 如果它无法设置的值对于任何方法，即使它已成功设置的值对于所有其他方法，则返回 S_FALSE 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="f0663-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0663-111">要求</span><span class="sxs-lookup"><span data-stu-id="f0663-111">Requirements</span></span>  
 <span data-ttu-id="f0663-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f0663-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0663-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0663-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0663-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0663-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0663-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0663-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
