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
ms.openlocfilehash: 7e160eddf667b542929c8dd3790de666a8e8bb77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413054"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="a2c5a-102">ICorDebugEval::GetResult 方法</span><span class="sxs-lookup"><span data-stu-id="a2c5a-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="a2c5a-103">获取此评估的结果。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2c5a-104">语法</span><span class="sxs-lookup"><span data-stu-id="a2c5a-104">Syntax</span></span>  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2c5a-105">参数</span><span class="sxs-lookup"><span data-stu-id="a2c5a-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="a2c5a-106">[out]一个表示此计算的结果，如果计算正常完成的 ICorDebugValue 对象的地址指针。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2c5a-107">备注</span><span class="sxs-lookup"><span data-stu-id="a2c5a-107">Remarks</span></span>  
 <span data-ttu-id="a2c5a-108">`GetResult`方法无效，只有在完成评估后。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="a2c5a-109">如果计算通常情况下，完成`ppResult`指定结果。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="a2c5a-110">如果它终止的异常，则结果将是引发的异常。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="a2c5a-111">如果计算一个新对象，则结果是对新对象的引用。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2c5a-112">要求</span><span class="sxs-lookup"><span data-stu-id="a2c5a-112">Requirements</span></span>  
 <span data-ttu-id="a2c5a-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2c5a-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2c5a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2c5a-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2c5a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2c5a-116">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2c5a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
