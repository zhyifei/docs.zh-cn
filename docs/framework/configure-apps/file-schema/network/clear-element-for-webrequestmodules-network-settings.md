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
ms.openlocfilehash: 5832d120824df75d374fc94cb0aa4e08189cb965
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088491"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="29e87-102">\<清除 webRequestModules 的 > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="29e87-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="29e87-103">从应用程序中删除所有已注册的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="29e87-103">Removes all registered Web request modules from the application.</span></span>  

<span data-ttu-id="29e87-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="29e87-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="29e87-105">\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="29e87-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="29e87-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webRequestModules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="29e87-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="29e87-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**clear >**</span><span class="sxs-lookup"><span data-stu-id="29e87-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="29e87-108">语法</span><span class="sxs-lookup"><span data-stu-id="29e87-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29e87-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="29e87-109">Attributes and Elements</span></span>  
 <span data-ttu-id="29e87-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="29e87-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29e87-111">特性</span><span class="sxs-lookup"><span data-stu-id="29e87-111">Attributes</span></span>  
 <span data-ttu-id="29e87-112">无。</span><span class="sxs-lookup"><span data-stu-id="29e87-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="29e87-113">子元素</span><span class="sxs-lookup"><span data-stu-id="29e87-113">Child Elements</span></span>  
 <span data-ttu-id="29e87-114">无。</span><span class="sxs-lookup"><span data-stu-id="29e87-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29e87-115">父元素</span><span class="sxs-lookup"><span data-stu-id="29e87-115">Parent Elements</span></span>  
  
|<span data-ttu-id="29e87-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="29e87-116">**Element**</span></span>|<span data-ttu-id="29e87-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="29e87-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="29e87-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="29e87-118">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="29e87-119">指定用于从网络主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="29e87-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29e87-120">备注</span><span class="sxs-lookup"><span data-stu-id="29e87-120">Remarks</span></span>  
 <span data-ttu-id="29e87-121">`clear` 元素将删除之前在配置文件中或在配置层次结构中的更高级别定义的所有已注册 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="29e87-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="29e87-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="29e87-122">Configuration Files</span></span>  
 <span data-ttu-id="29e87-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="29e87-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="29e87-124">示例</span><span class="sxs-lookup"><span data-stu-id="29e87-124">Example</span></span>  
 <span data-ttu-id="29e87-125">下面的示例将清除所有 Web 请求模块，然后为 HTTP 注册 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="29e87-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="29e87-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="29e87-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="29e87-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="29e87-127">Network Settings Schema</span></span>](index.md)
