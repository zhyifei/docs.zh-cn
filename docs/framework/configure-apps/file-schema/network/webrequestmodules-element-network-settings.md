---
title: '&lt;webRequestModules&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: 4e2a37f6829341b33475f91796e8671d867ac151
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699787"
---
# <a name="ltwebrequestmodulesgt-element-network-settings"></a><span data-ttu-id="9e81f-102">&lt;webRequestModules&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="9e81f-102">&lt;webRequestModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="9e81f-103">指定模块用于从网络主机请求信息。</span><span class="sxs-lookup"><span data-stu-id="9e81f-103">Specifies modules to use to request information from network hosts.</span></span>  
  
 <span data-ttu-id="9e81f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9e81f-104">\<configuration></span></span>  
<span data-ttu-id="9e81f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="9e81f-105">\<system.net></span></span>  
<span data-ttu-id="9e81f-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="9e81f-106">\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e81f-107">语法</span><span class="sxs-lookup"><span data-stu-id="9e81f-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e81f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9e81f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9e81f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9e81f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e81f-110">特性</span><span class="sxs-lookup"><span data-stu-id="9e81f-110">Attributes</span></span>  
 <span data-ttu-id="9e81f-111">无。</span><span class="sxs-lookup"><span data-stu-id="9e81f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9e81f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9e81f-112">Child Elements</span></span>  
  
|<span data-ttu-id="9e81f-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="9e81f-113">**Element**</span></span>|<span data-ttu-id="9e81f-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e81f-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9e81f-115">add</span><span class="sxs-lookup"><span data-stu-id="9e81f-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="9e81f-116">将自定义的 Web 请求模块添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e81f-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="9e81f-117">clear</span><span class="sxs-lookup"><span data-stu-id="9e81f-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="9e81f-118">从应用程序中删除所有已注册的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="9e81f-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="9e81f-119">remove</span><span class="sxs-lookup"><span data-stu-id="9e81f-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="9e81f-120">从应用程序中删除自定义的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="9e81f-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9e81f-121">父元素</span><span class="sxs-lookup"><span data-stu-id="9e81f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9e81f-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="9e81f-122">**Element**</span></span>|<span data-ttu-id="9e81f-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e81f-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9e81f-124">system.net</span><span class="sxs-lookup"><span data-stu-id="9e81f-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="9e81f-125">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="9e81f-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e81f-126">备注</span><span class="sxs-lookup"><span data-stu-id="9e81f-126">Remarks</span></span>  
 <span data-ttu-id="9e81f-127">此 `webRequestModules` 元素注册 <xref:System.Net.WebRequest> 类的子代，以处理向网络主机发出的信息请求。</span><span class="sxs-lookup"><span data-stu-id="9e81f-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="9e81f-128">Web 请求模块必须实现<xref:System.Net.IWebRequestCreate>接口。</span><span class="sxs-lookup"><span data-stu-id="9e81f-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="9e81f-129">.NET Framework 包括以开头的 Uri Web 请求模块`http://`， `https://`，和`file://`。</span><span class="sxs-lookup"><span data-stu-id="9e81f-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="9e81f-130">仅在配置文件中注册自定义模块可以覆盖默认模块。</span><span class="sxs-lookup"><span data-stu-id="9e81f-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9e81f-131">配置文件</span><span class="sxs-lookup"><span data-stu-id="9e81f-131">Configuration Files</span></span>  
 <span data-ttu-id="9e81f-132">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="9e81f-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e81f-133">示例</span><span class="sxs-lookup"><span data-stu-id="9e81f-133">Example</span></span>  
 <span data-ttu-id="9e81f-134">下面的示例注册默认的 HTTP 模块。</span><span class="sxs-lookup"><span data-stu-id="9e81f-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="9e81f-135">应使用正确的值指定模块的版本和 PublicKeyToken 替换值。</span><span class="sxs-lookup"><span data-stu-id="9e81f-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9e81f-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e81f-136">See also</span></span>
- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="9e81f-137">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="9e81f-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
