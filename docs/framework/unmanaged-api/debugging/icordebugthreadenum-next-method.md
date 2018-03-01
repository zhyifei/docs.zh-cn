---
title: "ICorDebugThreadEnum::Next 方法"
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
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ac9ff468f85248631ffd7f3a39a8827b1aef45b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="29d7f-102">ICorDebugThreadEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="29d7f-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="29d7f-103">从当前位置开始在枚举中获取指定 ICorDebugThread 实例数。</span><span class="sxs-lookup"><span data-stu-id="29d7f-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29d7f-104">语法</span><span class="sxs-lookup"><span data-stu-id="29d7f-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29d7f-105">参数</span><span class="sxs-lookup"><span data-stu-id="29d7f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="29d7f-106">[in]数`ICorDebugThread`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="29d7f-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="29d7f-107">[out]一个指针，其中每个指向数组`ICorDebugThread`表示一个线程的对象。</span><span class="sxs-lookup"><span data-stu-id="29d7f-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="29d7f-108">[out]指向数`ICorDebugThread`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="29d7f-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="29d7f-109">此值可能为 null 如果`celt`是之一。</span><span class="sxs-lookup"><span data-stu-id="29d7f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29d7f-110">惠?</span><span class="sxs-lookup"><span data-stu-id="29d7f-110">Requirements</span></span>  
 <span data-ttu-id="29d7f-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="29d7f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29d7f-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29d7f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29d7f-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29d7f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29d7f-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29d7f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
