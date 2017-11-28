---
title: "&lt;webRequestModules&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ac20d3da42b150734abbbd36c4ec9fc2e60b6216
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltwebrequestmodulesgt-element-network-settings"></a><span data-ttu-id="ce5de-102">&lt;webRequestModules&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="ce5de-102">&lt;webRequestModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="ce5de-103">指定要用于从网络主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="ce5de-103">Specifies modules to use to request information from network hosts.</span></span>  
  
 <span data-ttu-id="ce5de-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ce5de-104">\<configuration></span></span>  
<span data-ttu-id="ce5de-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="ce5de-105">\<system.net></span></span>  
<span data-ttu-id="ce5de-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="ce5de-106">\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce5de-107">语法</span><span class="sxs-lookup"><span data-stu-id="ce5de-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce5de-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ce5de-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ce5de-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ce5de-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce5de-110">特性</span><span class="sxs-lookup"><span data-stu-id="ce5de-110">Attributes</span></span>  
 <span data-ttu-id="ce5de-111">无。</span><span class="sxs-lookup"><span data-stu-id="ce5de-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce5de-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ce5de-112">Child Elements</span></span>  
  
|<span data-ttu-id="ce5de-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="ce5de-113">**Element**</span></span>|<span data-ttu-id="ce5de-114">**描述**</span><span class="sxs-lookup"><span data-stu-id="ce5de-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ce5de-115">add</span><span class="sxs-lookup"><span data-stu-id="ce5de-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="ce5de-116">将自定义的 Web 请求模块添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce5de-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="ce5de-117">clear</span><span class="sxs-lookup"><span data-stu-id="ce5de-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="ce5de-118">从应用程序中删除所有已注册的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="ce5de-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="ce5de-119">remove</span><span class="sxs-lookup"><span data-stu-id="ce5de-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="ce5de-120">从应用程序中删除自定义的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="ce5de-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce5de-121">父元素</span><span class="sxs-lookup"><span data-stu-id="ce5de-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ce5de-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="ce5de-122">**Element**</span></span>|<span data-ttu-id="ce5de-123">**描述**</span><span class="sxs-lookup"><span data-stu-id="ce5de-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ce5de-124">system.net</span><span class="sxs-lookup"><span data-stu-id="ce5de-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="ce5de-125">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="ce5de-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce5de-126">备注</span><span class="sxs-lookup"><span data-stu-id="ce5de-126">Remarks</span></span>  
 <span data-ttu-id="ce5de-127">此 `webRequestModules` 元素注册 <xref:System.Net.WebRequest> 类的子代，以处理向网络主机发出的信息请求。</span><span class="sxs-lookup"><span data-stu-id="ce5de-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="ce5de-128">Web 请求模块必须实现<xref:System.Net.IWebRequestCreate>接口。</span><span class="sxs-lookup"><span data-stu-id="ce5de-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="ce5de-129">.NET Framework 包括以 http://、 https:// 和 file:// 开头的 uri Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="ce5de-129">The .NET Framework includes Web request modules for URIs that begin with http://, https://, and file://.</span></span> <span data-ttu-id="ce5de-130">仅在配置文件中注册自定义模块可以覆盖默认模块。</span><span class="sxs-lookup"><span data-stu-id="ce5de-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ce5de-131">配置文件</span><span class="sxs-lookup"><span data-stu-id="ce5de-131">Configuration Files</span></span>  
 <span data-ttu-id="ce5de-132">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="ce5de-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce5de-133">示例</span><span class="sxs-lookup"><span data-stu-id="ce5de-133">Example</span></span>  
 <span data-ttu-id="ce5de-134">下面的示例注册默认 HTTP 模块。</span><span class="sxs-lookup"><span data-stu-id="ce5de-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="ce5de-135">版本和 PublicKeyToken 提供值应替换为指定的模块的正确值。</span><span class="sxs-lookup"><span data-stu-id="ce5de-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce5de-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce5de-136">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.IWebRequestCreate>  
 [<span data-ttu-id="ce5de-137">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="ce5de-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
