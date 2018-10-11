---
title: WCF 的 &lt;add&gt;
ms.date: 03/30/2017
ms.assetid: c196f6d7-77f6-4266-973c-305b2b4dd8a2
ms.openlocfilehash: 8b1bd0ef77cb1ecad4ada8db66c6c7da3b6ba997
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087188"
---
# <a name="ltaddgt-of-wcf"></a><span data-ttu-id="02fb6-102">WCF 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="02fb6-102">&lt;add&gt; of WCF</span></span>
<span data-ttu-id="02fb6-103">配置一个跟踪参与者，它侦听直接从运行时发出的跟踪记录，并按照配置跟踪参与者的任何方式处理这些记录。</span><span class="sxs-lookup"><span data-stu-id="02fb6-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="02fb6-104">这包括写入特定输出（例如，文件、控制台、ETW）、处理/聚合记录或可能需要的任何其他组合。</span><span class="sxs-lookup"><span data-stu-id="02fb6-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="02fb6-105">工作流跟踪和跟踪参与者的详细信息，请参阅[工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)并[跟踪参与者](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)。</span><span class="sxs-lookup"><span data-stu-id="02fb6-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
 <span data-ttu-id="02fb6-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="02fb6-106">\<system.serviceModel></span></span>  
<span data-ttu-id="02fb6-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="02fb6-107">\<tracking></span></span>  
<span data-ttu-id="02fb6-108">\<参与者 ></span><span class="sxs-lookup"><span data-stu-id="02fb6-108">\<participants></span></span>  
<span data-ttu-id="02fb6-109">\<add></span><span class="sxs-lookup"><span data-stu-id="02fb6-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02fb6-110">语法</span><span class="sxs-lookup"><span data-stu-id="02fb6-110">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String"           
         profileName="String"
         type="String" />
  </participants>
</tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="02fb6-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="02fb6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="02fb6-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="02fb6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02fb6-113">特性</span><span class="sxs-lookup"><span data-stu-id="02fb6-113">Attributes</span></span>  
  
|<span data-ttu-id="02fb6-114">元素</span><span class="sxs-lookup"><span data-stu-id="02fb6-114">Element</span></span>|<span data-ttu-id="02fb6-115">描述</span><span class="sxs-lookup"><span data-stu-id="02fb6-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02fb6-116">name</span><span class="sxs-lookup"><span data-stu-id="02fb6-116">name</span></span>|<span data-ttu-id="02fb6-117">一个字符串，指定跟踪参与者的名称。</span><span class="sxs-lookup"><span data-stu-id="02fb6-117">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="02fb6-118">profileName</span><span class="sxs-lookup"><span data-stu-id="02fb6-118">profileName</span></span>|<span data-ttu-id="02fb6-119">一个字符串，指定跟踪配置文件的名称，该跟踪配置文件定义跟踪参与者已订阅的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="02fb6-119">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="02fb6-120">类型</span><span class="sxs-lookup"><span data-stu-id="02fb6-120">type</span></span>|<span data-ttu-id="02fb6-121">一个字符串，指定跟踪参与者的类型。</span><span class="sxs-lookup"><span data-stu-id="02fb6-121">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02fb6-122">子元素</span><span class="sxs-lookup"><span data-stu-id="02fb6-122">Child Elements</span></span>  
 <span data-ttu-id="02fb6-123">无。</span><span class="sxs-lookup"><span data-stu-id="02fb6-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02fb6-124">父元素</span><span class="sxs-lookup"><span data-stu-id="02fb6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="02fb6-125">元素</span><span class="sxs-lookup"><span data-stu-id="02fb6-125">Element</span></span>|<span data-ttu-id="02fb6-126">描述</span><span class="sxs-lookup"><span data-stu-id="02fb6-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02fb6-127">\<参与者 ></span><span class="sxs-lookup"><span data-stu-id="02fb6-127">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="02fb6-128">跟踪参与者的列表</span><span class="sxs-lookup"><span data-stu-id="02fb6-128">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02fb6-129">备注</span><span class="sxs-lookup"><span data-stu-id="02fb6-129">Remarks</span></span>  
 <span data-ttu-id="02fb6-130">跟踪参与者用于获取从工作流发出的跟踪数据并将其存储在不同的媒体中。</span><span class="sxs-lookup"><span data-stu-id="02fb6-130">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="02fb6-131">同样，也可以在跟踪参与者中执行对跟踪记录的任何后续处理。</span><span class="sxs-lookup"><span data-stu-id="02fb6-131">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="02fb6-132">多个跟踪参与者可同时使用跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="02fb6-132">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="02fb6-133">每个跟踪参与者都可与不同的跟踪配置文件关联。</span><span class="sxs-lookup"><span data-stu-id="02fb6-133">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="02fb6-134">提供了将跟踪记录写入 ETW 会话的标准跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="02fb6-134">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="02fb6-135">通过在配置文件中添加特定于跟踪的行为，可以对工作流服务配置参与者。</span><span class="sxs-lookup"><span data-stu-id="02fb6-135">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="02fb6-136">通过启用 ETW 跟踪参与者，可以在事件查看器中查看跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="02fb6-136">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="02fb6-137">如果这不能满足您的要求，您还可以编写自定义跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="02fb6-137">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02fb6-138">示例</span><span class="sxs-lookup"><span data-stu-id="02fb6-138">Example</span></span>  
 <span data-ttu-id="02fb6-139">下面的配置示例演示在 Web.config 文件中配置的标准 ETW 跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="02fb6-139">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="02fb6-140">ETW 跟踪参与者用于将跟踪记录写入 ETW 的提供程序 ID 在 `<diagnostics>` 节中定义。</span><span class="sxs-lookup"><span data-stu-id="02fb6-140">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="02fb6-141">跟踪参与者具有一个与其关联的配置文件，用来指定跟踪参与者已订阅的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="02fb6-141">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="02fb6-142">它由 `profileName` 元素的 `<add>` 特性进行定义。</span><span class="sxs-lookup"><span data-stu-id="02fb6-142">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="02fb6-143">定义这些内容后，跟踪参与者将被添加到 `<etwTracking>` 服务行为中。</span><span class="sxs-lookup"><span data-stu-id="02fb6-143">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="02fb6-144">这会将所选跟踪参与者添加到工作流实例的扩展中，以便它们开始接收跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="02fb6-144">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02fb6-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="02fb6-145">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>  
 [<span data-ttu-id="02fb6-146">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="02fb6-146">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="02fb6-147">跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="02fb6-147">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
