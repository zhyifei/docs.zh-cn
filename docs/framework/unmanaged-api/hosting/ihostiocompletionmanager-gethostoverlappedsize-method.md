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
ms.openlocfilehash: 3c662021894acbb8eb448fa2166498254158caa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133865"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="c6791-102">IHostIoCompletionManager::GetHostOverlappedSize 方法</span><span class="sxs-lookup"><span data-stu-id="c6791-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="c6791-103">获取宿主打算追加到 i/o 请求的任何自定义数据的大小。</span><span class="sxs-lookup"><span data-stu-id="c6791-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6791-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6791-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6791-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6791-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="c6791-106">弄一个指针，指向公共语言运行时（CLR）应分配的字节数，以及 Win32 `OVERLAPPED` 对象的大小。</span><span class="sxs-lookup"><span data-stu-id="c6791-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6791-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c6791-107">Return Value</span></span>  
  
|<span data-ttu-id="c6791-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6791-108">HRESULT</span></span>|<span data-ttu-id="c6791-109">描述</span><span class="sxs-lookup"><span data-stu-id="c6791-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6791-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6791-110">S_OK</span></span>|<span data-ttu-id="c6791-111">`GetHostOverlappedSize` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="c6791-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="c6791-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6791-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6791-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c6791-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c6791-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c6791-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c6791-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="c6791-115">The call timed out.</span></span>|  
|<span data-ttu-id="c6791-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c6791-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c6791-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c6791-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c6791-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c6791-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c6791-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="c6791-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c6791-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6791-120">E_FAIL</span></span>|<span data-ttu-id="c6791-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c6791-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c6791-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="c6791-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c6791-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c6791-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6791-124">备注</span><span class="sxs-lookup"><span data-stu-id="c6791-124">Remarks</span></span>  
 <span data-ttu-id="c6791-125">对 Windows 平台 Api 的所有异步 i/o 调用都采用 Win32 `OVERLAPPED` 对象，该对象提供文件指针位置等信息。</span><span class="sxs-lookup"><span data-stu-id="c6791-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="c6791-126">若要维护状态，执行异步 i/o 调用的应用程序通常会将自定义数据添加到该结构中。</span><span class="sxs-lookup"><span data-stu-id="c6791-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="c6791-127">`GetHostOverlappedSize` 和[IHostIoCompletionManager：： InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)为主机提供了包含此类自定义数据的机会。</span><span class="sxs-lookup"><span data-stu-id="c6791-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="c6791-128">CLR 调用 `GetHostOverlappedSize` 方法来确定宿主打算追加到 `OVERLAPPED` 对象的自定义数据的大小。</span><span class="sxs-lookup"><span data-stu-id="c6791-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6791-129">`GetHostOverlappedSize` 只调用一次。</span><span class="sxs-lookup"><span data-stu-id="c6791-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="c6791-130">主机的自定义数据必须与每个 i/o 请求的大小相同。</span><span class="sxs-lookup"><span data-stu-id="c6791-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c6791-131">`OVERLAPPED` 对象本身的大小不包含在 `pcbSize`的值中。</span><span class="sxs-lookup"><span data-stu-id="c6791-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="c6791-132">有关 `OVERLAPPED` 结构的详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="c6791-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6791-133">要求</span><span class="sxs-lookup"><span data-stu-id="c6791-133">Requirements</span></span>  
 <span data-ttu-id="c6791-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6791-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6791-135">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c6791-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6791-136">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c6791-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6791-137">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6791-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6791-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6791-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="c6791-139">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="c6791-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="c6791-140">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="c6791-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
