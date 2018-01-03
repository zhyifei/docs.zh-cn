---
title: "ICLRDataTarget 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget
helpviewer_keywords: ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73966ffe89f0e84d5a516f20962472d900332faa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="430d3-102">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="430d3-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="430d3-103">提供与公共语言运行时 (CLR) 目标项进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="430d3-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="430d3-104">方法</span><span class="sxs-lookup"><span data-stu-id="430d3-104">Methods</span></span>  
  
|<span data-ttu-id="430d3-105">方法</span><span class="sxs-lookup"><span data-stu-id="430d3-105">Method</span></span>|<span data-ttu-id="430d3-106">描述</span><span class="sxs-lookup"><span data-stu-id="430d3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="430d3-107">GetCurrentThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="430d3-107">GetCurrentThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="430d3-108">获取当前线程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="430d3-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="430d3-109">GetImageBase 方法</span><span class="sxs-lookup"><span data-stu-id="430d3-109">GetImageBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="430d3-110">获取指定的映像的基的内存地址。</span><span class="sxs-lookup"><span data-stu-id="430d3-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="430d3-111">GetMachineType 方法</span><span class="sxs-lookup"><span data-stu-id="430d3-111">GetMachineType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="430d3-112">获取目标进程正在使用的指令集的种类的标识符。</span><span class="sxs-lookup"><span data-stu-id="430d3-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="430d3-113">GetPointerSize 方法</span><span class="sxs-lookup"><span data-stu-id="430d3-113">GetPointerSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="430d3-114">获取大小，以字节为单位，当前的目标的指针。</span><span class="sxs-lookup"><span data-stu-id="430d3-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="430d3-115">GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="430d3-115">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="430d3-116">获取具有指定标识符的线程的上下文指针。</span><span class="sxs-lookup"><span data-stu-id="430d3-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="430d3-117">GetTLSValue 方法</span><span class="sxs-lookup"><span data-stu-id="430d3-117">GetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="430d3-118">线程本地存储区 (TLS) 中获取一个值，指定线程的指定索引处。</span><span class="sxs-lookup"><span data-stu-id="430d3-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="430d3-119">ReadVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="430d3-119">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="430d3-120">从指定的虚拟内存地址的数据读入指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="430d3-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="430d3-121">Request 方法</span><span class="sxs-lookup"><span data-stu-id="430d3-121">Request Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|<span data-ttu-id="430d3-122">调用由公共语言运行时 (CLR) 数据访问服务以请求操作，如由实现定义。</span><span class="sxs-lookup"><span data-stu-id="430d3-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="430d3-123">SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="430d3-123">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="430d3-124">设置目标进程中的指定线程的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="430d3-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="430d3-125">SetTLSValue 方法</span><span class="sxs-lookup"><span data-stu-id="430d3-125">SetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="430d3-126">设置一个值以指定目标进程中线程的线程本地存储 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="430d3-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="430d3-127">WriteVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="430d3-127">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="430d3-128">从指定的缓冲区写入指定的虚拟内存地址的数据。</span><span class="sxs-lookup"><span data-stu-id="430d3-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="430d3-129">备注</span><span class="sxs-lookup"><span data-stu-id="430d3-129">Remarks</span></span>  
 <span data-ttu-id="430d3-130">API 客户端 （即调试器） 必须实现此接口为适合特定的目标项。</span><span class="sxs-lookup"><span data-stu-id="430d3-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="430d3-131">例如，活动进程的实现将不同于内存转储的。</span><span class="sxs-lookup"><span data-stu-id="430d3-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="430d3-132">惠?</span><span class="sxs-lookup"><span data-stu-id="430d3-132">Requirements</span></span>  
 <span data-ttu-id="430d3-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="430d3-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="430d3-134">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="430d3-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="430d3-135">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="430d3-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="430d3-136">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="430d3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="430d3-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="430d3-137">See Also</span></span>  
 [<span data-ttu-id="430d3-138">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="430d3-138">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="430d3-139">调试接口</span><span class="sxs-lookup"><span data-stu-id="430d3-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
