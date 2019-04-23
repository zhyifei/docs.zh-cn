---
title: ICorDebugHeapSegmentEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73036d1c12c46cbfda8031073a005bc9b376040e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137639"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="531c8-102">ICorDebugHeapSegmentEnum 接口</span><span class="sxs-lookup"><span data-stu-id="531c8-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="531c8-103">提供针对托管堆的内存区域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="531c8-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="531c8-104">此接口是 ICorDebugEnum 接口子类。</span><span class="sxs-lookup"><span data-stu-id="531c8-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="531c8-105">方法</span><span class="sxs-lookup"><span data-stu-id="531c8-105">Methods</span></span>  
  
|<span data-ttu-id="531c8-106">方法</span><span class="sxs-lookup"><span data-stu-id="531c8-106">Method</span></span>|<span data-ttu-id="531c8-107">描述</span><span class="sxs-lookup"><span data-stu-id="531c8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="531c8-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="531c8-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="531c8-109">获取指定的数目的[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)包含有关区域托管堆的信息的实例。</span><span class="sxs-lookup"><span data-stu-id="531c8-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="531c8-110">备注</span><span class="sxs-lookup"><span data-stu-id="531c8-110">Remarks</span></span>  
 <span data-ttu-id="531c8-111">`ICorDebugHeapSegmentEnum`接口实现 ICorDebugEnum 接口。</span><span class="sxs-lookup"><span data-stu-id="531c8-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="531c8-112">`ICorDebugHeapSegmentEnum`实例中填入[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)实例通过调用[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="531c8-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="531c8-113">[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)集合中的对象可以通过调用枚举[icordebugheapsegmentenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="531c8-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="531c8-114">`ICorDebugHeapSegmentEnum`集合对象枚举所有可能包含托管的对象的内存区域，但它不保证托管的对象实际驻留在这些区域中。</span><span class="sxs-lookup"><span data-stu-id="531c8-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="531c8-115">它可能包括有关空的或保留的内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="531c8-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="531c8-116">要求</span><span class="sxs-lookup"><span data-stu-id="531c8-116">Requirements</span></span>  
 <span data-ttu-id="531c8-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="531c8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="531c8-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="531c8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="531c8-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="531c8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="531c8-120">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="531c8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="531c8-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="531c8-121">See also</span></span>

- [<span data-ttu-id="531c8-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="531c8-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
