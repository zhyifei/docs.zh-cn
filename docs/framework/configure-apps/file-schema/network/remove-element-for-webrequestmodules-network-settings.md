---
title: "&lt;删除&gt;webRequestModules （网络设置） 的元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 391e5f2a7d9d8076ba9e9a3057e3d8899e2ce672
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="ltremovegt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="564bb-102">&lt;删除&gt;webRequestModules （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="564bb-102">&lt;remove&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="564bb-103">从应用程序中删除自定义的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="564bb-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="564bb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="564bb-104">\<configuration></span></span>  
<span data-ttu-id="564bb-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="564bb-105">\<system.net></span></span>  
<span data-ttu-id="564bb-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="564bb-106">\<webRequestModules></span></span>  
<span data-ttu-id="564bb-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="564bb-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="564bb-108">语法</span><span class="sxs-lookup"><span data-stu-id="564bb-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="564bb-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="564bb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="564bb-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="564bb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="564bb-111">特性</span><span class="sxs-lookup"><span data-stu-id="564bb-111">Attributes</span></span>  
  
|<span data-ttu-id="564bb-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="564bb-112">**Attribute**</span></span>|<span data-ttu-id="564bb-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="564bb-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="564bb-114">此 Web 请求模块处理的请求 URI 前缀。</span><span class="sxs-lookup"><span data-stu-id="564bb-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="564bb-115">子元素</span><span class="sxs-lookup"><span data-stu-id="564bb-115">Child Elements</span></span>  
 <span data-ttu-id="564bb-116">无。</span><span class="sxs-lookup"><span data-stu-id="564bb-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="564bb-117">父元素</span><span class="sxs-lookup"><span data-stu-id="564bb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="564bb-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="564bb-118">**Element**</span></span>|<span data-ttu-id="564bb-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="564bb-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="564bb-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="564bb-120">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="564bb-121">指定要用于从网络主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="564bb-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="564bb-122">备注</span><span class="sxs-lookup"><span data-stu-id="564bb-122">Remarks</span></span>  
 <span data-ttu-id="564bb-123">`remove`元素中移除指定的 URI 前缀已注册的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="564bb-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="564bb-124">值`prefix`属性应为有效的 URI-例如，"http"，前导字符或"http://www.contoso.com"。</span><span class="sxs-lookup"><span data-stu-id="564bb-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "http", or "http://www.contoso.com".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="564bb-125">配置文件</span><span class="sxs-lookup"><span data-stu-id="564bb-125">Configuration Files</span></span>  
 <span data-ttu-id="564bb-126">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="564bb-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="564bb-127">示例</span><span class="sxs-lookup"><span data-stu-id="564bb-127">Example</span></span>  
 <span data-ttu-id="564bb-128">下面的示例将对 HTTP 中删除该现有的 Web 请求模块，然后注册新的自定义 Web 请求模块到 www.contoso.com 的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="564bb-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to www.contoso.com.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="564bb-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="564bb-129">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="564bb-130">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="564bb-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
