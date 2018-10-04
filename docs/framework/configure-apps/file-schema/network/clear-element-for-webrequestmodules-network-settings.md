---
title: '&lt;清除&gt;webRequestModules （网络设置） 的'
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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2b313aa2481b1257715ac4dbc6d452e2120f4726
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48780987"
---
# <a name="ltcleargt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="e9997-102">&lt;清除&gt;webRequestModules （网络设置） 的</span><span class="sxs-lookup"><span data-stu-id="e9997-102">&lt;clear&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="e9997-103">从应用程序中删除所有已注册的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="e9997-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="e9997-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e9997-104">\<configuration></span></span>  
<span data-ttu-id="e9997-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e9997-105">\<system.net></span></span>  
<span data-ttu-id="e9997-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="e9997-106">\<webRequestModules></span></span>  
<span data-ttu-id="e9997-107">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="e9997-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9997-108">语法</span><span class="sxs-lookup"><span data-stu-id="e9997-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9997-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e9997-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e9997-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e9997-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9997-111">特性</span><span class="sxs-lookup"><span data-stu-id="e9997-111">Attributes</span></span>  
 <span data-ttu-id="e9997-112">无。</span><span class="sxs-lookup"><span data-stu-id="e9997-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e9997-113">子元素</span><span class="sxs-lookup"><span data-stu-id="e9997-113">Child Elements</span></span>  
 <span data-ttu-id="e9997-114">无。</span><span class="sxs-lookup"><span data-stu-id="e9997-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9997-115">父元素</span><span class="sxs-lookup"><span data-stu-id="e9997-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e9997-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="e9997-116">**Element**</span></span>|<span data-ttu-id="e9997-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="e9997-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e9997-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="e9997-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="e9997-119">指定模块用于从网络主机请求信息。</span><span class="sxs-lookup"><span data-stu-id="e9997-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9997-120">备注</span><span class="sxs-lookup"><span data-stu-id="e9997-120">Remarks</span></span>  
 <span data-ttu-id="e9997-121">`clear`元素中删除所有已注册的配置文件中或在配置层次结构中较高级别上前面定义的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="e9997-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e9997-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="e9997-122">Configuration Files</span></span>  
 <span data-ttu-id="e9997-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="e9997-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9997-124">示例</span><span class="sxs-lookup"><span data-stu-id="e9997-124">Example</span></span>  
 <span data-ttu-id="e9997-125">下面的示例将清除所有 Web 请求模块，然后为 HTTP 注册 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="e9997-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9997-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9997-126">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="e9997-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="e9997-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
