---
title: IHostMemoryManager::RegisterMemoryNotificationCallback 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
ms.openlocfilehash: 0c20df85560f715e829fe02be599788854fcb0f1
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804482"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="b12b0-102">IHostMemoryManager::RegisterMemoryNotificationCallback 方法</span><span class="sxs-lookup"><span data-stu-id="b12b0-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="b12b0-103">注册指向主机调用的回调函数的指针，以便向公共语言运行时（CLR）通知当前计算机上的当前内存负载。</span><span class="sxs-lookup"><span data-stu-id="b12b0-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b12b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="b12b0-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b12b0-105">参数</span><span class="sxs-lookup"><span data-stu-id="b12b0-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="b12b0-106">中一个接口指针，该指针指向由 CLR 实现的[ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="b12b0-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b12b0-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b12b0-107">Return Value</span></span>  
  
|<span data-ttu-id="b12b0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b12b0-108">HRESULT</span></span>|<span data-ttu-id="b12b0-109">说明</span><span class="sxs-lookup"><span data-stu-id="b12b0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b12b0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b12b0-110">S_OK</span></span>|<span data-ttu-id="b12b0-111">`RegisterMemoryNotificationCallback`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="b12b0-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="b12b0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b12b0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b12b0-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b12b0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b12b0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b12b0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b12b0-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="b12b0-115">The call timed out.</span></span>|  
|<span data-ttu-id="b12b0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b12b0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b12b0-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b12b0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b12b0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b12b0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b12b0-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="b12b0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b12b0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b12b0-120">E_FAIL</span></span>|<span data-ttu-id="b12b0-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b12b0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b12b0-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="b12b0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b12b0-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b12b0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b12b0-124">备注</span><span class="sxs-lookup"><span data-stu-id="b12b0-124">Remarks</span></span>  
 <span data-ttu-id="b12b0-125">由于 `ICLRMemoryNotificationCallback` 接口仅定义了一个方法（[ICLRMemoryNotificationCallback：： OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)），并且由于 `pCallback` 是一个指向 `ICLRMemoryNotificationCallback` CLR 提供的实例的指针，因此注册对于回调函数本身是有效的。</span><span class="sxs-lookup"><span data-stu-id="b12b0-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="b12b0-126">宿主调用 `OnMemoryNotification` 以报告内存压力条件，而不是使用标准的 Win32 `CreateMemoryResourceNotification` 函数。</span><span class="sxs-lookup"><span data-stu-id="b12b0-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="b12b0-127">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="b12b0-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b12b0-128">对 `OnMemoryNotification` 从不阻止的的调用。</span><span class="sxs-lookup"><span data-stu-id="b12b0-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="b12b0-129">它们始终立即返回。</span><span class="sxs-lookup"><span data-stu-id="b12b0-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b12b0-130">要求</span><span class="sxs-lookup"><span data-stu-id="b12b0-130">Requirements</span></span>  
 <span data-ttu-id="b12b0-131">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b12b0-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b12b0-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b12b0-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b12b0-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b12b0-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b12b0-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b12b0-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b12b0-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b12b0-135">See also</span></span>

- [<span data-ttu-id="b12b0-136">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b12b0-136">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="b12b0-137">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="b12b0-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
