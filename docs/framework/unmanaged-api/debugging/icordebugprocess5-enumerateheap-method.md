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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b404b7762e085eb44f0bd3b448fcee9eab9a3c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103904"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="34325-102">ICorDebugProcess5::EnumerateHeap 方法</span><span class="sxs-lookup"><span data-stu-id="34325-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="34325-103">获取托管堆上对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="34325-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34325-104">语法</span><span class="sxs-lookup"><span data-stu-id="34325-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34325-105">参数</span><span class="sxs-lookup"><span data-stu-id="34325-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="34325-106">[out]指向的地址的指针[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)接口对象，它驻留在托管堆对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="34325-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34325-107">备注</span><span class="sxs-lookup"><span data-stu-id="34325-107">Remarks</span></span>  
 <span data-ttu-id="34325-108">然后再调用`ICorDebugProcess5::EnumerateHeap`方法时，应调用[ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)方法，并检查的值`areGCStructuresValid`所返回的字段[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)若要确保在其当前状态中的垃圾回收堆是可枚举的对象。</span><span class="sxs-lookup"><span data-stu-id="34325-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="34325-109">此外，`ICorDebugProcess5::EnumerateHeap`返回`E_FAIL`如果则附加在进程内存之前的生命周期的过早地分配托管的堆。</span><span class="sxs-lookup"><span data-stu-id="34325-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="34325-110">[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)接口对象是派生自 ICorDebugEnum 接口，可用于枚举的标准枚举数[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)对象。</span><span class="sxs-lookup"><span data-stu-id="34325-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="34325-111">此方法填充[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)集合对象与[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)提供信息有关的所有对象的实例。</span><span class="sxs-lookup"><span data-stu-id="34325-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="34325-112">集合还可能包括[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)提供不按任何根路径的对象的信息的实例对象，但尚未由垃圾回收器回收。</span><span class="sxs-lookup"><span data-stu-id="34325-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34325-113">要求</span><span class="sxs-lookup"><span data-stu-id="34325-113">Requirements</span></span>  
 <span data-ttu-id="34325-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34325-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34325-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34325-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34325-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34325-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="34325-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="34325-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="34325-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="34325-118">See also</span></span>

- [<span data-ttu-id="34325-119">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="34325-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="34325-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="34325-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
