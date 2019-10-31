---
title: ICorDebugFunction::GetToken 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetToken
helpviewer_keywords:
- ICorDebugFunction::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: c6bbf479-062e-48e9-9c70-0f92e293e36a
topic_type:
- apiref
ms.openlocfilehash: 4229d567fc4ced5e3b78b390ced29fb9ea60f93b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137846"
---
# <a name="icordebugfunctiongettoken-method"></a><span data-ttu-id="4c7a6-102">ICorDebugFunction::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="4c7a6-102">ICorDebugFunction::GetToken Method</span></span>
<span data-ttu-id="4c7a6-103">获取此函数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="4c7a6-103">Gets the metadata token for this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c7a6-104">语法</span><span class="sxs-lookup"><span data-stu-id="4c7a6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdMethodDef *pMethodDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c7a6-105">参数</span><span class="sxs-lookup"><span data-stu-id="4c7a6-105">Parameters</span></span>  
 `pMethodDef`  
 <span data-ttu-id="4c7a6-106">弄一个指针，指向用于引用此函数的元数据的 `mdMethodDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="4c7a6-106">[out] A pointer to an `mdMethodDef` token that references the metadata for this function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c7a6-107">要求</span><span class="sxs-lookup"><span data-stu-id="4c7a6-107">Requirements</span></span>  
 <span data-ttu-id="4c7a6-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4c7a6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c7a6-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c7a6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c7a6-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c7a6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c7a6-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c7a6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
