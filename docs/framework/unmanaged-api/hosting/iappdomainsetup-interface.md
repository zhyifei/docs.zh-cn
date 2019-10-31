---
title: IAppDomainSetup 接口
ms.date: 03/30/2017
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
ms.openlocfilehash: 0fab64c31d4a73995c16d21767f4569f21c7df9a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126874"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="d1602-102">IAppDomainSetup 接口</span><span class="sxs-lookup"><span data-stu-id="d1602-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="d1602-103">提供属性，这些属性使宿主可以在调用[ICorRuntimeHost：： CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)方法来创建它之前配置 <xref:System.AppDomain?displayProperty=nameWithType> 类型。</span><span class="sxs-lookup"><span data-stu-id="d1602-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d1602-104">属性</span><span class="sxs-lookup"><span data-stu-id="d1602-104">Properties</span></span>  
  
|<span data-ttu-id="d1602-105">Property</span><span class="sxs-lookup"><span data-stu-id="d1602-105">Property</span></span>|<span data-ttu-id="d1602-106">描述</span><span class="sxs-lookup"><span data-stu-id="d1602-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="d1602-107">获取或设置包含该应用程序的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="d1602-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="d1602-108">获取或设置应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="d1602-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="d1602-109">获取或设置特定于应用程序的区域的名称，在该区域中对文件进行卷影复制。</span><span class="sxs-lookup"><span data-stu-id="d1602-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="d1602-110">获取或设置应用程序的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d1602-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="d1602-111">获取或设置用于存储和访问动态生成的文件的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="d1602-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="d1602-112">获取或设置与此域关联的许可证文件的路径。</span><span class="sxs-lookup"><span data-stu-id="d1602-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="d1602-113">获取或设置目录列表，该列表与要探测其专用程序集的 <xref:System.AppDomainSetup.ApplicationBase%2A> 目录组合在一起。</span><span class="sxs-lookup"><span data-stu-id="d1602-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="d1602-114">获取或设置一个字符串值，该值包含或排除从应用程序的搜索路径 <xref:System.AppDomainSetup.ApplicationBase%2A>。</span><span class="sxs-lookup"><span data-stu-id="d1602-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="d1602-115">获取或设置目录的名称，这些目录包含要进行卷影复制的程序集。</span><span class="sxs-lookup"><span data-stu-id="d1602-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="d1602-116">获取或设置一个字符串，该字符串指示阴影复制是打开还是关闭。</span><span class="sxs-lookup"><span data-stu-id="d1602-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="d1602-117">有效值为 "true" 或 "false"。</span><span class="sxs-lookup"><span data-stu-id="d1602-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1602-118">备注</span><span class="sxs-lookup"><span data-stu-id="d1602-118">Remarks</span></span>  
 <span data-ttu-id="d1602-119">`IAppDomainSetup` 接口对应于 <xref:System.AppDomainSetup> 类型实现的托管 <xref:System.IAppDomainSetup> 接口。</span><span class="sxs-lookup"><span data-stu-id="d1602-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="d1602-120">有关其属性的详细说明，请参阅 <xref:System.IAppDomainSetup?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d1602-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="d1602-121">`IAppDomainSetup` 表示可以在创建之前添加到 <xref:System.AppDomain> 实例的程序集绑定信息。</span><span class="sxs-lookup"><span data-stu-id="d1602-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="d1602-122">例如，主机可以设置 <xref:System.AppDomainSetup.ApplicationBase%2A> 属性来建立根目录，公共语言运行时（CLR）会探测托管程序集。</span><span class="sxs-lookup"><span data-stu-id="d1602-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1602-123">要求</span><span class="sxs-lookup"><span data-stu-id="d1602-123">Requirements</span></span>  
 <span data-ttu-id="d1602-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1602-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1602-125">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d1602-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1602-126">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d1602-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1602-127">**.NET Framework 版本：** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1602-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1602-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1602-128">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [<span data-ttu-id="d1602-129">承载接口</span><span class="sxs-lookup"><span data-stu-id="d1602-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
