---
title: ICorDebugHeapEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25f352a3a6dfae69116d6cda2497d55485b951cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417058"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="1fe7a-102">ICorDebugHeapEnum 接口</span><span class="sxs-lookup"><span data-stu-id="1fe7a-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="1fe7a-103">提供针对托管堆上的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="1fe7a-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="1fe7a-104">此接口是 ICorDebugEnum 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="1fe7a-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1fe7a-105">方法</span><span class="sxs-lookup"><span data-stu-id="1fe7a-105">Methods</span></span>  
  
|<span data-ttu-id="1fe7a-106">方法</span><span class="sxs-lookup"><span data-stu-id="1fe7a-106">Method</span></span>|<span data-ttu-id="1fe7a-107">描述</span><span class="sxs-lookup"><span data-stu-id="1fe7a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1fe7a-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="1fe7a-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|<span data-ttu-id="1fe7a-109">获取指定的数目的[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)包含托管堆上对象的信息的实例。</span><span class="sxs-lookup"><span data-stu-id="1fe7a-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fe7a-110">备注</span><span class="sxs-lookup"><span data-stu-id="1fe7a-110">Remarks</span></span>  
 <span data-ttu-id="1fe7a-111">`ICorDebugHeapEnum`接口实现 ICorDebugEnum 接口。</span><span class="sxs-lookup"><span data-stu-id="1fe7a-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="1fe7a-112">`ICorDebugHeapEnum`实例填入[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)实例通过调用[icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1fe7a-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="1fe7a-113">每个[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)集合中的实例表示在堆上的实时对象，或者不根路径的任何对象，但尚未被垃圾回收器回收的对象。</span><span class="sxs-lookup"><span data-stu-id="1fe7a-113">Each [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="1fe7a-114">[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)集合中的对象可以通过调用枚举[icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1fe7a-114">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fe7a-115">要求</span><span class="sxs-lookup"><span data-stu-id="1fe7a-115">Requirements</span></span>  
 <span data-ttu-id="1fe7a-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1fe7a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fe7a-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fe7a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fe7a-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fe7a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fe7a-119">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fe7a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fe7a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fe7a-120">See Also</span></span>  
 [<span data-ttu-id="1fe7a-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="1fe7a-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
