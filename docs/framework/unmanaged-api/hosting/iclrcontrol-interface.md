---
title: "ICLRControl 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRControl
helpviewer_keywords: ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 98b41ea0062534d9e990a7fe366e8f746ae87f38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="43bbb-102">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="43bbb-102">ICLRControl Interface</span></span>
<span data-ttu-id="43bbb-103">提供使主机可获取对，引用和配置的公共语言运行时 (CLR) 方面的方法。</span><span class="sxs-lookup"><span data-stu-id="43bbb-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43bbb-104">方法</span><span class="sxs-lookup"><span data-stu-id="43bbb-104">Methods</span></span>  
  
|<span data-ttu-id="43bbb-105">方法</span><span class="sxs-lookup"><span data-stu-id="43bbb-105">Method</span></span>|<span data-ttu-id="43bbb-106">描述</span><span class="sxs-lookup"><span data-stu-id="43bbb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43bbb-107">GetCLRManager 方法</span><span class="sxs-lookup"><span data-stu-id="43bbb-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="43bbb-108">到任何主机可用于配置 CLR 管理器类型的实例中获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="43bbb-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="43bbb-109">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="43bbb-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="43bbb-110">设置其类型派生自此<xref:System.AppDomainManager>作为应用程序域管理器的类型。</span><span class="sxs-lookup"><span data-stu-id="43bbb-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43bbb-111">要求</span><span class="sxs-lookup"><span data-stu-id="43bbb-111">Requirements</span></span>  
 <span data-ttu-id="43bbb-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43bbb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43bbb-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43bbb-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43bbb-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="43bbb-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43bbb-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43bbb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43bbb-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43bbb-116">See Also</span></span>  
 [<span data-ttu-id="43bbb-117">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="43bbb-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="43bbb-118">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="43bbb-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="43bbb-119">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="43bbb-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="43bbb-120">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="43bbb-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="43bbb-121">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="43bbb-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="43bbb-122">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="43bbb-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="43bbb-123">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="43bbb-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="43bbb-124">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="43bbb-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="43bbb-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="43bbb-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
