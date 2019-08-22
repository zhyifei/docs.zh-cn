---
title: <appDomainResourceMonitoring> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b82be30c18cde361aa412ee1b631c8368c8de1b3
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663933"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="79ba4-102">\<appDomainResourceMonitoring > 元素</span><span class="sxs-lookup"><span data-stu-id="79ba4-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="79ba4-103">指示运行时在过程的生命周期过程中收集所有应用程序域的统计数据。</span><span class="sxs-lookup"><span data-stu-id="79ba4-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="79ba4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="79ba4-104">\<configuration></span></span>  
<span data-ttu-id="79ba4-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="79ba4-105">\<runtime></span></span>  
<span data-ttu-id="79ba4-106">\<appDomainResourceMonitoring></span><span class="sxs-lookup"><span data-stu-id="79ba4-106">\<appDomainResourceMonitoring></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79ba4-107">语法</span><span class="sxs-lookup"><span data-stu-id="79ba4-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79ba4-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="79ba4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="79ba4-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="79ba4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79ba4-110">特性</span><span class="sxs-lookup"><span data-stu-id="79ba4-110">Attributes</span></span>  
  
|<span data-ttu-id="79ba4-111">特性</span><span class="sxs-lookup"><span data-stu-id="79ba4-111">Attribute</span></span>|<span data-ttu-id="79ba4-112">描述</span><span class="sxs-lookup"><span data-stu-id="79ba4-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="79ba4-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="79ba4-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="79ba4-114">指定运行时是否收集应用程序域资源监视的统计信息。</span><span class="sxs-lookup"><span data-stu-id="79ba4-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="79ba4-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="79ba4-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="79ba4-116">值</span><span class="sxs-lookup"><span data-stu-id="79ba4-116">Value</span></span>|<span data-ttu-id="79ba4-117">描述</span><span class="sxs-lookup"><span data-stu-id="79ba4-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="79ba4-118">收集应用程序域资源监视的统计信息。</span><span class="sxs-lookup"><span data-stu-id="79ba4-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="79ba4-119">不收集应用程序域资源监视的统计信息。</span><span class="sxs-lookup"><span data-stu-id="79ba4-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79ba4-120">子元素</span><span class="sxs-lookup"><span data-stu-id="79ba4-120">Child Elements</span></span>  
 <span data-ttu-id="79ba4-121">无。</span><span class="sxs-lookup"><span data-stu-id="79ba4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79ba4-122">父元素</span><span class="sxs-lookup"><span data-stu-id="79ba4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="79ba4-123">元素</span><span class="sxs-lookup"><span data-stu-id="79ba4-123">Element</span></span>|<span data-ttu-id="79ba4-124">描述</span><span class="sxs-lookup"><span data-stu-id="79ba4-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="79ba4-125">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="79ba4-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="79ba4-126">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="79ba4-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79ba4-127">备注</span><span class="sxs-lookup"><span data-stu-id="79ba4-127">Remarks</span></span>  
 <span data-ttu-id="79ba4-128">应用程序域资源监视可通过托管应用程序域类、托管[ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)接口和 Windows 事件跟踪 (ETW) 获得。</span><span class="sxs-lookup"><span data-stu-id="79ba4-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="79ba4-129">启用监视后, 会在进程的生存期内收集进程中所有应用程序域的统计信息。</span><span class="sxs-lookup"><span data-stu-id="79ba4-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="79ba4-130">若要从托管代码启用监视, 请<xref:System.AppDomain.MonitoringIsEnabled%2A>使用属性。</span><span class="sxs-lookup"><span data-stu-id="79ba4-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="79ba4-131">此配置元素仅在 .NET Framework 4 及更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="79ba4-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79ba4-132">示例</span><span class="sxs-lookup"><span data-stu-id="79ba4-132">Example</span></span>  
 <span data-ttu-id="79ba4-133">下面的示例演示如何启用应用程序域资源监视。</span><span class="sxs-lookup"><span data-stu-id="79ba4-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="79ba4-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="79ba4-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="79ba4-135">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="79ba4-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="79ba4-136">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="79ba4-136">Configuration File Schema</span></span>](../index.md)
