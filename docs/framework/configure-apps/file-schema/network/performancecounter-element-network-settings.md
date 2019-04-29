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
ms.openlocfilehash: 30c5cd07c92a8fc3c340cab0ff9ae74e940c0c12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705229"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="ec24f-102">\<performanceCounter > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="ec24f-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="ec24f-103">启用或禁用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="ec24f-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="ec24f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ec24f-104">\<configuration></span></span>  
<span data-ttu-id="ec24f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ec24f-105">\<system.net></span></span>  
<span data-ttu-id="ec24f-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="ec24f-106">\<settings></span></span>  
<span data-ttu-id="ec24f-107">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="ec24f-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec24f-108">语法</span><span class="sxs-lookup"><span data-stu-id="ec24f-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec24f-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ec24f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ec24f-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ec24f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec24f-111">特性</span><span class="sxs-lookup"><span data-stu-id="ec24f-111">Attributes</span></span>  
  
|<span data-ttu-id="ec24f-112">特性</span><span class="sxs-lookup"><span data-stu-id="ec24f-112">Attribute</span></span>|<span data-ttu-id="ec24f-113">描述</span><span class="sxs-lookup"><span data-stu-id="ec24f-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ec24f-114">指定是否启用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="ec24f-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="ec24f-115">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ec24f-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec24f-116">子元素</span><span class="sxs-lookup"><span data-stu-id="ec24f-116">Child Elements</span></span>  
 <span data-ttu-id="ec24f-117">无。</span><span class="sxs-lookup"><span data-stu-id="ec24f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec24f-118">父元素</span><span class="sxs-lookup"><span data-stu-id="ec24f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ec24f-119">元素</span><span class="sxs-lookup"><span data-stu-id="ec24f-119">Element</span></span>|<span data-ttu-id="ec24f-120">描述</span><span class="sxs-lookup"><span data-stu-id="ec24f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec24f-121">settings</span><span class="sxs-lookup"><span data-stu-id="ec24f-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="ec24f-122">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="ec24f-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec24f-123">备注</span><span class="sxs-lookup"><span data-stu-id="ec24f-123">Remarks</span></span>  
 <span data-ttu-id="ec24f-124">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="ec24f-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="ec24f-125">需要在要使用的配置文件中启用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="ec24f-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="ec24f-126">通过配置文件中的单个设置即可启用或禁用所有网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="ec24f-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="ec24f-127">不能启用或禁用单个网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="ec24f-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="ec24f-128">有关特定的网络性能计数器的详细信息，请参阅[网络性能计数器](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="ec24f-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="ec24f-129">默认值为的性能计数器已禁用的网络。</span><span class="sxs-lookup"><span data-stu-id="ec24f-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="ec24f-130"><xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>属性可以用于获取的当前值**启用**适用的配置文件中的属性。</span><span class="sxs-lookup"><span data-stu-id="ec24f-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec24f-131">示例</span><span class="sxs-lookup"><span data-stu-id="ec24f-131">Example</span></span>  
 <span data-ttu-id="ec24f-132">下面的示例演示如何配置<xref:System.Net>和相关命名空间，以启用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="ec24f-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ec24f-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec24f-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ec24f-134">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="ec24f-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="ec24f-135">网络性能计数器</span><span class="sxs-lookup"><span data-stu-id="ec24f-135">Networking Performance Counters</span></span>](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking)
