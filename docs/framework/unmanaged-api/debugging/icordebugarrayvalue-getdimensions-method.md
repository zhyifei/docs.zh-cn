---
title: ICorDebugArrayValue::GetDimensions 方法
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a52075f33d594787c516f84b65b3319991380907
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500360"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="81cad-102">ICorDebugArrayValue::GetDimensions 方法</span><span class="sxs-lookup"><span data-stu-id="81cad-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="81cad-103">获取此数组的每个维度中的元素数。</span><span class="sxs-lookup"><span data-stu-id="81cad-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81cad-104">语法</span><span class="sxs-lookup"><span data-stu-id="81cad-104">Syntax</span></span>  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81cad-105">参数</span><span class="sxs-lookup"><span data-stu-id="81cad-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="81cad-106">[in]此 ICorDebugArrayValue 对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="81cad-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="81cad-107">该值也为的大小`dims`由于其大小为维数的数组`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="81cad-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="81cad-108">[out]一个整数数组，其中每个指定的元素数，在此维度中`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="81cad-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81cad-109">要求</span><span class="sxs-lookup"><span data-stu-id="81cad-109">Requirements</span></span>  
 <span data-ttu-id="81cad-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="81cad-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81cad-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81cad-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81cad-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81cad-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81cad-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81cad-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
