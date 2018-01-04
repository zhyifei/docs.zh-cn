---
title: "IHostIoCompletionManager::GetHostOverlappedSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.GetHostOverlappedSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41fc1a4a0debe0c302115c79962c0da50cc4ee37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="4510e-102">IHostIoCompletionManager::GetHostOverlappedSize 方法</span><span class="sxs-lookup"><span data-stu-id="4510e-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="4510e-103">获取宿主要追加到输入/输出请求的任何自定义数据的大小。</span><span class="sxs-lookup"><span data-stu-id="4510e-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4510e-104">语法</span><span class="sxs-lookup"><span data-stu-id="4510e-104">Syntax</span></span>  
  
```  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4510e-105">参数</span><span class="sxs-lookup"><span data-stu-id="4510e-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="4510e-106">[out]公共语言运行时 (CLR) 应分配除了 Win32 的大小的字节数的指针`OVERLAPPED`对象。</span><span class="sxs-lookup"><span data-stu-id="4510e-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4510e-107">返回值</span><span class="sxs-lookup"><span data-stu-id="4510e-107">Return Value</span></span>  
  
|<span data-ttu-id="4510e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4510e-108">HRESULT</span></span>|<span data-ttu-id="4510e-109">描述</span><span class="sxs-lookup"><span data-stu-id="4510e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4510e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4510e-110">S_OK</span></span>|<span data-ttu-id="4510e-111">`GetHostOverlappedSize`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4510e-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="4510e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4510e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4510e-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4510e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4510e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4510e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4510e-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="4510e-115">The call timed out.</span></span>|  
|<span data-ttu-id="4510e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4510e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4510e-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="4510e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4510e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4510e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4510e-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="4510e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4510e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4510e-120">E_FAIL</span></span>|<span data-ttu-id="4510e-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4510e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4510e-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="4510e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4510e-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4510e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4510e-124">备注</span><span class="sxs-lookup"><span data-stu-id="4510e-124">Remarks</span></span>  
 <span data-ttu-id="4510e-125">所有 Windows 平台 Api 的异步 I/O 调用都采用 Win32`OVERLAPPED`对象，提供的文件指针位置等信息。</span><span class="sxs-lookup"><span data-stu-id="4510e-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="4510e-126">若要维护状态，通常进行异步 I/O 调用的应用程序，请向结构中添加自定义数据。</span><span class="sxs-lookup"><span data-stu-id="4510e-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="4510e-127">`GetHostOverlappedSize`和[ihostiocompletionmanager:: Initializehostoverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)提供要包括此类自定义数据的主机有机会。</span><span class="sxs-lookup"><span data-stu-id="4510e-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="4510e-128">CLR 调用`GetHostOverlappedSize`方法来确定要附加到主机的自定义数据的大小`OVERLAPPED`对象。</span><span class="sxs-lookup"><span data-stu-id="4510e-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4510e-129">`GetHostOverlappedSize`一次调用。</span><span class="sxs-lookup"><span data-stu-id="4510e-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="4510e-130">主机的自定义数据必须为每个 I/O 请求相同的大小。</span><span class="sxs-lookup"><span data-stu-id="4510e-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4510e-131">大小`OVERLAPPED`对象本身不包含的值中`pcbSize`。</span><span class="sxs-lookup"><span data-stu-id="4510e-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="4510e-132">有关详细信息`OVERLAPPED`结构，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="4510e-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4510e-133">惠?</span><span class="sxs-lookup"><span data-stu-id="4510e-133">Requirements</span></span>  
 <span data-ttu-id="4510e-134">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4510e-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4510e-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4510e-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4510e-136">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4510e-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4510e-137">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4510e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4510e-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="4510e-138">See Also</span></span>  
 <xref:System.Threading.NativeOverlapped>  
 [<span data-ttu-id="4510e-139">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="4510e-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="4510e-140">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="4510e-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
