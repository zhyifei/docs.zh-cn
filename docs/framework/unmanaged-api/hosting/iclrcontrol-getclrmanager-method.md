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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09079c8847b7cb995d97a4577d03982602bbadfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979168"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="ec7c4-102">ICLRControl::GetCLRManager 方法</span><span class="sxs-lookup"><span data-stu-id="ec7c4-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="ec7c4-103">到任何主机可用于配置公共语言运行时 (CLR) 管理器类型的实例获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec7c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec7c4-104">Syntax</span></span>  
  
```  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec7c4-105">参数</span><span class="sxs-lookup"><span data-stu-id="ec7c4-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="ec7c4-106">[in]`IID`要返回的管理器类型。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="ec7c4-107">以下`IID`支持值。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-107">The following `IID` values are supported.</span></span>  
  
-   <span data-ttu-id="ec7c4-108">IID_ICLRDebugManager:指定的`ppObject`的类型将为[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="ec7c4-109">IID_ICLRErrorReportingManager:指定的`ppObject`的类型将为[ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="ec7c4-110">IID_ICLRGCManager:指定的`ppObject`的类型将为[ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="ec7c4-111">IID_ICLRHostProtectionManager:指定的`ppObject`的类型将为[ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="ec7c4-112">IID_ICLROnEventManager:指定的`ppObject`的类型将为[ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="ec7c4-113">IID_ICLRPolicyManager:指定的`ppObject`的类型将为[ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
-   <span data-ttu-id="ec7c4-114">IID_ICLRTaskManager:指定的`ppObject`的类型将为[ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="ec7c4-115">[out]请求管理器中或为空，如果请求无效的管理器类型的接口指针。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec7c4-116">返回值</span><span class="sxs-lookup"><span data-stu-id="ec7c4-116">Return Value</span></span>  
  
|<span data-ttu-id="ec7c4-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec7c4-117">HRESULT</span></span>|<span data-ttu-id="ec7c4-118">描述</span><span class="sxs-lookup"><span data-stu-id="ec7c4-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec7c4-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec7c4-119">S_OK</span></span>|<span data-ttu-id="ec7c4-120">该方法成功返回。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="ec7c4-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ec7c4-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ec7c4-122">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ec7c4-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ec7c4-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ec7c4-124">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-124">The call timed out.</span></span>|  
|<span data-ttu-id="ec7c4-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ec7c4-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ec7c4-126">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ec7c4-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ec7c4-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ec7c4-128">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ec7c4-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ec7c4-129">E_FAIL</span></span>|<span data-ttu-id="ec7c4-130">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ec7c4-131">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ec7c4-132">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ec7c4-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="ec7c4-133">E_NOINTERFACE</span></span>|<span data-ttu-id="ec7c4-134">不支持的接口类型。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec7c4-135">要求</span><span class="sxs-lookup"><span data-stu-id="ec7c4-135">Requirements</span></span>  
 <span data-ttu-id="ec7c4-136">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec7c4-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec7c4-137">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ec7c4-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec7c4-138">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ec7c4-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec7c4-139">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec7c4-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec7c4-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec7c4-140">See also</span></span>

- [<span data-ttu-id="ec7c4-141">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="ec7c4-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="ec7c4-142">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="ec7c4-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
