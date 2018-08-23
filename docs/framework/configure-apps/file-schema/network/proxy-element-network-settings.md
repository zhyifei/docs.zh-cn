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
ms.openlocfilehash: 5fba4bfa14642092dbb7c0153bcd92160a62b12b
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754637"
---
# <a name="ltproxygt-element-network-settings"></a><span data-ttu-id="4da2a-102">&lt;代理&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="4da2a-102">&lt;proxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="4da2a-103">定义代理服务器。</span><span class="sxs-lookup"><span data-stu-id="4da2a-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="4da2a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4da2a-104">\<configuration></span></span>  
<span data-ttu-id="4da2a-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="4da2a-105">\<system.net></span></span>  
<span data-ttu-id="4da2a-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="4da2a-106">\<defaultProxy></span></span>  
<span data-ttu-id="4da2a-107">\<代理 ></span><span class="sxs-lookup"><span data-stu-id="4da2a-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4da2a-108">语法</span><span class="sxs-lookup"><span data-stu-id="4da2a-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4da2a-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4da2a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4da2a-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4da2a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4da2a-111">特性</span><span class="sxs-lookup"><span data-stu-id="4da2a-111">Attributes</span></span>  
  
|<span data-ttu-id="4da2a-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="4da2a-112">**Attribute**</span></span>|<span data-ttu-id="4da2a-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="4da2a-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="4da2a-114">指定是否自动检测代理。</span><span class="sxs-lookup"><span data-stu-id="4da2a-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="4da2a-115">默认值为 `unspecified`。</span><span class="sxs-lookup"><span data-stu-id="4da2a-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="4da2a-116">指定对于本地资源是否跳过代理。</span><span class="sxs-lookup"><span data-stu-id="4da2a-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="4da2a-117">本地资源包括本地服务器 (`http://localhost`， `http://loopback`，或`http://127.0.0.1`) 和不带句点的 URI (`http://webserver`)。</span><span class="sxs-lookup"><span data-stu-id="4da2a-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="4da2a-118">默认值为 `unspecified`。</span><span class="sxs-lookup"><span data-stu-id="4da2a-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="4da2a-119">指定代理要使用的 URI。</span><span class="sxs-lookup"><span data-stu-id="4da2a-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="4da2a-120">指定的配置脚本的位置。</span><span class="sxs-lookup"><span data-stu-id="4da2a-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="4da2a-121">不要使用`bypassonlocal`具有此特性的属性。</span><span class="sxs-lookup"><span data-stu-id="4da2a-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="4da2a-122">指定是否使用 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="4da2a-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="4da2a-123">如果设置为`true`，后续属性将替代 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="4da2a-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="4da2a-124">默认值为 `unspecified`。</span><span class="sxs-lookup"><span data-stu-id="4da2a-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4da2a-125">子元素</span><span class="sxs-lookup"><span data-stu-id="4da2a-125">Child Elements</span></span>  
 <span data-ttu-id="4da2a-126">无。</span><span class="sxs-lookup"><span data-stu-id="4da2a-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4da2a-127">父元素</span><span class="sxs-lookup"><span data-stu-id="4da2a-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4da2a-128">**元素**</span><span class="sxs-lookup"><span data-stu-id="4da2a-128">**Element**</span></span>|<span data-ttu-id="4da2a-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="4da2a-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4da2a-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="4da2a-130">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="4da2a-131">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="4da2a-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="4da2a-132">文本值</span><span class="sxs-lookup"><span data-stu-id="4da2a-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4da2a-133">备注</span><span class="sxs-lookup"><span data-stu-id="4da2a-133">Remarks</span></span>  
 <span data-ttu-id="4da2a-134">`proxy`元素定义为应用程序代理服务器。</span><span class="sxs-lookup"><span data-stu-id="4da2a-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="4da2a-135">如果从配置文件缺少此元素，然后.NET Framework 将使用的代理设置在 Internet Explorer 中。</span><span class="sxs-lookup"><span data-stu-id="4da2a-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="4da2a-136">值为`proxyaddress`属性应为格式正确的统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="4da2a-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="4da2a-137">`scriptLocation`特性引用了自动检测代理配置脚本。</span><span class="sxs-lookup"><span data-stu-id="4da2a-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="4da2a-138"><xref:System.Net.WebProxy>类将尝试查找配置脚本 (通常命名 Wpad.dat) 时**使用自动配置脚本**Internet 资源管理器中选择选项。</span><span class="sxs-lookup"><span data-stu-id="4da2a-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="4da2a-139">如果`bypassonlocal`设置为任何值，`scriptLocation`将被忽略。</span><span class="sxs-lookup"><span data-stu-id="4da2a-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="4da2a-140">使用`usesystemdefault`要迁移到版本 2.0 的.NET Framework 版本 1.1 应用程序的属性。</span><span class="sxs-lookup"><span data-stu-id="4da2a-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="4da2a-141">如果引发异常`proxyaddress`属性指定了无效的默认代理。</span><span class="sxs-lookup"><span data-stu-id="4da2a-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="4da2a-142">异常的 <xref:System.Exception.InnerException%2A> 属性应具有错误根本原因的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4da2a-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4da2a-143">配置文件</span><span class="sxs-lookup"><span data-stu-id="4da2a-143">Configuration Files</span></span>  
 <span data-ttu-id="4da2a-144">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="4da2a-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da2a-145">示例</span><span class="sxs-lookup"><span data-stu-id="4da2a-145">Example</span></span>  
 <span data-ttu-id="4da2a-146">以下示例使用从 Internet 资源管理器代理的默认值，指定代理地址，并跳过本地访问的代理。</span><span class="sxs-lookup"><span data-stu-id="4da2a-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4da2a-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="4da2a-147">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="4da2a-148">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="4da2a-148">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
