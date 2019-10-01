---
title: webRequestModules 的 <clear> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
ms.openlocfilehash: 95a190dac3a9512b404a054c60c48de9c4574790
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698343"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="4fd7c-102">用于 webRequestModules 的 0clear > 元素（网络设置） @no__t</span><span class="sxs-lookup"><span data-stu-id="4fd7c-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="4fd7c-103">从应用程序中删除所有已注册的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="4fd7c-103">Removes all registered Web request modules from the application.</span></span>  
  
[<span data-ttu-id="4fd7c-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="4fd7c-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="4fd7c-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4fd7c-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="4fd7c-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<webRequestModules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4fd7c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="4fd7c-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="4fd7c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fd7c-108">语法</span><span class="sxs-lookup"><span data-stu-id="4fd7c-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fd7c-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4fd7c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4fd7c-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4fd7c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fd7c-111">特性</span><span class="sxs-lookup"><span data-stu-id="4fd7c-111">Attributes</span></span>  
 <span data-ttu-id="4fd7c-112">无。</span><span class="sxs-lookup"><span data-stu-id="4fd7c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4fd7c-113">子元素</span><span class="sxs-lookup"><span data-stu-id="4fd7c-113">Child Elements</span></span>  
 <span data-ttu-id="4fd7c-114">无。</span><span class="sxs-lookup"><span data-stu-id="4fd7c-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4fd7c-115">父元素</span><span class="sxs-lookup"><span data-stu-id="4fd7c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4fd7c-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="4fd7c-116">**Element**</span></span>|<span data-ttu-id="4fd7c-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="4fd7c-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4fd7c-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="4fd7c-118">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="4fd7c-119">指定用于从网络主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="4fd7c-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fd7c-120">备注</span><span class="sxs-lookup"><span data-stu-id="4fd7c-120">Remarks</span></span>  
 <span data-ttu-id="4fd7c-121">@No__t-0 元素删除先前在配置文件中或在配置层次结构中的更高级别定义的所有已注册 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="4fd7c-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4fd7c-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="4fd7c-122">Configuration Files</span></span>  
 <span data-ttu-id="4fd7c-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="4fd7c-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fd7c-124">示例</span><span class="sxs-lookup"><span data-stu-id="4fd7c-124">Example</span></span>  
 <span data-ttu-id="4fd7c-125">下面的示例将清除所有 Web 请求模块，然后为 HTTP 注册 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="4fd7c-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4fd7c-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="4fd7c-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="4fd7c-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="4fd7c-127">Network Settings Schema</span></span>](index.md)
