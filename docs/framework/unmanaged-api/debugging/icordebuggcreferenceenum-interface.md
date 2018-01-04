---
title: "ICorDebugGCReferenceEnum 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGCReferenceEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGCReferenceEnum
helpviewer_keywords: ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1afe52c3df8f61b234b3c68ee819ba8389593c82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="af19d-102">ICorDebugGCReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="af19d-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="af19d-103">提供针对将进行垃圾回收的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="af19d-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af19d-104">方法</span><span class="sxs-lookup"><span data-stu-id="af19d-104">Methods</span></span>  
  
|<span data-ttu-id="af19d-105">方法</span><span class="sxs-lookup"><span data-stu-id="af19d-105">Method</span></span>|<span data-ttu-id="af19d-106">描述</span><span class="sxs-lookup"><span data-stu-id="af19d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af19d-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="af19d-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="af19d-108">获取指定的数目的[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)包含有关将进行垃圾回收的对象的信息的实例。</span><span class="sxs-lookup"><span data-stu-id="af19d-108">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af19d-109">备注</span><span class="sxs-lookup"><span data-stu-id="af19d-109">Remarks</span></span>  
 <span data-ttu-id="af19d-110">`ICorDebugGCReferenceEnum`接口实现"ICorDebugEnum"接口。</span><span class="sxs-lookup"><span data-stu-id="af19d-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="af19d-111">`ICorDebugGCReferenceEnum`实例填入[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)实例通过调用[icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="af19d-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="af19d-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)对象可以通过调用枚举[ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="af19d-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="af19d-113">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)填充此方法对集合中的对象表示三种类型的对象：</span><span class="sxs-lookup"><span data-stu-id="af19d-113">The [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
-   <span data-ttu-id="af19d-114">从所有托管堆栈的对象。</span><span class="sxs-lookup"><span data-stu-id="af19d-114">Objects from all managed stacks.</span></span> <span data-ttu-id="af19d-115">这包括实时引用中托管的代码，以及由公共语言运行时创建的对象。</span><span class="sxs-lookup"><span data-stu-id="af19d-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
-   <span data-ttu-id="af19d-116">来自句柄表的对象。</span><span class="sxs-lookup"><span data-stu-id="af19d-116">Objects from the handle table.</span></span> <span data-ttu-id="af19d-117">这包括的强引用 (`HNDTYPE_STRONG`和`HNDTYPE_REFCOUNT`) 和模块中的静态变量。</span><span class="sxs-lookup"><span data-stu-id="af19d-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
-   <span data-ttu-id="af19d-118">终结器队列中的对象。</span><span class="sxs-lookup"><span data-stu-id="af19d-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="af19d-119">终结器队列根对象，直到运行终结器。</span><span class="sxs-lookup"><span data-stu-id="af19d-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af19d-120">惠?</span><span class="sxs-lookup"><span data-stu-id="af19d-120">Requirements</span></span>  
 <span data-ttu-id="af19d-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af19d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af19d-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af19d-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af19d-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af19d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af19d-124">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af19d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af19d-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="af19d-125">See Also</span></span>  
 [<span data-ttu-id="af19d-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="af19d-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
