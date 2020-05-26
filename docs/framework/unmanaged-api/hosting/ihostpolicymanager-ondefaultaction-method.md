---
title: IHostPolicyManager::OnDefaultAction 方法
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type:
- apiref
ms.openlocfilehash: e6aa8cb814e509d310c2f5b5524e0fd6727fc43f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804275"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="626a8-102">IHostPolicyManager::OnDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="626a8-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="626a8-103">向宿主通知公共语言运行时（CLR）将使用调用[ICLRPolicyManager：： SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md)方法设置的默认操作，以响应线程中止或 <xref:System.AppDomain> 卸载。</span><span class="sxs-lookup"><span data-stu-id="626a8-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="626a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="626a8-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="626a8-105">参数</span><span class="sxs-lookup"><span data-stu-id="626a8-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="626a8-106">中[EClrOperation](eclroperation-enumeration.md)值之一，指示 CLR 响应的事件类型。</span><span class="sxs-lookup"><span data-stu-id="626a8-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="626a8-107">中[EPolicyAction](epolicyaction-enumeration.md)值之一，指示 CLR 响应事件所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="626a8-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="626a8-108">返回值</span><span class="sxs-lookup"><span data-stu-id="626a8-108">Return Value</span></span>  
  
|<span data-ttu-id="626a8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="626a8-109">HRESULT</span></span>|<span data-ttu-id="626a8-110">说明</span><span class="sxs-lookup"><span data-stu-id="626a8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="626a8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="626a8-111">S_OK</span></span>|<span data-ttu-id="626a8-112">`OnDefaultAction`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="626a8-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="626a8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="626a8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="626a8-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="626a8-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="626a8-115">顺利</span><span class="sxs-lookup"><span data-stu-id="626a8-115">successfully</span></span>|  
|<span data-ttu-id="626a8-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="626a8-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="626a8-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="626a8-117">The call timed out.</span></span>|  
|<span data-ttu-id="626a8-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="626a8-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="626a8-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="626a8-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="626a8-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="626a8-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="626a8-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="626a8-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="626a8-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="626a8-122">E_FAIL</span></span>|<span data-ttu-id="626a8-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="626a8-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="626a8-124">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="626a8-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="626a8-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="626a8-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="626a8-126">要求</span><span class="sxs-lookup"><span data-stu-id="626a8-126">Requirements</span></span>  
 <span data-ttu-id="626a8-127">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="626a8-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="626a8-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="626a8-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="626a8-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="626a8-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="626a8-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="626a8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="626a8-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="626a8-131">See also</span></span>

- [<span data-ttu-id="626a8-132">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="626a8-132">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="626a8-133">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="626a8-133">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="626a8-134">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="626a8-134">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="626a8-135">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="626a8-135">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
