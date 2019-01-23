---
title: COR_HEAPOBJECT 结构
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34b02dfa3fb0f1e5f4cfadc297194dc4f3160c8a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628469"
---
# <a name="corheapobject-structure"></a><span data-ttu-id="a79c6-102">COR_HEAPOBJECT 结构</span><span class="sxs-lookup"><span data-stu-id="a79c6-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="a79c6-103">提供有关托管堆上的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="a79c6-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a79c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="a79c6-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="a79c6-105">成员</span><span class="sxs-lookup"><span data-stu-id="a79c6-105">Members</span></span>  
  
|<span data-ttu-id="a79c6-106">成员</span><span class="sxs-lookup"><span data-stu-id="a79c6-106">Member</span></span>|<span data-ttu-id="a79c6-107">描述</span><span class="sxs-lookup"><span data-stu-id="a79c6-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="a79c6-108">在内存中对象的地址。</span><span class="sxs-lookup"><span data-stu-id="a79c6-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="a79c6-109">对象，以字节为单位的总大小。</span><span class="sxs-lookup"><span data-stu-id="a79c6-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="a79c6-110">一个[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)表示的对象类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="a79c6-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a79c6-111">备注</span><span class="sxs-lookup"><span data-stu-id="a79c6-111">Remarks</span></span>  
 <span data-ttu-id="a79c6-112">`COR_HEAPOBJECT` 实例可以检索通过枚举[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)接口对象通过调用来填充[ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a79c6-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="a79c6-113">一个`COR_HEAPOBJECT`实例提供了有关托管堆上一个活动对象或不根路径的任何对象，但尚未被垃圾回收器回收的对象有关的信息。</span><span class="sxs-lookup"><span data-stu-id="a79c6-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="a79c6-114">为了提高性能，`COR_HEAPOBJECT.address`字段是`CORDB_ADDRESS`值而不是 ICorDebugValue 接口在很多调试 API 中使用的值。</span><span class="sxs-lookup"><span data-stu-id="a79c6-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="a79c6-115">若要获取给定的对象地址的 ICorDebugValue 对象，可以将传递`CORDB_ADDRESS`值设为[ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a79c6-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="a79c6-116">为了提高性能，`COR_HEAPOBJECT.type`字段是`COR_TYPEID`值而不是 ICorDebugType 接口在很多调试 API 中使用的值。</span><span class="sxs-lookup"><span data-stu-id="a79c6-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="a79c6-117">若要获取给定的类型 ID ICorDebugType 对象，可以将传递`COR_TYPEID`值设为[ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a79c6-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="a79c6-118">`COR_HEAPOBJECT`结构包含引用计数 COM 接口。</span><span class="sxs-lookup"><span data-stu-id="a79c6-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="a79c6-119">如果检索`COR_HEAPOBJECT`通过调用枚举器中的实例[icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)方法，随后必须释放该引用。</span><span class="sxs-lookup"><span data-stu-id="a79c6-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a79c6-120">要求</span><span class="sxs-lookup"><span data-stu-id="a79c6-120">Requirements</span></span>  
 <span data-ttu-id="a79c6-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a79c6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a79c6-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a79c6-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a79c6-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a79c6-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a79c6-124">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a79c6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a79c6-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="a79c6-125">See also</span></span>
- [<span data-ttu-id="a79c6-126">调试结构</span><span class="sxs-lookup"><span data-stu-id="a79c6-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="a79c6-127">调试</span><span class="sxs-lookup"><span data-stu-id="a79c6-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
