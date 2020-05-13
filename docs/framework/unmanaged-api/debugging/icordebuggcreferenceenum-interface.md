---
title: ICorDebugGCReferenceEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
ms.openlocfilehash: 5650a7e6e6cb0108f0d043914ea94debe2b703bf
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213096"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="83d60-102">ICorDebugGCReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="83d60-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="83d60-103">提供针对将进行垃圾回收的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="83d60-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83d60-104">方法</span><span class="sxs-lookup"><span data-stu-id="83d60-104">Methods</span></span>  
  
|<span data-ttu-id="83d60-105">方法</span><span class="sxs-lookup"><span data-stu-id="83d60-105">Method</span></span>|<span data-ttu-id="83d60-106">描述</span><span class="sxs-lookup"><span data-stu-id="83d60-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83d60-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="83d60-107">Next Method</span></span>](icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="83d60-108">获取指定数量的[COR_GC_REFERENCE](cor-gc-reference-structure.md)实例，这些实例包含有关将进行垃圾回收的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="83d60-108">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83d60-109">备注</span><span class="sxs-lookup"><span data-stu-id="83d60-109">Remarks</span></span>  
 <span data-ttu-id="83d60-110">`ICorDebugGCReferenceEnum`接口实现 "ICorDebugEnum" 接口。</span><span class="sxs-lookup"><span data-stu-id="83d60-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="83d60-111">`ICorDebugGCReferenceEnum`实例通过调用[ICorDebugProcess5：： EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md)方法填充[COR_GC_REFERENCE](cor-gc-reference-structure.md)的实例。</span><span class="sxs-lookup"><span data-stu-id="83d60-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="83d60-112">可以通过调用[ICorDebugGCReference：： Next](icordebuggcreferenceenum-next-method.md)方法来枚举[COR_GC_REFERENCE](cor-gc-reference-structure.md)的对象。</span><span class="sxs-lookup"><span data-stu-id="83d60-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="83d60-113">此方法填充的集合中的[COR_GC_REFERENCE](cor-gc-reference-structure.md)对象表示三种对象：</span><span class="sxs-lookup"><span data-stu-id="83d60-113">The [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="83d60-114">所有托管堆栈中的对象。</span><span class="sxs-lookup"><span data-stu-id="83d60-114">Objects from all managed stacks.</span></span> <span data-ttu-id="83d60-115">这包括托管代码中的实时引用以及由公共语言运行时创建的对象。</span><span class="sxs-lookup"><span data-stu-id="83d60-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="83d60-116">句柄表中的对象。</span><span class="sxs-lookup"><span data-stu-id="83d60-116">Objects from the handle table.</span></span> <span data-ttu-id="83d60-117">这包括模块中的强引用（ `HNDTYPE_STRONG` 和 `HNDTYPE_REFCOUNT` ）和静态变量。</span><span class="sxs-lookup"><span data-stu-id="83d60-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="83d60-118">终结器队列中的对象。</span><span class="sxs-lookup"><span data-stu-id="83d60-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="83d60-119">终结器队列根对象，直到终结器运行。</span><span class="sxs-lookup"><span data-stu-id="83d60-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83d60-120">要求</span><span class="sxs-lookup"><span data-stu-id="83d60-120">Requirements</span></span>  
 <span data-ttu-id="83d60-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83d60-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83d60-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83d60-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83d60-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83d60-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83d60-124">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83d60-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d60-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="83d60-125">See also</span></span>

- [<span data-ttu-id="83d60-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="83d60-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
