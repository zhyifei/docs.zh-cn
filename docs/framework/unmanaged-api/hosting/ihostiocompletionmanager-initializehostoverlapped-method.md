---
title: IHostIoCompletionManager::InitializeHostOverlapped 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
ms.openlocfilehash: 9fd299ad25166bcbcf0202da13a5b4cbdd20d7d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133805"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="8790c-102">IHostIoCompletionManager::InitializeHostOverlapped 方法</span><span class="sxs-lookup"><span data-stu-id="8790c-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="8790c-103">向宿主提供初始化任何自定义数据以追加到用于异步 i/o 请求的 Win32 `OVERLAPPED` 结构的机会。</span><span class="sxs-lookup"><span data-stu-id="8790c-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8790c-104">语法</span><span class="sxs-lookup"><span data-stu-id="8790c-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8790c-105">参数</span><span class="sxs-lookup"><span data-stu-id="8790c-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="8790c-106">中指向要包含在 i/o 请求中的 Win32 `OVERLAPPED` 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="8790c-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8790c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="8790c-107">Return Value</span></span>  
  
|<span data-ttu-id="8790c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8790c-108">HRESULT</span></span>|<span data-ttu-id="8790c-109">描述</span><span class="sxs-lookup"><span data-stu-id="8790c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8790c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8790c-110">S_OK</span></span>|<span data-ttu-id="8790c-111">`InitializeHostOverlapped` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="8790c-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="8790c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8790c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8790c-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8790c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8790c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8790c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8790c-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="8790c-115">The call timed out.</span></span>|  
|<span data-ttu-id="8790c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8790c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8790c-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8790c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8790c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8790c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8790c-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="8790c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8790c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8790c-120">E_FAIL</span></span>|<span data-ttu-id="8790c-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8790c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8790c-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="8790c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8790c-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8790c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8790c-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8790c-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8790c-125">没有足够的内存可用于分配请求的资源。</span><span class="sxs-lookup"><span data-stu-id="8790c-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8790c-126">备注</span><span class="sxs-lookup"><span data-stu-id="8790c-126">Remarks</span></span>  
 <span data-ttu-id="8790c-127">Windows 平台函数使用 `OVERLAPPED` 结构来存储异步 i/o 请求的状态。</span><span class="sxs-lookup"><span data-stu-id="8790c-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="8790c-128">CLR 调用 `InitializeHostOverlapped` 方法，使宿主有机会将自定义数据追加到 `OVERLAPPED` 实例。</span><span class="sxs-lookup"><span data-stu-id="8790c-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8790c-129">若要从自定义数据块开始，主机必须将偏移量设置为 `OVERLAPPED` 结构的大小（`sizeof(OVERLAPPED)`）。</span><span class="sxs-lookup"><span data-stu-id="8790c-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="8790c-130">E_OUTOFMEMORY 的返回值指示宿主未能初始化其自定义数据。</span><span class="sxs-lookup"><span data-stu-id="8790c-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="8790c-131">在这种情况下，CLR 将报告错误并导致调用失败。</span><span class="sxs-lookup"><span data-stu-id="8790c-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8790c-132">要求</span><span class="sxs-lookup"><span data-stu-id="8790c-132">Requirements</span></span>  
 <span data-ttu-id="8790c-133">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8790c-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8790c-134">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8790c-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8790c-135">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8790c-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8790c-136">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8790c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8790c-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="8790c-137">See also</span></span>

- [<span data-ttu-id="8790c-138">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="8790c-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="8790c-139">GetHostOverlappedSize 方法</span><span class="sxs-lookup"><span data-stu-id="8790c-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="8790c-140">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="8790c-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
