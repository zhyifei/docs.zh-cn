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
ms.openlocfilehash: e542145e888049231a6c5e4cccbb4ee96c62f98b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213252"
---
# <a name="icordebugfunctiongettoken-method"></a><span data-ttu-id="a086d-102">ICorDebugFunction::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="a086d-102">ICorDebugFunction::GetToken Method</span></span>
<span data-ttu-id="a086d-103">获取此函数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="a086d-103">Gets the metadata token for this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a086d-104">语法</span><span class="sxs-lookup"><span data-stu-id="a086d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdMethodDef *pMethodDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a086d-105">参数</span><span class="sxs-lookup"><span data-stu-id="a086d-105">Parameters</span></span>  
 `pMethodDef`  
 <span data-ttu-id="a086d-106">弄指向 `mdMethodDef` 引用此函数的元数据的标记的指针。</span><span class="sxs-lookup"><span data-stu-id="a086d-106">[out] A pointer to an `mdMethodDef` token that references the metadata for this function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a086d-107">要求</span><span class="sxs-lookup"><span data-stu-id="a086d-107">Requirements</span></span>  
 <span data-ttu-id="a086d-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a086d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a086d-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a086d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a086d-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a086d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a086d-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a086d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
