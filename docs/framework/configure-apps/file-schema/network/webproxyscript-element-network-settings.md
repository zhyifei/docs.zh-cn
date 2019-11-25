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
ms.openlocfilehash: dbad888cd0537f63c09840ac1053f924db9ea9bc
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089059"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="d76d7-102">\<w > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="d76d7-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="d76d7-103">配置用于发现 Web 代理的脚本的特征。</span><span class="sxs-lookup"><span data-stu-id="d76d7-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  

<span data-ttu-id="d76d7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d76d7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d76d7-105">\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d76d7-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="d76d7-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**设置 >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d76d7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="d76d7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<w >**</span><span class="sxs-lookup"><span data-stu-id="d76d7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d76d7-108">语法</span><span class="sxs-lookup"><span data-stu-id="d76d7-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d76d7-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d76d7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d76d7-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d76d7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d76d7-111">特性</span><span class="sxs-lookup"><span data-stu-id="d76d7-111">Attributes</span></span>  
  
|<span data-ttu-id="d76d7-112">特性</span><span class="sxs-lookup"><span data-stu-id="d76d7-112">Attribute</span></span>|<span data-ttu-id="d76d7-113">描述</span><span class="sxs-lookup"><span data-stu-id="d76d7-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="d76d7-114">指定下载脚本的最长时间，以小时、分钟和秒为单位。</span><span class="sxs-lookup"><span data-stu-id="d76d7-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="d76d7-115">默认值为一分钟。</span><span class="sxs-lookup"><span data-stu-id="d76d7-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d76d7-116">子元素</span><span class="sxs-lookup"><span data-stu-id="d76d7-116">Child Elements</span></span>  
 <span data-ttu-id="d76d7-117">无。</span><span class="sxs-lookup"><span data-stu-id="d76d7-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d76d7-118">父元素</span><span class="sxs-lookup"><span data-stu-id="d76d7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d76d7-119">元素</span><span class="sxs-lookup"><span data-stu-id="d76d7-119">Element</span></span>|<span data-ttu-id="d76d7-120">描述</span><span class="sxs-lookup"><span data-stu-id="d76d7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d76d7-121">设置</span><span class="sxs-lookup"><span data-stu-id="d76d7-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="d76d7-122">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="d76d7-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d76d7-123">备注</span><span class="sxs-lookup"><span data-stu-id="d76d7-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d76d7-124">配置文件</span><span class="sxs-lookup"><span data-stu-id="d76d7-124">Configuration Files</span></span>  
 <span data-ttu-id="d76d7-125">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="d76d7-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76d7-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="d76d7-126">See also</span></span>

- [<span data-ttu-id="d76d7-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="d76d7-127">Network Settings Schema</span></span>](index.md)
