---
title: "ICorDebugProcess5::GetGCHeapInformation 方法"
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
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 70e9e3ab6c7332e492b7146e52e0265653803bf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="429d4-102">ICorDebugProcess5::GetGCHeapInformation 方法</span><span class="sxs-lookup"><span data-stu-id="429d4-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="429d4-103">提供有关垃圾回收堆，包括它是否是当前可枚举的常规信息。</span><span class="sxs-lookup"><span data-stu-id="429d4-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="429d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="429d4-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="429d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="429d4-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="429d4-106">[out]指向的指针[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)值，该值提供有关垃圾回收堆的常规信息。</span><span class="sxs-lookup"><span data-stu-id="429d4-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="429d4-107">备注</span><span class="sxs-lookup"><span data-stu-id="429d4-107">Remarks</span></span>  
 <span data-ttu-id="429d4-108">`ICorDebugProcess5::GetGCHeapInformation`枚举堆之前，必须先调用方法或单个堆的区域，以确保垃圾回收结构在进程中当前有效。</span><span class="sxs-lookup"><span data-stu-id="429d4-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="429d4-109">正在集合时，不能将遍历垃圾回收堆。</span><span class="sxs-lookup"><span data-stu-id="429d4-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="429d4-110">否则，在枚举可能捕获无效的垃圾回收结构。</span><span class="sxs-lookup"><span data-stu-id="429d4-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="429d4-111">惠?</span><span class="sxs-lookup"><span data-stu-id="429d4-111">Requirements</span></span>  
 <span data-ttu-id="429d4-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="429d4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="429d4-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="429d4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="429d4-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="429d4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="429d4-115">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="429d4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="429d4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="429d4-116">See Also</span></span>  
 [<span data-ttu-id="429d4-117">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="429d4-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="429d4-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="429d4-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
