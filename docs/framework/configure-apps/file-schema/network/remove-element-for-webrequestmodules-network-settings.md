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
ms.openlocfilehash: 20a586e945a889d1fd8a8d4c5c09c8b790c56fc3
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664019"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="9a24b-102">\<删除 webRequestModules 的 > 元素 (网络设置)</span><span class="sxs-lookup"><span data-stu-id="9a24b-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="9a24b-103">从应用程序中移除自定义 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="9a24b-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="9a24b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9a24b-104">\<configuration></span></span>  
<span data-ttu-id="9a24b-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="9a24b-105">\<system.net></span></span>  
<span data-ttu-id="9a24b-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="9a24b-106">\<webRequestModules></span></span>  
<span data-ttu-id="9a24b-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="9a24b-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a24b-108">语法</span><span class="sxs-lookup"><span data-stu-id="9a24b-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a24b-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9a24b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9a24b-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9a24b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a24b-111">特性</span><span class="sxs-lookup"><span data-stu-id="9a24b-111">Attributes</span></span>  
  
|<span data-ttu-id="9a24b-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="9a24b-112">**Attribute**</span></span>|<span data-ttu-id="9a24b-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="9a24b-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="9a24b-114">此 Web 请求模块处理的请求的 URI 前缀。</span><span class="sxs-lookup"><span data-stu-id="9a24b-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a24b-115">子元素</span><span class="sxs-lookup"><span data-stu-id="9a24b-115">Child Elements</span></span>  
 <span data-ttu-id="9a24b-116">无。</span><span class="sxs-lookup"><span data-stu-id="9a24b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a24b-117">父元素</span><span class="sxs-lookup"><span data-stu-id="9a24b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9a24b-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="9a24b-118">**Element**</span></span>|<span data-ttu-id="9a24b-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="9a24b-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9a24b-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="9a24b-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="9a24b-121">指定用于从网络主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="9a24b-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a24b-122">备注</span><span class="sxs-lookup"><span data-stu-id="9a24b-122">Remarks</span></span>  
 <span data-ttu-id="9a24b-123">`remove`元素将为指定的 URI 前缀删除已注册的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="9a24b-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="9a24b-124">`prefix`特性的值应为有效 URI 的前导字符, 例如, "`http`" 或 "`http://www.contoso.com`"。</span><span class="sxs-lookup"><span data-stu-id="9a24b-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9a24b-125">配置文件</span><span class="sxs-lookup"><span data-stu-id="9a24b-125">Configuration Files</span></span>  
 <span data-ttu-id="9a24b-126">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="9a24b-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a24b-127">示例</span><span class="sxs-lookup"><span data-stu-id="9a24b-127">Example</span></span>  

<span data-ttu-id="9a24b-128">下面的示例将删除 HTTP 的现有 Web 请求模块, 然后将新的自定义 Web 请求模块注册到`www.contoso.com`的 http 请求。</span><span class="sxs-lookup"><span data-stu-id="9a24b-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="9a24b-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a24b-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="9a24b-130">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="9a24b-130">Network Settings Schema</span></span>](index.md)
