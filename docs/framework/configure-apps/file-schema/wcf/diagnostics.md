---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 3fc7828d399555f7c459f6dd067ce9a24b8998b6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108025"
---
# <a name="diagnostics"></a><span data-ttu-id="a9610-101">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="a9610-101">\<diagnostics></span></span>
<span data-ttu-id="a9610-102">`diagnostics` 元素定义管理员可以用来进行运行时检查和控制的设置。</span><span class="sxs-lookup"><span data-stu-id="a9610-102">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
 <span data-ttu-id="a9610-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a9610-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a9610-104">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="a9610-104">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9610-105">语法</span><span class="sxs-lookup"><span data-stu-id="a9610-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9610-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a9610-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a9610-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a9610-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9610-108">特性</span><span class="sxs-lookup"><span data-stu-id="a9610-108">Attributes</span></span>  
  
|<span data-ttu-id="a9610-109">特性</span><span class="sxs-lookup"><span data-stu-id="a9610-109">Attribute</span></span>|<span data-ttu-id="a9610-110">描述</span><span class="sxs-lookup"><span data-stu-id="a9610-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a9610-111">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="a9610-111">etwProviderId</span></span>|<span data-ttu-id="a9610-112">一个字符串，指定将事件写入到 ETW 会话的事件跟踪提供程序的标识符。</span><span class="sxs-lookup"><span data-stu-id="a9610-112">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="a9610-113">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="a9610-113">performanceCounters</span></span>|<span data-ttu-id="a9610-114">指定是否启用程序集的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="a9610-114">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="a9610-115">有效值为</span><span class="sxs-lookup"><span data-stu-id="a9610-115">Valid values are</span></span><br /><br /> <span data-ttu-id="a9610-116">-关闭：性能计数器被禁用。</span><span class="sxs-lookup"><span data-stu-id="a9610-116">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="a9610-117">-ServiceOnly:只启用与此服务相关的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="a9610-117">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="a9610-118">-所有：可以在运行时查看性能计数器。</span><span class="sxs-lookup"><span data-stu-id="a9610-118">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="a9610-119">-默认值：创建单个性能计数器实例 _WCF_Admin。</span><span class="sxs-lookup"><span data-stu-id="a9610-119">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="a9610-120">此实例用于启用基础结构所使用的 SQM 数据的集合。</span><span class="sxs-lookup"><span data-stu-id="a9610-120">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="a9610-121">此实例的计数器值均未进行更新，因此将保持为零。</span><span class="sxs-lookup"><span data-stu-id="a9610-121">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="a9610-122">这是在 WCF 没有配置的情况下的默认值。</span><span class="sxs-lookup"><span data-stu-id="a9610-122">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="a9610-123">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="a9610-123">wmiProviderEnabled</span></span>|<span data-ttu-id="a9610-124">一个布尔值，指定是否启用程序集的 WMI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="a9610-124">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="a9610-125">用户要获得在运行时访问 Windows Communication Foundation (WCF) 的检查和控制功能的权限，需要使用 WMI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="a9610-125">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="a9610-126">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="a9610-126">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9610-127">子元素</span><span class="sxs-lookup"><span data-stu-id="a9610-127">Child Elements</span></span>  
  
|<span data-ttu-id="a9610-128">元素</span><span class="sxs-lookup"><span data-stu-id="a9610-128">Element</span></span>|<span data-ttu-id="a9610-129">描述</span><span class="sxs-lookup"><span data-stu-id="a9610-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9610-130">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="a9610-130">\<endToEndTracing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|<span data-ttu-id="a9610-131">一个配置元素，用于启用和禁用服务应用程序运行过程中端对端跟踪的不同方面。</span><span class="sxs-lookup"><span data-stu-id="a9610-131">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="a9610-132">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="a9610-132">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|<span data-ttu-id="a9610-133">描述 WCF 消息日志记录的设置。</span><span class="sxs-lookup"><span data-stu-id="a9610-133">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9610-134">父元素</span><span class="sxs-lookup"><span data-stu-id="a9610-134">Parent Elements</span></span>  
  
|<span data-ttu-id="a9610-135">元素</span><span class="sxs-lookup"><span data-stu-id="a9610-135">Element</span></span>|<span data-ttu-id="a9610-136">描述</span><span class="sxs-lookup"><span data-stu-id="a9610-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9610-137">serviceModel</span><span class="sxs-lookup"><span data-stu-id="a9610-137">serviceModel</span></span>|<span data-ttu-id="a9610-138">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="a9610-138">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9610-139">备注</span><span class="sxs-lookup"><span data-stu-id="a9610-139">Remarks</span></span>  
 <span data-ttu-id="a9610-140">`diagnostics` 节定义了位于程序集中的所有服务的诊断设置。</span><span class="sxs-lookup"><span data-stu-id="a9610-140">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="a9610-141">无法在服务级别定义单独的诊断设置，除非程序集中只有一个服务。</span><span class="sxs-lookup"><span data-stu-id="a9610-141">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="a9610-142">将根据本节的需求来设置属性。</span><span class="sxs-lookup"><span data-stu-id="a9610-142">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9610-143">示例</span><span class="sxs-lookup"><span data-stu-id="a9610-143">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a9610-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9610-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
