---
title: ICorDebugArrayValue::GetElement 方法
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1be7eaeccb53e8b180aeb9492cd887f952bbaea5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645638"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="704a9-102">ICorDebugArrayValue::GetElement 方法</span><span class="sxs-lookup"><span data-stu-id="704a9-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="704a9-103">获取给定的数组元素的值。</span><span class="sxs-lookup"><span data-stu-id="704a9-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="704a9-104">语法</span><span class="sxs-lookup"><span data-stu-id="704a9-104">Syntax</span></span>  
  
```  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="704a9-105">参数</span><span class="sxs-lookup"><span data-stu-id="704a9-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="704a9-106">[in]此维度的数目`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="704a9-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="704a9-107">该值也为的大小`indices`由于其大小为维数的数组`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="704a9-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="704a9-108">[in]索引值，其中每个指定的维度内的位置的数组`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="704a9-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="704a9-109">此值不能为 null。</span><span class="sxs-lookup"><span data-stu-id="704a9-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="704a9-110">[out]指向一个 ICorDebugValue 对象，表示指定的元素的值的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="704a9-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="704a9-111">要求</span><span class="sxs-lookup"><span data-stu-id="704a9-111">Requirements</span></span>  
 <span data-ttu-id="704a9-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="704a9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="704a9-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="704a9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="704a9-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="704a9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="704a9-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="704a9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
