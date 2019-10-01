---
title: webRequestModules 的 <add> 元素（网络设置）
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
ms.openlocfilehash: 0248706ed78de160ef0131a0c7595374febf1aa9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699579"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="4ba60-102">用于 webRequestModules 的 0add > 元素（网络设置） @no__t</span><span class="sxs-lookup"><span data-stu-id="4ba60-102">\<add> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="4ba60-103">向应用程序添加自定义 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="4ba60-103">Adds a custom Web request module to the application.</span></span>  
  
[<span data-ttu-id="4ba60-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="4ba60-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="4ba60-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4ba60-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="4ba60-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<webRequestModules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4ba60-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="4ba60-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="4ba60-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ba60-108">语法</span><span class="sxs-lookup"><span data-stu-id="4ba60-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ba60-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4ba60-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4ba60-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4ba60-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ba60-111">特性</span><span class="sxs-lookup"><span data-stu-id="4ba60-111">Attributes</span></span>  
  
|<span data-ttu-id="4ba60-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="4ba60-112">**Attribute**</span></span>|<span data-ttu-id="4ba60-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="4ba60-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="4ba60-114">此 Web 请求模块处理的请求的 URI 前缀。</span><span class="sxs-lookup"><span data-stu-id="4ba60-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="4ba60-115">实现此 Web 请求模块的由逗号分隔的完全限定的类型名称（由 <xref:System.Type.FullName%2A> 属性指示）和程序集名称（由 <xref:System.Reflection.Assembly.FullName%2A> 属性指示）。</span><span class="sxs-lookup"><span data-stu-id="4ba60-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ba60-116">子元素</span><span class="sxs-lookup"><span data-stu-id="4ba60-116">Child Elements</span></span>  
 <span data-ttu-id="4ba60-117">无。</span><span class="sxs-lookup"><span data-stu-id="4ba60-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ba60-118">父元素</span><span class="sxs-lookup"><span data-stu-id="4ba60-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4ba60-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="4ba60-119">**Element**</span></span>|<span data-ttu-id="4ba60-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="4ba60-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4ba60-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="4ba60-121">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="4ba60-122">指定用于从网络主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="4ba60-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ba60-123">备注</span><span class="sxs-lookup"><span data-stu-id="4ba60-123">Remarks</span></span>  
 <span data-ttu-id="4ba60-124">@No__t-0 特性定义使用指定 Web 请求模块的 URI 前缀。</span><span class="sxs-lookup"><span data-stu-id="4ba60-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="4ba60-125">通常会将 Web 请求模块注册为处理特定协议（如 HTTP 或 FTP），但可以注册它来处理对服务器上特定服务器或路径的请求。</span><span class="sxs-lookup"><span data-stu-id="4ba60-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="4ba60-126">当 URI 匹配前缀传递到 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> 方法时，将创建 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="4ba60-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="4ba60-127">@No__t-0 属性的值应为有效 URI 的前导字符。</span><span class="sxs-lookup"><span data-stu-id="4ba60-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="4ba60-128">例如，`http` 或 `http://www.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="4ba60-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="4ba60-129">@No__t-0 属性的值应为有效的类型名称和相应的程序集名称，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="4ba60-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="4ba60-130">配置文件</span><span class="sxs-lookup"><span data-stu-id="4ba60-130">Configuration Files</span></span>  
 <span data-ttu-id="4ba60-131">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="4ba60-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ba60-132">示例</span><span class="sxs-lookup"><span data-stu-id="4ba60-132">Example</span></span>  
 <span data-ttu-id="4ba60-133">下面的示例为 HTTP 注册自定义 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="4ba60-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="4ba60-134">应将版本和 PublicKeyToken 的值替换为指定模块的正确值。</span><span class="sxs-lookup"><span data-stu-id="4ba60-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4ba60-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ba60-135">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="4ba60-136">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="4ba60-136">Network Settings Schema</span></span>](index.md)
