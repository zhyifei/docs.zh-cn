---
title: IHostControl 接口
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 961f166cdb2c69e29fef4753a37edcc57c427257
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438085"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="4837b-102">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="4837b-102">IHostControl Interface</span></span>
<span data-ttu-id="4837b-103">提供用于配置加载的程序集，以及用于确定主机支持哪些承载接口方法。</span><span class="sxs-lookup"><span data-stu-id="4837b-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4837b-104">方法</span><span class="sxs-lookup"><span data-stu-id="4837b-104">Methods</span></span>  
  
|<span data-ttu-id="4837b-105">方法</span><span class="sxs-lookup"><span data-stu-id="4837b-105">Method</span></span>|<span data-ttu-id="4837b-106">描述</span><span class="sxs-lookup"><span data-stu-id="4837b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4837b-107">GetHostManager 方法</span><span class="sxs-lookup"><span data-stu-id="4837b-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="4837b-108">获取具有指定的接口指针接口的主机的实现`IID`。</span><span class="sxs-lookup"><span data-stu-id="4837b-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="4837b-109">SetAppDomainManager 方法</span><span class="sxs-lookup"><span data-stu-id="4837b-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="4837b-110">通知主机应用程序域已创建。</span><span class="sxs-lookup"><span data-stu-id="4837b-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4837b-111">要求</span><span class="sxs-lookup"><span data-stu-id="4837b-111">Requirements</span></span>  
 <span data-ttu-id="4837b-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4837b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4837b-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4837b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4837b-114">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4837b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4837b-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4837b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4837b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4837b-116">See Also</span></span>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="4837b-117">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="4837b-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="4837b-118">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="4837b-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="4837b-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="4837b-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
