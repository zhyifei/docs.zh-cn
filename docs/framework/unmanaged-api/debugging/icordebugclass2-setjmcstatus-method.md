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
ms.openlocfilehash: 9fb2f960098e970b4d3d9f0be499f4d9fda6558e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893896"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="f5055-102">ICorDebugClass2::SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="f5055-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="f5055-103">对于类的每个方法，设置一个值，该值指示该方法是否为用户定义的代码。</span><span class="sxs-lookup"><span data-stu-id="f5055-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5055-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5055-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5055-105">参数</span><span class="sxs-lookup"><span data-stu-id="f5055-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="f5055-106">中设置为`true`以指示该方法是用户定义的代码;否则，将设置`false`为。</span><span class="sxs-lookup"><span data-stu-id="f5055-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5055-107">备注</span><span class="sxs-lookup"><span data-stu-id="f5055-107">Remarks</span></span>  
 <span data-ttu-id="f5055-108">仅我的代码（JMC）分档器将跳过非用户定义的代码。</span><span class="sxs-lookup"><span data-stu-id="f5055-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="f5055-109">用户定义的代码必须是可调试代码的子集。</span><span class="sxs-lookup"><span data-stu-id="f5055-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="f5055-110">`SetJMCStatus`如果无法为任何方法设置值，则返回 S_FALSE 的 HRESULT 值，即使它成功设置了所有其他方法的值也是如此。</span><span class="sxs-lookup"><span data-stu-id="f5055-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5055-111">要求</span><span class="sxs-lookup"><span data-stu-id="f5055-111">Requirements</span></span>  
 <span data-ttu-id="f5055-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5055-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5055-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5055-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5055-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5055-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5055-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5055-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
