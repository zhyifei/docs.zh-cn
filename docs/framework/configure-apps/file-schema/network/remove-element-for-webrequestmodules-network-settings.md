---
title: webRequestModules 的 <remove> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: f8209ea89ac8cd214389feddee8c475e10bc939a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697821"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="89b68-102">用于 webRequestModules 的 0remove > 元素（网络设置） @no__t</span><span class="sxs-lookup"><span data-stu-id="89b68-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="89b68-103">从应用程序中移除自定义 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="89b68-103">Removes a custom Web request module from the application.</span></span>  
  
[<span data-ttu-id="89b68-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="89b68-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="89b68-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="89b68-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="89b68-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<webRequestModules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="89b68-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="89b68-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="89b68-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89b68-108">语法</span><span class="sxs-lookup"><span data-stu-id="89b68-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89b68-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="89b68-109">Attributes and Elements</span></span>  
 <span data-ttu-id="89b68-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="89b68-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89b68-111">特性</span><span class="sxs-lookup"><span data-stu-id="89b68-111">Attributes</span></span>  
  
|<span data-ttu-id="89b68-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="89b68-112">**Attribute**</span></span>|<span data-ttu-id="89b68-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="89b68-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="89b68-114">此 Web 请求模块处理的请求的 URI 前缀。</span><span class="sxs-lookup"><span data-stu-id="89b68-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89b68-115">子元素</span><span class="sxs-lookup"><span data-stu-id="89b68-115">Child Elements</span></span>  
 <span data-ttu-id="89b68-116">无。</span><span class="sxs-lookup"><span data-stu-id="89b68-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89b68-117">父元素</span><span class="sxs-lookup"><span data-stu-id="89b68-117">Parent Elements</span></span>  
  
|<span data-ttu-id="89b68-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="89b68-118">**Element**</span></span>|<span data-ttu-id="89b68-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="89b68-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="89b68-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="89b68-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="89b68-121">指定用于从网络主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="89b68-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89b68-122">备注</span><span class="sxs-lookup"><span data-stu-id="89b68-122">Remarks</span></span>  
 <span data-ttu-id="89b68-123">@No__t-0 元素删除指定 URI 前缀的已注册 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="89b68-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="89b68-124">@No__t-0 属性的值应为有效 URI 的前导字符，例如 "`http`" 或 "`http://www.contoso.com`"。</span><span class="sxs-lookup"><span data-stu-id="89b68-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="89b68-125">配置文件</span><span class="sxs-lookup"><span data-stu-id="89b68-125">Configuration Files</span></span>  
 <span data-ttu-id="89b68-126">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="89b68-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89b68-127">示例</span><span class="sxs-lookup"><span data-stu-id="89b68-127">Example</span></span>  

<span data-ttu-id="89b68-128">下面的示例将删除 HTTP 的现有 Web 请求模块，然后将 HTTP 请求的新的自定义 Web 请求模块注册到 `www.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="89b68-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="89b68-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="89b68-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="89b68-130">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="89b68-130">Network Settings Schema</span></span>](index.md)
