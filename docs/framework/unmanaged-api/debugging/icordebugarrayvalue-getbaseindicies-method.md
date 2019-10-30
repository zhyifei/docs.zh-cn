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
ms.openlocfilehash: e103401b85626e53db53e1894c22b161774e5163
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088692"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="edfa8-102">ICorDebugArrayValue::GetBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="edfa8-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="edfa8-103">获取数组中每个维的基索引。</span><span class="sxs-lookup"><span data-stu-id="edfa8-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edfa8-104">语法</span><span class="sxs-lookup"><span data-stu-id="edfa8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edfa8-105">参数</span><span class="sxs-lookup"><span data-stu-id="edfa8-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="edfa8-106">中此 `ICorDebugArrayValue` 对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="edfa8-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="edfa8-107">此值也是 `indicies` 数组的大小，因为其大小等于 `ICorDebugArrayValue` 对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="edfa8-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="edfa8-108">弄整数数组，其中每个整数都是此 `ICorDebugArrayValue` 对象的维度的基本索引（即起始索引）。</span><span class="sxs-lookup"><span data-stu-id="edfa8-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edfa8-109">要求</span><span class="sxs-lookup"><span data-stu-id="edfa8-109">Requirements</span></span>  
 <span data-ttu-id="edfa8-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="edfa8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edfa8-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="edfa8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="edfa8-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edfa8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edfa8-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edfa8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
