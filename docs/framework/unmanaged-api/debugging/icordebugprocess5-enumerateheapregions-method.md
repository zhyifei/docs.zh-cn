---
title: "ICorDebugProcess5::EnumerateHeapRegions 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateHeapRegions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1365ed5fd8cf308716b16d78e79a26584bd966c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="f661a-102">ICorDebugProcess5::EnumerateHeapRegions 方法</span><span class="sxs-lookup"><span data-stu-id="f661a-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="f661a-103">获取托管堆的内存范围的枚举数。</span><span class="sxs-lookup"><span data-stu-id="f661a-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f661a-104">语法</span><span class="sxs-lookup"><span data-stu-id="f661a-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f661a-105">参数</span><span class="sxs-lookup"><span data-stu-id="f661a-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="f661a-106">[out]指向的地址的指针[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)接口对象，它的对象位于托管堆的内存范围的枚举数。</span><span class="sxs-lookup"><span data-stu-id="f661a-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f661a-107">备注</span><span class="sxs-lookup"><span data-stu-id="f661a-107">Remarks</span></span>  
 <span data-ttu-id="f661a-108">之前调用`ICorDebugProcess5::EnumerateHeapRegions`方法时，应调用[icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)方法并检查的值的`areGCStructuresValid`字段返回[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)要确保其当前状态中的垃圾回收堆是可枚举对象。</span><span class="sxs-lookup"><span data-stu-id="f661a-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="f661a-109">此外，`ICorDebugProcess5::EnumerateHeapRegions`方法返回`E_FAIL`如果附加的进程的生存期内太早，内存区域创建之前。</span><span class="sxs-lookup"><span data-stu-id="f661a-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="f661a-110">此方法可得到保证，可能包含托管的对象的所有内存区域进行枚举，但它无法保障托管的对象实际驻留在这些区域中。</span><span class="sxs-lookup"><span data-stu-id="f661a-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="f661a-111">[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)集合对象可能包含空或保留的内存区域。</span><span class="sxs-lookup"><span data-stu-id="f661a-111">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="f661a-112">[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)接口对象是从使您能够枚举 ICorDebugEnum 接口派生的标准枚举器[COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)对象。</span><span class="sxs-lookup"><span data-stu-id="f661a-112">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) objects.</span></span> <span data-ttu-id="f661a-113">每个[COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)对象提供了特定分段，以及该片段中的对象的代的内存范围信息。</span><span class="sxs-lookup"><span data-stu-id="f661a-113">Each [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f661a-114">要求</span><span class="sxs-lookup"><span data-stu-id="f661a-114">Requirements</span></span>  
 <span data-ttu-id="f661a-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f661a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f661a-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f661a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f661a-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f661a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f661a-118">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f661a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f661a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f661a-119">See Also</span></span>  
 [<span data-ttu-id="f661a-120">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="f661a-120">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="f661a-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="f661a-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
