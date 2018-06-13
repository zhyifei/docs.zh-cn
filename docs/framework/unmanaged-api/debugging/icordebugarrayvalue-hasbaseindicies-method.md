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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 574df434360dfab644a4c937dac46ebc3871a53a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399494"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="b714c-102">ICorDebugArrayValue::HasBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="b714c-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="b714c-103">获取一个值，该值指示此数组的任何维度是否具有基索引为非零。</span><span class="sxs-lookup"><span data-stu-id="b714c-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b714c-104">语法</span><span class="sxs-lookup"><span data-stu-id="b714c-104">Syntax</span></span>  
  
```  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b714c-105">参数</span><span class="sxs-lookup"><span data-stu-id="b714c-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="b714c-106">[out]一个布尔值，是一个指向`true`如果一个或多个维度的这`ICorDebugArrayValue`对象具有基索引为非零; 否则，布尔值为`false`。</span><span class="sxs-lookup"><span data-stu-id="b714c-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b714c-107">要求</span><span class="sxs-lookup"><span data-stu-id="b714c-107">Requirements</span></span>  
 <span data-ttu-id="b714c-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b714c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b714c-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b714c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b714c-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b714c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b714c-111">**.NET framework 版本：** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b714c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
