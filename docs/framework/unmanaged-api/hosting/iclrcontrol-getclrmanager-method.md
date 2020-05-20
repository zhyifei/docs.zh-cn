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
ms.openlocfilehash: 04cb45cd021532b6cb3d74a195cbd62e1ab8d31d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615847"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="bb65b-102">ICLRControl::GetCLRManager 方法</span><span class="sxs-lookup"><span data-stu-id="bb65b-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="bb65b-103">获取一个接口指针，该指针指向主机可用于配置公共语言运行时（CLR）的任何管理器类型的实例。</span><span class="sxs-lookup"><span data-stu-id="bb65b-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb65b-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb65b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb65b-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb65b-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="bb65b-106">中`IID`要返回的管理器类型的。</span><span class="sxs-lookup"><span data-stu-id="bb65b-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="bb65b-107">支持以下 `IID` 值。</span><span class="sxs-lookup"><span data-stu-id="bb65b-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="bb65b-108">IID_ICLRDebugManager：指定 `ppObject` 将为[ICLRDebugManager](iclrdebugmanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="bb65b-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="bb65b-109">IID_ICLRErrorReportingManager：指定 `ppObject` 将为[ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="bb65b-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="bb65b-110">IID_ICLRGCManager：指定 `ppObject` 将为[ICLRGCManager](iclrgcmanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="bb65b-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="bb65b-111">IID_ICLRHostProtectionManager：指定 `ppObject` 将为[ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="bb65b-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="bb65b-112">IID_ICLROnEventManager：指定 `ppObject` 将为[ICLROnEventManager](iclroneventmanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="bb65b-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="bb65b-113">IID_ICLRPolicyManager：指定 `ppObject` 将为[ICLRPolicyManager](iclrpolicymanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="bb65b-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="bb65b-114">IID_ICLRTaskManager：指定 `ppObject` 将为[ICLRTaskManager](iclrtaskmanager-interface.md)类型。</span><span class="sxs-lookup"><span data-stu-id="bb65b-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="bb65b-115">弄指向请求的管理器的接口指针; 如果请求的管理器类型无效，则为 null。</span><span class="sxs-lookup"><span data-stu-id="bb65b-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb65b-116">返回值</span><span class="sxs-lookup"><span data-stu-id="bb65b-116">Return Value</span></span>  
  
|<span data-ttu-id="bb65b-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bb65b-117">HRESULT</span></span>|<span data-ttu-id="bb65b-118">说明</span><span class="sxs-lookup"><span data-stu-id="bb65b-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb65b-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb65b-119">S_OK</span></span>|<span data-ttu-id="bb65b-120">该方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="bb65b-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="bb65b-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bb65b-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bb65b-122">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="bb65b-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bb65b-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bb65b-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bb65b-124">调用超时。</span><span class="sxs-lookup"><span data-stu-id="bb65b-124">The call timed out.</span></span>|  
|<span data-ttu-id="bb65b-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bb65b-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bb65b-126">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="bb65b-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bb65b-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bb65b-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bb65b-128">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="bb65b-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bb65b-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bb65b-129">E_FAIL</span></span>|<span data-ttu-id="bb65b-130">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="bb65b-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bb65b-131">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="bb65b-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bb65b-132">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="bb65b-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bb65b-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="bb65b-133">E_NOINTERFACE</span></span>|<span data-ttu-id="bb65b-134">接口类型不受支持。</span><span class="sxs-lookup"><span data-stu-id="bb65b-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb65b-135">要求</span><span class="sxs-lookup"><span data-stu-id="bb65b-135">Requirements</span></span>  
 <span data-ttu-id="bb65b-136">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb65b-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb65b-137">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bb65b-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb65b-138">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="bb65b-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb65b-139">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb65b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb65b-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb65b-140">See also</span></span>

- [<span data-ttu-id="bb65b-141">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="bb65b-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="bb65b-142">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="bb65b-142">IHostControl Interface</span></span>](ihostcontrol-interface.md)
