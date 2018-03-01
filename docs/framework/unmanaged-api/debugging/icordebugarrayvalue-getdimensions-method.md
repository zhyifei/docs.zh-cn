---
title: "ICorDebugArrayValue::GetDimensions 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1769969d411d66417d2b2df7ddc9f810bd7f48ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="ddedc-102">ICorDebugArrayValue::GetDimensions 方法</span><span class="sxs-lookup"><span data-stu-id="ddedc-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="ddedc-103">获取此数组的每个维度中的元素数。</span><span class="sxs-lookup"><span data-stu-id="ddedc-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddedc-104">语法</span><span class="sxs-lookup"><span data-stu-id="ddedc-104">Syntax</span></span>  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ddedc-105">参数</span><span class="sxs-lookup"><span data-stu-id="ddedc-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="ddedc-106">[in]此 ICorDebugArrayValue 对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="ddedc-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="ddedc-107">该值也为的大小`dims`数组因为其大小等于的维度数`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="ddedc-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="ddedc-108">[out]整数的数组，其中每个在此维度中指定的元素数`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="ddedc-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddedc-109">惠?</span><span class="sxs-lookup"><span data-stu-id="ddedc-109">Requirements</span></span>  
 <span data-ttu-id="ddedc-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ddedc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddedc-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddedc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddedc-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddedc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddedc-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddedc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
