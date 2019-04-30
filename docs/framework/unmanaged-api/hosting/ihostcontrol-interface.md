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
ms.openlocfilehash: 014e5c9951091046ae07374794743e82affcd5ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967722"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="1795c-102">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="1795c-102">IHostControl Interface</span></span>
<span data-ttu-id="1795c-103">提供用于配置加载的程序集，以及用于确定主机支持的托管接口的方法。</span><span class="sxs-lookup"><span data-stu-id="1795c-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1795c-104">方法</span><span class="sxs-lookup"><span data-stu-id="1795c-104">Methods</span></span>  
  
|<span data-ttu-id="1795c-105">方法</span><span class="sxs-lookup"><span data-stu-id="1795c-105">Method</span></span>|<span data-ttu-id="1795c-106">描述</span><span class="sxs-lookup"><span data-stu-id="1795c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1795c-107">GetHostManager 方法</span><span class="sxs-lookup"><span data-stu-id="1795c-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="1795c-108">获取具有指定的接口指针接口的主机的实现`IID`。</span><span class="sxs-lookup"><span data-stu-id="1795c-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="1795c-109">SetAppDomainManager 方法</span><span class="sxs-lookup"><span data-stu-id="1795c-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="1795c-110">通知主机应用程序域已创建。</span><span class="sxs-lookup"><span data-stu-id="1795c-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1795c-111">要求</span><span class="sxs-lookup"><span data-stu-id="1795c-111">Requirements</span></span>  
 <span data-ttu-id="1795c-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1795c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1795c-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1795c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1795c-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1795c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1795c-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1795c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1795c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="1795c-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="1795c-117">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="1795c-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="1795c-118">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="1795c-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="1795c-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="1795c-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
