---
title: <performanceCounter> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 3fe6b19d0055aafad859b55960800d9786d7fa08
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698001"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="c6ea8-102">\<performanceCounter > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="c6ea8-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="c6ea8-103">启用或禁用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-103">Enables or disables networking performance counters.</span></span>  
  
[<span data-ttu-id="c6ea8-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c6ea8-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c6ea8-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c6ea8-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="c6ea8-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c6ea8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="c6ea8-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<performanceCounters >**</span><span class="sxs-lookup"><span data-stu-id="c6ea8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6ea8-108">语法</span><span class="sxs-lookup"><span data-stu-id="c6ea8-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6ea8-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c6ea8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c6ea8-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6ea8-111">特性</span><span class="sxs-lookup"><span data-stu-id="c6ea8-111">Attributes</span></span>  
  
|<span data-ttu-id="c6ea8-112">特性</span><span class="sxs-lookup"><span data-stu-id="c6ea8-112">Attribute</span></span>|<span data-ttu-id="c6ea8-113">描述</span><span class="sxs-lookup"><span data-stu-id="c6ea8-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c6ea8-114">指定是否启用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="c6ea8-115">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6ea8-116">子元素</span><span class="sxs-lookup"><span data-stu-id="c6ea8-116">Child Elements</span></span>  
 <span data-ttu-id="c6ea8-117">无。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6ea8-118">父元素</span><span class="sxs-lookup"><span data-stu-id="c6ea8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c6ea8-119">元素</span><span class="sxs-lookup"><span data-stu-id="c6ea8-119">Element</span></span>|<span data-ttu-id="c6ea8-120">描述</span><span class="sxs-lookup"><span data-stu-id="c6ea8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6ea8-121">设置</span><span class="sxs-lookup"><span data-stu-id="c6ea8-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="c6ea8-122">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6ea8-123">备注</span><span class="sxs-lookup"><span data-stu-id="c6ea8-123">Remarks</span></span>  
 <span data-ttu-id="c6ea8-124">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="c6ea8-125">需要在要使用的配置文件中启用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="c6ea8-126">通过配置文件中的单个设置即可启用或禁用所有网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="c6ea8-127">不能启用或禁用单个网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="c6ea8-128">有关特定的网络性能计数器的详细信息，请参阅[联网性能计数器](../../../debug-trace-profile/performance-counters.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="c6ea8-129">默认值是禁用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="c6ea8-130">@No__t-0 属性可用于从适用的配置文件中获取**已启用**属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6ea8-131">示例</span><span class="sxs-lookup"><span data-stu-id="c6ea8-131">Example</span></span>  
 <span data-ttu-id="c6ea8-132">下面的示例演示如何配置 @no__t 0 和相关命名空间，以启用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c6ea8-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6ea8-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6ea8-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c6ea8-134">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="c6ea8-134">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c6ea8-135">网络性能计数器</span><span class="sxs-lookup"><span data-stu-id="c6ea8-135">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking)
