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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8e7fcb4f44d6bdf6f18c93b1046b549331621a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667114"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="2b7df-102">ICorDebugEval::GetResult 方法</span><span class="sxs-lookup"><span data-stu-id="2b7df-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="2b7df-103">获取此评估的结果。</span><span class="sxs-lookup"><span data-stu-id="2b7df-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b7df-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b7df-104">Syntax</span></span>  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b7df-105">参数</span><span class="sxs-lookup"><span data-stu-id="2b7df-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="2b7df-106">[out]ICorDebugValue 对象，表示此评估的结果，如果计算正常完成的地址指针。</span><span class="sxs-lookup"><span data-stu-id="2b7df-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b7df-107">备注</span><span class="sxs-lookup"><span data-stu-id="2b7df-107">Remarks</span></span>  
 <span data-ttu-id="2b7df-108">`GetResult`仅在完成评估后，方法均有效。</span><span class="sxs-lookup"><span data-stu-id="2b7df-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="2b7df-109">如果计算通常情况下，完成`ppResult`指定的结果。</span><span class="sxs-lookup"><span data-stu-id="2b7df-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="2b7df-110">如果出现异常终止，则结果是引发的异常。</span><span class="sxs-lookup"><span data-stu-id="2b7df-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="2b7df-111">如果评估的一个新的对象，结果是对新对象的引用。</span><span class="sxs-lookup"><span data-stu-id="2b7df-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b7df-112">要求</span><span class="sxs-lookup"><span data-stu-id="2b7df-112">Requirements</span></span>  
 <span data-ttu-id="2b7df-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b7df-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b7df-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b7df-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b7df-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b7df-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b7df-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b7df-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
