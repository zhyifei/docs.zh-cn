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
ms.openlocfilehash: fa2be894af6e44d09c25a736f45acba56052f9fa
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895043"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="647d1-102">ICorDebugArrayValue::GetDimensions 方法</span><span class="sxs-lookup"><span data-stu-id="647d1-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="647d1-103">获取此数组的每个维度中的元素数。</span><span class="sxs-lookup"><span data-stu-id="647d1-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="647d1-104">语法</span><span class="sxs-lookup"><span data-stu-id="647d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="647d1-105">参数</span><span class="sxs-lookup"><span data-stu-id="647d1-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="647d1-106">中此 ICorDebugArrayValue 对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="647d1-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="647d1-107">此值也是`dims`数组的大小，因为其大小等于`ICorDebugArrayValue`对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="647d1-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="647d1-108">弄一个整数数组，其中每个整数指定了此`ICorDebugArrayValue`对象的维度中的元素数目。</span><span class="sxs-lookup"><span data-stu-id="647d1-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="647d1-109">要求</span><span class="sxs-lookup"><span data-stu-id="647d1-109">Requirements</span></span>  
 <span data-ttu-id="647d1-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="647d1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="647d1-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="647d1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="647d1-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="647d1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="647d1-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="647d1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
