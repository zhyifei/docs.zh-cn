---
title: ICorDebugProcess5::EnumerateHeapRegions 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c05ebc819d5fdd40ec20e62ece9f556244d914c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661030"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="9a907-102">ICorDebugProcess5::EnumerateHeapRegions 方法</span><span class="sxs-lookup"><span data-stu-id="9a907-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="9a907-103">获取托管堆的内存范围的枚举器。</span><span class="sxs-lookup"><span data-stu-id="9a907-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a907-104">语法</span><span class="sxs-lookup"><span data-stu-id="9a907-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a907-105">参数</span><span class="sxs-lookup"><span data-stu-id="9a907-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="9a907-106">[out]指向的地址的指针[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)接口对象，它的对象位于托管堆的内存范围的枚举器。</span><span class="sxs-lookup"><span data-stu-id="9a907-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a907-107">备注</span><span class="sxs-lookup"><span data-stu-id="9a907-107">Remarks</span></span>  
 <span data-ttu-id="9a907-108">然后再调用`ICorDebugProcess5::EnumerateHeapRegions`方法时，应调用[ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)方法，并检查的值`areGCStructuresValid`所返回的字段[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)若要确保在其当前状态中的垃圾回收堆是可枚举的对象。</span><span class="sxs-lookup"><span data-stu-id="9a907-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="9a907-109">此外，`ICorDebugProcess5::EnumerateHeapRegions`方法将返回`E_FAIL`附加过早地在进程生存期内，如果内存区域在创建前。</span><span class="sxs-lookup"><span data-stu-id="9a907-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="9a907-110">此方法保证将枚举所有可能包含托管的对象的内存区域，但它不保证托管的对象实际驻留在这些区域中。</span><span class="sxs-lookup"><span data-stu-id="9a907-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="9a907-111">[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)集合对象可能包含空的或保留的内存区域。</span><span class="sxs-lookup"><span data-stu-id="9a907-111">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="9a907-112">[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)接口对象是派生自 ICorDebugEnum 接口，可用于枚举的标准枚举数[COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)对象。</span><span class="sxs-lookup"><span data-stu-id="9a907-112">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) objects.</span></span> <span data-ttu-id="9a907-113">每个[COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)对象提供有关特定数据段，以及在该时间段中的对象的代的内存范围信息。</span><span class="sxs-lookup"><span data-stu-id="9a907-113">Each [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a907-114">要求</span><span class="sxs-lookup"><span data-stu-id="9a907-114">Requirements</span></span>  
 <span data-ttu-id="9a907-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9a907-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a907-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a907-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a907-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a907-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a907-118">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a907-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a907-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a907-119">See also</span></span>
- [<span data-ttu-id="9a907-120">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="9a907-120">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="9a907-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="9a907-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
