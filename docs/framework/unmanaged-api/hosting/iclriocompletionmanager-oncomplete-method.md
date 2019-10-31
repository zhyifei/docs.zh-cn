---
title: ICLRIoCompletionManager::OnComplete 方法
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
ms.openlocfilehash: b44a71137e39130bb0fe4c303fdff62c76d38cbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141007"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="d797c-102">ICLRIoCompletionManager::OnComplete 方法</span><span class="sxs-lookup"><span data-stu-id="d797c-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="d797c-103">通知公共语言运行时（CLR）通过调用[IHostIoCompletionManager：： Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)方法发出的 i/o 请求的状态。</span><span class="sxs-lookup"><span data-stu-id="d797c-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d797c-104">语法</span><span class="sxs-lookup"><span data-stu-id="d797c-104">Syntax</span></span>  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d797c-105">参数</span><span class="sxs-lookup"><span data-stu-id="d797c-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="d797c-106">中一个 HRESULT 值，指示绑定操作的状态。</span><span class="sxs-lookup"><span data-stu-id="d797c-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="d797c-107">S_OK 指示操作已成功完成。</span><span class="sxs-lookup"><span data-stu-id="d797c-107">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="d797c-108">HOST_E_INTERRUPTED 指示调用在完成前终止。</span><span class="sxs-lookup"><span data-stu-id="d797c-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="d797c-109">E_FAIL 指示发生了未知、无法恢复的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d797c-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="d797c-110">中处理 i/o 请求过程中传输的字节数。</span><span class="sxs-lookup"><span data-stu-id="d797c-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="d797c-111">中指向传递到 `IHostIoCompletionManager::Bind` 方法调用的 `OVERLAPPED` 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="d797c-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d797c-112">返回值</span><span class="sxs-lookup"><span data-stu-id="d797c-112">Return Value</span></span>  
  
|<span data-ttu-id="d797c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d797c-113">HRESULT</span></span>|<span data-ttu-id="d797c-114">描述</span><span class="sxs-lookup"><span data-stu-id="d797c-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d797c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d797c-115">S_OK</span></span>|<span data-ttu-id="d797c-116">`OnComplete` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="d797c-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="d797c-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d797c-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d797c-118">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d797c-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d797c-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d797c-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d797c-120">调用超时。</span><span class="sxs-lookup"><span data-stu-id="d797c-120">The call timed out.</span></span>|  
|<span data-ttu-id="d797c-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d797c-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d797c-122">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d797c-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d797c-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d797c-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d797c-124">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="d797c-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d797c-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d797c-125">E_FAIL</span></span>|<span data-ttu-id="d797c-126">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d797c-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d797c-127">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="d797c-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d797c-128">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d797c-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d797c-129">备注</span><span class="sxs-lookup"><span data-stu-id="d797c-129">Remarks</span></span>  
 <span data-ttu-id="d797c-130">如果主机实现 i/o 完成抽象，则 CLR 通过使用[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)的方法在主机上发出 i/o 请求。</span><span class="sxs-lookup"><span data-stu-id="d797c-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="d797c-131">然后，宿主调用 `OnComplete` 方法，以通知运行时此类请求的结果。</span><span class="sxs-lookup"><span data-stu-id="d797c-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d797c-132">要求</span><span class="sxs-lookup"><span data-stu-id="d797c-132">Requirements</span></span>  
 <span data-ttu-id="d797c-133">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d797c-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d797c-134">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d797c-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d797c-135">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d797c-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d797c-136">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d797c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d797c-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="d797c-137">See also</span></span>

- [<span data-ttu-id="d797c-138">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="d797c-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="d797c-139">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="d797c-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="d797c-140">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="d797c-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
