---
title: ICorDebugProcess5::EnumerateHandles 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f2177702c6c5999033d0852a932e52c0725fb8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422654"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="c22f6-102">ICorDebugProcess5::EnumerateHandles 方法</span><span class="sxs-lookup"><span data-stu-id="c22f6-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="c22f6-103">在进程中获取对象句柄的枚举数。</span><span class="sxs-lookup"><span data-stu-id="c22f6-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c22f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="c22f6-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c22f6-105">参数</span><span class="sxs-lookup"><span data-stu-id="c22f6-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="c22f6-106">[in]按位组合[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)指定的句柄以包含在集合中的类型的值。</span><span class="sxs-lookup"><span data-stu-id="c22f6-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="c22f6-107">[out]指向的地址的指针[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)即的枚举数对象要进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="c22f6-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c22f6-108">备注</span><span class="sxs-lookup"><span data-stu-id="c22f6-108">Remarks</span></span>  
 <span data-ttu-id="c22f6-109">`EnumerateHandles` 是一个 helper 函数，支持的句柄表的检查。</span><span class="sxs-lookup"><span data-stu-id="c22f6-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="c22f6-110">它是类似于[icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)方法，只不过而不是填充[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)集合的所有对象要进行垃圾回收，它包括具有来自句柄表的句柄的对象。</span><span class="sxs-lookup"><span data-stu-id="c22f6-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="c22f6-111">`types`参数指定要包含在集合中的句柄类型。</span><span class="sxs-lookup"><span data-stu-id="c22f6-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="c22f6-112">`types` 可以是任何的以下三个成员[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)枚举：</span><span class="sxs-lookup"><span data-stu-id="c22f6-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
-   <span data-ttu-id="c22f6-113">`CorHandleStrongOnly` （仅引用强句柄）。</span><span class="sxs-lookup"><span data-stu-id="c22f6-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
-   <span data-ttu-id="c22f6-114">`CorHandleWeakOnly` （仅弱引用到句柄）。</span><span class="sxs-lookup"><span data-stu-id="c22f6-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
-   <span data-ttu-id="c22f6-115">`CorHandleAll` （所有句柄）。</span><span class="sxs-lookup"><span data-stu-id="c22f6-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c22f6-116">要求</span><span class="sxs-lookup"><span data-stu-id="c22f6-116">Requirements</span></span>  
 <span data-ttu-id="c22f6-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c22f6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c22f6-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c22f6-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c22f6-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c22f6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c22f6-120">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c22f6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c22f6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="c22f6-121">See Also</span></span>  
 [<span data-ttu-id="c22f6-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="c22f6-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="c22f6-123">调试</span><span class="sxs-lookup"><span data-stu-id="c22f6-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
