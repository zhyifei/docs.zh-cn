---
title: "&lt;serviceActivations&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 956134f0db25055fb9a2f9317a770989cfdab67f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltserviceactivationsgt"></a><span data-ttu-id="a1fb6-102">&lt;serviceActivations&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="a1fb6-102">&lt;add&gt; of &lt;serviceActivations&gt;</span></span>
<span data-ttu-id="a1fb6-103">一个配置元素，用于定义虚拟服务激活设置（映射到 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 服务类型）的设置。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-103">A configuration element that allows you to define virtual service activation settings that map to your [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service types.</span></span> <span data-ttu-id="a1fb6-104">使用此配置元素可以在不使用 .svc 文件的情况下激活承载在 WAS/IIS 中的服务。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="a1fb6-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a1fb6-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a1fb6-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="a1fb6-106">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1fb6-107">语法</span><span class="sxs-lookup"><span data-stu-id="a1fb6-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1fb6-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a1fb6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a1fb6-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1fb6-110">特性</span><span class="sxs-lookup"><span data-stu-id="a1fb6-110">Attributes</span></span>  
  
|<span data-ttu-id="a1fb6-111">特性</span><span class="sxs-lookup"><span data-stu-id="a1fb6-111">Attribute</span></span>|<span data-ttu-id="a1fb6-112">描述</span><span class="sxs-lookup"><span data-stu-id="a1fb6-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1fb6-113">factory</span><span class="sxs-lookup"><span data-stu-id="a1fb6-113">factory</span></span>|<span data-ttu-id="a1fb6-114">一个字符串，指定生成服务激活元素的工厂的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-114">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|  
|<span data-ttu-id="a1fb6-115">service</span><span class="sxs-lookup"><span data-stu-id="a1fb6-115">service</span></span>|<span data-ttu-id="a1fb6-116">实现服务的 ServiceType（完全限定的 Typename 或短的 Typename（将它置于 App_Code 文件夹中时））。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-116">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|  
|<span data-ttu-id="a1fb6-117">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="a1fb6-117">relativeAddress</span></span>|<span data-ttu-id="a1fb6-118">当前 IIS 应用程序内的相对地址，例如“Service.svc”。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-118">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="a1fb6-119">在 WCF4.0 中，此相对地址必须包含其中一个已知文件扩展名（.svc、.xamlx、...）之一。relativeUrl 不存在于任何物理文件中</span><span class="sxs-lookup"><span data-stu-id="a1fb6-119">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1fb6-120">子元素</span><span class="sxs-lookup"><span data-stu-id="a1fb6-120">Child Elements</span></span>  
 <span data-ttu-id="a1fb6-121">无。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1fb6-122">父元素</span><span class="sxs-lookup"><span data-stu-id="a1fb6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a1fb6-123">元素</span><span class="sxs-lookup"><span data-stu-id="a1fb6-123">Element</span></span>|<span data-ttu-id="a1fb6-124">描述</span><span class="sxs-lookup"><span data-stu-id="a1fb6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1fb6-125">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="a1fb6-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="a1fb6-126">一个描述激活设置的配置节。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-126">A configuration section that describes activation settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1fb6-127">备注</span><span class="sxs-lookup"><span data-stu-id="a1fb6-127">Remarks</span></span>  
 <span data-ttu-id="a1fb6-128">下面的示例演示如何在 web.config 文件中配置激活设置。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-128">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a1fb6-129">使用此配置，您可以在不使用 .svc 文件的情况下激活 GreetingService。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-129">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="a1fb6-130">请注意，`<serviceHostingEnvironment>` 是应用程序级配置。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-130">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="a1fb6-131">必须将包含此配置的 `web.config` 放置到虚拟应用程序的根目录下。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-131">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="a1fb6-132">此外，`serviceHostingEnvironment` 是一个可继承的 machinetoApplication 节。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-132">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="a1fb6-133">如果在计算机的根目录中注册了一个服务，应用程序中的每个服务都将继承此服务。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-133">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="a1fb6-134">基于配置的激活支持通过 http 协议和非 http 协议进行激活。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-134">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="a1fb6-135">它要求在 relatativeAddress 中使用扩展名，即 .svc、.xoml 或 .xamlx。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-135">It requires extensions in the relatativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="a1fb6-136">您可以将自己的扩展名映射到已知的 buildProviders，然后就可以通过任意扩展名激活服务。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-136">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="a1fb6-137">如果发生冲突，`<serviceActivations>` 节将重写 .svc 注册。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-137">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1fb6-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1fb6-138">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceActivationElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
