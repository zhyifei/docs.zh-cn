---
title: <webProxyScript> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: 2abab3de2965c31c11d9acaf7b78f3a668563506
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697457"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="3795f-102">\<webProxyScript > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="3795f-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="3795f-103">配置用于发现 Web 代理的脚本的特征。</span><span class="sxs-lookup"><span data-stu-id="3795f-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
[<span data-ttu-id="3795f-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="3795f-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="3795f-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3795f-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="3795f-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3795f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="3795f-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<webProxyScript >**</span><span class="sxs-lookup"><span data-stu-id="3795f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3795f-108">语法</span><span class="sxs-lookup"><span data-stu-id="3795f-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3795f-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3795f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3795f-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3795f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3795f-111">特性</span><span class="sxs-lookup"><span data-stu-id="3795f-111">Attributes</span></span>  
  
|<span data-ttu-id="3795f-112">特性</span><span class="sxs-lookup"><span data-stu-id="3795f-112">Attribute</span></span>|<span data-ttu-id="3795f-113">描述</span><span class="sxs-lookup"><span data-stu-id="3795f-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="3795f-114">指定下载脚本的最长时间，以小时、分钟和秒为单位。</span><span class="sxs-lookup"><span data-stu-id="3795f-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="3795f-115">默认值为一分钟。</span><span class="sxs-lookup"><span data-stu-id="3795f-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3795f-116">子元素</span><span class="sxs-lookup"><span data-stu-id="3795f-116">Child Elements</span></span>  
 <span data-ttu-id="3795f-117">无。</span><span class="sxs-lookup"><span data-stu-id="3795f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3795f-118">父元素</span><span class="sxs-lookup"><span data-stu-id="3795f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3795f-119">元素</span><span class="sxs-lookup"><span data-stu-id="3795f-119">Element</span></span>|<span data-ttu-id="3795f-120">描述</span><span class="sxs-lookup"><span data-stu-id="3795f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3795f-121">设置</span><span class="sxs-lookup"><span data-stu-id="3795f-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="3795f-122">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="3795f-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3795f-123">备注</span><span class="sxs-lookup"><span data-stu-id="3795f-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3795f-124">配置文件</span><span class="sxs-lookup"><span data-stu-id="3795f-124">Configuration Files</span></span>  
 <span data-ttu-id="3795f-125">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="3795f-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3795f-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="3795f-126">See also</span></span>

- [<span data-ttu-id="3795f-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="3795f-127">Network Settings Schema</span></span>](index.md)
