---
title: "ICorDebugArrayValue::GetDimensions 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.GetDimensions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 364035a0b6e26f5649ef9be5839d096be2fb02dc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="c24c1-102">ICorDebugArrayValue::GetDimensions 方法</span><span class="sxs-lookup"><span data-stu-id="c24c1-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="c24c1-103">获取此数组的每个维度中的元素数。</span><span class="sxs-lookup"><span data-stu-id="c24c1-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c24c1-104">语法</span><span class="sxs-lookup"><span data-stu-id="c24c1-104">Syntax</span></span>  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c24c1-105">参数</span><span class="sxs-lookup"><span data-stu-id="c24c1-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="c24c1-106">[in]此 ICorDebugArrayValue 对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="c24c1-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="c24c1-107">该值也为的大小`dims`数组因为其大小等于的维度数`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="c24c1-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="c24c1-108">[out]整数的数组，其中每个在此维度中指定的元素数`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="c24c1-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c24c1-109">要求</span><span class="sxs-lookup"><span data-stu-id="c24c1-109">Requirements</span></span>  
 <span data-ttu-id="c24c1-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c24c1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c24c1-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c24c1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c24c1-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c24c1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c24c1-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c24c1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
