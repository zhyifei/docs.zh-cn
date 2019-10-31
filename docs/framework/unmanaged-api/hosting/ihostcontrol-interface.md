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
ms.openlocfilehash: 444a78705c61d5a53764f55185ef1a907830bd71
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195882"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="3ae70-102">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="3ae70-102">IHostControl Interface</span></span>
<span data-ttu-id="3ae70-103">提供用于配置程序集加载和确定宿主支持哪些宿主接口的方法。</span><span class="sxs-lookup"><span data-stu-id="3ae70-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ae70-104">方法</span><span class="sxs-lookup"><span data-stu-id="3ae70-104">Methods</span></span>  
  
|<span data-ttu-id="3ae70-105">方法</span><span class="sxs-lookup"><span data-stu-id="3ae70-105">Method</span></span>|<span data-ttu-id="3ae70-106">描述</span><span class="sxs-lookup"><span data-stu-id="3ae70-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ae70-107">GetHostManager 方法</span><span class="sxs-lookup"><span data-stu-id="3ae70-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="3ae70-108">获取一个接口指针，该指针指向具有指定 `IID`的接口的主机实现。</span><span class="sxs-lookup"><span data-stu-id="3ae70-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="3ae70-109">SetAppDomainManager 方法</span><span class="sxs-lookup"><span data-stu-id="3ae70-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="3ae70-110">通知宿主已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="3ae70-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ae70-111">要求</span><span class="sxs-lookup"><span data-stu-id="3ae70-111">Requirements</span></span>  
 <span data-ttu-id="3ae70-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ae70-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ae70-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3ae70-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ae70-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="3ae70-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ae70-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ae70-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae70-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ae70-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="3ae70-117">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="3ae70-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="3ae70-118">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="3ae70-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="3ae70-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="3ae70-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
