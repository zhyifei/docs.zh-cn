---
title: '&lt;defaultProxy&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 48c5f5a50563cdbea5fa806e7c7524e413ba3712
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596171"
---
# <a name="ltdefaultproxygt-element-network-settings"></a><span data-ttu-id="32299-102">&lt;defaultProxy&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="32299-102">&lt;defaultProxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="32299-103">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="32299-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
 <span data-ttu-id="32299-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="32299-104">\<configuration></span></span>  
<span data-ttu-id="32299-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="32299-105">\<system.net></span></span>  
<span data-ttu-id="32299-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="32299-106">\<defaultProxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32299-107">语法</span><span class="sxs-lookup"><span data-stu-id="32299-107">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32299-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="32299-108">Attributes and Elements</span></span>  
 <span data-ttu-id="32299-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="32299-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32299-110">特性</span><span class="sxs-lookup"><span data-stu-id="32299-110">Attributes</span></span>  
  
|<span data-ttu-id="32299-111">**元素**</span><span class="sxs-lookup"><span data-stu-id="32299-111">**Element**</span></span>|<span data-ttu-id="32299-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="32299-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="32299-113">指定是否使用 Web 代理。</span><span class="sxs-lookup"><span data-stu-id="32299-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="32299-114">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="32299-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="32299-115">指定是否使用此主机的默认凭据来访问 Web 代理。</span><span class="sxs-lookup"><span data-stu-id="32299-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="32299-116">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="32299-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32299-117">子元素</span><span class="sxs-lookup"><span data-stu-id="32299-117">Child Elements</span></span>  
  
|<span data-ttu-id="32299-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="32299-118">**Element**</span></span>|<span data-ttu-id="32299-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="32299-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="32299-120">bypasslist</span><span class="sxs-lookup"><span data-stu-id="32299-120">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="32299-121">提供一组描述不使用代理的地址的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="32299-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="32299-122">module</span><span class="sxs-lookup"><span data-stu-id="32299-122">module</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)|<span data-ttu-id="32299-123">向应用程序添加新的代理模块。</span><span class="sxs-lookup"><span data-stu-id="32299-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="32299-124">proxy</span><span class="sxs-lookup"><span data-stu-id="32299-124">proxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)|<span data-ttu-id="32299-125">定义代理服务器。</span><span class="sxs-lookup"><span data-stu-id="32299-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32299-126">父元素</span><span class="sxs-lookup"><span data-stu-id="32299-126">Parent Elements</span></span>  
  
|<span data-ttu-id="32299-127">**元素**</span><span class="sxs-lookup"><span data-stu-id="32299-127">**Element**</span></span>|<span data-ttu-id="32299-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="32299-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="32299-129">system.net</span><span class="sxs-lookup"><span data-stu-id="32299-129">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="32299-130">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="32299-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32299-131">备注</span><span class="sxs-lookup"><span data-stu-id="32299-131">Remarks</span></span>  
 <span data-ttu-id="32299-132">如果 defaultProxy 元素为空，则将沿用 Internet Explorer 中的代理设置。</span><span class="sxs-lookup"><span data-stu-id="32299-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="32299-133">这种行为在 .NET Framework 1.1 版中有所不同。</span><span class="sxs-lookup"><span data-stu-id="32299-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="32299-134">如果引发异常[模块](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)元素指定非公共类型，该类型不派生自<xref:System.Net.IWebProxy>类，可能出现的默认构造函数为此对象的异常，或者出现异常时正在检索系统指定的默认代理。</span><span class="sxs-lookup"><span data-stu-id="32299-134">An exception is thrown if the [module](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the default constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="32299-135">异常的 <xref:System.Exception.InnerException%2A> 属性应具有错误根本原因的详细信息。</span><span class="sxs-lookup"><span data-stu-id="32299-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="32299-136">配置文件</span><span class="sxs-lookup"><span data-stu-id="32299-136">Configuration Files</span></span>  
 <span data-ttu-id="32299-137">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="32299-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="32299-138">示例</span><span class="sxs-lookup"><span data-stu-id="32299-138">Example</span></span>  
 <span data-ttu-id="32299-139">以下示例使用来自 Internet 资源管理器代理的默认值、 指定代理地址，并跳过本地访问和访问 contoso.com 的代理。</span><span class="sxs-lookup"><span data-stu-id="32299-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="32299-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="32299-140">See also</span></span>
- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="32299-141">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="32299-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
