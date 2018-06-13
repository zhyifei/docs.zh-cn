---
title: IHostIoCompletionManager::CloseIoCompletionPort 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 761e3b22014bdd628ffc6763615a285a16a86309
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441764"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="38a12-102">IHostIoCompletionManager::CloseIoCompletionPort 方法</span><span class="sxs-lookup"><span data-stu-id="38a12-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="38a12-103">请求主机关闭的端口已打开通过以前调用[CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)。</span><span class="sxs-lookup"><span data-stu-id="38a12-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a12-104">语法</span><span class="sxs-lookup"><span data-stu-id="38a12-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38a12-105">参数</span><span class="sxs-lookup"><span data-stu-id="38a12-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="38a12-106">[in]要关闭的端口的句柄。</span><span class="sxs-lookup"><span data-stu-id="38a12-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38a12-107">返回值</span><span class="sxs-lookup"><span data-stu-id="38a12-107">Return Value</span></span>  
  
|<span data-ttu-id="38a12-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="38a12-108">HRESULT</span></span>|<span data-ttu-id="38a12-109">描述</span><span class="sxs-lookup"><span data-stu-id="38a12-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="38a12-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="38a12-110">S_OK</span></span>|<span data-ttu-id="38a12-111">`CloseIoCompletionPort` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="38a12-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="38a12-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="38a12-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="38a12-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="38a12-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="38a12-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="38a12-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="38a12-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="38a12-115">The call timed out.</span></span>|  
|<span data-ttu-id="38a12-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="38a12-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="38a12-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="38a12-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="38a12-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="38a12-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="38a12-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="38a12-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="38a12-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="38a12-120">E_FAIL</span></span>|<span data-ttu-id="38a12-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="38a12-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="38a12-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="38a12-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="38a12-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="38a12-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="38a12-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="38a12-124">E_INVALIDARG</span></span>|<span data-ttu-id="38a12-125">传递了无效的端口句柄。</span><span class="sxs-lookup"><span data-stu-id="38a12-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38a12-126">备注</span><span class="sxs-lookup"><span data-stu-id="38a12-126">Remarks</span></span>  
 <span data-ttu-id="38a12-127">`hPort` 必须由以前调用的端口的句柄`CreateIoCompletionPort`。</span><span class="sxs-lookup"><span data-stu-id="38a12-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38a12-128">要求</span><span class="sxs-lookup"><span data-stu-id="38a12-128">Requirements</span></span>  
 <span data-ttu-id="38a12-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="38a12-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38a12-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="38a12-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38a12-131">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="38a12-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38a12-132">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38a12-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a12-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="38a12-133">See Also</span></span>  
 [<span data-ttu-id="38a12-134">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="38a12-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="38a12-135">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="38a12-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
