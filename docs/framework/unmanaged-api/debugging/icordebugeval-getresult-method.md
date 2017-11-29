---
title: "ICorDebugEval::GetResult 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.GetResult
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7379237c73d79d9e8c66112a101edadca357cb10
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="d6319-102">ICorDebugEval::GetResult 方法</span><span class="sxs-lookup"><span data-stu-id="d6319-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="d6319-103">获取此评估的结果。</span><span class="sxs-lookup"><span data-stu-id="d6319-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6319-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6319-104">Syntax</span></span>  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6319-105">参数</span><span class="sxs-lookup"><span data-stu-id="d6319-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="d6319-106">[out]一个表示此计算的结果，如果计算正常完成的 ICorDebugValue 对象的地址指针。</span><span class="sxs-lookup"><span data-stu-id="d6319-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6319-107">备注</span><span class="sxs-lookup"><span data-stu-id="d6319-107">Remarks</span></span>  
 <span data-ttu-id="d6319-108">`GetResult`方法无效，只有在完成评估后。</span><span class="sxs-lookup"><span data-stu-id="d6319-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="d6319-109">如果计算通常情况下，完成`ppResult`指定结果。</span><span class="sxs-lookup"><span data-stu-id="d6319-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="d6319-110">如果它终止的异常，则结果将是引发的异常。</span><span class="sxs-lookup"><span data-stu-id="d6319-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="d6319-111">如果计算一个新对象，则结果是对新对象的引用。</span><span class="sxs-lookup"><span data-stu-id="d6319-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6319-112">要求</span><span class="sxs-lookup"><span data-stu-id="d6319-112">Requirements</span></span>  
 <span data-ttu-id="d6319-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6319-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6319-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6319-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6319-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6319-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6319-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6319-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
