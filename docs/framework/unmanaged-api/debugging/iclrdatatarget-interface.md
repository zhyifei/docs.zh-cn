---
title: ICLRDataTarget 接口
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed3cb62b56e80a7fe4ea54b43ac9f4a28b8d102
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100244"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="8bec5-102">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="8bec5-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="8bec5-103">提供与公共语言运行时 (CLR) 的目标项进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="8bec5-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8bec5-104">方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-104">Methods</span></span>  
  
|<span data-ttu-id="8bec5-105">方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-105">Method</span></span>|<span data-ttu-id="8bec5-106">描述</span><span class="sxs-lookup"><span data-stu-id="8bec5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8bec5-107">GetCurrentThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-107">GetCurrentThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="8bec5-108">获取当前线程的操作系统识别符。</span><span class="sxs-lookup"><span data-stu-id="8bec5-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="8bec5-109">GetImageBase 方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-109">GetImageBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="8bec5-110">获取指定的图像的基础内存地址。</span><span class="sxs-lookup"><span data-stu-id="8bec5-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="8bec5-111">GetMachineType 方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-111">GetMachineType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="8bec5-112">获取目标进程正在使用的指令集的类型的标识符。</span><span class="sxs-lookup"><span data-stu-id="8bec5-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="8bec5-113">GetPointerSize 方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-113">GetPointerSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="8bec5-114">获取以字节为单位，指向当前目标的指针的大小。</span><span class="sxs-lookup"><span data-stu-id="8bec5-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="8bec5-115">GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-115">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="8bec5-116">获取一个指向线程的上下文具有指定标识符。</span><span class="sxs-lookup"><span data-stu-id="8bec5-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="8bec5-117">GetTLSValue 方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-117">GetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="8bec5-118">线程本地存储区 (TLS) 中获取一个值，指定线程的指定索引处。</span><span class="sxs-lookup"><span data-stu-id="8bec5-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="8bec5-119">ReadVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-119">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="8bec5-120">从指定的虚拟内存地址数据读入指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8bec5-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="8bec5-121">Request 方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-121">Request Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|<span data-ttu-id="8bec5-122">调用由公共语言运行时 (CLR) 数据访问服务以请求操作，如由实现定义。</span><span class="sxs-lookup"><span data-stu-id="8bec5-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="8bec5-123">SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-123">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="8bec5-124">目标进程中设置指定线程的当前的上下文。</span><span class="sxs-lookup"><span data-stu-id="8bec5-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="8bec5-125">SetTLSValue 方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-125">SetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="8bec5-126">设置中指定目标进程中线程的线程本地存储 (TLS) 的值。</span><span class="sxs-lookup"><span data-stu-id="8bec5-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="8bec5-127">WriteVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="8bec5-127">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="8bec5-128">将数据从指定的缓冲区写入到指定的虚拟内存地址。</span><span class="sxs-lookup"><span data-stu-id="8bec5-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bec5-129">备注</span><span class="sxs-lookup"><span data-stu-id="8bec5-129">Remarks</span></span>  
 <span data-ttu-id="8bec5-130">API 客户端 （即调试器） 必须实现此接口作为适用于特定的目标项。</span><span class="sxs-lookup"><span data-stu-id="8bec5-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="8bec5-131">例如，活动进程的实现将不同于内存转储的。</span><span class="sxs-lookup"><span data-stu-id="8bec5-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bec5-132">要求</span><span class="sxs-lookup"><span data-stu-id="8bec5-132">Requirements</span></span>  
 <span data-ttu-id="8bec5-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8bec5-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bec5-134">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="8bec5-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8bec5-135">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bec5-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bec5-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bec5-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bec5-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bec5-137">See also</span></span>

- [<span data-ttu-id="8bec5-138">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="8bec5-138">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="8bec5-139">调试接口</span><span class="sxs-lookup"><span data-stu-id="8bec5-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
