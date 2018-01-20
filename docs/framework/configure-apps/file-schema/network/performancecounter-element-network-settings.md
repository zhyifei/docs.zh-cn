---
title: "&lt;performanceCounter&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: c50bf9e882ade86e70db217a75fef2a893c45572
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ltperformancecountergt-element-network-settings"></a><span data-ttu-id="00961-102">&lt;performanceCounter&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="00961-102">&lt;performanceCounter&gt; Element (Network Settings)</span></span>
<span data-ttu-id="00961-103">启用或禁用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="00961-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="00961-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="00961-104">\<configuration></span></span>  
<span data-ttu-id="00961-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="00961-105">\<system.net></span></span>  
<span data-ttu-id="00961-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="00961-106">\<settings></span></span>  
<span data-ttu-id="00961-107">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="00961-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00961-108">语法</span><span class="sxs-lookup"><span data-stu-id="00961-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00961-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="00961-109">Attributes and Elements</span></span>  
 <span data-ttu-id="00961-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="00961-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00961-111">特性</span><span class="sxs-lookup"><span data-stu-id="00961-111">Attributes</span></span>  
  
|<span data-ttu-id="00961-112">特性</span><span class="sxs-lookup"><span data-stu-id="00961-112">Attribute</span></span>|<span data-ttu-id="00961-113">描述</span><span class="sxs-lookup"><span data-stu-id="00961-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="00961-114">指定是否启用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="00961-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="00961-115">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="00961-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00961-116">子元素</span><span class="sxs-lookup"><span data-stu-id="00961-116">Child Elements</span></span>  
 <span data-ttu-id="00961-117">无。</span><span class="sxs-lookup"><span data-stu-id="00961-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00961-118">父元素</span><span class="sxs-lookup"><span data-stu-id="00961-118">Parent Elements</span></span>  
  
|<span data-ttu-id="00961-119">元素</span><span class="sxs-lookup"><span data-stu-id="00961-119">Element</span></span>|<span data-ttu-id="00961-120">描述</span><span class="sxs-lookup"><span data-stu-id="00961-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00961-121">settings</span><span class="sxs-lookup"><span data-stu-id="00961-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="00961-122">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="00961-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00961-123">备注</span><span class="sxs-lookup"><span data-stu-id="00961-123">Remarks</span></span>  
 <span data-ttu-id="00961-124">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="00961-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="00961-125">需要在要使用的配置文件中启用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="00961-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="00961-126">通过配置文件中的单个设置即可启用或禁用所有网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="00961-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="00961-127">不能启用或禁用单个网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="00961-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="00961-128">有关特定的网络性能计数器的详细信息，请参阅[网络性能计数器](http://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd)。</span><span class="sxs-lookup"><span data-stu-id="00961-128">For more information on the specific networking performance counters, see [Networking Performance Counters](http://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd).</span></span>  
  
 <span data-ttu-id="00961-129">默认值为该网络的性能计数器已禁用。</span><span class="sxs-lookup"><span data-stu-id="00961-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="00961-130"><xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>属性可以用于获取的当前值**启用**从适用的配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="00961-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00961-131">示例</span><span class="sxs-lookup"><span data-stu-id="00961-131">Example</span></span>  
 <span data-ttu-id="00961-132">下面的示例演示如何配置<xref:System.Net>和相关命名空间以启用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="00961-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00961-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="00961-133">See Also</span></span>  
 <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="00961-134">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="00961-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [<span data-ttu-id="00961-135">网络性能计数器</span><span class="sxs-lookup"><span data-stu-id="00961-135">Networking Performance Counters</span></span>](http://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd)
