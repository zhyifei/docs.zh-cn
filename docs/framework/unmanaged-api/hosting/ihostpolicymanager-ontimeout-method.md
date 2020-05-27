---
title: IHostPolicyManager::OnTimeout 方法
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
ms.openlocfilehash: fb0f943d710322257d052edc5c16108671622790
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804220"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="4275a-102">IHostPolicyManager::OnTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="4275a-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="4275a-103">向宿主通知公共语言运行时（CLR）将通过对[ICLRPolicyManager：： SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md)方法的调用来执行指定的操作，以响应超时。</span><span class="sxs-lookup"><span data-stu-id="4275a-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4275a-104">语法</span><span class="sxs-lookup"><span data-stu-id="4275a-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4275a-105">参数</span><span class="sxs-lookup"><span data-stu-id="4275a-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="4275a-106">中[EClrOperation](eclroperation-enumeration.md)值之一，指示已超时的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="4275a-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="4275a-107">中[EPolicyAction](epolicyaction-enumeration.md)值之一，指示 CLR 响应超时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="4275a-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4275a-108">返回值</span><span class="sxs-lookup"><span data-stu-id="4275a-108">Return Value</span></span>  
  
|<span data-ttu-id="4275a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4275a-109">HRESULT</span></span>|<span data-ttu-id="4275a-110">说明</span><span class="sxs-lookup"><span data-stu-id="4275a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4275a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4275a-111">S_OK</span></span>|<span data-ttu-id="4275a-112">`OnTimeout`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4275a-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="4275a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4275a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4275a-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4275a-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4275a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4275a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4275a-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="4275a-116">The call timed out.</span></span>|  
|<span data-ttu-id="4275a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4275a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4275a-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="4275a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4275a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4275a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4275a-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="4275a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4275a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4275a-121">E_FAIL</span></span>|<span data-ttu-id="4275a-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4275a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4275a-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="4275a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4275a-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4275a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4275a-125">要求</span><span class="sxs-lookup"><span data-stu-id="4275a-125">Requirements</span></span>  
 <span data-ttu-id="4275a-126">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4275a-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4275a-127">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4275a-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4275a-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="4275a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4275a-129">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4275a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4275a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4275a-130">See also</span></span>

- [<span data-ttu-id="4275a-131">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="4275a-131">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="4275a-132">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="4275a-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="4275a-133">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="4275a-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="4275a-134">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="4275a-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
