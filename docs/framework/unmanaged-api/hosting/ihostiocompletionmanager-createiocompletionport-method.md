---
title: IHostIoCompletionManager::CreateIoCompletionPort 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52e1dd05a87eaf06b5352d7c8d63c402a65d95ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439070"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="ef026-102">IHostIoCompletionManager::CreateIoCompletionPort 方法</span><span class="sxs-lookup"><span data-stu-id="ef026-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="ef026-103">主机创建新的 I/O 完成端口的请求。</span><span class="sxs-lookup"><span data-stu-id="ef026-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef026-104">语法</span><span class="sxs-lookup"><span data-stu-id="ef026-104">Syntax</span></span>  
  
```  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef026-105">参数</span><span class="sxs-lookup"><span data-stu-id="ef026-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="ef026-106">[out]指向新创建的 I/O 完成端口或 0 （零），如果无法创建该端口的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="ef026-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef026-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ef026-107">Return Value</span></span>  
  
|<span data-ttu-id="ef026-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef026-108">HRESULT</span></span>|<span data-ttu-id="ef026-109">描述</span><span class="sxs-lookup"><span data-stu-id="ef026-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef026-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef026-110">S_OK</span></span>|<span data-ttu-id="ef026-111">`CreateIoCompletionPort` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ef026-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="ef026-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ef026-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ef026-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ef026-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ef026-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ef026-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ef026-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="ef026-115">The call timed out.</span></span>|  
|<span data-ttu-id="ef026-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ef026-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ef026-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ef026-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ef026-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ef026-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ef026-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ef026-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ef026-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ef026-120">E_FAIL</span></span>|<span data-ttu-id="ef026-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ef026-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ef026-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="ef026-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ef026-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ef026-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ef026-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ef026-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ef026-125">没有足够的内存的可用，无法分配请求的资源。</span><span class="sxs-lookup"><span data-stu-id="ef026-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef026-126">备注</span><span class="sxs-lookup"><span data-stu-id="ef026-126">Remarks</span></span>  
 <span data-ttu-id="ef026-127">CLR 调用`CreateIoCompletionPort`方法来请求主机创建新的 I/O 完成端口。</span><span class="sxs-lookup"><span data-stu-id="ef026-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="ef026-128">它将 I/O 操作绑定到通过调用此端口[ihostiocompletionmanager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ef026-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="ef026-129">主机状态回过来向报告 CLR 通过调用[iclriocompletionmanager:: Oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)。</span><span class="sxs-lookup"><span data-stu-id="ef026-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef026-130">要求</span><span class="sxs-lookup"><span data-stu-id="ef026-130">Requirements</span></span>  
 <span data-ttu-id="ef026-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ef026-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef026-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ef026-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef026-133">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ef026-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef026-134">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef026-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef026-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef026-135">See Also</span></span>  
 [<span data-ttu-id="ef026-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="ef026-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="ef026-137">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="ef026-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
