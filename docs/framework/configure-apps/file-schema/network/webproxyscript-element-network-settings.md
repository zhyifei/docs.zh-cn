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
ms.openlocfilehash: 8a77c2567401fd80e355bb7fcee17b6684653ebe
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659035"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="dff5a-102">\<w > 元素 (网络设置)</span><span class="sxs-lookup"><span data-stu-id="dff5a-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="dff5a-103">配置用于发现 Web 代理的脚本的特征。</span><span class="sxs-lookup"><span data-stu-id="dff5a-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="dff5a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dff5a-104">\<configuration></span></span>  
<span data-ttu-id="dff5a-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="dff5a-105">\<system.net></span></span>  
<span data-ttu-id="dff5a-106">\<设置 ></span><span class="sxs-lookup"><span data-stu-id="dff5a-106">\<settings></span></span>  
<span data-ttu-id="dff5a-107">\<webProxyScript></span><span class="sxs-lookup"><span data-stu-id="dff5a-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dff5a-108">语法</span><span class="sxs-lookup"><span data-stu-id="dff5a-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dff5a-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dff5a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dff5a-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="dff5a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dff5a-111">特性</span><span class="sxs-lookup"><span data-stu-id="dff5a-111">Attributes</span></span>  
  
|<span data-ttu-id="dff5a-112">特性</span><span class="sxs-lookup"><span data-stu-id="dff5a-112">Attribute</span></span>|<span data-ttu-id="dff5a-113">描述</span><span class="sxs-lookup"><span data-stu-id="dff5a-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="dff5a-114">指定下载脚本的最长时间, 以小时、分钟和秒为单位。</span><span class="sxs-lookup"><span data-stu-id="dff5a-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="dff5a-115">默认值为一分钟。</span><span class="sxs-lookup"><span data-stu-id="dff5a-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dff5a-116">子元素</span><span class="sxs-lookup"><span data-stu-id="dff5a-116">Child Elements</span></span>  
 <span data-ttu-id="dff5a-117">无。</span><span class="sxs-lookup"><span data-stu-id="dff5a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dff5a-118">父元素</span><span class="sxs-lookup"><span data-stu-id="dff5a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dff5a-119">元素</span><span class="sxs-lookup"><span data-stu-id="dff5a-119">Element</span></span>|<span data-ttu-id="dff5a-120">描述</span><span class="sxs-lookup"><span data-stu-id="dff5a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dff5a-121">设置</span><span class="sxs-lookup"><span data-stu-id="dff5a-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="dff5a-122">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="dff5a-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dff5a-123">备注</span><span class="sxs-lookup"><span data-stu-id="dff5a-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="dff5a-124">配置文件</span><span class="sxs-lookup"><span data-stu-id="dff5a-124">Configuration Files</span></span>  
 <span data-ttu-id="dff5a-125">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="dff5a-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dff5a-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="dff5a-126">See also</span></span>

- [<span data-ttu-id="dff5a-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="dff5a-127">Network Settings Schema</span></span>](index.md)
