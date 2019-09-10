---
title: <add> 的 <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: a0f68717f765482f53e675458fae63d1a374d6fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850327"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="4193a-102">\<添加 serviceActivations > \<的 ></span><span class="sxs-lookup"><span data-stu-id="4193a-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="4193a-103">一个配置元素，允许您定义映射到 Windows Communication Foundation （WCF）服务类型的虚拟服务激活设置。</span><span class="sxs-lookup"><span data-stu-id="4193a-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="4193a-104">使用此配置元素可以在不使用 .svc 文件的情况下激活承载在 WAS/IIS 中的服务。</span><span class="sxs-lookup"><span data-stu-id="4193a-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="4193a-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4193a-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4193a-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4193a-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4193a-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="4193a-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="4193a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceActivations >** ](serviceactivations.md)</span><span class="sxs-lookup"><span data-stu-id="4193a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceActivations>**](serviceactivations.md)</span></span>\
<span data-ttu-id="4193a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="4193a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="4193a-110">语法</span><span class="sxs-lookup"><span data-stu-id="4193a-110">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4193a-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4193a-111">Attributes and Elements</span></span>

<span data-ttu-id="4193a-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4193a-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4193a-113">特性</span><span class="sxs-lookup"><span data-stu-id="4193a-113">Attributes</span></span>

|<span data-ttu-id="4193a-114">特性</span><span class="sxs-lookup"><span data-stu-id="4193a-114">Attribute</span></span>|<span data-ttu-id="4193a-115">描述</span><span class="sxs-lookup"><span data-stu-id="4193a-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="4193a-116">factory</span><span class="sxs-lookup"><span data-stu-id="4193a-116">factory</span></span>|<span data-ttu-id="4193a-117">一个字符串，指定生成服务激活元素的工厂的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="4193a-117">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="4193a-118">服务</span><span class="sxs-lookup"><span data-stu-id="4193a-118">service</span></span>|<span data-ttu-id="4193a-119">实现服务的 ServiceType（完全限定的 Typename 或短的 Typename（将它置于 App_Code 文件夹中时））。</span><span class="sxs-lookup"><span data-stu-id="4193a-119">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="4193a-120">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="4193a-120">relativeAddress</span></span>|<span data-ttu-id="4193a-121">当前 IIS 应用程序内的相对地址，例如“Service.svc”。</span><span class="sxs-lookup"><span data-stu-id="4193a-121">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="4193a-122">在 WCF4.0 中，此相对地址必须包含其中一个已知文件扩展名（.svc、.xamlx、...）之一。relativeUrl 不存在于任何物理文件中</span><span class="sxs-lookup"><span data-stu-id="4193a-122">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="4193a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4193a-123">Child Elements</span></span>

<span data-ttu-id="4193a-124">无。</span><span class="sxs-lookup"><span data-stu-id="4193a-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4193a-125">父元素</span><span class="sxs-lookup"><span data-stu-id="4193a-125">Parent Elements</span></span>

|<span data-ttu-id="4193a-126">元素</span><span class="sxs-lookup"><span data-stu-id="4193a-126">Element</span></span>|<span data-ttu-id="4193a-127">描述</span><span class="sxs-lookup"><span data-stu-id="4193a-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4193a-128">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="4193a-128">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="4193a-129">一个描述激活设置的配置节。</span><span class="sxs-lookup"><span data-stu-id="4193a-129">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4193a-130">备注</span><span class="sxs-lookup"><span data-stu-id="4193a-130">Remarks</span></span>

<span data-ttu-id="4193a-131">下面的示例演示如何在 web.config 文件中配置激活设置。</span><span class="sxs-lookup"><span data-stu-id="4193a-131">The following example shows how to configure activation settings within your web.config file.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="4193a-132">使用此配置，您可以在不使用 .svc 文件的情况下激活 GreetingService。</span><span class="sxs-lookup"><span data-stu-id="4193a-132">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="4193a-133">请注意，`<serviceHostingEnvironment>` 是应用程序级配置。</span><span class="sxs-lookup"><span data-stu-id="4193a-133">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="4193a-134">必须将包含此配置的 `web.config` 放置到虚拟应用程序的根目录下。</span><span class="sxs-lookup"><span data-stu-id="4193a-134">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="4193a-135">此外， `serviceHostingEnvironment`是 machineToApplication 可继承部分。</span><span class="sxs-lookup"><span data-stu-id="4193a-135">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="4193a-136">如果在计算机的根目录中注册了一个服务，应用程序中的每个服务都将继承此服务。</span><span class="sxs-lookup"><span data-stu-id="4193a-136">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="4193a-137">基于配置的激活支持通过 http 协议和非 http 协议进行激活。</span><span class="sxs-lookup"><span data-stu-id="4193a-137">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="4193a-138">它需要 relativeAddress 中的扩展，即 xoml 或 .xamlx。</span><span class="sxs-lookup"><span data-stu-id="4193a-138">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="4193a-139">您可以将自己的扩展名映射到已知的 buildProviders，然后就可以通过任意扩展名激活服务。</span><span class="sxs-lookup"><span data-stu-id="4193a-139">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="4193a-140">如果发生冲突，`<serviceActivations>` 节将重写 .svc 注册。</span><span class="sxs-lookup"><span data-stu-id="4193a-140">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="4193a-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="4193a-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
