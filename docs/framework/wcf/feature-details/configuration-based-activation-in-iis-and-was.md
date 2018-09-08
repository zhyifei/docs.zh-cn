---
title: IIS 和 WAS 中的基于配置的激活
ms.date: 03/30/2017
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
ms.openlocfilehash: d15202a7d34f3246cd7679687b6a510252fe3541
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210203"
---
# <a name="configuration-based-activation-in-iis-and-was"></a><span data-ttu-id="c506f-102">IIS 和 WAS 中的基于配置的激活</span><span class="sxs-lookup"><span data-stu-id="c506f-102">Configuration-Based Activation in IIS and WAS</span></span>
<span data-ttu-id="c506f-103">通常当托管在 Internet 信息服务 (IIS) 或 Windows 进程激活服务 (WAS) 下的 Windows Communication Foundation (WCF) 服务，必须提供.svc 文件。</span><span class="sxs-lookup"><span data-stu-id="c506f-103">Normally when hosting a Windows Communication Foundation (WCF) service under Internet Information Services (IIS) or Windows Process Activation Service (WAS), you must provide a .svc file.</span></span> <span data-ttu-id="c506f-104">.svc 文件包含该服务的名称以及可选的自定义服务主机工厂。</span><span class="sxs-lookup"><span data-stu-id="c506f-104">The .svc file contains the name of the service and an optional custom service host factory.</span></span> <span data-ttu-id="c506f-105">此附加文件将增加可管理性开销。</span><span class="sxs-lookup"><span data-stu-id="c506f-105">This additional file adds manageability overhead.</span></span> <span data-ttu-id="c506f-106">基于配置的激活功能不要求具有 .svc 文件，因此不会有相关开销。</span><span class="sxs-lookup"><span data-stu-id="c506f-106">The configuration-based activation feature removes the requirement to have a .svc file and therefore the associated overhead.</span></span>  
  
## <a name="configuration-based-activation"></a><span data-ttu-id="c506f-107">基于配置的激活</span><span class="sxs-lookup"><span data-stu-id="c506f-107">Configuration-Based Activation</span></span>  
 <span data-ttu-id="c506f-108">基于配置的激活接受通常放置在 .svc 文件中的元数据并将其放置在 Web.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="c506f-108">Configuration-based activation takes the metadata that used to be placed in the .svc file and places it in the Web.config file.</span></span> <span data-ttu-id="c506f-109">在 <`serviceHostingEnvironment`> 元素没有 <`serviceActivations`> 元素。</span><span class="sxs-lookup"><span data-stu-id="c506f-109">Within the<`serviceHostingEnvironment`> element there is a <`serviceActivations`> element.</span></span> <span data-ttu-id="c506f-110">在 <`serviceActivations`> 元素有一个或多个 <`add`> 元素、 一个用于每个托管服务。</span><span class="sxs-lookup"><span data-stu-id="c506f-110">Within the <`serviceActivations`> element are one or more <`add`> elements, one for each hosted service.</span></span> <span data-ttu-id="c506f-111"><`add`> 元素包含使你能够设置的服务以及服务类型或服务主机工厂的相对地址的属性。</span><span class="sxs-lookup"><span data-stu-id="c506f-111">The <`add`> element contains attributes that let you set the relative address for the service and the service type or a service host factory.</span></span> <span data-ttu-id="c506f-112">下面的配置示例代码演示如何使用此节。</span><span class="sxs-lookup"><span data-stu-id="c506f-112">The following configuration example code shows how this section is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c506f-113">每个 <`add`> 元素中必须指定服务特性或工厂特性。</span><span class="sxs-lookup"><span data-stu-id="c506f-113">Each <`add`> element must specify a service or a factory attribute.</span></span> <span data-ttu-id="c506f-114">允许同时指定服务特性和工厂特性。</span><span class="sxs-lookup"><span data-stu-id="c506f-114">Specifying both service and factory attributes is allowed.</span></span>  
  
```xml  
<serviceHostingEnvironment>  
  <serviceActivations>  
    <add relativeAddress="MyServiceAddress" service="Service" factory="MyServiceHostFactory"/>  
  </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
 <span data-ttu-id="c506f-115">在 Web.config 文件中使用此节，您可以将服务源代码放置在应用程序的 App_Code 目录中，或者将已编译的程序集放置在应用程序的 Bin 目录中。</span><span class="sxs-lookup"><span data-stu-id="c506f-115">With this in the Web.config file, you can place the service source code in the App_Code directory of the application or a complied assembly in the Bin directory of the application.</span></span>  
  
> [!NOTE]
>  -   <span data-ttu-id="c506f-116">使用基于配置的激活时，不支持 .svc 文件中的内联代码。</span><span class="sxs-lookup"><span data-stu-id="c506f-116">When using configuration-based activation, inline code in .svc files is not supported.</span></span>  
> -   <span data-ttu-id="c506f-117">`relativeAddress`属性必须设置为相对地址如"\<子目录 > / service.svc"或"~ /\<子 /service.svc"。</span><span class="sxs-lookup"><span data-stu-id="c506f-117">The `relativeAddress` attribute must be set to a relative address such as "\<sub-directory>/service.svc" or "~/\<sub-directory/service.svc".</span></span>  
> -   <span data-ttu-id="c506f-118">如果注册的相对地址不具有与 WCF 关联的已知扩展，则会引发配置异常。</span><span class="sxs-lookup"><span data-stu-id="c506f-118">A configuration exception is thrown if you register a relative address that does not have a known extension associated with WCF.</span></span>  
> -   <span data-ttu-id="c506f-119">指定的相对地址相对于虚拟应用程序的根目录。</span><span class="sxs-lookup"><span data-stu-id="c506f-119">The relative address specified is relative to the root of the virtual application.</span></span>  
> -   <span data-ttu-id="c506f-120">由于配置具有分层模型，因此虚拟应用程序继承计算机和站点级别的已注册相对地址。</span><span class="sxs-lookup"><span data-stu-id="c506f-120">Due to the hierarchical model of configuration, the registered relative addresses at machine and site level are inherited by virtual applications.</span></span>  
> -   <span data-ttu-id="c506f-121">配置文件中的注册优先于 .svc、.xamlx、.xoml 或其他文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="c506f-121">Registrations in a configuration file take precedence over settings in a .svc, .xamlx, .xoml, or other file.</span></span>  
> -   <span data-ttu-id="c506f-122">发送到 IIS/WAS 的 URI 中的所有“\”（反斜杠）都会自动转换为“/”（正斜杠）。</span><span class="sxs-lookup"><span data-stu-id="c506f-122">Any ‘\’ (backslashes) in a URI sent to IIS/WAS are automatically converted to a ‘/’ (forward slash).</span></span> <span data-ttu-id="c506f-123">如果添加的相对地址中含有“\”并且您向 IIS 发送的 URI 使用该相对地址，则反斜杠会转换为正斜杠，并且 IIS 无法将其与相对地址进行匹配。</span><span class="sxs-lookup"><span data-stu-id="c506f-123">If a relative address is added that contains a ‘\’ and you send IIS a URI that uses the relative address, the backslash is converted to a forward slash and IIS cannot match it to the relative address.</span></span> <span data-ttu-id="c506f-124">IIS 会发出跟踪信息，指示未找到任何匹配项。</span><span class="sxs-lookup"><span data-stu-id="c506f-124">IIS sends out trace information that indicates that there are no matches found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c506f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="c506f-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>  
 [<span data-ttu-id="c506f-126">托管服务</span><span class="sxs-lookup"><span data-stu-id="c506f-126">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="c506f-127">承载工作流服务概述</span><span class="sxs-lookup"><span data-stu-id="c506f-127">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 [<span data-ttu-id="c506f-128">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="c506f-128">\<serviceHostingEnvironment></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)  
 [<span data-ttu-id="c506f-129">Windows Server App Fabric 承载功能</span><span class="sxs-lookup"><span data-stu-id="c506f-129">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
