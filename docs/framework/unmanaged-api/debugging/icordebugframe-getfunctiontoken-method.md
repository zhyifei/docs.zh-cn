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
ms.openlocfilehash: e7821022e6966dbdea90d57b6899f09b2ed1964e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090526"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="8e82b-102">ICorDebugFrame::GetFunctionToken 方法</span><span class="sxs-lookup"><span data-stu-id="8e82b-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="8e82b-103">获取包含与此堆栈帧关联的代码的函数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="8e82b-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e82b-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e82b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e82b-105">参数</span><span class="sxs-lookup"><span data-stu-id="8e82b-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="8e82b-106">弄一个指针，指向用于引用函数的元数据的 `mdMethodDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="8e82b-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e82b-107">要求</span><span class="sxs-lookup"><span data-stu-id="8e82b-107">Requirements</span></span>  
 <span data-ttu-id="8e82b-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e82b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e82b-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e82b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e82b-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e82b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e82b-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e82b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
