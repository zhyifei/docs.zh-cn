---
title: <proxy> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 5f327a2bb4fe316497614f14669907d514c20654
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089194"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="c8cf6-102">\<proxy > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="c8cf6-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="c8cf6-103">定义代理服务器。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-103">Defines a proxy server.</span></span>  

<span data-ttu-id="c8cf6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8cf6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c8cf6-105">\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c8cf6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="c8cf6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c8cf6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="c8cf6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<代理**></span><span class="sxs-lookup"><span data-stu-id="c8cf6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c8cf6-108">语法</span><span class="sxs-lookup"><span data-stu-id="c8cf6-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8cf6-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c8cf6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c8cf6-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8cf6-111">特性</span><span class="sxs-lookup"><span data-stu-id="c8cf6-111">Attributes</span></span>  
  
|<span data-ttu-id="c8cf6-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="c8cf6-112">**Attribute**</span></span>|<span data-ttu-id="c8cf6-113">**描述**</span><span class="sxs-lookup"><span data-stu-id="c8cf6-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="c8cf6-114">指定是否自动检测代理。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="c8cf6-115">默认值为 `unspecified`。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="c8cf6-116">指定对于本地资源是否跳过代理。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="c8cf6-117">本地资源包括本地服务器（`http://localhost`、`http://loopback`或 `http://127.0.0.1`）和没有句点（`http://webserver`）的 URI。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="c8cf6-118">默认值为 `unspecified`。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="c8cf6-119">指定要使用的代理 URI。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="c8cf6-120">指定配置脚本的位置。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="c8cf6-121">不要将 `bypassonlocal` 特性与此特性一起使用。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="c8cf6-122">指定是否使用 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="c8cf6-123">如果设置为 `true`，则后续属性将替代 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="c8cf6-124">默认值为 `unspecified`。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8cf6-125">子元素</span><span class="sxs-lookup"><span data-stu-id="c8cf6-125">Child Elements</span></span>  
 <span data-ttu-id="c8cf6-126">无。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8cf6-127">父元素</span><span class="sxs-lookup"><span data-stu-id="c8cf6-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c8cf6-128">**元素**</span><span class="sxs-lookup"><span data-stu-id="c8cf6-128">**Element**</span></span>|<span data-ttu-id="c8cf6-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="c8cf6-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c8cf6-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="c8cf6-130">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="c8cf6-131">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="c8cf6-132">文本值</span><span class="sxs-lookup"><span data-stu-id="c8cf6-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8cf6-133">备注</span><span class="sxs-lookup"><span data-stu-id="c8cf6-133">Remarks</span></span>  
 <span data-ttu-id="c8cf6-134">`proxy` 元素为应用程序定义代理服务器。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="c8cf6-135">如果配置文件中缺少此元素，则 .NET Framework 将使用 Internet Explorer 中的代理设置。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="c8cf6-136">`proxyaddress` 属性的值应为格式正确的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="c8cf6-137">`scriptLocation` 属性是指自动检测代理配置脚本。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="c8cf6-138">如果在 Internet Explorer 中选择了 "**使用自动配置脚本**" 选项，则 <xref:System.Net.WebProxy> 类将尝试查找配置脚本（通常名为 Wpad .dat）。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="c8cf6-139">如果 `bypassonlocal` 设置为任何值，则忽略 `scriptLocation`。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="c8cf6-140">使用迁移到版本 2.0 .NET Framework 版本1.1 应用程序的 `usesystemdefault` 属性。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="c8cf6-141">如果 `proxyaddress` 特性指定了无效的默认代理，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="c8cf6-142">异常的 <xref:System.Exception.InnerException%2A> 属性应具有错误根本原因的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c8cf6-143">配置文件</span><span class="sxs-lookup"><span data-stu-id="c8cf6-143">Configuration Files</span></span>  
 <span data-ttu-id="c8cf6-144">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8cf6-145">示例</span><span class="sxs-lookup"><span data-stu-id="c8cf6-145">Example</span></span>  
 <span data-ttu-id="c8cf6-146">以下示例使用 Internet Explorer 代理中的默认值，指定代理地址，并绕过代理进行本地访问。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c8cf6-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8cf6-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="c8cf6-148">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="c8cf6-148">Network Settings Schema</span></span>](index.md)
