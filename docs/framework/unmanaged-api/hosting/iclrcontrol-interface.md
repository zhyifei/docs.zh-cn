---
title: ICLRControl 接口
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f70e7958cc9ac198738ed72732fe7b6563c89067
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175417"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="63e47-102">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="63e47-102">ICLRControl Interface</span></span>
<span data-ttu-id="63e47-103">提供允许主机来获得对，引用和配置的公共语言运行时 (CLR) 方面的方法。</span><span class="sxs-lookup"><span data-stu-id="63e47-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63e47-104">方法</span><span class="sxs-lookup"><span data-stu-id="63e47-104">Methods</span></span>  
  
|<span data-ttu-id="63e47-105">方法</span><span class="sxs-lookup"><span data-stu-id="63e47-105">Method</span></span>|<span data-ttu-id="63e47-106">描述</span><span class="sxs-lookup"><span data-stu-id="63e47-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63e47-107">GetCLRManager 方法</span><span class="sxs-lookup"><span data-stu-id="63e47-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="63e47-108">到任何主机可用于配置 CLR 的 manager 类型的实例获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="63e47-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="63e47-109">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="63e47-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="63e47-110">设置类型派生自<xref:System.AppDomainManager>作为应用程序域管理器的类型。</span><span class="sxs-lookup"><span data-stu-id="63e47-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63e47-111">要求</span><span class="sxs-lookup"><span data-stu-id="63e47-111">Requirements</span></span>  
 <span data-ttu-id="63e47-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="63e47-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63e47-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63e47-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63e47-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="63e47-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63e47-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63e47-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63e47-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="63e47-116">See also</span></span>

- [<span data-ttu-id="63e47-117">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="63e47-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="63e47-118">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="63e47-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="63e47-119">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="63e47-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="63e47-120">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="63e47-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="63e47-121">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="63e47-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="63e47-122">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="63e47-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="63e47-123">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="63e47-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="63e47-124">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="63e47-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="63e47-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="63e47-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
