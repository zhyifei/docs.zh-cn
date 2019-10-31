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
ms.openlocfilehash: 84fc99f6a5feb7ec73ee16942ba2794fc082dc89
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133897"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="b1df3-102">IHostIoCompletionManager::Bind 方法</span><span class="sxs-lookup"><span data-stu-id="b1df3-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="b1df3-103">将指定的句柄绑定到由之前对[CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)的调用创建的 i/o 完成端口。</span><span class="sxs-lookup"><span data-stu-id="b1df3-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1df3-104">语法</span><span class="sxs-lookup"><span data-stu-id="b1df3-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1df3-105">参数</span><span class="sxs-lookup"><span data-stu-id="b1df3-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="b1df3-106">中要绑定到的 i/o 完成端口 `hHandle`。</span><span class="sxs-lookup"><span data-stu-id="b1df3-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="b1df3-107">如果 `hPort` 的值为 null，`hHandle` 将绑定到默认 i/o 完成端口。</span><span class="sxs-lookup"><span data-stu-id="b1df3-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="b1df3-108">中要绑定到 `hPort`的操作系统句柄。</span><span class="sxs-lookup"><span data-stu-id="b1df3-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1df3-109">返回值</span><span class="sxs-lookup"><span data-stu-id="b1df3-109">Return Value</span></span>  
  
|<span data-ttu-id="b1df3-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b1df3-110">HRESULT</span></span>|<span data-ttu-id="b1df3-111">描述</span><span class="sxs-lookup"><span data-stu-id="b1df3-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b1df3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b1df3-112">S_OK</span></span>|<span data-ttu-id="b1df3-113">`Bind` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="b1df3-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="b1df3-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b1df3-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b1df3-115">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b1df3-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b1df3-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b1df3-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b1df3-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="b1df3-117">The call timed out.</span></span>|  
|<span data-ttu-id="b1df3-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b1df3-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b1df3-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b1df3-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b1df3-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b1df3-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b1df3-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="b1df3-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b1df3-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b1df3-122">E_FAIL</span></span>|<span data-ttu-id="b1df3-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b1df3-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b1df3-124">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="b1df3-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b1df3-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b1df3-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1df3-126">备注</span><span class="sxs-lookup"><span data-stu-id="b1df3-126">Remarks</span></span>  
 <span data-ttu-id="b1df3-127">I/o 完成端口是使用对 `CreateIoCompletionPort`的调用创建的。</span><span class="sxs-lookup"><span data-stu-id="b1df3-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="b1df3-128">CLR 调用 `Bind` 将句柄绑定到该端口。</span><span class="sxs-lookup"><span data-stu-id="b1df3-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1df3-129">当 i/o 请求完成时，主机必须调用[ICLRIoCompletionManager：： OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b1df3-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1df3-130">要求</span><span class="sxs-lookup"><span data-stu-id="b1df3-130">Requirements</span></span>  
 <span data-ttu-id="b1df3-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1df3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1df3-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b1df3-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b1df3-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b1df3-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1df3-134">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1df3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1df3-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1df3-135">See also</span></span>

- [<span data-ttu-id="b1df3-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="b1df3-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
