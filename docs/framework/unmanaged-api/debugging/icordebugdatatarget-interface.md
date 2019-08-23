---
title: ICorDebugDataTarget 接口
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c6a8ee1bcc65e640ef871e57acdeef21acd7896
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930825"
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="9a0af-102">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="9a0af-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="9a0af-103">提供一个回调接口，该接口可提供对特定目标进程的访问。</span><span class="sxs-lookup"><span data-stu-id="9a0af-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a0af-104">方法</span><span class="sxs-lookup"><span data-stu-id="9a0af-104">Methods</span></span>  
  
|<span data-ttu-id="9a0af-105">方法</span><span class="sxs-lookup"><span data-stu-id="9a0af-105">Method</span></span>|<span data-ttu-id="9a0af-106">描述</span><span class="sxs-lookup"><span data-stu-id="9a0af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a0af-107">GetPlatform 方法</span><span class="sxs-lookup"><span data-stu-id="9a0af-107">GetPlatform Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="9a0af-108">提供有关平台的信息, 包括在其上运行目标进程的处理器体系结构和操作系统。</span><span class="sxs-lookup"><span data-stu-id="9a0af-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="9a0af-109">ReadVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="9a0af-109">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="9a0af-110">获取从指定地址开始的连续内存块, 并将其返回到提供的缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="9a0af-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="9a0af-111">GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="9a0af-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="9a0af-112">请求指定线程的当前线程上下文。</span><span class="sxs-lookup"><span data-stu-id="9a0af-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a0af-113">备注</span><span class="sxs-lookup"><span data-stu-id="9a0af-113">Remarks</span></span>  
 <span data-ttu-id="9a0af-114">`ICorDebugDataTarget`及其方法具有以下特征:</span><span class="sxs-lookup"><span data-stu-id="9a0af-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
- <span data-ttu-id="9a0af-115">调试服务调用此接口上的方法以访问目标进程中的内存和其他数据。</span><span class="sxs-lookup"><span data-stu-id="9a0af-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
- <span data-ttu-id="9a0af-116">调试器客户端必须根据特定目标 (例如, 实时进程或内存转储) 实现此接口。</span><span class="sxs-lookup"><span data-stu-id="9a0af-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
- <span data-ttu-id="9a0af-117">只能从其他`ICorDebug*`接口实现的方法中调用方法。`ICorDebugDataTarget`</span><span class="sxs-lookup"><span data-stu-id="9a0af-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="9a0af-118">这确保了调试器客户端可以控制调用它的线程和时间。</span><span class="sxs-lookup"><span data-stu-id="9a0af-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
- <span data-ttu-id="9a0af-119">`ICorDebugDataTarget`实现必须始终返回有关目标的最新信息。</span><span class="sxs-lookup"><span data-stu-id="9a0af-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="9a0af-120">如果调用了`ICorDebug*`接口 (和因此`ICorDebugDataTarget`方法), 则目标进程应停止并且不以任何方式更改。</span><span class="sxs-lookup"><span data-stu-id="9a0af-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="9a0af-121">如果目标是实时进程并且其状态发生更改, 则必须再次调用[ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)方法以提供替换 ICorDebugProcess 实例。</span><span class="sxs-lookup"><span data-stu-id="9a0af-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9a0af-122">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="9a0af-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a0af-123">要求</span><span class="sxs-lookup"><span data-stu-id="9a0af-123">Requirements</span></span>  
 <span data-ttu-id="9a0af-124">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9a0af-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a0af-125">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="9a0af-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a0af-126">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a0af-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a0af-127">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a0af-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a0af-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a0af-128">See also</span></span>

- [<span data-ttu-id="9a0af-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="9a0af-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9a0af-130">调试</span><span class="sxs-lookup"><span data-stu-id="9a0af-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
