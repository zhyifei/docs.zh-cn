---
title: ICLRDomainManager 接口
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
ms.openlocfilehash: aa874205cf14232e7a69ed2215086e33c0beab4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129343"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="cd4b8-102">ICLRDomainManager 接口</span><span class="sxs-lookup"><span data-stu-id="cd4b8-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="cd4b8-103">使宿主能够指定将用于初始化默认应用程序域的应用程序域管理器，并指定初始化属性。</span><span class="sxs-lookup"><span data-stu-id="cd4b8-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd4b8-104">方法</span><span class="sxs-lookup"><span data-stu-id="cd4b8-104">Methods</span></span>  
  
|<span data-ttu-id="cd4b8-105">方法</span><span class="sxs-lookup"><span data-stu-id="cd4b8-105">Method</span></span>|<span data-ttu-id="cd4b8-106">描述</span><span class="sxs-lookup"><span data-stu-id="cd4b8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd4b8-107">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="cd4b8-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="cd4b8-108">指定从应用程序域管理器的 <xref:System.AppDomainManager?displayProperty=nameWithType> 类派生的类型，将用于初始化默认应用程序域。</span><span class="sxs-lookup"><span data-stu-id="cd4b8-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="cd4b8-109">SetPropertiesForDefaultAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="cd4b8-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="cd4b8-110">设置将用于初始化默认应用程序域的属性。</span><span class="sxs-lookup"><span data-stu-id="cd4b8-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd4b8-111">备注</span><span class="sxs-lookup"><span data-stu-id="cd4b8-111">Remarks</span></span>  
 <span data-ttu-id="cd4b8-112">若要获取此接口的实例，请使用管理器类型 IID `IID_ICLRDomainManager`调用[ICLRControl：： GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="cd4b8-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd4b8-113">要求</span><span class="sxs-lookup"><span data-stu-id="cd4b8-113">Requirements</span></span>  
 <span data-ttu-id="cd4b8-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd4b8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd4b8-115">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="cd4b8-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cd4b8-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="cd4b8-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd4b8-117">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd4b8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd4b8-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd4b8-118">See also</span></span>

- [<span data-ttu-id="cd4b8-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="cd4b8-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="cd4b8-120">承载</span><span class="sxs-lookup"><span data-stu-id="cd4b8-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
