---
title: ICorDebugProcess5 接口
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3aed85e989313e4778e12a6f6bb789ccef49747
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423366"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="07cd0-102">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="07cd0-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="07cd0-103">扩展 ICorDebugProcess 接口以支持对托管堆，以提供有关垃圾回收的托管对象的信息的访问，并确定调试器是否从应用程序本地本机映像缓存加载映像。</span><span class="sxs-lookup"><span data-stu-id="07cd0-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07cd0-104">方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-104">Methods</span></span>  
  
|<span data-ttu-id="07cd0-105">方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-105">Method</span></span>|<span data-ttu-id="07cd0-106">描述</span><span class="sxs-lookup"><span data-stu-id="07cd0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07cd0-107">EnableNGenPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-107">EnableNGenPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="07cd0-108">设置一个值，确定如何应用程序加载托管调试器下运行时的本机映像。</span><span class="sxs-lookup"><span data-stu-id="07cd0-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="07cd0-109">EnumerateGCReferences 方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-109">EnumerateGCReferences Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="07cd0-110">获取要进行垃圾回收的过程中的所有对象的枚举数。</span><span class="sxs-lookup"><span data-stu-id="07cd0-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="07cd0-111">EnumerateHandles 方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-111">EnumerateHandles Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="07cd0-112">在进程中获取对象句柄的枚举数。</span><span class="sxs-lookup"><span data-stu-id="07cd0-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="07cd0-113">EnumerateHeap 方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-113">EnumerateHeap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="07cd0-114">托管堆上获取对象的枚举数。</span><span class="sxs-lookup"><span data-stu-id="07cd0-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="07cd0-115">EnumerateHeapRegions 方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-115">EnumerateHeapRegions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="07cd0-116">获取针对托管堆区域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="07cd0-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="07cd0-117">GetArrayLayout 方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-117">GetArrayLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="07cd0-118">获取内存的布局信息的数组。</span><span class="sxs-lookup"><span data-stu-id="07cd0-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="07cd0-119">GetGCHeapInformation 方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-119">GetGCHeapInformation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="07cd0-120">获取一个指向[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)结构，其中包含有关要进行垃圾回收托管堆上的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="07cd0-120">Gets a pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="07cd0-121">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-121">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|<span data-ttu-id="07cd0-122">获取托管堆上对象的指针。</span><span class="sxs-lookup"><span data-stu-id="07cd0-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="07cd0-123">GetTypeFields 方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-123">GetTypeFields Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="07cd0-124">获取一个指针指向包含有关基于其类型标识符的类型的字段信息的数组。</span><span class="sxs-lookup"><span data-stu-id="07cd0-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="07cd0-125">GetTypeForTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-125">GetTypeForTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="07cd0-126">获取一个类型对象，提供有关基于其类型标识符的对象信息。</span><span class="sxs-lookup"><span data-stu-id="07cd0-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="07cd0-127">GetTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-127">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="07cd0-128">指定地址处获取该对象类型标识符。</span><span class="sxs-lookup"><span data-stu-id="07cd0-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="07cd0-129">GetTypeLayout 方法</span><span class="sxs-lookup"><span data-stu-id="07cd0-129">GetTypeLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="07cd0-130">在根据其类型标识符的内存中获取对象的布局信息。</span><span class="sxs-lookup"><span data-stu-id="07cd0-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07cd0-131">备注</span><span class="sxs-lookup"><span data-stu-id="07cd0-131">Remarks</span></span>  
 <span data-ttu-id="07cd0-132">此接口进行逻辑扩展 ICorDebugProcess，ICorDebugProcess2，和[ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="07cd0-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07cd0-133">此接口不支持从另一台计算机或从另一个进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="07cd0-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07cd0-134">要求</span><span class="sxs-lookup"><span data-stu-id="07cd0-134">Requirements</span></span>  
 <span data-ttu-id="07cd0-135">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07cd0-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07cd0-136">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07cd0-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07cd0-137">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07cd0-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07cd0-138">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07cd0-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07cd0-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="07cd0-139">See Also</span></span>  
 [<span data-ttu-id="07cd0-140">调试接口</span><span class="sxs-lookup"><span data-stu-id="07cd0-140">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="07cd0-141">调试</span><span class="sxs-lookup"><span data-stu-id="07cd0-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
