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
ms.openlocfilehash: a6552bde30bf3363f1a5a25788fba99e473975c7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616275"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="43c00-102">ICorDebugProcess5::EnumerateHandles 方法</span><span class="sxs-lookup"><span data-stu-id="43c00-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="43c00-103">获取可枚举对象句柄的进程中。</span><span class="sxs-lookup"><span data-stu-id="43c00-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c00-104">语法</span><span class="sxs-lookup"><span data-stu-id="43c00-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43c00-105">参数</span><span class="sxs-lookup"><span data-stu-id="43c00-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="43c00-106">[in]按位组合[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)值，该值指定要包含在集合中的句柄的类型。</span><span class="sxs-lookup"><span data-stu-id="43c00-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="43c00-107">[out]指向的地址的指针[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) ，它是一个枚举器的对象进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="43c00-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43c00-108">备注</span><span class="sxs-lookup"><span data-stu-id="43c00-108">Remarks</span></span>  
 <span data-ttu-id="43c00-109">`EnumerateHandles` 是一个帮助程序函数支持的句柄表的检查。</span><span class="sxs-lookup"><span data-stu-id="43c00-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="43c00-110">它是类似于[ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)方法，不同之处在于而不是填充[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)集合的所有对象进行垃圾回收它包括具有来自句柄表的句柄的对象。</span><span class="sxs-lookup"><span data-stu-id="43c00-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="43c00-111">`types`参数指定要包含在集合中的句柄类型。</span><span class="sxs-lookup"><span data-stu-id="43c00-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="43c00-112">`types` 可以是任何以下三个成员[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)枚举：</span><span class="sxs-lookup"><span data-stu-id="43c00-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="43c00-113">`CorHandleStrongOnly` （仅限强引用到句柄）。</span><span class="sxs-lookup"><span data-stu-id="43c00-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="43c00-114">`CorHandleWeakOnly` （仅限弱引用到句柄）。</span><span class="sxs-lookup"><span data-stu-id="43c00-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="43c00-115">`CorHandleAll` （所有句柄）。</span><span class="sxs-lookup"><span data-stu-id="43c00-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43c00-116">要求</span><span class="sxs-lookup"><span data-stu-id="43c00-116">Requirements</span></span>  
 <span data-ttu-id="43c00-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43c00-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43c00-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43c00-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43c00-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43c00-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43c00-120">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43c00-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c00-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="43c00-121">See also</span></span>

- [<span data-ttu-id="43c00-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="43c00-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="43c00-123">调试</span><span class="sxs-lookup"><span data-stu-id="43c00-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
