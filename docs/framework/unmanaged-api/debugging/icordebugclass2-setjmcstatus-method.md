---
title: "ICorDebugClass2::SetJMCStatus 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da9f61bd9a652b4c8e340ddecdee4b48bbdb086e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="1f796-102">ICorDebugClass2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="1f796-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="1f796-103">对于类的每个方法，设置一个值，该值指示方法是否是由用户定义代码。</span><span class="sxs-lookup"><span data-stu-id="1f796-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f796-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f796-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f796-105">参数</span><span class="sxs-lookup"><span data-stu-id="1f796-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="1f796-106">[in]设置为`true`以指示的方法是用户定义的代码; 否则，设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="1f796-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f796-107">备注</span><span class="sxs-lookup"><span data-stu-id="1f796-107">Remarks</span></span>  
 <span data-ttu-id="1f796-108">仅我的代码 (JMC) 分档器将跳过用户定义的代码。</span><span class="sxs-lookup"><span data-stu-id="1f796-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="1f796-109">用户定义的代码必须是代码的可调试的子集。</span><span class="sxs-lookup"><span data-stu-id="1f796-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="1f796-110">`SetJMCStatus`如果它无法设置的值的任何方法，即使它已成功设置的值对于所有其他方法，则返回 S_FALSE HRESULT 的值。</span><span class="sxs-lookup"><span data-stu-id="1f796-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f796-111">要求</span><span class="sxs-lookup"><span data-stu-id="1f796-111">Requirements</span></span>  
 <span data-ttu-id="1f796-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1f796-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f796-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f796-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f796-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f796-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f796-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f796-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
