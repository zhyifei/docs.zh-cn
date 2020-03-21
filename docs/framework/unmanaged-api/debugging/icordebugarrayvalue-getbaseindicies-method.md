---
title: ICorDebugArrayValue::GetBaseIndicies 方法
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
ms.openlocfilehash: 7c6d1905cdbd12b960014e687034ea9d163b68d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179036"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="39417-102">ICorDebugArrayValue::GetBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="39417-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="39417-103">获取数组中每个维度的基本索引。</span><span class="sxs-lookup"><span data-stu-id="39417-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39417-104">语法</span><span class="sxs-lookup"><span data-stu-id="39417-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39417-105">parameters</span><span class="sxs-lookup"><span data-stu-id="39417-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="39417-106">[在]此`ICorDebugArrayValue`对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="39417-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="39417-107">此值也是数组的大小，`indicies`因为它的大小等于`ICorDebugArrayValue`对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="39417-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="39417-108">[出]整数数组，每个数组都是此`ICorDebugArrayValue`对象维度的基础索引（即起始索引）。</span><span class="sxs-lookup"><span data-stu-id="39417-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39417-109">要求</span><span class="sxs-lookup"><span data-stu-id="39417-109">Requirements</span></span>  
 <span data-ttu-id="39417-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39417-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39417-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39417-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39417-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39417-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39417-113">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39417-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
