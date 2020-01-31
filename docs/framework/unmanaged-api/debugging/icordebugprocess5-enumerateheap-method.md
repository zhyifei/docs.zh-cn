---
title: ICorDebugProcess5::EnumerateHeap 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
ms.openlocfilehash: 780f9eb0984e35c4487d770b5e7ff33917cf07ed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792417"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="41b17-102">ICorDebugProcess5::EnumerateHeap 方法</span><span class="sxs-lookup"><span data-stu-id="41b17-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="41b17-103">获取托管堆上的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="41b17-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41b17-104">语法</span><span class="sxs-lookup"><span data-stu-id="41b17-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41b17-105">参数</span><span class="sxs-lookup"><span data-stu-id="41b17-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="41b17-106">弄指向[ICorDebugHeapEnum](icordebugheapenum-interface.md)接口对象地址的指针，该接口对象是驻留在托管堆上的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="41b17-106">[out] A pointer to the address of an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41b17-107">备注</span><span class="sxs-lookup"><span data-stu-id="41b17-107">Remarks</span></span>  
 <span data-ttu-id="41b17-108">在调用 `ICorDebugProcess5::EnumerateHeap` 方法之前，应调用[ICorDebugProcess5：： GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md)方法，并检查返回的[COR_HEAPINFO](cor-heapinfo-structure.md)对象的 `areGCStructuresValid` 字段的值，以确保其当前状态的垃圾回收堆可枚举。</span><span class="sxs-lookup"><span data-stu-id="41b17-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="41b17-109">此外，如果在进程的生存期内附加过早，则 `ICorDebugProcess5::EnumerateHeap` 返回 `E_FAIL`，在分配托管堆的内存之前。</span><span class="sxs-lookup"><span data-stu-id="41b17-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="41b17-110">[ICorDebugHeapEnum](icordebugheapenum-interface.md)接口对象是从 ICorDebugEnum 接口派生的标准枚举器，该枚举器可用于枚举[COR_HEAPOBJECT](cor-heapobject-structure.md)的对象。</span><span class="sxs-lookup"><span data-stu-id="41b17-110">The [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="41b17-111">此方法用提供所有对象的相关信息[COR_HEAPOBJECT](cor-heapobject-structure.md)实例填充[ICorDebugHeapEnum](icordebugheapenum-interface.md)集合对象。</span><span class="sxs-lookup"><span data-stu-id="41b17-111">This method populates the [ICorDebugHeapEnum](icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="41b17-112">集合还可以包含[COR_HEAPOBJECT](cor-heapobject-structure.md)实例，这些实例提供有关非对象的根对象，但未被垃圾回收器收集的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="41b17-112">The collection may also include [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41b17-113">需求</span><span class="sxs-lookup"><span data-stu-id="41b17-113">Requirements</span></span>  
 <span data-ttu-id="41b17-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="41b17-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41b17-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41b17-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41b17-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41b17-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41b17-117">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41b17-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41b17-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41b17-118">See also</span></span>

- [<span data-ttu-id="41b17-119">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="41b17-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="41b17-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="41b17-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
