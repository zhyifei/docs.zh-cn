---
title: "IHostPolicyManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager
helpviewer_keywords: IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0efbc0c51121156d112c63ba4ae59c6c9e95cd95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="00be2-102">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="00be2-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="00be2-103">提供通知的情况下执行公共语言运行时 (CLR) 的操作主机中止、 超时或失败的方法。</span><span class="sxs-lookup"><span data-stu-id="00be2-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00be2-104">方法</span><span class="sxs-lookup"><span data-stu-id="00be2-104">Methods</span></span>  
  
|<span data-ttu-id="00be2-105">方法</span><span class="sxs-lookup"><span data-stu-id="00be2-105">Method</span></span>|<span data-ttu-id="00be2-106">描述</span><span class="sxs-lookup"><span data-stu-id="00be2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="00be2-107">OnDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="00be2-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="00be2-108">通知主机 CLR 即将需要通过调用指定的默认操作[iclrpolicymanager:: Setdefaultaction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)以响应线程中止或<xref:System.AppDomain>卸载。</span><span class="sxs-lookup"><span data-stu-id="00be2-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="00be2-109">OnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="00be2-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="00be2-110">通知 CLR 即将采取措施通过调用指定的主机[iclrpolicymanager:: Setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)以响应的资源分配或回收故障。</span><span class="sxs-lookup"><span data-stu-id="00be2-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="00be2-111">OnTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="00be2-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="00be2-112">通知 CLR 即将采取措施通过调用指定的主机[iclrpolicymanager:: Setactionontimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)以响应超时。</span><span class="sxs-lookup"><span data-stu-id="00be2-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00be2-113">惠?</span><span class="sxs-lookup"><span data-stu-id="00be2-113">Requirements</span></span>  
 <span data-ttu-id="00be2-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00be2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00be2-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="00be2-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00be2-116">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="00be2-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00be2-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00be2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00be2-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="00be2-118">See Also</span></span>  
 [<span data-ttu-id="00be2-119">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="00be2-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="00be2-120">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="00be2-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="00be2-121">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="00be2-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="00be2-122">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="00be2-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="00be2-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="00be2-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
