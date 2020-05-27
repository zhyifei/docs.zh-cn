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
ms.openlocfilehash: 5e2e49b4c993e127a31b54d40f721e0714198780
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804781"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="2e8fd-102">IHostIoCompletionManager::CloseIoCompletionPort 方法</span><span class="sxs-lookup"><span data-stu-id="2e8fd-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="2e8fd-103">请求宿主关闭通过之前对[CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md)的调用打开的端口。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e8fd-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e8fd-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e8fd-105">参数</span><span class="sxs-lookup"><span data-stu-id="2e8fd-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="2e8fd-106">中要关闭的端口的句柄。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e8fd-107">返回值</span><span class="sxs-lookup"><span data-stu-id="2e8fd-107">Return Value</span></span>  
  
|<span data-ttu-id="2e8fd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e8fd-108">HRESULT</span></span>|<span data-ttu-id="2e8fd-109">说明</span><span class="sxs-lookup"><span data-stu-id="2e8fd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e8fd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e8fd-110">S_OK</span></span>|<span data-ttu-id="2e8fd-111">`CloseIoCompletionPort`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="2e8fd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2e8fd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2e8fd-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2e8fd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2e8fd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2e8fd-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-115">The call timed out.</span></span>|  
|<span data-ttu-id="2e8fd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e8fd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2e8fd-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2e8fd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2e8fd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2e8fd-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2e8fd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2e8fd-120">E_FAIL</span></span>|<span data-ttu-id="2e8fd-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2e8fd-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2e8fd-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2e8fd-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2e8fd-124">E_INVALIDARG</span></span>|<span data-ttu-id="2e8fd-125">传递了无效的端口句柄。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e8fd-126">备注</span><span class="sxs-lookup"><span data-stu-id="2e8fd-126">Remarks</span></span>  
 <span data-ttu-id="2e8fd-127">`hPort`必须是由先前对的调用创建的端口的句柄 `CreateIoCompletionPort` 。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e8fd-128">要求</span><span class="sxs-lookup"><span data-stu-id="2e8fd-128">Requirements</span></span>  
 <span data-ttu-id="2e8fd-129">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e8fd-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2e8fd-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e8fd-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="2e8fd-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e8fd-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e8fd-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e8fd-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e8fd-133">See also</span></span>

- [<span data-ttu-id="2e8fd-134">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="2e8fd-134">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="2e8fd-135">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="2e8fd-135">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
