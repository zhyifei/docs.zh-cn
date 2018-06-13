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
ms.openlocfilehash: d234e01e3d47a64b9a001591ee2b61074eea8afb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403388"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="a1136-102">ICorDebugClass2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="a1136-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="a1136-103">对于类的每个方法，设置一个值，该值指示方法是否是由用户定义代码。</span><span class="sxs-lookup"><span data-stu-id="a1136-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1136-104">语法</span><span class="sxs-lookup"><span data-stu-id="a1136-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1136-105">参数</span><span class="sxs-lookup"><span data-stu-id="a1136-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="a1136-106">[in]设置为`true`以指示的方法是用户定义的代码; 否则，设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="a1136-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1136-107">备注</span><span class="sxs-lookup"><span data-stu-id="a1136-107">Remarks</span></span>  
 <span data-ttu-id="a1136-108">仅我的代码 (JMC) 分档器将跳过用户定义的代码。</span><span class="sxs-lookup"><span data-stu-id="a1136-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="a1136-109">用户定义的代码必须是代码的可调试的子集。</span><span class="sxs-lookup"><span data-stu-id="a1136-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="a1136-110">`SetJMCStatus` 如果它无法设置的值的任何方法，即使它已成功设置的值对于所有其他方法，则返回 S_FALSE HRESULT 的值。</span><span class="sxs-lookup"><span data-stu-id="a1136-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1136-111">要求</span><span class="sxs-lookup"><span data-stu-id="a1136-111">Requirements</span></span>  
 <span data-ttu-id="a1136-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a1136-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1136-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1136-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1136-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1136-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1136-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1136-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
