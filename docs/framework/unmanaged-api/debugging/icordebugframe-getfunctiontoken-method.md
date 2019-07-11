---
title: ICorDebugFrame::GetFunctionToken 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunctionToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f50e5fcee3705e05aeed820cf736613c12b00e50
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754870"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="c714e-102">ICorDebugFrame::GetFunctionToken 方法</span><span class="sxs-lookup"><span data-stu-id="c714e-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="c714e-103">获取包含与此堆栈帧关联的代码的函数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="c714e-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c714e-104">语法</span><span class="sxs-lookup"><span data-stu-id="c714e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c714e-105">参数</span><span class="sxs-lookup"><span data-stu-id="c714e-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="c714e-106">[out]一个指向`mdMethodDef`引用函数的元数据的令牌。</span><span class="sxs-lookup"><span data-stu-id="c714e-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c714e-107">要求</span><span class="sxs-lookup"><span data-stu-id="c714e-107">Requirements</span></span>  
 <span data-ttu-id="c714e-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c714e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c714e-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c714e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c714e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c714e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c714e-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c714e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
