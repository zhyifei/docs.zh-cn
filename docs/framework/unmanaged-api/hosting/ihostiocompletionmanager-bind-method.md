---
title: IHostIoCompletionManager::Bind 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c03cdb9f9205676d17d6e18b9b2e074132ee26f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594767"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="a2f52-102">IHostIoCompletionManager::Bind 方法</span><span class="sxs-lookup"><span data-stu-id="a2f52-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="a2f52-103">将指定的句柄绑定到已创建的早期调用到 I/O 完成端口[CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a2f52-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2f52-104">语法</span><span class="sxs-lookup"><span data-stu-id="a2f52-104">Syntax</span></span>  
  
```  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2f52-105">参数</span><span class="sxs-lookup"><span data-stu-id="a2f52-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="a2f52-106">[in]I/O 完成端口绑定到`hHandle`。</span><span class="sxs-lookup"><span data-stu-id="a2f52-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="a2f52-107">如果的值`hPort`为 null，`hHandle`绑定到默认 I/O 完成端口。</span><span class="sxs-lookup"><span data-stu-id="a2f52-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="a2f52-108">[in]若要将绑定到的操作系统句柄`hPort`。</span><span class="sxs-lookup"><span data-stu-id="a2f52-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2f52-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a2f52-109">Return Value</span></span>  
  
|<span data-ttu-id="a2f52-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a2f52-110">HRESULT</span></span>|<span data-ttu-id="a2f52-111">描述</span><span class="sxs-lookup"><span data-stu-id="a2f52-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a2f52-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a2f52-112">S_OK</span></span>|<span data-ttu-id="a2f52-113">`Bind` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a2f52-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="a2f52-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a2f52-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a2f52-115">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a2f52-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a2f52-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a2f52-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a2f52-117">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="a2f52-117">The call timed out.</span></span>|  
|<span data-ttu-id="a2f52-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a2f52-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a2f52-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a2f52-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a2f52-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a2f52-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a2f52-121">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="a2f52-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a2f52-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a2f52-122">E_FAIL</span></span>|<span data-ttu-id="a2f52-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a2f52-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a2f52-124">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="a2f52-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a2f52-125">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a2f52-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2f52-126">备注</span><span class="sxs-lookup"><span data-stu-id="a2f52-126">Remarks</span></span>  
 <span data-ttu-id="a2f52-127">通过调用创建 I/O 完成端口`CreateIoCompletionPort`。</span><span class="sxs-lookup"><span data-stu-id="a2f52-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="a2f52-128">CLR 调用`Bind`若要将句柄绑定到该端口。</span><span class="sxs-lookup"><span data-stu-id="a2f52-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2f52-129">宿主的 I/O 请求完成时，必须调用[iclriocompletionmanager:: Oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a2f52-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2f52-130">要求</span><span class="sxs-lookup"><span data-stu-id="a2f52-130">Requirements</span></span>  
 <span data-ttu-id="a2f52-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2f52-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2f52-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a2f52-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2f52-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a2f52-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2f52-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2f52-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f52-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2f52-135">See also</span></span>
- [<span data-ttu-id="a2f52-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="a2f52-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
