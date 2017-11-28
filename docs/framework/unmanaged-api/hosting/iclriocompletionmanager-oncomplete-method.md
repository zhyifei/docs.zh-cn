---
title: "ICLRIoCompletionManager::OnComplete 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRIoCompletionManager.OnComplete
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9bd38679d1b8d099e5eb6330e03e2333b03780dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="0e006-102">ICLRIoCompletionManager::OnComplete 方法</span><span class="sxs-lookup"><span data-stu-id="0e006-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="0e006-103">进行调用的 I/O 请求的状态通知公共语言运行时 (CLR) [ihostiocompletionmanager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0e006-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e006-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e006-104">Syntax</span></span>  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e006-105">参数</span><span class="sxs-lookup"><span data-stu-id="0e006-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="0e006-106">[in]HRESULT 值，该值指示绑定操作的状态。</span><span class="sxs-lookup"><span data-stu-id="0e006-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
-   <span data-ttu-id="0e006-107">则为 S_OK 表示该操作成功完成。</span><span class="sxs-lookup"><span data-stu-id="0e006-107">S_OK indicates that the operation completed successfully.</span></span>  
  
-   <span data-ttu-id="0e006-108">HOST_E_INTERRUPTED 指示调用终止之前完成。</span><span class="sxs-lookup"><span data-stu-id="0e006-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
-   <span data-ttu-id="0e006-109">E_FAIL 指示发生了未知的、 不可恢复的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0e006-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="0e006-110">[in]在处理 I/O 请求过程中传输的字节数。</span><span class="sxs-lookup"><span data-stu-id="0e006-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="0e006-111">[in]指向的指针`OVERLAPPED`结构传递给调用`IHostIoCompletionManager::Bind`方法。</span><span class="sxs-lookup"><span data-stu-id="0e006-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e006-112">返回值</span><span class="sxs-lookup"><span data-stu-id="0e006-112">Return Value</span></span>  
  
|<span data-ttu-id="0e006-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e006-113">HRESULT</span></span>|<span data-ttu-id="0e006-114">描述</span><span class="sxs-lookup"><span data-stu-id="0e006-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e006-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e006-115">S_OK</span></span>|<span data-ttu-id="0e006-116">`OnComplete`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0e006-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="0e006-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0e006-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0e006-118">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0e006-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0e006-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e006-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0e006-120">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="0e006-120">The call timed out.</span></span>|  
|<span data-ttu-id="0e006-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0e006-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0e006-122">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0e006-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0e006-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0e006-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0e006-124">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="0e006-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0e006-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e006-125">E_FAIL</span></span>|<span data-ttu-id="0e006-126">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0e006-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0e006-127">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="0e006-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0e006-128">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0e006-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e006-129">备注</span><span class="sxs-lookup"><span data-stu-id="0e006-129">Remarks</span></span>  
 <span data-ttu-id="0e006-130">如果主机实现的 I/O 完成抽象，CLR 通过使用的方法进行输入/输出请求通过主机[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="0e006-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="0e006-131">主机然后调用`OnComplete`方法来通知运行时的此类请求的结果。</span><span class="sxs-lookup"><span data-stu-id="0e006-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e006-132">要求</span><span class="sxs-lookup"><span data-stu-id="0e006-132">Requirements</span></span>  
 <span data-ttu-id="0e006-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e006-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e006-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0e006-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e006-135">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0e006-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e006-136">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e006-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e006-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e006-137">See Also</span></span>  
 [<span data-ttu-id="0e006-138">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="0e006-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="0e006-139">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="0e006-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="0e006-140">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="0e006-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
