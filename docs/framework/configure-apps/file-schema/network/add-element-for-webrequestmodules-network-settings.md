---
title: '&lt;添加&gt;webRequestModules （网络设置） 的元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 921f5f2bfda1a19d022d3f3f4131e3653fd17ea7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="d8d69-102">&lt;添加&gt;webRequestModules （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="d8d69-102">&lt;add&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="d8d69-103">将自定义的 Web 请求模块添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="d8d69-103">Adds a custom Web request module to the application.</span></span>  
  
 <span data-ttu-id="d8d69-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d8d69-104">\<configuration></span></span>  
<span data-ttu-id="d8d69-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="d8d69-105">\<system.net></span></span>  
<span data-ttu-id="d8d69-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="d8d69-106">\<webRequestModules></span></span>  
<span data-ttu-id="d8d69-107">\<add></span><span class="sxs-lookup"><span data-stu-id="d8d69-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8d69-108">语法</span><span class="sxs-lookup"><span data-stu-id="d8d69-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8d69-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d8d69-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d8d69-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d8d69-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8d69-111">特性</span><span class="sxs-lookup"><span data-stu-id="d8d69-111">Attributes</span></span>  
  
|<span data-ttu-id="d8d69-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="d8d69-112">**Attribute**</span></span>|<span data-ttu-id="d8d69-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="d8d69-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="d8d69-114">此 Web 请求模块处理的请求 URI 前缀。</span><span class="sxs-lookup"><span data-stu-id="d8d69-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="d8d69-115">完全限定的类型名称 (由<xref:System.Type.FullName%2A>属性) 和程序集名称 (由<xref:System.Reflection.Assembly.FullName%2A>属性)，用逗号、 实现此 Web 请求模块分隔。</span><span class="sxs-lookup"><span data-stu-id="d8d69-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8d69-116">子元素</span><span class="sxs-lookup"><span data-stu-id="d8d69-116">Child Elements</span></span>  
 <span data-ttu-id="d8d69-117">无。</span><span class="sxs-lookup"><span data-stu-id="d8d69-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8d69-118">父元素</span><span class="sxs-lookup"><span data-stu-id="d8d69-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d8d69-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="d8d69-119">**Element**</span></span>|<span data-ttu-id="d8d69-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="d8d69-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d8d69-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="d8d69-121">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="d8d69-122">指定要用于从网络主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="d8d69-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8d69-123">备注</span><span class="sxs-lookup"><span data-stu-id="d8d69-123">Remarks</span></span>  
 <span data-ttu-id="d8d69-124">`prefix`属性定义了使用指定的 Web 请求模块的 URI 前缀。</span><span class="sxs-lookup"><span data-stu-id="d8d69-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="d8d69-125">Web 请求模块通常注册用于处理特定的协议，如 HTTP 或 FTP，但可以注册用于处理请求的特定服务器或服务器上的路径。</span><span class="sxs-lookup"><span data-stu-id="d8d69-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="d8d69-126">当 URI 匹配的前缀传递给创建 Web 请求模块<xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="d8d69-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="d8d69-127">值`prefix`属性应为有效的 URI-例如，"http"，前导字符或"http://www.contoso.com"。</span><span class="sxs-lookup"><span data-stu-id="d8d69-127">The value for the `prefix` attribute should be the leading characters of a valid URI --for example, "http", or "http://www.contoso.com".</span></span>  
  
 <span data-ttu-id="d8d69-128">值`type`属性应为有效类型名称和相应的程序集名称，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="d8d69-128">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma .</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d8d69-129">配置文件</span><span class="sxs-lookup"><span data-stu-id="d8d69-129">Configuration Files</span></span>  
 <span data-ttu-id="d8d69-130">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="d8d69-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8d69-131">示例</span><span class="sxs-lookup"><span data-stu-id="d8d69-131">Example</span></span>  
 <span data-ttu-id="d8d69-132">下面的示例对 HTTP 注册自定义的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="d8d69-132">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="d8d69-133">版本和 PublicKeyToken 提供值应替换为指定的模块的正确值。</span><span class="sxs-lookup"><span data-stu-id="d8d69-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8d69-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8d69-134">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="d8d69-135">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="d8d69-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
