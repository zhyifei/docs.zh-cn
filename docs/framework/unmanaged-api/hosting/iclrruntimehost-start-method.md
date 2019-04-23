---
title: ICLRRuntimeHost::Start 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 608612f6a0f4395092e33ce75fdbd249f19ae4f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59172609"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="ed3a4-102">ICLRRuntimeHost::Start 方法</span><span class="sxs-lookup"><span data-stu-id="ed3a4-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="ed3a4-103">初始化公共语言运行时 (CLR) 到另一进程。</span><span class="sxs-lookup"><span data-stu-id="ed3a4-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed3a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="ed3a4-104">Syntax</span></span>  
  
```  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ed3a4-105">返回值</span><span class="sxs-lookup"><span data-stu-id="ed3a4-105">Return Value</span></span>  
  
|<span data-ttu-id="ed3a4-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed3a4-106">HRESULT</span></span>|<span data-ttu-id="ed3a4-107">描述</span><span class="sxs-lookup"><span data-stu-id="ed3a4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed3a4-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed3a4-108">S_OK</span></span>|<span data-ttu-id="ed3a4-109">`Start` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ed3a4-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="ed3a4-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ed3a4-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ed3a4-111">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ed3a4-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ed3a4-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ed3a4-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ed3a4-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="ed3a4-113">The call timed out.</span></span>|  
|<span data-ttu-id="ed3a4-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ed3a4-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ed3a4-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ed3a4-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ed3a4-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ed3a4-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ed3a4-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ed3a4-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ed3a4-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ed3a4-118">E_FAIL</span></span>|<span data-ttu-id="ed3a4-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ed3a4-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ed3a4-120">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="ed3a4-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ed3a4-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ed3a4-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed3a4-122">备注</span><span class="sxs-lookup"><span data-stu-id="ed3a4-122">Remarks</span></span>  
 <span data-ttu-id="ed3a4-123">在许多情况下它不需要调用`Start`，因为运行时将运行托管的代码的第一个请求时自动初始化自身。</span><span class="sxs-lookup"><span data-stu-id="ed3a4-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="ed3a4-124">但是，可以使用`Start`指定完全时运行时应进行初始化。</span><span class="sxs-lookup"><span data-stu-id="ed3a4-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed3a4-125">要求</span><span class="sxs-lookup"><span data-stu-id="ed3a4-125">Requirements</span></span>  
 <span data-ttu-id="ed3a4-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed3a4-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed3a4-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ed3a4-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed3a4-128">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ed3a4-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed3a4-129">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed3a4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3a4-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed3a4-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="ed3a4-131">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="ed3a4-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
