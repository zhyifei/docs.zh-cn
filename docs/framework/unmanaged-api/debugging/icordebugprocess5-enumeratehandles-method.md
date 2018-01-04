---
title: "ICorDebugProcess5::EnumerateHandles 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateHandles
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c9bf9f1a4d565e0af4f3ee34a2805116407027d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="d4311-102">ICorDebugProcess5::EnumerateHandles 方法</span><span class="sxs-lookup"><span data-stu-id="d4311-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="d4311-103">在进程中获取对象句柄的枚举数。</span><span class="sxs-lookup"><span data-stu-id="d4311-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4311-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4311-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4311-105">参数</span><span class="sxs-lookup"><span data-stu-id="d4311-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="d4311-106">[in]按位组合[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)指定的句柄以包含在集合中的类型的值。</span><span class="sxs-lookup"><span data-stu-id="d4311-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="d4311-107">[out]指向的地址的指针[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)即的枚举数对象要进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d4311-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4311-108">备注</span><span class="sxs-lookup"><span data-stu-id="d4311-108">Remarks</span></span>  
 <span data-ttu-id="d4311-109">`EnumerateHandles`是一个 helper 函数，支持的句柄表的检查。</span><span class="sxs-lookup"><span data-stu-id="d4311-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="d4311-110">它是类似于[icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)方法，只不过而不是填充[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)集合的所有对象要进行垃圾回收，它包括具有来自句柄表的句柄的对象。</span><span class="sxs-lookup"><span data-stu-id="d4311-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="d4311-111">`types`参数指定要包含在集合中的句柄类型。</span><span class="sxs-lookup"><span data-stu-id="d4311-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="d4311-112">`types`可以是任何的以下三个成员[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)枚举：</span><span class="sxs-lookup"><span data-stu-id="d4311-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
-   <span data-ttu-id="d4311-113">`CorHandleStrongOnly`（仅引用强句柄）。</span><span class="sxs-lookup"><span data-stu-id="d4311-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
-   <span data-ttu-id="d4311-114">`CorHandleWeakOnly`（仅弱引用到句柄）。</span><span class="sxs-lookup"><span data-stu-id="d4311-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
-   <span data-ttu-id="d4311-115">`CorHandleAll`（所有句柄）。</span><span class="sxs-lookup"><span data-stu-id="d4311-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4311-116">惠?</span><span class="sxs-lookup"><span data-stu-id="d4311-116">Requirements</span></span>  
 <span data-ttu-id="d4311-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4311-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4311-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4311-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4311-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4311-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4311-120">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4311-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4311-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4311-121">See Also</span></span>  
 [<span data-ttu-id="d4311-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="d4311-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="d4311-123">调试</span><span class="sxs-lookup"><span data-stu-id="d4311-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
