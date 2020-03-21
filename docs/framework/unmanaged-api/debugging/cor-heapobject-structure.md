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
ms.openlocfilehash: efb3d913e1d8ef0c486d7e5e1d9777ae7d88bc71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179339"
---
# <a name="cor_heapobject-structure"></a><span data-ttu-id="0f73b-102">COR_HEAPOBJECT 结构</span><span class="sxs-lookup"><span data-stu-id="0f73b-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="0f73b-103">提供有关托管堆上的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="0f73b-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f73b-104">语法</span><span class="sxs-lookup"><span data-stu-id="0f73b-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="0f73b-105">成员</span><span class="sxs-lookup"><span data-stu-id="0f73b-105">Members</span></span>  
  
|<span data-ttu-id="0f73b-106">成员</span><span class="sxs-lookup"><span data-stu-id="0f73b-106">Member</span></span>|<span data-ttu-id="0f73b-107">说明</span><span class="sxs-lookup"><span data-stu-id="0f73b-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="0f73b-108">内存中对象的地址。</span><span class="sxs-lookup"><span data-stu-id="0f73b-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="0f73b-109">对象的总大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="0f73b-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="0f73b-110">表示对象类型的[COR_TYPEID](cor-typeid-structure.md)令牌。</span><span class="sxs-lookup"><span data-stu-id="0f73b-110">A [COR_TYPEID](cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f73b-111">备注</span><span class="sxs-lookup"><span data-stu-id="0f73b-111">Remarks</span></span>  
 <span data-ttu-id="0f73b-112">`COR_HEAPOBJECT`可以通过枚举[ICorDebugHeapEnum](icordebugheapenum-interface.md)接口对象来检索实例，该接口对象通过调用[ICorDebugProcess5：：：枚举堆](icordebugprocess5-enumerateheap-method.md)方法填充。</span><span class="sxs-lookup"><span data-stu-id="0f73b-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="0f73b-113">实例`COR_HEAPOBJECT`提供有关托管堆上的实时对象的信息，或者提供有关未由任何对象扎根但尚未由垃圾回收器收集的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="0f73b-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="0f73b-114">为了更好的性能，该`COR_HEAPOBJECT.address`字段是一`CORDB_ADDRESS`个值，而不是许多调试 API 中使用的 ICorDebugValue 接口值。</span><span class="sxs-lookup"><span data-stu-id="0f73b-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="0f73b-115">要获取给定对象地址的 ICorDebugValue 对象，可以将`CORDB_ADDRESS`该值传递给[ICorDebugProcess5：：：getObject](icordebugprocess5-getobject-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0f73b-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="0f73b-116">为了更好的性能，该`COR_HEAPOBJECT.type`字段是一`COR_TYPEID`个值，而不是许多调试 API 中使用的 ICorDebugType 接口值。</span><span class="sxs-lookup"><span data-stu-id="0f73b-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="0f73b-117">要获取给定类型 ID 的 ICorDebugType 对象，可以将`COR_TYPEID`该值传递给[ICorDebugProcess5：：getTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0f73b-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="0f73b-118">该`COR_HEAPOBJECT`结构包括一个引用计数的COM接口。</span><span class="sxs-lookup"><span data-stu-id="0f73b-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="0f73b-119">如果通过调用`COR_HEAPOBJECT`[ICorDebugHeapEnum：Next](icordebugheapenum-next-method.md)方法从枚举器检索实例，则必须随后释放引用。</span><span class="sxs-lookup"><span data-stu-id="0f73b-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f73b-120">要求</span><span class="sxs-lookup"><span data-stu-id="0f73b-120">Requirements</span></span>  
 <span data-ttu-id="0f73b-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f73b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f73b-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f73b-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f73b-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f73b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f73b-124">**.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f73b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f73b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f73b-125">See also</span></span>

- [<span data-ttu-id="0f73b-126">调试结构</span><span class="sxs-lookup"><span data-stu-id="0f73b-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="0f73b-127">调试</span><span class="sxs-lookup"><span data-stu-id="0f73b-127">Debugging</span></span>](index.md)
