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
ms.openlocfilehash: 64fb60abf4f5730dbc15204dbc034b08cacefab9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121251"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="f780e-102">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="f780e-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="f780e-103">扩展 ICorDebugProcess 接口以支持对托管堆的访问，以提供有关托管对象的垃圾回收的信息，以及确定调试器是否从应用程序本地本机映像缓存中加载图像。</span><span class="sxs-lookup"><span data-stu-id="f780e-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f780e-104">方法</span><span class="sxs-lookup"><span data-stu-id="f780e-104">Methods</span></span>  
  
|<span data-ttu-id="f780e-105">方法</span><span class="sxs-lookup"><span data-stu-id="f780e-105">Method</span></span>|<span data-ttu-id="f780e-106">描述</span><span class="sxs-lookup"><span data-stu-id="f780e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f780e-107">EnableNGenPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="f780e-107">EnableNGenPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="f780e-108">设置一个值，该值确定应用程序在托管调试器下运行时如何加载本机映像。</span><span class="sxs-lookup"><span data-stu-id="f780e-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="f780e-109">EnumerateGCReferences 方法</span><span class="sxs-lookup"><span data-stu-id="f780e-109">EnumerateGCReferences Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="f780e-110">获取一个枚举器，该枚举器用于进程中要进行垃圾回收的所有对象。</span><span class="sxs-lookup"><span data-stu-id="f780e-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="f780e-111">EnumerateHandles 方法</span><span class="sxs-lookup"><span data-stu-id="f780e-111">EnumerateHandles Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="f780e-112">获取进程中的对象句柄的枚举器。</span><span class="sxs-lookup"><span data-stu-id="f780e-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="f780e-113">EnumerateHeap 方法</span><span class="sxs-lookup"><span data-stu-id="f780e-113">EnumerateHeap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="f780e-114">获取托管堆上的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="f780e-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="f780e-115">EnumerateHeapRegions 方法</span><span class="sxs-lookup"><span data-stu-id="f780e-115">EnumerateHeapRegions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="f780e-116">获取托管堆区域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="f780e-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="f780e-117">GetArrayLayout 方法</span><span class="sxs-lookup"><span data-stu-id="f780e-117">GetArrayLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="f780e-118">获取有关内存中数组的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="f780e-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="f780e-119">GetGCHeapInformation 方法</span><span class="sxs-lookup"><span data-stu-id="f780e-119">GetGCHeapInformation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="f780e-120">获取一个指向[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)结构的指针，该结构包含有关要在托管堆上进行垃圾回收的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="f780e-120">Gets a pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="f780e-121">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="f780e-121">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|<span data-ttu-id="f780e-122">获取指向托管堆上的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f780e-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="f780e-123">GetTypeFields 方法</span><span class="sxs-lookup"><span data-stu-id="f780e-123">GetTypeFields Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="f780e-124">获取一个指针，该指针指向一个数组，该数组包含基于类型标识符的类型的字段信息。</span><span class="sxs-lookup"><span data-stu-id="f780e-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="f780e-125">GetTypeForTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="f780e-125">GetTypeForTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="f780e-126">获取一个类型对象，该对象基于其类型标识符提供有关对象的信息。</span><span class="sxs-lookup"><span data-stu-id="f780e-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="f780e-127">GetTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="f780e-127">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="f780e-128">获取指定地址处的对象的类型标识符。</span><span class="sxs-lookup"><span data-stu-id="f780e-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="f780e-129">GetTypeLayout 方法</span><span class="sxs-lookup"><span data-stu-id="f780e-129">GetTypeLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="f780e-130">根据对象的类型标识符获取有关该对象在内存中的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="f780e-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f780e-131">备注</span><span class="sxs-lookup"><span data-stu-id="f780e-131">Remarks</span></span>  
 <span data-ttu-id="f780e-132">此接口以逻辑方式扩展了 ICorDebugProcess、ICorDebugProcess2 和[ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f780e-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f780e-133">此接口不支持从另一台计算机或从其他进程进行远程调用。</span><span class="sxs-lookup"><span data-stu-id="f780e-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f780e-134">要求</span><span class="sxs-lookup"><span data-stu-id="f780e-134">Requirements</span></span>  
 <span data-ttu-id="f780e-135">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f780e-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f780e-136">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f780e-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f780e-137">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f780e-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f780e-138">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f780e-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f780e-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="f780e-139">See also</span></span>

- [<span data-ttu-id="f780e-140">调试接口</span><span class="sxs-lookup"><span data-stu-id="f780e-140">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f780e-141">调试</span><span class="sxs-lookup"><span data-stu-id="f780e-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
