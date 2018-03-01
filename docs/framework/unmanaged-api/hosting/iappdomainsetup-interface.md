---
title: "IAppDomainSetup 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9db1b787015231b3d9053d4ed316cb70c5db96ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="e7710-102">IAppDomainSetup 接口</span><span class="sxs-lookup"><span data-stu-id="e7710-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="e7710-103">提供的属性，使该主机可配置<xref:System.AppDomain?displayProperty=nameWithType>类型之前调用[icorruntimehost:: Createdomainex](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)方法来创建它。</span><span class="sxs-lookup"><span data-stu-id="e7710-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e7710-104">属性</span><span class="sxs-lookup"><span data-stu-id="e7710-104">Properties</span></span>  
  
|<span data-ttu-id="e7710-105">属性</span><span class="sxs-lookup"><span data-stu-id="e7710-105">Property</span></span>|<span data-ttu-id="e7710-106">描述</span><span class="sxs-lookup"><span data-stu-id="e7710-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="e7710-107">获取或设置包含应用程序的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="e7710-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="e7710-108">获取或设置应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="e7710-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="e7710-109">获取或设置特定于应用程序的、 从中对文件进行卷影复制使用的区域名称。</span><span class="sxs-lookup"><span data-stu-id="e7710-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="e7710-110">获取或设置应用程序的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e7710-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="e7710-111">获取或设置在其中存储和访问动态生成的文件的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="e7710-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="e7710-112">获取或设置与此域关联的许可证文件的路径。</span><span class="sxs-lookup"><span data-stu-id="e7710-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="e7710-113">获取或设置的结合的目录列表<xref:System.AppDomainSetup.ApplicationBase%2A>目录探测专用程序集。</span><span class="sxs-lookup"><span data-stu-id="e7710-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="e7710-114">获取或设置一个字符串值，包括或排除<xref:System.AppDomainSetup.ApplicationBase%2A>应用程序的搜索路径中。</span><span class="sxs-lookup"><span data-stu-id="e7710-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="e7710-115">获取或设置包含要进行影像复制程序集的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="e7710-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="e7710-116">获取或设置指示是否卷影复制打开还是关闭的字符串。</span><span class="sxs-lookup"><span data-stu-id="e7710-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="e7710-117">有效值为"true"或"false"。</span><span class="sxs-lookup"><span data-stu-id="e7710-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7710-118">备注</span><span class="sxs-lookup"><span data-stu-id="e7710-118">Remarks</span></span>  
 <span data-ttu-id="e7710-119">`IAppDomainSetup`接口对应于托管<xref:System.IAppDomainSetup>接口，该接口<xref:System.AppDomainSetup>类型实现。</span><span class="sxs-lookup"><span data-stu-id="e7710-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="e7710-120">请参阅<xref:System.IAppDomainSetup?displayProperty=nameWithType>有关其属性的详细说明。</span><span class="sxs-lookup"><span data-stu-id="e7710-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="e7710-121">`IAppDomainSetup`表示可以添加到的程序集绑定信息<xref:System.AppDomain>之前创建的实例。</span><span class="sxs-lookup"><span data-stu-id="e7710-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="e7710-122">例如，主机可以设置<xref:System.AppDomainSetup.ApplicationBase%2A>属性建立公共语言运行时 (CLR) 来探测程序根目录的托管程序集。</span><span class="sxs-lookup"><span data-stu-id="e7710-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7710-123">惠?</span><span class="sxs-lookup"><span data-stu-id="e7710-123">Requirements</span></span>  
 <span data-ttu-id="e7710-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7710-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7710-125">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7710-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7710-126">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e7710-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7710-127">**.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7710-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7710-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7710-128">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainSetup>  
 <xref:System.IAppDomainSetup>  
 [<span data-ttu-id="e7710-129">承载接口</span><span class="sxs-lookup"><span data-stu-id="e7710-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
