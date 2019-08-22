---
title: <webRequestModules> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: c30a7a0bcce62c99d7c1ec0ff17389b8c2cd2f17
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663944"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="5070f-102">\<webRequestModules > 元素 (网络设置)</span><span class="sxs-lookup"><span data-stu-id="5070f-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="5070f-103">指定用于从网络主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="5070f-103">Specifies modules to use to request information from network hosts.</span></span>  
  
 <span data-ttu-id="5070f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5070f-104">\<configuration></span></span>  
<span data-ttu-id="5070f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="5070f-105">\<system.net></span></span>  
<span data-ttu-id="5070f-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="5070f-106">\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5070f-107">语法</span><span class="sxs-lookup"><span data-stu-id="5070f-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5070f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5070f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5070f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5070f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5070f-110">特性</span><span class="sxs-lookup"><span data-stu-id="5070f-110">Attributes</span></span>  
 <span data-ttu-id="5070f-111">无。</span><span class="sxs-lookup"><span data-stu-id="5070f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5070f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5070f-112">Child Elements</span></span>  
  
|<span data-ttu-id="5070f-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="5070f-113">**Element**</span></span>|<span data-ttu-id="5070f-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="5070f-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5070f-115">add</span><span class="sxs-lookup"><span data-stu-id="5070f-115">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="5070f-116">向应用程序添加自定义 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="5070f-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="5070f-117">clear</span><span class="sxs-lookup"><span data-stu-id="5070f-117">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="5070f-118">从应用程序中删除所有已注册的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="5070f-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="5070f-119">remove</span><span class="sxs-lookup"><span data-stu-id="5070f-119">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="5070f-120">从应用程序中移除自定义 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="5070f-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5070f-121">父元素</span><span class="sxs-lookup"><span data-stu-id="5070f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5070f-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="5070f-122">**Element**</span></span>|<span data-ttu-id="5070f-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="5070f-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5070f-124">system.net</span><span class="sxs-lookup"><span data-stu-id="5070f-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="5070f-125">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="5070f-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5070f-126">备注</span><span class="sxs-lookup"><span data-stu-id="5070f-126">Remarks</span></span>  
 <span data-ttu-id="5070f-127">此 `webRequestModules` 元素注册 <xref:System.Net.WebRequest> 类的子代，以处理向网络主机发出的信息请求。</span><span class="sxs-lookup"><span data-stu-id="5070f-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="5070f-128">Web 请求模块必须实现<xref:System.Net.IWebRequestCreate>接口。</span><span class="sxs-lookup"><span data-stu-id="5070f-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="5070f-129">.NET Framework 包含以`http://`、 `https://`和`file://`开头的 uri 的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="5070f-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="5070f-130">只能通过在配置文件中注册自定义模块来重写默认模块。</span><span class="sxs-lookup"><span data-stu-id="5070f-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5070f-131">配置文件</span><span class="sxs-lookup"><span data-stu-id="5070f-131">Configuration Files</span></span>  
 <span data-ttu-id="5070f-132">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="5070f-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5070f-133">示例</span><span class="sxs-lookup"><span data-stu-id="5070f-133">Example</span></span>  
 <span data-ttu-id="5070f-134">下面的示例将注册默认的 HTTP 模块。</span><span class="sxs-lookup"><span data-stu-id="5070f-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="5070f-135">应将版本和 PublicKeyToken 的值替换为指定模块的正确值。</span><span class="sxs-lookup"><span data-stu-id="5070f-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5070f-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="5070f-136">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="5070f-137">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="5070f-137">Network Settings Schema</span></span>](index.md)
