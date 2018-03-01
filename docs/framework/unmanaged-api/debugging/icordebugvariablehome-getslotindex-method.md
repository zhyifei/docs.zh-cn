---
title: "ICorDebugVariableHome::GetSlotIndex 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ff62b79fbbb0896941730797473209872e6bfc2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="7cc8d-102">ICorDebugVariableHome::GetSlotIndex 方法</span><span class="sxs-lookup"><span data-stu-id="7cc8d-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="7cc8d-103">获取本地变量的托管的槽索引。</span><span class="sxs-lookup"><span data-stu-id="7cc8d-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cc8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7cc8d-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7cc8d-105">参数</span><span class="sxs-lookup"><span data-stu-id="7cc8d-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="7cc8d-106">[out]指向本地变量的槽索引的指针。</span><span class="sxs-lookup"><span data-stu-id="7cc8d-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cc8d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7cc8d-107">Return Value</span></span>  
 <span data-ttu-id="7cc8d-108">该方法返回以下值。</span><span class="sxs-lookup"><span data-stu-id="7cc8d-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="7cc8d-109">“值”</span><span class="sxs-lookup"><span data-stu-id="7cc8d-109">Value</span></span>|<span data-ttu-id="7cc8d-110">描述</span><span class="sxs-lookup"><span data-stu-id="7cc8d-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="7cc8d-111">方法调用返回中的槽索引值`pSlotIndex`。</span><span class="sxs-lookup"><span data-stu-id="7cc8d-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="7cc8d-112">当前[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)实例表示的函数自变量。</span><span class="sxs-lookup"><span data-stu-id="7cc8d-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cc8d-113">备注</span><span class="sxs-lookup"><span data-stu-id="7cc8d-113">Remarks</span></span>  
 <span data-ttu-id="7cc8d-114">槽索引可用于检索此本地变量的元数据。</span><span class="sxs-lookup"><span data-stu-id="7cc8d-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cc8d-115">惠?</span><span class="sxs-lookup"><span data-stu-id="7cc8d-115">Requirements</span></span>  
 <span data-ttu-id="7cc8d-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7cc8d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cc8d-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7cc8d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cc8d-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cc8d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cc8d-119">**.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cc8d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc8d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="7cc8d-120">See Also</span></span>  
 [<span data-ttu-id="7cc8d-121">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="7cc8d-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
