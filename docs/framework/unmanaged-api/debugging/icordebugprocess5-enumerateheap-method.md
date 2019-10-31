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
ms.openlocfilehash: c8cfc9cdf6580a002f6ac15080012a9e8c63be20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129653"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="07098-102">ICorDebugProcess5::EnumerateHeap 方法</span><span class="sxs-lookup"><span data-stu-id="07098-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="07098-103">获取托管堆上的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="07098-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07098-104">语法</span><span class="sxs-lookup"><span data-stu-id="07098-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07098-105">参数</span><span class="sxs-lookup"><span data-stu-id="07098-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="07098-106">弄指向[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)接口对象地址的指针，该接口对象是驻留在托管堆上的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="07098-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07098-107">备注</span><span class="sxs-lookup"><span data-stu-id="07098-107">Remarks</span></span>  
 <span data-ttu-id="07098-108">在调用 `ICorDebugProcess5::EnumerateHeap` 方法之前，应调用[ICorDebugProcess5：： GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)方法，并检查返回的[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)对象的 `areGCStructuresValid` 字段的值，以确保其当前状态为可枚举。</span><span class="sxs-lookup"><span data-stu-id="07098-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="07098-109">此外，如果在进程的生存期内附加过早，则 `ICorDebugProcess5::EnumerateHeap` 返回 `E_FAIL`，在分配托管堆的内存之前。</span><span class="sxs-lookup"><span data-stu-id="07098-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="07098-110">[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)接口对象是从 ICorDebugEnum 接口派生的标准枚举器，该枚举器可用于枚举[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)对象。</span><span class="sxs-lookup"><span data-stu-id="07098-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="07098-111">此方法用提供所有对象相关信息的[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)实例填充[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)集合对象。</span><span class="sxs-lookup"><span data-stu-id="07098-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="07098-112">集合还可以包含[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)实例，这些实例提供的信息不是任何对象的根对象，但尚未被垃圾回收器收集。</span><span class="sxs-lookup"><span data-stu-id="07098-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07098-113">要求</span><span class="sxs-lookup"><span data-stu-id="07098-113">Requirements</span></span>  
 <span data-ttu-id="07098-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07098-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07098-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07098-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07098-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07098-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07098-117">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07098-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07098-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="07098-118">See also</span></span>

- [<span data-ttu-id="07098-119">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="07098-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="07098-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="07098-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
