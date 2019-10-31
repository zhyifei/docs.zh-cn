---
title: ICLRControl::GetCLRManager 方法
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
ms.openlocfilehash: fa9608423456caeb6020e883a14f2c41583ac4d9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126614"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="8a608-102">ICLRControl::GetCLRManager 方法</span><span class="sxs-lookup"><span data-stu-id="8a608-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="8a608-103">获取一个接口指针，该指针指向主机可用于配置公共语言运行时（CLR）的任何管理器类型的实例。</span><span class="sxs-lookup"><span data-stu-id="8a608-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a608-104">语法</span><span class="sxs-lookup"><span data-stu-id="8a608-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a608-105">参数</span><span class="sxs-lookup"><span data-stu-id="8a608-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="8a608-106">中要返回的管理器类型的 `IID`。</span><span class="sxs-lookup"><span data-stu-id="8a608-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="8a608-107">支持以下 `IID` 值。</span><span class="sxs-lookup"><span data-stu-id="8a608-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="8a608-108">IID_ICLRDebugManager：指定 `ppObject` 将是[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="8a608-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="8a608-109">IID_ICLRErrorReportingManager：指定 `ppObject` 将是[ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="8a608-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="8a608-110">IID_ICLRGCManager：指定 `ppObject` 将是[ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="8a608-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="8a608-111">IID_ICLRHostProtectionManager：指定 `ppObject` 将是[ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="8a608-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="8a608-112">IID_ICLROnEventManager：指定 `ppObject` 将是[ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="8a608-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="8a608-113">IID_ICLRPolicyManager：指定 `ppObject` 将是[ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="8a608-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="8a608-114">IID_ICLRTaskManager：指定 `ppObject` 将是[ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="8a608-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="8a608-115">弄指向请求的管理器的接口指针; 如果请求的管理器类型无效，则为 null。</span><span class="sxs-lookup"><span data-stu-id="8a608-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a608-116">返回值</span><span class="sxs-lookup"><span data-stu-id="8a608-116">Return Value</span></span>  
  
|<span data-ttu-id="8a608-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a608-117">HRESULT</span></span>|<span data-ttu-id="8a608-118">描述</span><span class="sxs-lookup"><span data-stu-id="8a608-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a608-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a608-119">S_OK</span></span>|<span data-ttu-id="8a608-120">方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8a608-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="8a608-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8a608-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8a608-122">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8a608-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8a608-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8a608-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8a608-124">调用超时。</span><span class="sxs-lookup"><span data-stu-id="8a608-124">The call timed out.</span></span>|  
|<span data-ttu-id="8a608-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8a608-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8a608-126">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8a608-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8a608-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8a608-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8a608-128">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="8a608-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8a608-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8a608-129">E_FAIL</span></span>|<span data-ttu-id="8a608-130">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8a608-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8a608-131">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="8a608-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8a608-132">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8a608-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8a608-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="8a608-133">E_NOINTERFACE</span></span>|<span data-ttu-id="8a608-134">接口类型不受支持。</span><span class="sxs-lookup"><span data-stu-id="8a608-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a608-135">要求</span><span class="sxs-lookup"><span data-stu-id="8a608-135">Requirements</span></span>  
 <span data-ttu-id="8a608-136">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8a608-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a608-137">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8a608-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a608-138">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8a608-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a608-139">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a608-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a608-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a608-140">See also</span></span>

- [<span data-ttu-id="8a608-141">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="8a608-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="8a608-142">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="8a608-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
