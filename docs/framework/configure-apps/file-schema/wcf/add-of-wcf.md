---
title: <add>WCF 的
ms.date: 03/30/2017
ms.assetid: c196f6d7-77f6-4266-973c-305b2b4dd8a2
ms.openlocfilehash: 0b21bdabc76ec4853a0f2664cdd3cead149417a1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850297"
---
# <a name="add-of-wcf"></a><span data-ttu-id="35d55-102">\<添加 WCF ></span><span class="sxs-lookup"><span data-stu-id="35d55-102">\<add> of WCF</span></span>
<span data-ttu-id="35d55-103">配置一个跟踪参与者，它侦听直接从运行时发出的跟踪记录，并按照配置跟踪参与者的任何方式处理这些记录。</span><span class="sxs-lookup"><span data-stu-id="35d55-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="35d55-104">这包括写入特定输出（例如，文件、控制台、ETW）、处理/聚合记录或可能需要的任何其他组合。</span><span class="sxs-lookup"><span data-stu-id="35d55-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="35d55-105">有关工作流跟踪和跟踪参与者的详细信息，请参阅[工作流跟踪和](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)跟踪和[跟踪参与者](../../../windows-workflow-foundation/tracking-participants.md)。</span><span class="sxs-lookup"><span data-stu-id="35d55-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="35d55-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="35d55-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="35d55-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="35d55-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="35d55-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="35d55-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="35d55-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<参与者 >** ](participants-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="35d55-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<participants>**](participants-of-wcf.md)</span></span>\
<span data-ttu-id="35d55-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="35d55-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35d55-111">语法</span><span class="sxs-lookup"><span data-stu-id="35d55-111">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35d55-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="35d55-112">Attributes and Elements</span></span>  
 <span data-ttu-id="35d55-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="35d55-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35d55-114">特性</span><span class="sxs-lookup"><span data-stu-id="35d55-114">Attributes</span></span>  
  
|<span data-ttu-id="35d55-115">元素</span><span class="sxs-lookup"><span data-stu-id="35d55-115">Element</span></span>|<span data-ttu-id="35d55-116">描述</span><span class="sxs-lookup"><span data-stu-id="35d55-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35d55-117">NAME</span><span class="sxs-lookup"><span data-stu-id="35d55-117">name</span></span>|<span data-ttu-id="35d55-118">一个字符串，指定跟踪参与者的名称。</span><span class="sxs-lookup"><span data-stu-id="35d55-118">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="35d55-119">profileName</span><span class="sxs-lookup"><span data-stu-id="35d55-119">profileName</span></span>|<span data-ttu-id="35d55-120">一个字符串，指定跟踪配置文件的名称，该跟踪配置文件定义跟踪参与者已订阅的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="35d55-120">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="35d55-121">type</span><span class="sxs-lookup"><span data-stu-id="35d55-121">type</span></span>|<span data-ttu-id="35d55-122">一个字符串，指定跟踪参与者的类型。</span><span class="sxs-lookup"><span data-stu-id="35d55-122">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35d55-123">子元素</span><span class="sxs-lookup"><span data-stu-id="35d55-123">Child Elements</span></span>  
 <span data-ttu-id="35d55-124">无。</span><span class="sxs-lookup"><span data-stu-id="35d55-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35d55-125">父元素</span><span class="sxs-lookup"><span data-stu-id="35d55-125">Parent Elements</span></span>  
  
|<span data-ttu-id="35d55-126">元素</span><span class="sxs-lookup"><span data-stu-id="35d55-126">Element</span></span>|<span data-ttu-id="35d55-127">描述</span><span class="sxs-lookup"><span data-stu-id="35d55-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35d55-128">\<participants></span><span class="sxs-lookup"><span data-stu-id="35d55-128">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="35d55-129">跟踪参与者的列表</span><span class="sxs-lookup"><span data-stu-id="35d55-129">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35d55-130">备注</span><span class="sxs-lookup"><span data-stu-id="35d55-130">Remarks</span></span>  
 <span data-ttu-id="35d55-131">跟踪参与者用于获取从工作流发出的跟踪数据并将其存储在不同的媒体中。</span><span class="sxs-lookup"><span data-stu-id="35d55-131">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="35d55-132">同样，也可以在跟踪参与者中执行对跟踪记录的任何后续处理。</span><span class="sxs-lookup"><span data-stu-id="35d55-132">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="35d55-133">多个跟踪参与者可同时使用跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="35d55-133">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="35d55-134">每个跟踪参与者都可与不同的跟踪配置文件关联。</span><span class="sxs-lookup"><span data-stu-id="35d55-134">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="35d55-135">提供了将跟踪记录写入 ETW 会话的标准跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="35d55-135">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="35d55-136">通过在配置文件中添加特定于跟踪的行为，可以对工作流服务配置参与者。</span><span class="sxs-lookup"><span data-stu-id="35d55-136">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="35d55-137">通过启用 ETW 跟踪参与者，可以在事件查看器中查看跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="35d55-137">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="35d55-138">如果这不能满足您的需求，您还可以编写自定义跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="35d55-138">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35d55-139">示例</span><span class="sxs-lookup"><span data-stu-id="35d55-139">Example</span></span>  
 <span data-ttu-id="35d55-140">下面的配置示例演示在 Web.config 文件中配置的标准 ETW 跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="35d55-140">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="35d55-141">ETW 跟踪参与者用于将跟踪记录写入 ETW 的提供程序 ID 在 `<diagnostics>` 节中定义。</span><span class="sxs-lookup"><span data-stu-id="35d55-141">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="35d55-142">跟踪参与者具有一个与其关联的配置文件，用来指定跟踪参与者已订阅的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="35d55-142">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="35d55-143">它由 `profileName` 元素的 `<add>` 特性进行定义。</span><span class="sxs-lookup"><span data-stu-id="35d55-143">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="35d55-144">定义这些内容后，跟踪参与者将被添加到 `<etwTracking>` 服务行为中。</span><span class="sxs-lookup"><span data-stu-id="35d55-144">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="35d55-145">这会将所选跟踪参与者添加到工作流实例的扩展中，以便它们开始接收跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="35d55-145">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0" />
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile" />
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="35d55-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="35d55-146">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="35d55-147">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="35d55-147">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="35d55-148">跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="35d55-148">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
