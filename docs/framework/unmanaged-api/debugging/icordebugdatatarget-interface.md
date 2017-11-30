---
title: "ICorDebugDataTarget 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget
helpviewer_keywords: ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 030ad5e61d215bd840da5b16a56e4b8f8b7791ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="0786c-102">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="0786c-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="0786c-103">提供一个回调接口，该接口可提供对特定目标进程的访问。</span><span class="sxs-lookup"><span data-stu-id="0786c-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0786c-104">方法</span><span class="sxs-lookup"><span data-stu-id="0786c-104">Methods</span></span>  
  
|<span data-ttu-id="0786c-105">方法</span><span class="sxs-lookup"><span data-stu-id="0786c-105">Method</span></span>|<span data-ttu-id="0786c-106">描述</span><span class="sxs-lookup"><span data-stu-id="0786c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0786c-107">GetPlatform 方法</span><span class="sxs-lookup"><span data-stu-id="0786c-107">GetPlatform Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="0786c-108">提供有关平台，包括处理器体系结构和目标进程正在其运行的操作系统的信息。</span><span class="sxs-lookup"><span data-stu-id="0786c-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="0786c-109">ReadVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="0786c-109">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="0786c-110">获取指定的地址处开始的连续内存块，并在提供的缓冲区中将其返回。</span><span class="sxs-lookup"><span data-stu-id="0786c-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="0786c-111">GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="0786c-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="0786c-112">请求指定的线程的当前线程上下文。</span><span class="sxs-lookup"><span data-stu-id="0786c-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0786c-113">备注</span><span class="sxs-lookup"><span data-stu-id="0786c-113">Remarks</span></span>  
 <span data-ttu-id="0786c-114">`ICorDebugDataTarget`和其方法具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="0786c-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
-   <span data-ttu-id="0786c-115">调试服务对此接口可访问内存和目标进程中的其他数据调用方法。</span><span class="sxs-lookup"><span data-stu-id="0786c-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
-   <span data-ttu-id="0786c-116">调试器客户端必须实现此接口为适合特定的目标 （例如，活动进程或内存转储）。</span><span class="sxs-lookup"><span data-stu-id="0786c-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
-   <span data-ttu-id="0786c-117">`ICorDebugDataTarget`方法可以在其他实现的方法内调用只能从`ICorDebug*`接口。</span><span class="sxs-lookup"><span data-stu-id="0786c-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="0786c-118">这可确保调试器客户端已通过的线程调用，以及何时进行控制。</span><span class="sxs-lookup"><span data-stu-id="0786c-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
-   <span data-ttu-id="0786c-119">`ICorDebugDataTarget`实现必须始终返回有关目标的最新信息。</span><span class="sxs-lookup"><span data-stu-id="0786c-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="0786c-120">应停止目标进程，并将其以任何方式时不更改`ICorDebug*`接口 (并因此`ICorDebugDataTarget`方法) 正被调用。</span><span class="sxs-lookup"><span data-stu-id="0786c-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="0786c-121">如果目标为活动的进程并且其状态更改， [iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)方法必须再次调用提供的替换 ICorDebugProcess 实例。</span><span class="sxs-lookup"><span data-stu-id="0786c-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0786c-122">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="0786c-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0786c-123">要求</span><span class="sxs-lookup"><span data-stu-id="0786c-123">Requirements</span></span>  
 <span data-ttu-id="0786c-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0786c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0786c-125">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0786c-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0786c-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0786c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0786c-127">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0786c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0786c-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0786c-128">See Also</span></span>  
 [<span data-ttu-id="0786c-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="0786c-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0786c-130">调试</span><span class="sxs-lookup"><span data-stu-id="0786c-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
