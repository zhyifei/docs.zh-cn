---
title: "&lt;添加&gt;webRequestModules （网络设置） 的元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 9b7d2c0f52ea42fcb98be149ab005cd67c2db46a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="2b077-102">&lt;添加&gt;webRequestModules （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="2b077-102">&lt;add&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="2b077-103">将自定义的 Web 请求模块添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="2b077-103">Adds a custom Web request module to the application.</span></span>  
  
 <span data-ttu-id="2b077-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2b077-104">\<configuration></span></span>  
<span data-ttu-id="2b077-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="2b077-105">\<system.net></span></span>  
<span data-ttu-id="2b077-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="2b077-106">\<webRequestModules></span></span>  
<span data-ttu-id="2b077-107">\<add></span><span class="sxs-lookup"><span data-stu-id="2b077-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b077-108">语法</span><span class="sxs-lookup"><span data-stu-id="2b077-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b077-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2b077-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2b077-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2b077-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b077-111">特性</span><span class="sxs-lookup"><span data-stu-id="2b077-111">Attributes</span></span>  
  
|<span data-ttu-id="2b077-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="2b077-112">**Attribute**</span></span>|<span data-ttu-id="2b077-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="2b077-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="2b077-114">此 Web 请求模块处理的请求 URI 前缀。</span><span class="sxs-lookup"><span data-stu-id="2b077-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="2b077-115">完全限定的类型名称 (由<xref:System.Type.FullName%2A>属性) 和程序集名称 (由<xref:System.Reflection.Assembly.FullName%2A>属性)，用逗号、 实现此 Web 请求模块分隔。</span><span class="sxs-lookup"><span data-stu-id="2b077-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b077-116">子元素</span><span class="sxs-lookup"><span data-stu-id="2b077-116">Child Elements</span></span>  
 <span data-ttu-id="2b077-117">无。</span><span class="sxs-lookup"><span data-stu-id="2b077-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b077-118">父元素</span><span class="sxs-lookup"><span data-stu-id="2b077-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2b077-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="2b077-119">**Element**</span></span>|<span data-ttu-id="2b077-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="2b077-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2b077-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="2b077-121">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="2b077-122">指定要用于从网络主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="2b077-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b077-123">备注</span><span class="sxs-lookup"><span data-stu-id="2b077-123">Remarks</span></span>  
 <span data-ttu-id="2b077-124">`prefix`属性定义了使用指定的 Web 请求模块的 URI 前缀。</span><span class="sxs-lookup"><span data-stu-id="2b077-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="2b077-125">Web 请求模块通常注册用于处理特定的协议，如 HTTP 或 FTP，但可以注册用于处理请求的特定服务器或服务器上的路径。</span><span class="sxs-lookup"><span data-stu-id="2b077-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="2b077-126">当 URI 匹配的前缀传递给创建 Web 请求模块<xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="2b077-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="2b077-127">值`prefix`属性应为有效的 URI-例如，"http"或"http://www.contoso.com"的开始字符。</span><span class="sxs-lookup"><span data-stu-id="2b077-127">The value for the `prefix` attribute should be the leading characters of a valid URI --for example, "http", or "http://www.contoso.com".</span></span>  
  
 <span data-ttu-id="2b077-128">值`type`属性应为有效类型名称和相应的程序集名称，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="2b077-128">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma .</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2b077-129">配置文件</span><span class="sxs-lookup"><span data-stu-id="2b077-129">Configuration Files</span></span>  
 <span data-ttu-id="2b077-130">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="2b077-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b077-131">示例</span><span class="sxs-lookup"><span data-stu-id="2b077-131">Example</span></span>  
 <span data-ttu-id="2b077-132">下面的示例对 HTTP 注册自定义的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="2b077-132">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="2b077-133">版本和 PublicKeyToken 提供值应替换为指定的模块的正确值。</span><span class="sxs-lookup"><span data-stu-id="2b077-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2b077-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b077-134">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="2b077-135">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="2b077-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
