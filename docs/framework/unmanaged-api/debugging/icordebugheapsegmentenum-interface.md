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
ms.openlocfilehash: 0a5a87c71bea603073c35dd851e443ca8c497523
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210431"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="0d3df-102">ICorDebugHeapSegmentEnum 接口</span><span class="sxs-lookup"><span data-stu-id="0d3df-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="0d3df-103">提供针对托管堆的内存区域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="0d3df-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="0d3df-104">此接口是 ICorDebugEnum 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="0d3df-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d3df-105">方法</span><span class="sxs-lookup"><span data-stu-id="0d3df-105">Methods</span></span>  
  
|<span data-ttu-id="0d3df-106">方法</span><span class="sxs-lookup"><span data-stu-id="0d3df-106">Method</span></span>|<span data-ttu-id="0d3df-107">描述</span><span class="sxs-lookup"><span data-stu-id="0d3df-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d3df-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="0d3df-108">Next Method</span></span>](icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="0d3df-109">获取指定数量的[COR_HEAPOBJECT](cor-heapobject-structure.md)实例，这些实例包含有关托管堆区域的信息。</span><span class="sxs-lookup"><span data-stu-id="0d3df-109">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d3df-110">备注</span><span class="sxs-lookup"><span data-stu-id="0d3df-110">Remarks</span></span>  
 <span data-ttu-id="0d3df-111">`ICorDebugHeapSegmentEnum`接口实现 ICorDebugEnum 接口。</span><span class="sxs-lookup"><span data-stu-id="0d3df-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="0d3df-112">`ICorDebugHeapSegmentEnum`实例通过调用[ICorDebugProcess5：： EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md)方法填充[COR_HEAPOBJECT](cor-heapobject-structure.md)的实例。</span><span class="sxs-lookup"><span data-stu-id="0d3df-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="0d3df-113">可以通过调用[ICorDebugHeapSegmentEnum：： Next](icordebugheapsegmentenum-next-method.md)方法枚举集合中的[COR_HEAPOBJECT](cor-heapobject-structure.md)对象。</span><span class="sxs-lookup"><span data-stu-id="0d3df-113">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="0d3df-114">`ICorDebugHeapSegmentEnum`集合对象枚举可能包含托管对象的所有内存区域，但不保证托管对象实际驻留在这些区域中。</span><span class="sxs-lookup"><span data-stu-id="0d3df-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="0d3df-115">它可能包括有关空的或保留的内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="0d3df-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d3df-116">要求</span><span class="sxs-lookup"><span data-stu-id="0d3df-116">Requirements</span></span>  
 <span data-ttu-id="0d3df-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0d3df-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d3df-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d3df-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d3df-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d3df-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d3df-120">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d3df-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d3df-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d3df-121">See also</span></span>

- [<span data-ttu-id="0d3df-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="0d3df-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
