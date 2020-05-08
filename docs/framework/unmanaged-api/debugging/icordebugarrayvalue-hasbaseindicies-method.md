---
title: ICorDebugArrayValue::HasBaseIndicies 方法
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
ms.openlocfilehash: e6e8eb91bbc41faf0dcea010da9aa54995058653
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894976"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="21585-102">ICorDebugArrayValue::HasBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="21585-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="21585-103">获取一个值，该值指示此数组的任何维度是否具有非零的基本索引。</span><span class="sxs-lookup"><span data-stu-id="21585-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21585-104">语法</span><span class="sxs-lookup"><span data-stu-id="21585-104">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21585-105">参数</span><span class="sxs-lookup"><span data-stu-id="21585-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="21585-106">弄指向布尔值的指针， `true`如果此`ICorDebugArrayValue`对象的一个或多个维度的基本索引为非零，则为;否则，布尔值为`false`。</span><span class="sxs-lookup"><span data-stu-id="21585-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21585-107">要求</span><span class="sxs-lookup"><span data-stu-id="21585-107">Requirements</span></span>  
 <span data-ttu-id="21585-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21585-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21585-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21585-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21585-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21585-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21585-111">**.NET Framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21585-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
