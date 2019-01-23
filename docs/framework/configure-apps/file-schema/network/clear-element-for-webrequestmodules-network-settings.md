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
ms.openlocfilehash: ccb9a19d4e6d79a84123014746b659a7168b2158
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606999"
---
# <a name="ltcleargt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="73217-102">&lt;清除&gt;webRequestModules （网络设置） 的</span><span class="sxs-lookup"><span data-stu-id="73217-102">&lt;clear&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="73217-103">从应用程序中删除所有已注册的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="73217-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="73217-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="73217-104">\<configuration></span></span>  
<span data-ttu-id="73217-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="73217-105">\<system.net></span></span>  
<span data-ttu-id="73217-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="73217-106">\<webRequestModules></span></span>  
<span data-ttu-id="73217-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="73217-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73217-108">语法</span><span class="sxs-lookup"><span data-stu-id="73217-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73217-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="73217-109">Attributes and Elements</span></span>  
 <span data-ttu-id="73217-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="73217-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73217-111">特性</span><span class="sxs-lookup"><span data-stu-id="73217-111">Attributes</span></span>  
 <span data-ttu-id="73217-112">无。</span><span class="sxs-lookup"><span data-stu-id="73217-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73217-113">子元素</span><span class="sxs-lookup"><span data-stu-id="73217-113">Child Elements</span></span>  
 <span data-ttu-id="73217-114">无。</span><span class="sxs-lookup"><span data-stu-id="73217-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73217-115">父元素</span><span class="sxs-lookup"><span data-stu-id="73217-115">Parent Elements</span></span>  
  
|<span data-ttu-id="73217-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="73217-116">**Element**</span></span>|<span data-ttu-id="73217-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="73217-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="73217-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="73217-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="73217-119">指定模块用于从网络主机请求信息。</span><span class="sxs-lookup"><span data-stu-id="73217-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73217-120">备注</span><span class="sxs-lookup"><span data-stu-id="73217-120">Remarks</span></span>  
 <span data-ttu-id="73217-121">`clear`元素中删除所有已注册的配置文件中或在配置层次结构中较高级别上前面定义的 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="73217-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="73217-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="73217-122">Configuration Files</span></span>  
 <span data-ttu-id="73217-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="73217-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73217-124">示例</span><span class="sxs-lookup"><span data-stu-id="73217-124">Example</span></span>  
 <span data-ttu-id="73217-125">下面的示例将清除所有 Web 请求模块，然后为 HTTP 注册 Web 请求模块。</span><span class="sxs-lookup"><span data-stu-id="73217-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73217-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="73217-126">See also</span></span>
- <xref:System.Net.WebRequest>
- [<span data-ttu-id="73217-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="73217-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
