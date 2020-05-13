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
ms.openlocfilehash: 50b0859d6727a25906f2c8b0f3fe96da228ab886
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213551"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="087f2-102">ICorDebugProcess5::EnumerateHeapRegions 方法</span><span class="sxs-lookup"><span data-stu-id="087f2-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="087f2-103">获取托管堆的内存范围的枚举器。</span><span class="sxs-lookup"><span data-stu-id="087f2-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="087f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="087f2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="087f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="087f2-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="087f2-106">弄指向[ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)接口对象地址的指针，该对象是对象驻留在托管堆中的内存范围的枚举器。</span><span class="sxs-lookup"><span data-stu-id="087f2-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="087f2-107">备注</span><span class="sxs-lookup"><span data-stu-id="087f2-107">Remarks</span></span>  
 <span data-ttu-id="087f2-108">在调用 `ICorDebugProcess5::EnumerateHeapRegions` 方法之前，应调用[ICorDebugProcess5：： GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md)方法，并检查 `areGCStructuresValid` 返回[COR_HEAPINFO](cor-heapinfo-structure.md)对象的字段值，以确保其当前状态的垃圾回收堆可枚举。</span><span class="sxs-lookup"><span data-stu-id="087f2-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="087f2-109">此外，如果在 `ICorDebugProcess5::EnumerateHeapRegions` 进程的 `E_FAIL` 生存期内附加过早，则在创建内存区域之前，此方法返回。</span><span class="sxs-lookup"><span data-stu-id="087f2-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="087f2-110">此方法保证可以枚举可能包含托管对象的所有内存区域，但不保证托管对象实际驻留在这些区域中。</span><span class="sxs-lookup"><span data-stu-id="087f2-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="087f2-111">[ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)集合对象可能包含空的或保留的内存区域。</span><span class="sxs-lookup"><span data-stu-id="087f2-111">The [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="087f2-112">[ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)接口对象是从 ICorDebugEnum 接口派生的标准枚举器，该枚举器可用于枚举[COR_SEGMENT](cor-segment-structure.md)的对象。</span><span class="sxs-lookup"><span data-stu-id="087f2-112">The [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](cor-segment-structure.md) objects.</span></span> <span data-ttu-id="087f2-113">每个[COR_SEGMENT](cor-segment-structure.md)对象均提供有关特定段的内存范围以及该段中的对象的生成信息。</span><span class="sxs-lookup"><span data-stu-id="087f2-113">Each [COR_SEGMENT](cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="087f2-114">要求</span><span class="sxs-lookup"><span data-stu-id="087f2-114">Requirements</span></span>  
 <span data-ttu-id="087f2-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="087f2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="087f2-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="087f2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="087f2-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="087f2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="087f2-118">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="087f2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="087f2-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="087f2-119">See also</span></span>

- [<span data-ttu-id="087f2-120">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="087f2-120">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="087f2-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="087f2-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
