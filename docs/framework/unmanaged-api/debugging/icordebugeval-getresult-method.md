---
title: ICorDebugEval::GetResult 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
ms.openlocfilehash: 52bfe669d3b078657916554255a11cecfc07d484
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085089"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="e4d75-102">ICorDebugEval::GetResult 方法</span><span class="sxs-lookup"><span data-stu-id="e4d75-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="e4d75-103">获取此计算的结果。</span><span class="sxs-lookup"><span data-stu-id="e4d75-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d75-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4d75-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4d75-105">参数</span><span class="sxs-lookup"><span data-stu-id="e4d75-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="e4d75-106">弄一个指针，指向表示此计算结果的 ICorDebugValue 对象的地址（如果计算正常完成）。</span><span class="sxs-lookup"><span data-stu-id="e4d75-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4d75-107">备注</span><span class="sxs-lookup"><span data-stu-id="e4d75-107">Remarks</span></span>  
 <span data-ttu-id="e4d75-108">只有完成计算后，`GetResult` 方法才有效。</span><span class="sxs-lookup"><span data-stu-id="e4d75-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="e4d75-109">如果计算正常完成，`ppResult` 将指定结果。</span><span class="sxs-lookup"><span data-stu-id="e4d75-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="e4d75-110">如果终止时出现异常，则结果为引发的异常。</span><span class="sxs-lookup"><span data-stu-id="e4d75-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="e4d75-111">如果计算为新的对象，则结果是对新的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="e4d75-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4d75-112">要求</span><span class="sxs-lookup"><span data-stu-id="e4d75-112">Requirements</span></span>  
 <span data-ttu-id="e4d75-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4d75-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4d75-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4d75-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4d75-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4d75-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4d75-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4d75-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
