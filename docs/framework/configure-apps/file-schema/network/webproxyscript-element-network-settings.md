---
title: "&lt;webProxyScript&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4c7d6154d354e806a04ccc9da062db64c534039b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebproxyscriptgt-element-network-settings"></a><span data-ttu-id="bb722-102">&lt;webProxyScript&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="bb722-102">&lt;webProxyScript&gt; Element (Network Settings)</span></span>
<span data-ttu-id="bb722-103">配置用于发现 Web 代理的脚本的特征。</span><span class="sxs-lookup"><span data-stu-id="bb722-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="bb722-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bb722-104">\<configuration></span></span>  
<span data-ttu-id="bb722-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="bb722-105">\<system.net></span></span>  
<span data-ttu-id="bb722-106">\<设置 ></span><span class="sxs-lookup"><span data-stu-id="bb722-106">\<settings></span></span>  
<span data-ttu-id="bb722-107">\<webProxyScript ></span><span class="sxs-lookup"><span data-stu-id="bb722-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb722-108">语法</span><span class="sxs-lookup"><span data-stu-id="bb722-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb722-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bb722-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bb722-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bb722-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb722-111">特性</span><span class="sxs-lookup"><span data-stu-id="bb722-111">Attributes</span></span>  
  
|<span data-ttu-id="bb722-112">特性</span><span class="sxs-lookup"><span data-stu-id="bb722-112">Attribute</span></span>|<span data-ttu-id="bb722-113">描述</span><span class="sxs-lookup"><span data-stu-id="bb722-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="bb722-114">指定的最长时间中小时、 分钟和秒下载脚本。</span><span class="sxs-lookup"><span data-stu-id="bb722-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="bb722-115">默认值为一分钟。</span><span class="sxs-lookup"><span data-stu-id="bb722-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb722-116">子元素</span><span class="sxs-lookup"><span data-stu-id="bb722-116">Child Elements</span></span>  
 <span data-ttu-id="bb722-117">无。</span><span class="sxs-lookup"><span data-stu-id="bb722-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb722-118">父元素</span><span class="sxs-lookup"><span data-stu-id="bb722-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bb722-119">元素</span><span class="sxs-lookup"><span data-stu-id="bb722-119">Element</span></span>|<span data-ttu-id="bb722-120">描述</span><span class="sxs-lookup"><span data-stu-id="bb722-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb722-121">设置</span><span class="sxs-lookup"><span data-stu-id="bb722-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="bb722-122">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="bb722-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb722-123">备注</span><span class="sxs-lookup"><span data-stu-id="bb722-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bb722-124">配置文件</span><span class="sxs-lookup"><span data-stu-id="bb722-124">Configuration Files</span></span>  
 <span data-ttu-id="bb722-125">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="bb722-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb722-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb722-126">See Also</span></span>  
 [<span data-ttu-id="bb722-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="bb722-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
