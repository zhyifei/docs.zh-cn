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
ms.openlocfilehash: 39c9752912e88b04455516c0e9bed43610ba8aa0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703815"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="c9fa7-102">ICLRIoCompletionManager::OnComplete 方法</span><span class="sxs-lookup"><span data-stu-id="c9fa7-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="c9fa7-103">通知公共语言运行时（CLR）通过调用[IHostIoCompletionManager：： Bind](ihostiocompletionmanager-bind-method.md)方法发出的 i/o 请求的状态。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9fa7-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9fa7-104">Syntax</span></span>  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9fa7-105">参数</span><span class="sxs-lookup"><span data-stu-id="c9fa7-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="c9fa7-106">中一个 HRESULT 值，指示绑定操作的状态。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="c9fa7-107">S_OK 指示操作已成功完成。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-107">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="c9fa7-108">HOST_E_INTERRUPTED 指示调用在完成前终止。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="c9fa7-109">E_FAIL 指示发生了未知、无法恢复的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="c9fa7-110">中处理 i/o 请求过程中传输的字节数。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="c9fa7-111">中指向 `OVERLAPPED` 传递给方法调用的结构的指针 `IHostIoCompletionManager::Bind` 。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9fa7-112">返回值</span><span class="sxs-lookup"><span data-stu-id="c9fa7-112">Return Value</span></span>  
  
|<span data-ttu-id="c9fa7-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9fa7-113">HRESULT</span></span>|<span data-ttu-id="c9fa7-114">说明</span><span class="sxs-lookup"><span data-stu-id="c9fa7-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9fa7-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9fa7-115">S_OK</span></span>|<span data-ttu-id="c9fa7-116">`OnComplete`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="c9fa7-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c9fa7-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c9fa7-118">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c9fa7-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c9fa7-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c9fa7-120">调用超时。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-120">The call timed out.</span></span>|  
|<span data-ttu-id="c9fa7-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c9fa7-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c9fa7-122">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c9fa7-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c9fa7-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c9fa7-124">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c9fa7-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9fa7-125">E_FAIL</span></span>|<span data-ttu-id="c9fa7-126">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c9fa7-127">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c9fa7-128">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9fa7-129">备注</span><span class="sxs-lookup"><span data-stu-id="c9fa7-129">Remarks</span></span>  
 <span data-ttu-id="c9fa7-130">如果主机实现 i/o 完成抽象，则 CLR 通过使用[IHostIoCompletionManager](ihostiocompletionmanager-interface.md)的方法在主机上发出 i/o 请求。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="c9fa7-131">然后，宿主调用 `OnComplete` 方法以通知运行时此类请求的结果。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9fa7-132">要求</span><span class="sxs-lookup"><span data-stu-id="c9fa7-132">Requirements</span></span>  
 <span data-ttu-id="c9fa7-133">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c9fa7-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9fa7-134">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c9fa7-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9fa7-135">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c9fa7-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9fa7-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9fa7-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9fa7-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9fa7-137">See also</span></span>

- [<span data-ttu-id="c9fa7-138">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="c9fa7-138">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="c9fa7-139">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="c9fa7-139">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="c9fa7-140">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="c9fa7-140">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
