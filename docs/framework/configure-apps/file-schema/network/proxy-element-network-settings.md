---
title: '&lt;代理&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b5ae716994f9b8222a633699367c94480179c97b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltproxygt-element-network-settings"></a><span data-ttu-id="01fe6-102">&lt;代理&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="01fe6-102">&lt;proxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="01fe6-103">定义代理服务器。</span><span class="sxs-lookup"><span data-stu-id="01fe6-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="01fe6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="01fe6-104">\<configuration></span></span>  
<span data-ttu-id="01fe6-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="01fe6-105">\<system.net></span></span>  
<span data-ttu-id="01fe6-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="01fe6-106">\<defaultProxy></span></span>  
<span data-ttu-id="01fe6-107">\<代理 ></span><span class="sxs-lookup"><span data-stu-id="01fe6-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01fe6-108">语法</span><span class="sxs-lookup"><span data-stu-id="01fe6-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01fe6-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="01fe6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="01fe6-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="01fe6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01fe6-111">特性</span><span class="sxs-lookup"><span data-stu-id="01fe6-111">Attributes</span></span>  
  
|<span data-ttu-id="01fe6-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="01fe6-112">**Attribute**</span></span>|<span data-ttu-id="01fe6-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="01fe6-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="01fe6-114">指定是否自动检测代理。</span><span class="sxs-lookup"><span data-stu-id="01fe6-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="01fe6-115">默认值为 `unspecified`。</span><span class="sxs-lookup"><span data-stu-id="01fe6-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="01fe6-116">指定对于本地资源是否跳过代理。</span><span class="sxs-lookup"><span data-stu-id="01fe6-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="01fe6-117">本地资源包括本地服务器 (http://localhost， http://loopback，或http://127.0.0.1)和不带句点的 URI (http://webserver)。</span><span class="sxs-lookup"><span data-stu-id="01fe6-117">Local resources include the local server (http://localhost, http://loopback, or http://127.0.0.1) and a URI without a period (http://webserver).</span></span> <span data-ttu-id="01fe6-118">默认值为 `unspecified`。</span><span class="sxs-lookup"><span data-stu-id="01fe6-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="01fe6-119">指定的代理 URI 来使用。</span><span class="sxs-lookup"><span data-stu-id="01fe6-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="01fe6-120">指定的配置脚本的位置。</span><span class="sxs-lookup"><span data-stu-id="01fe6-120">Specifies the location of the configuration script.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="01fe6-121">指定是否使用 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="01fe6-121">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="01fe6-122">如果设置为`true`，后续的属性将替代 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="01fe6-122">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="01fe6-123">默认值为 `unspecified`。</span><span class="sxs-lookup"><span data-stu-id="01fe6-123">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01fe6-124">子元素</span><span class="sxs-lookup"><span data-stu-id="01fe6-124">Child Elements</span></span>  
 <span data-ttu-id="01fe6-125">无。</span><span class="sxs-lookup"><span data-stu-id="01fe6-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01fe6-126">父元素</span><span class="sxs-lookup"><span data-stu-id="01fe6-126">Parent Elements</span></span>  
  
|<span data-ttu-id="01fe6-127">**元素**</span><span class="sxs-lookup"><span data-stu-id="01fe6-127">**Element**</span></span>|<span data-ttu-id="01fe6-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="01fe6-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="01fe6-129">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="01fe6-129">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="01fe6-130">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="01fe6-130">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="01fe6-131">文本值</span><span class="sxs-lookup"><span data-stu-id="01fe6-131">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01fe6-132">备注</span><span class="sxs-lookup"><span data-stu-id="01fe6-132">Remarks</span></span>  
 <span data-ttu-id="01fe6-133">`proxy`元素定义为应用程序代理服务器。</span><span class="sxs-lookup"><span data-stu-id="01fe6-133">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="01fe6-134">如果从配置文件缺少时此元素，则.NET Framework 将代理设置使用在 Internet 资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="01fe6-134">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="01fe6-135">值`proxyaddress`属性应为格式正确的统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="01fe6-135">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="01fe6-136">`scriptLocation`特性引用了自动检测代理配置脚本。</span><span class="sxs-lookup"><span data-stu-id="01fe6-136">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="01fe6-137"><xref:System.Net.WebProxy>类将尝试查找配置脚本 (通常命名 Wpad.dat) 时**使用自动配置脚本**在 Internet Explorer 中选择选项。</span><span class="sxs-lookup"><span data-stu-id="01fe6-137">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span>  
  
 <span data-ttu-id="01fe6-138">使用`usesystemdefault`.NET Framework 1.1 版应用程序迁移到 2.0 版的属性。</span><span class="sxs-lookup"><span data-stu-id="01fe6-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="01fe6-139">如果引发异常`proxyaddress`属性指定了无效的默认代理。</span><span class="sxs-lookup"><span data-stu-id="01fe6-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="01fe6-140">异常的 <xref:System.Exception.InnerException%2A> 属性应具有错误根本原因的详细信息。</span><span class="sxs-lookup"><span data-stu-id="01fe6-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="01fe6-141">配置文件</span><span class="sxs-lookup"><span data-stu-id="01fe6-141">Configuration Files</span></span>  
 <span data-ttu-id="01fe6-142">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="01fe6-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01fe6-143">示例</span><span class="sxs-lookup"><span data-stu-id="01fe6-143">Example</span></span>  
 <span data-ttu-id="01fe6-144">下面的示例使用来自 Internet 资源管理器代理的默认值，指定代理地址，并跳过代理以进行本地访问。</span><span class="sxs-lookup"><span data-stu-id="01fe6-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01fe6-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="01fe6-145">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="01fe6-146">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="01fe6-146">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
