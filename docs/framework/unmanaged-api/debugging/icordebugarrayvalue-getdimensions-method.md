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
ms.openlocfilehash: c5199794098e4d83588728eeb165aee5f81fe4c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088504"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="e3f93-102">ICorDebugArrayValue::GetDimensions 方法</span><span class="sxs-lookup"><span data-stu-id="e3f93-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="e3f93-103">获取此数组的每个维度中的元素数。</span><span class="sxs-lookup"><span data-stu-id="e3f93-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3f93-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3f93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3f93-105">参数</span><span class="sxs-lookup"><span data-stu-id="e3f93-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="e3f93-106">中此 ICorDebugArrayValue 对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="e3f93-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="e3f93-107">此值也是 `dims` 数组的大小，因为其大小等于 `ICorDebugArrayValue` 对象的维度数。</span><span class="sxs-lookup"><span data-stu-id="e3f93-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="e3f93-108">弄一个整数数组，其中每个整数指定此 `ICorDebugArrayValue` 对象中维度中的元素数。</span><span class="sxs-lookup"><span data-stu-id="e3f93-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3f93-109">要求</span><span class="sxs-lookup"><span data-stu-id="e3f93-109">Requirements</span></span>  
 <span data-ttu-id="e3f93-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3f93-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3f93-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3f93-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3f93-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3f93-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3f93-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3f93-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
