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
ms.openlocfilehash: 35e043c56977bf644efe1dd9cee1409f50cc877f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179019"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="beb8b-102">ICorDebugArrayValue::GetDimensions 方法</span><span class="sxs-lookup"><span data-stu-id="beb8b-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="beb8b-103">获取此数组的每个维度中的元素数。</span><span class="sxs-lookup"><span data-stu-id="beb8b-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beb8b-104">语法</span><span class="sxs-lookup"><span data-stu-id="beb8b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="beb8b-105">parameters</span><span class="sxs-lookup"><span data-stu-id="beb8b-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="beb8b-106">[在]此 ICorDebugArrayValue 对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="beb8b-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="beb8b-107">此值也是数组的大小，`dims`因为它的大小等于`ICorDebugArrayValue`对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="beb8b-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="beb8b-108">[出]整数数组，每个数组指定此`ICorDebugArrayValue`对象中维度中的元素数。</span><span class="sxs-lookup"><span data-stu-id="beb8b-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beb8b-109">要求</span><span class="sxs-lookup"><span data-stu-id="beb8b-109">Requirements</span></span>  
 <span data-ttu-id="beb8b-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="beb8b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beb8b-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="beb8b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="beb8b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beb8b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beb8b-113">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beb8b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
