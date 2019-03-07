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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f24a1434f737e8281a0c68dd09d2e17b34371694
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471649"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="2352b-102">ICorDebugArrayValue::GetBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="2352b-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="2352b-103">获取数组中的每个维的基索引。</span><span class="sxs-lookup"><span data-stu-id="2352b-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2352b-104">语法</span><span class="sxs-lookup"><span data-stu-id="2352b-104">Syntax</span></span>  
  
```  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2352b-105">参数</span><span class="sxs-lookup"><span data-stu-id="2352b-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="2352b-106">[in]此维度的数目`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="2352b-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="2352b-107">该值也为的大小`indicies`由于其大小为维数的数组`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="2352b-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="2352b-108">[out]一个整数数组，其中每个是此维度的基索引 （也就是说的起始索引）`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="2352b-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2352b-109">要求</span><span class="sxs-lookup"><span data-stu-id="2352b-109">Requirements</span></span>  
 <span data-ttu-id="2352b-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2352b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2352b-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2352b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2352b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2352b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2352b-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2352b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
