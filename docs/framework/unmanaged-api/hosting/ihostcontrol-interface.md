---
title: "IHostControl 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostControl
helpviewer_keywords: IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d0eaecef4cc34549c7d37953a5c8144bdd983692
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="4a803-102">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="4a803-102">IHostControl Interface</span></span>
<span data-ttu-id="4a803-103">提供用于配置加载的程序集，以及用于确定主机支持哪些承载接口方法。</span><span class="sxs-lookup"><span data-stu-id="4a803-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a803-104">方法</span><span class="sxs-lookup"><span data-stu-id="4a803-104">Methods</span></span>  
  
|<span data-ttu-id="4a803-105">方法</span><span class="sxs-lookup"><span data-stu-id="4a803-105">Method</span></span>|<span data-ttu-id="4a803-106">描述</span><span class="sxs-lookup"><span data-stu-id="4a803-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a803-107">GetHostManager 方法</span><span class="sxs-lookup"><span data-stu-id="4a803-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="4a803-108">获取具有指定的接口指针接口的主机的实现`IID`。</span><span class="sxs-lookup"><span data-stu-id="4a803-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="4a803-109">SetAppDomainManager 方法</span><span class="sxs-lookup"><span data-stu-id="4a803-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="4a803-110">通知主机应用程序域已创建。</span><span class="sxs-lookup"><span data-stu-id="4a803-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a803-111">惠?</span><span class="sxs-lookup"><span data-stu-id="4a803-111">Requirements</span></span>  
 <span data-ttu-id="4a803-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a803-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a803-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4a803-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a803-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4a803-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a803-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a803-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a803-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a803-116">See Also</span></span>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="4a803-117">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="4a803-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="4a803-118">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="4a803-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="4a803-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="4a803-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
