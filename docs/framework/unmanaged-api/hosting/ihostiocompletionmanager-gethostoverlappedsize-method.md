---
title: IHostIoCompletionManager::GetHostOverlappedSize 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4a5661128765cc058417fef6373767d46a4bd7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111795"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="71978-102">IHostIoCompletionManager::GetHostOverlappedSize 方法</span><span class="sxs-lookup"><span data-stu-id="71978-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="71978-103">获取宿主要追加到输入/输出请求的任何自定义数据的大小。</span><span class="sxs-lookup"><span data-stu-id="71978-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71978-104">语法</span><span class="sxs-lookup"><span data-stu-id="71978-104">Syntax</span></span>  
  
```  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71978-105">参数</span><span class="sxs-lookup"><span data-stu-id="71978-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="71978-106">[out]指向公共语言运行时 (CLR) 除了 Win32 的大小应分配的字节数的`OVERLAPPED`对象。</span><span class="sxs-lookup"><span data-stu-id="71978-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71978-107">返回值</span><span class="sxs-lookup"><span data-stu-id="71978-107">Return Value</span></span>  
  
|<span data-ttu-id="71978-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71978-108">HRESULT</span></span>|<span data-ttu-id="71978-109">描述</span><span class="sxs-lookup"><span data-stu-id="71978-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71978-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="71978-110">S_OK</span></span>|`GetHostOverlappedSize` <span data-ttu-id="71978-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="71978-111">returned successfully.</span></span>|  
|<span data-ttu-id="71978-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71978-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71978-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="71978-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71978-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71978-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71978-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="71978-115">The call timed out.</span></span>|  
|<span data-ttu-id="71978-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71978-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71978-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="71978-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71978-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71978-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71978-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="71978-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71978-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71978-120">E_FAIL</span></span>|<span data-ttu-id="71978-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="71978-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71978-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="71978-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71978-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="71978-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71978-124">备注</span><span class="sxs-lookup"><span data-stu-id="71978-124">Remarks</span></span>  
 <span data-ttu-id="71978-125">所有 Windows 平台 Api 的异步 I/O 调用都采用 Win32`OVERLAPPED`对象，它提供的文件指针位置等信息。</span><span class="sxs-lookup"><span data-stu-id="71978-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="71978-126">若要维护状态，通常进行异步 I/O 调用的应用程序，请向结构中添加自定义数据。</span><span class="sxs-lookup"><span data-stu-id="71978-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> `GetHostOverlappedSize` <span data-ttu-id="71978-127">并[ihostiocompletionmanager:: Initializehostoverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)提供要包括此类自定义数据的主机的机会。</span><span class="sxs-lookup"><span data-stu-id="71978-127">and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="71978-128">CLR 调用`GetHostOverlappedSize`方法，以确定要附加到主机的自定义数据的大小`OVERLAPPED`对象。</span><span class="sxs-lookup"><span data-stu-id="71978-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
>  `GetHostOverlappedSize` <span data-ttu-id="71978-129">一次调用。</span><span class="sxs-lookup"><span data-stu-id="71978-129">is called only once.</span></span> <span data-ttu-id="71978-130">主机的自定义数据必须为每个 I/O 请求大小相同。</span><span class="sxs-lookup"><span data-stu-id="71978-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="71978-131">大小`OVERLAPPED`中的值不包括对象本身`pcbSize`。</span><span class="sxs-lookup"><span data-stu-id="71978-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="71978-132">有关详细信息`OVERLAPPED`结构，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="71978-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71978-133">要求</span><span class="sxs-lookup"><span data-stu-id="71978-133">Requirements</span></span>  
 <span data-ttu-id="71978-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71978-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71978-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71978-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71978-136">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="71978-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="71978-137">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="71978-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="71978-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="71978-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="71978-139">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="71978-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="71978-140">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="71978-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
