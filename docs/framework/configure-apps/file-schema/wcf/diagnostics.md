---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 2749bc6c66d491a8a160d98b508fb43aa027b806
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398044"
---
# <a name="diagnostics"></a><span data-ttu-id="2006d-101">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="2006d-101">\<diagnostics></span></span>
<span data-ttu-id="2006d-102">`diagnostics` 元素定义管理员可以用来进行运行时检查和控制的设置。</span><span class="sxs-lookup"><span data-stu-id="2006d-102">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
<span data-ttu-id="2006d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2006d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2006d-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2006d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2006d-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<诊断 >**</span><span class="sxs-lookup"><span data-stu-id="2006d-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2006d-106">语法</span><span class="sxs-lookup"><span data-stu-id="2006d-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics etwProviderId="String"
               performanceCounters="Off/ServiceOnly/All/Default"
               wmiProviderEnabled="Boolean">
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2006d-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2006d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2006d-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2006d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2006d-109">特性</span><span class="sxs-lookup"><span data-stu-id="2006d-109">Attributes</span></span>  
  
|<span data-ttu-id="2006d-110">特性</span><span class="sxs-lookup"><span data-stu-id="2006d-110">Attribute</span></span>|<span data-ttu-id="2006d-111">描述</span><span class="sxs-lookup"><span data-stu-id="2006d-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2006d-112">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="2006d-112">etwProviderId</span></span>|<span data-ttu-id="2006d-113">一个字符串，指定将事件写入到 ETW 会话的事件跟踪提供程序的标识符。</span><span class="sxs-lookup"><span data-stu-id="2006d-113">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="2006d-114">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="2006d-114">performanceCounters</span></span>|<span data-ttu-id="2006d-115">指定是否启用程序集的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="2006d-115">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="2006d-116">有效值为</span><span class="sxs-lookup"><span data-stu-id="2006d-116">Valid values are</span></span><br /><br /> <span data-ttu-id="2006d-117">非性能计数器被禁用。</span><span class="sxs-lookup"><span data-stu-id="2006d-117">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="2006d-118">ServiceOnly只启用与此服务相关的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="2006d-118">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="2006d-119">一切可以在运行时查看性能计数器。</span><span class="sxs-lookup"><span data-stu-id="2006d-119">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="2006d-120">缺省值创建单个性能计数器实例 _WCF_Admin。</span><span class="sxs-lookup"><span data-stu-id="2006d-120">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="2006d-121">此实例用于启用基础结构所使用的 SQM 数据的集合。</span><span class="sxs-lookup"><span data-stu-id="2006d-121">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="2006d-122">此实例的计数器值均未进行更新，因此将保持为零。</span><span class="sxs-lookup"><span data-stu-id="2006d-122">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="2006d-123">这是在 WCF 没有配置的情况下的默认值。</span><span class="sxs-lookup"><span data-stu-id="2006d-123">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="2006d-124">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="2006d-124">wmiProviderEnabled</span></span>|<span data-ttu-id="2006d-125">一个布尔值，指定是否启用程序集的 WMI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="2006d-125">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="2006d-126">用户要获得在运行时访问 Windows Communication Foundation (WCF) 的检查和控制功能的权限，需要使用 WMI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="2006d-126">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="2006d-127">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="2006d-127">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2006d-128">子元素</span><span class="sxs-lookup"><span data-stu-id="2006d-128">Child Elements</span></span>  
  
|<span data-ttu-id="2006d-129">元素</span><span class="sxs-lookup"><span data-stu-id="2006d-129">Element</span></span>|<span data-ttu-id="2006d-130">描述</span><span class="sxs-lookup"><span data-stu-id="2006d-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2006d-131">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="2006d-131">\<endToEndTracing></span></span>](endtoendtracing.md)|<span data-ttu-id="2006d-132">一个配置元素，用于启用和禁用服务应用程序运行过程中端对端跟踪的不同方面。</span><span class="sxs-lookup"><span data-stu-id="2006d-132">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="2006d-133">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="2006d-133">\<messageLogging></span></span>](messagelogging.md)|<span data-ttu-id="2006d-134">描述 WCF 消息日志记录的设置。</span><span class="sxs-lookup"><span data-stu-id="2006d-134">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2006d-135">父元素</span><span class="sxs-lookup"><span data-stu-id="2006d-135">Parent Elements</span></span>  
  
|<span data-ttu-id="2006d-136">元素</span><span class="sxs-lookup"><span data-stu-id="2006d-136">Element</span></span>|<span data-ttu-id="2006d-137">描述</span><span class="sxs-lookup"><span data-stu-id="2006d-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2006d-138">serviceModel</span><span class="sxs-lookup"><span data-stu-id="2006d-138">serviceModel</span></span>|<span data-ttu-id="2006d-139">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="2006d-139">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2006d-140">备注</span><span class="sxs-lookup"><span data-stu-id="2006d-140">Remarks</span></span>  
 <span data-ttu-id="2006d-141">`diagnostics` 节定义了位于程序集中的所有服务的诊断设置。</span><span class="sxs-lookup"><span data-stu-id="2006d-141">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="2006d-142">无法在服务级别定义单独的诊断设置，除非程序集中只有一个服务。</span><span class="sxs-lookup"><span data-stu-id="2006d-142">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="2006d-143">将根据本节的需求来设置属性。</span><span class="sxs-lookup"><span data-stu-id="2006d-143">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2006d-144">示例</span><span class="sxs-lookup"><span data-stu-id="2006d-144">Example</span></span>  
  
```xml  
<diagnostics wmiProviderEnabled="false"
             performanceCounters="all">
  <messageLogging logEntireMessage="true"
                  logMalformedMessages="true"
                  logMessagesAtServiceLevel="true"
                  logMessagesAtTransportLevel="true"
                  maxMessagesToLog="42"
                  maxSizeOfMessageToLog="42">
    <filters>
      <clear />
    </filters>
  </messageLogging>
</diagnostics>
```  
  
## <a name="see-also"></a><span data-ttu-id="2006d-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="2006d-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
