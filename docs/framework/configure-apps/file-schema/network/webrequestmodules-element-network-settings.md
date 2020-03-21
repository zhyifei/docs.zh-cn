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
ms.openlocfilehash: 7f2805283f89e6165d336b3e593d34054e02115d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154538"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="d979b-102">\<webRequestModules> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="d979b-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="d979b-103">指定用于从网络主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="d979b-103">Specifies modules to use to request information from network hosts.</span></span>  
  
[<span data-ttu-id="d979b-104">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="d979b-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d979b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d979b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="d979b-106">&nbsp;&nbsp;&nbsp;&nbsp;\<web 请求模块></span><span class="sxs-lookup"><span data-stu-id="d979b-106">&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d979b-107">语法</span><span class="sxs-lookup"><span data-stu-id="d979b-107">Syntax</span></span>  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d979b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d979b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d979b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d979b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d979b-110">属性</span><span class="sxs-lookup"><span data-stu-id="d979b-110">Attributes</span></span>  
 <span data-ttu-id="d979b-111">无。</span><span class="sxs-lookup"><span data-stu-id="d979b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d979b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d979b-112">Child Elements</span></span>  
  
|<span data-ttu-id="d979b-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="d979b-113">**Element**</span></span>|<span data-ttu-id="d979b-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="d979b-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d979b-115">添加</span><span class="sxs-lookup"><span data-stu-id="d979b-115">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="d979b-116">向应用程序添加自定义 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="d979b-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="d979b-117">清楚</span><span class="sxs-lookup"><span data-stu-id="d979b-117">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="d979b-118">从应用程序中删除所有已注册的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="d979b-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="d979b-119">删除</span><span class="sxs-lookup"><span data-stu-id="d979b-119">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="d979b-120">从应用程序中删除自定义 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="d979b-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d979b-121">父元素</span><span class="sxs-lookup"><span data-stu-id="d979b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d979b-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="d979b-122">**Element**</span></span>|<span data-ttu-id="d979b-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="d979b-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d979b-124">system.net</span><span class="sxs-lookup"><span data-stu-id="d979b-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="d979b-125">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="d979b-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d979b-126">备注</span><span class="sxs-lookup"><span data-stu-id="d979b-126">Remarks</span></span>  
 <span data-ttu-id="d979b-127">此 `webRequestModules` 元素注册 <xref:System.Net.WebRequest> 类的子代，以处理向网络主机发出的信息请求。</span><span class="sxs-lookup"><span data-stu-id="d979b-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="d979b-128">Web 请求模块必须实现<xref:System.Net.IWebRequestCreate>接口。</span><span class="sxs-lookup"><span data-stu-id="d979b-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="d979b-129">.NET 框架包括以`http://`和`https://`开头的 URI 的 Web`file://`请求模块。</span><span class="sxs-lookup"><span data-stu-id="d979b-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="d979b-130">只能通过在配置文件中注册自定义模块来覆盖默认模块。</span><span class="sxs-lookup"><span data-stu-id="d979b-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d979b-131">配置文件</span><span class="sxs-lookup"><span data-stu-id="d979b-131">Configuration Files</span></span>  
 <span data-ttu-id="d979b-132">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="d979b-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d979b-133">示例</span><span class="sxs-lookup"><span data-stu-id="d979b-133">Example</span></span>  
 <span data-ttu-id="d979b-134">以下示例注册默认 HTTP 模块。</span><span class="sxs-lookup"><span data-stu-id="d979b-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="d979b-135">应将版本和 PublicKeyToken 的值替换为指定模块的正确值。</span><span class="sxs-lookup"><span data-stu-id="d979b-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d979b-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d979b-136">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="d979b-137">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="d979b-137">Network Settings Schema</span></span>](index.md)
