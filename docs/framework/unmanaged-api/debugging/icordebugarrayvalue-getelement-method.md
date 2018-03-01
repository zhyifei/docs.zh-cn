---
title: "ICorDebugArrayValue::GetElement 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9aba987aa6f806bfe1608e081aac4cb501cd23fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="88bd6-102">ICorDebugArrayValue::GetElement 方法</span><span class="sxs-lookup"><span data-stu-id="88bd6-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="88bd6-103">获取给定的数组元素的值。</span><span class="sxs-lookup"><span data-stu-id="88bd6-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88bd6-104">语法</span><span class="sxs-lookup"><span data-stu-id="88bd6-104">Syntax</span></span>  
  
```  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88bd6-105">参数</span><span class="sxs-lookup"><span data-stu-id="88bd6-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="88bd6-106">[in]此维度数`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="88bd6-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="88bd6-107">该值也为的大小`indices`数组因为其大小等于的维度数`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="88bd6-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="88bd6-108">[in]数组的索引值，其中每个指定的维度内的位置的`ICorDebugArrayValue`对象。</span><span class="sxs-lookup"><span data-stu-id="88bd6-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="88bd6-109">此值不得为空。</span><span class="sxs-lookup"><span data-stu-id="88bd6-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="88bd6-110">[out]指向一个 ICorDebugValue 对象，表示指定元素的值的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="88bd6-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88bd6-111">惠?</span><span class="sxs-lookup"><span data-stu-id="88bd6-111">Requirements</span></span>  
 <span data-ttu-id="88bd6-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="88bd6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88bd6-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88bd6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88bd6-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88bd6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88bd6-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88bd6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
