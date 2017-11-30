---
title: "IHostIoCompletionManager::InitializeHostOverlapped 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.InitializeHostOverlapped
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26e8f9d963e6924a8c6abd73c3e025543c7d5b83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="ab568-102">IHostIoCompletionManager::InitializeHostOverlapped 方法</span><span class="sxs-lookup"><span data-stu-id="ab568-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="ab568-103">为宿主提供初始化任何自定义的数据，可将附加到 Win32 的机会`OVERLAPPED`用于异步 I/O 请求的结构。</span><span class="sxs-lookup"><span data-stu-id="ab568-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab568-104">语法</span><span class="sxs-lookup"><span data-stu-id="ab568-104">Syntax</span></span>  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab568-105">参数</span><span class="sxs-lookup"><span data-stu-id="ab568-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="ab568-106">[in]一个指向 Win32`OVERLAPPED`结构要包含在 I/O 请求。</span><span class="sxs-lookup"><span data-stu-id="ab568-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab568-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ab568-107">Return Value</span></span>  
  
|<span data-ttu-id="ab568-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab568-108">HRESULT</span></span>|<span data-ttu-id="ab568-109">描述</span><span class="sxs-lookup"><span data-stu-id="ab568-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab568-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab568-110">S_OK</span></span>|<span data-ttu-id="ab568-111">`InitializeHostOverlapped`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ab568-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="ab568-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ab568-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ab568-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ab568-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ab568-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ab568-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ab568-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="ab568-115">The call timed out.</span></span>|  
|<span data-ttu-id="ab568-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ab568-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ab568-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ab568-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ab568-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ab568-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ab568-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ab568-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ab568-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ab568-120">E_FAIL</span></span>|<span data-ttu-id="ab568-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ab568-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ab568-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="ab568-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ab568-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ab568-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ab568-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ab568-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ab568-125">没有足够的内存的可用，无法分配请求的资源。</span><span class="sxs-lookup"><span data-stu-id="ab568-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab568-126">备注</span><span class="sxs-lookup"><span data-stu-id="ab568-126">Remarks</span></span>  
 <span data-ttu-id="ab568-127">Windows 平台函数使用`OVERLAPPED`结构，用于存储有关异步 I/O 请求的状态。</span><span class="sxs-lookup"><span data-stu-id="ab568-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="ab568-128">CLR 调用`InitializeHostOverlapped`方法以便为主机提供自定义将数据追加到机会`OVERLAPPED`实例。</span><span class="sxs-lookup"><span data-stu-id="ab568-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ab568-129">若要获取其自定义数据块的开头，主机必须设置偏移量的大小`OVERLAPPED`结构 (`sizeof(OVERLAPPED)`)。</span><span class="sxs-lookup"><span data-stu-id="ab568-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="ab568-130">返回值 E_OUTOFMEMORY 指示主机具有无法初始化其自定义数据。</span><span class="sxs-lookup"><span data-stu-id="ab568-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="ab568-131">在这种情况下，CLR 报告错误，并且无法进行调用。</span><span class="sxs-lookup"><span data-stu-id="ab568-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab568-132">要求</span><span class="sxs-lookup"><span data-stu-id="ab568-132">Requirements</span></span>  
 <span data-ttu-id="ab568-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ab568-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab568-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ab568-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ab568-135">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ab568-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab568-136">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab568-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab568-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab568-137">See Also</span></span>  
 [<span data-ttu-id="ab568-138">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="ab568-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="ab568-139">GetHostOverlappedSize 方法</span><span class="sxs-lookup"><span data-stu-id="ab568-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)  
 [<span data-ttu-id="ab568-140">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="ab568-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
