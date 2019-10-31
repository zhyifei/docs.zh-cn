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
ms.openlocfilehash: 3ab4da3fcf43731587dae6f3a8e82ea48c5ee1ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129641"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="fb112-102">ICorDebugProcess5::EnumerateHeapRegions 方法</span><span class="sxs-lookup"><span data-stu-id="fb112-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="fb112-103">获取托管堆的内存范围的枚举器。</span><span class="sxs-lookup"><span data-stu-id="fb112-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb112-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb112-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb112-105">参数</span><span class="sxs-lookup"><span data-stu-id="fb112-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="fb112-106">弄指向[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)接口对象地址的指针，该对象是对象驻留在托管堆中的内存范围的枚举器。</span><span class="sxs-lookup"><span data-stu-id="fb112-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb112-107">备注</span><span class="sxs-lookup"><span data-stu-id="fb112-107">Remarks</span></span>  
 <span data-ttu-id="fb112-108">在调用 `ICorDebugProcess5::EnumerateHeapRegions` 方法之前，应调用[ICorDebugProcess5：： GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)方法，并检查返回的[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)对象的 `areGCStructuresValid` 字段的值，以确保其当前状态为可枚举。</span><span class="sxs-lookup"><span data-stu-id="fb112-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="fb112-109">此外，如果在进程的生存期内附加过早，则在创建内存区域之前，`ICorDebugProcess5::EnumerateHeapRegions` 方法返回 `E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="fb112-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="fb112-110">此方法保证可以枚举可能包含托管对象的所有内存区域，但不保证托管对象实际驻留在这些区域中。</span><span class="sxs-lookup"><span data-stu-id="fb112-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="fb112-111">[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)集合对象可能包含空的或保留的内存区域。</span><span class="sxs-lookup"><span data-stu-id="fb112-111">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="fb112-112">[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)接口对象是从 ICorDebugEnum 接口派生的标准枚举器，该枚举器可用于枚举[COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)对象。</span><span class="sxs-lookup"><span data-stu-id="fb112-112">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) objects.</span></span> <span data-ttu-id="fb112-113">每个[COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)对象都提供有关特定段的内存范围以及该段中的对象的生成信息。</span><span class="sxs-lookup"><span data-stu-id="fb112-113">Each [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb112-114">要求</span><span class="sxs-lookup"><span data-stu-id="fb112-114">Requirements</span></span>  
 <span data-ttu-id="fb112-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb112-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb112-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb112-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb112-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb112-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb112-118">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb112-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb112-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb112-119">See also</span></span>

- [<span data-ttu-id="fb112-120">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="fb112-120">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="fb112-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="fb112-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
