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
ms.openlocfilehash: 49f89f7d36e74b1fa5921230d7dc6d271d4c0883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134633"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="0f140-102">ICorDebugGCReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="0f140-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="0f140-103">提供针对将进行垃圾回收的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="0f140-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0f140-104">方法</span><span class="sxs-lookup"><span data-stu-id="0f140-104">Methods</span></span>  
  
|<span data-ttu-id="0f140-105">方法</span><span class="sxs-lookup"><span data-stu-id="0f140-105">Method</span></span>|<span data-ttu-id="0f140-106">描述</span><span class="sxs-lookup"><span data-stu-id="0f140-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f140-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="0f140-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="0f140-108">获取指定数量的[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)实例，其中包含有关将进行垃圾回收的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="0f140-108">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f140-109">备注</span><span class="sxs-lookup"><span data-stu-id="0f140-109">Remarks</span></span>  
 <span data-ttu-id="0f140-110">`ICorDebugGCReferenceEnum` 接口实现 "ICorDebugEnum" 接口。</span><span class="sxs-lookup"><span data-stu-id="0f140-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="0f140-111">`ICorDebugGCReferenceEnum` 实例通过调用[ICorDebugProcess5：： EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)方法填充[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)实例。</span><span class="sxs-lookup"><span data-stu-id="0f140-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="0f140-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)对象可通过调用[ICorDebugGCReference：： Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)方法进行枚举。</span><span class="sxs-lookup"><span data-stu-id="0f140-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="0f140-113">此方法填充的集合中的[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)对象表示三种对象：</span><span class="sxs-lookup"><span data-stu-id="0f140-113">The [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="0f140-114">所有托管堆栈中的对象。</span><span class="sxs-lookup"><span data-stu-id="0f140-114">Objects from all managed stacks.</span></span> <span data-ttu-id="0f140-115">这包括托管代码中的实时引用以及由公共语言运行时创建的对象。</span><span class="sxs-lookup"><span data-stu-id="0f140-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="0f140-116">句柄表中的对象。</span><span class="sxs-lookup"><span data-stu-id="0f140-116">Objects from the handle table.</span></span> <span data-ttu-id="0f140-117">这包括模块中的强引用（`HNDTYPE_STRONG` 和 `HNDTYPE_REFCOUNT`）和静态变量。</span><span class="sxs-lookup"><span data-stu-id="0f140-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="0f140-118">终结器队列中的对象。</span><span class="sxs-lookup"><span data-stu-id="0f140-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="0f140-119">终结器队列根对象，直到终结器运行。</span><span class="sxs-lookup"><span data-stu-id="0f140-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f140-120">要求</span><span class="sxs-lookup"><span data-stu-id="0f140-120">Requirements</span></span>  
 <span data-ttu-id="0f140-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f140-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f140-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f140-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f140-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f140-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f140-124">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f140-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f140-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f140-125">See also</span></span>

- [<span data-ttu-id="0f140-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="0f140-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
