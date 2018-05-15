---
title: '&lt;serviceActivations&gt;'
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: c62f2bd1a34aca31ea9f9d5de17840f2967b269c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltserviceactivationsgt"></a><span data-ttu-id="af511-102">&lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="af511-102">&lt;serviceActivations&gt;</span></span>
<span data-ttu-id="af511-103">一个配置元素，您可以添加定义虚拟服务激活设置的设置映射到你的 Windows Communication Foundation (WCF) 服务类型。</span><span class="sxs-lookup"><span data-stu-id="af511-103">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="af511-104">使用此配置元素可以在不使用 .svc 文件的情况下激活承载在 WAS/IIS 中的服务。</span><span class="sxs-lookup"><span data-stu-id="af511-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="af511-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="af511-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="af511-106">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="af511-106">\<serviceHostingEnvironment></span></span>  
<span data-ttu-id="af511-107">\<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="af511-107">\<serviceActivations></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af511-108">语法</span><span class="sxs-lookup"><span data-stu-id="af511-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af511-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="af511-109">Attributes and Elements</span></span>  
 <span data-ttu-id="af511-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="af511-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af511-111">特性</span><span class="sxs-lookup"><span data-stu-id="af511-111">Attributes</span></span>  
 <span data-ttu-id="af511-112">无。</span><span class="sxs-lookup"><span data-stu-id="af511-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="af511-113">子元素</span><span class="sxs-lookup"><span data-stu-id="af511-113">Child Elements</span></span>  
  
|<span data-ttu-id="af511-114">元素</span><span class="sxs-lookup"><span data-stu-id="af511-114">Element</span></span>|<span data-ttu-id="af511-115">描述</span><span class="sxs-lookup"><span data-stu-id="af511-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af511-116">\<add></span><span class="sxs-lookup"><span data-stu-id="af511-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="af511-117">添加一个指定激活服务应用程序的配置元素。</span><span class="sxs-lookup"><span data-stu-id="af511-117">Adds a configuration element that specifies the activation of a service application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af511-118">父元素</span><span class="sxs-lookup"><span data-stu-id="af511-118">Parent Elements</span></span>  
  
|<span data-ttu-id="af511-119">元素</span><span class="sxs-lookup"><span data-stu-id="af511-119">Element</span></span>|<span data-ttu-id="af511-120">描述</span><span class="sxs-lookup"><span data-stu-id="af511-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af511-121">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="af511-121">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="af511-122">定义服务承载环境要为特定传输实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="af511-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af511-123">备注</span><span class="sxs-lookup"><span data-stu-id="af511-123">Remarks</span></span>  
 <span data-ttu-id="af511-124">下面的示例演示如何在 web.config 文件中配置激活设置。</span><span class="sxs-lookup"><span data-stu-id="af511-124">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
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
  
 <span data-ttu-id="af511-125">使用此配置，您可以在不使用 .svc 文件的情况下激活 GreetingService。</span><span class="sxs-lookup"><span data-stu-id="af511-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="af511-126">请注意，`<serviceHostingEnvironment>` 是应用程序级配置。</span><span class="sxs-lookup"><span data-stu-id="af511-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="af511-127">必须将包含此配置的 `web.config` 放置到虚拟应用程序的根目录下。</span><span class="sxs-lookup"><span data-stu-id="af511-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="af511-128">此外，`serviceHostingEnvironment` 是一个可继承的 machinetoApplication 节。</span><span class="sxs-lookup"><span data-stu-id="af511-128">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="af511-129">如果在计算机的根目录中注册了一个服务，应用程序中的每个服务都将继承此服务。</span><span class="sxs-lookup"><span data-stu-id="af511-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="af511-130">基于配置的激活支持通过 http 协议和非 http 协议进行激活。</span><span class="sxs-lookup"><span data-stu-id="af511-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="af511-131">它要求在 relatativeAddress 中使用扩展名，即 .svc、.xoml 或 .xamlx。</span><span class="sxs-lookup"><span data-stu-id="af511-131">It requires extensions in the relatativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="af511-132">您可以将自己的扩展名映射到已知的 buildProviders，然后就可以通过任意扩展名激活服务。</span><span class="sxs-lookup"><span data-stu-id="af511-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="af511-133">如果发生冲突，`<serviceActivations>` 节将重写 .svc 注册。</span><span class="sxs-lookup"><span data-stu-id="af511-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af511-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="af511-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
