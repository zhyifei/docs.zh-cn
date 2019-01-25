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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 797b6031449672e8b610b2a53e77497e5835ea6a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657423"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="a17e0-102">ICLRDomainManager 接口</span><span class="sxs-lookup"><span data-stu-id="a17e0-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="a17e0-103">使宿主能够指定将用于初始化默认应用程序域，并指定初始化属性的应用程序域管理器。</span><span class="sxs-lookup"><span data-stu-id="a17e0-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a17e0-104">方法</span><span class="sxs-lookup"><span data-stu-id="a17e0-104">Methods</span></span>  
  
|<span data-ttu-id="a17e0-105">方法</span><span class="sxs-lookup"><span data-stu-id="a17e0-105">Method</span></span>|<span data-ttu-id="a17e0-106">描述</span><span class="sxs-lookup"><span data-stu-id="a17e0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a17e0-107">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="a17e0-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="a17e0-108">指定的类型，派生自<xref:System.AppDomainManager?displayProperty=nameWithType>的将用来初始化默认应用程序域的应用程序域管理器类。</span><span class="sxs-lookup"><span data-stu-id="a17e0-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="a17e0-109">SetPropertiesForDefaultAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="a17e0-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="a17e0-110">设置将用来初始化默认应用程序域的属性。</span><span class="sxs-lookup"><span data-stu-id="a17e0-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a17e0-111">备注</span><span class="sxs-lookup"><span data-stu-id="a17e0-111">Remarks</span></span>  
 <span data-ttu-id="a17e0-112">若要获取此接口的实例，请调用[iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)方法替换管理器类型 IID `IID_ICLRDomainManager`。</span><span class="sxs-lookup"><span data-stu-id="a17e0-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a17e0-113">要求</span><span class="sxs-lookup"><span data-stu-id="a17e0-113">Requirements</span></span>  
 <span data-ttu-id="a17e0-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a17e0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a17e0-115">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a17e0-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a17e0-116">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a17e0-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a17e0-117">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a17e0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a17e0-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a17e0-118">See also</span></span>
- [<span data-ttu-id="a17e0-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="a17e0-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="a17e0-120">承载</span><span class="sxs-lookup"><span data-stu-id="a17e0-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
