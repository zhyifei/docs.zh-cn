---
title: "&lt;参与者&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e20cc8ed26feccf6fcf7fae40d2a219cd103dbb0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltparticipantsgt"></a><span data-ttu-id="7eb46-102">&lt;参与者&gt;</span><span class="sxs-lookup"><span data-stu-id="7eb46-102">&lt;participants&gt;</span></span>
<span data-ttu-id="7eb46-103">配置一列跟踪参与者，它们侦听直接从运行时发出的跟踪记录，并按照它们的任何方式处理这些记录。</span><span class="sxs-lookup"><span data-stu-id="7eb46-103">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="7eb46-104">这包括写入特定输出（例如，文件、控制台、ETW）、处理/聚合记录或可能需要的任何其他组合。</span><span class="sxs-lookup"><span data-stu-id="7eb46-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="7eb46-105">工作流跟踪和跟踪参与者的详细信息，请参阅[工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)和[跟踪参与者](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)。</span><span class="sxs-lookup"><span data-stu-id="7eb46-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="7eb46-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="7eb46-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7eb46-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="7eb46-107">\<tracking></span></span>  
<span data-ttu-id="7eb46-108">\<参与者 ></span><span class="sxs-lookup"><span data-stu-id="7eb46-108">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eb46-109">语法</span><span class="sxs-lookup"><span data-stu-id="7eb46-109">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" 
         profileName="String" 
         type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7eb46-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7eb46-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7eb46-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7eb46-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7eb46-112">特性</span><span class="sxs-lookup"><span data-stu-id="7eb46-112">Attributes</span></span>  
 <span data-ttu-id="7eb46-113">无。</span><span class="sxs-lookup"><span data-stu-id="7eb46-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7eb46-114">子元素</span><span class="sxs-lookup"><span data-stu-id="7eb46-114">Child Elements</span></span>  
  
|<span data-ttu-id="7eb46-115">元素</span><span class="sxs-lookup"><span data-stu-id="7eb46-115">Element</span></span>|<span data-ttu-id="7eb46-116">说明</span><span class="sxs-lookup"><span data-stu-id="7eb46-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7eb46-117">\<add></span><span class="sxs-lookup"><span data-stu-id="7eb46-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="7eb46-118">包含跟踪参与者的设置。</span><span class="sxs-lookup"><span data-stu-id="7eb46-118">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7eb46-119">父元素</span><span class="sxs-lookup"><span data-stu-id="7eb46-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7eb46-120">元素</span><span class="sxs-lookup"><span data-stu-id="7eb46-120">Element</span></span>|<span data-ttu-id="7eb46-121">描述</span><span class="sxs-lookup"><span data-stu-id="7eb46-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7eb46-122">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="7eb46-122">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="7eb46-123">表示一个配置节，用于定义工作流服务的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="7eb46-123">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7eb46-124">备注</span><span class="sxs-lookup"><span data-stu-id="7eb46-124">Remarks</span></span>  
 <span data-ttu-id="7eb46-125">跟踪参与者用于获取从工作流发出的跟踪数据并将其存储在不同的媒体中。</span><span class="sxs-lookup"><span data-stu-id="7eb46-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="7eb46-126">同样，也可以在跟踪参与者中执行对跟踪记录的任何后续处理。</span><span class="sxs-lookup"><span data-stu-id="7eb46-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="7eb46-127">多个跟踪参与者可同时使用跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="7eb46-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="7eb46-128">每个跟踪参与者都可与不同的跟踪配置文件关联。</span><span class="sxs-lookup"><span data-stu-id="7eb46-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="7eb46-129">提供了将跟踪记录写入 ETW 会话的标准跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="7eb46-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="7eb46-130">通过在配置文件中添加特定于跟踪的行为，可以对工作流服务配置参与者。</span><span class="sxs-lookup"><span data-stu-id="7eb46-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="7eb46-131">通过启用 ETW 跟踪参与者，可以在事件查看器中查看跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="7eb46-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="7eb46-132">如果这不能满足您的需求，您还可以编写自定义跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="7eb46-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7eb46-133">示例</span><span class="sxs-lookup"><span data-stu-id="7eb46-133">Example</span></span>  
 <span data-ttu-id="7eb46-134">下面的配置示例演示在 Web.config 文件中配置的标准 ETW 跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="7eb46-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="7eb46-135">在中定义 ETW 跟踪参与者使用跟踪记录写入 ETW 提供程序 Id **\<诊断 >**部分。</span><span class="sxs-lookup"><span data-stu-id="7eb46-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="7eb46-136">跟踪参与者具有一个与其关联的配置文件，用来指定跟踪参与者已订阅的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="7eb46-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="7eb46-137">这定义由**profileName**属性**\<添加 >**元素。</span><span class="sxs-lookup"><span data-stu-id="7eb46-137">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="7eb46-138">这些定义后，跟踪参与者添加到 **\<etwTracking >**服务行为。</span><span class="sxs-lookup"><span data-stu-id="7eb46-138">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="7eb46-139">这会将所选跟踪参与者添加到工作流实例的扩展中，以便它们开始接收跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="7eb46-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7eb46-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7eb46-140">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>  
 [<span data-ttu-id="7eb46-141">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="7eb46-141">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="7eb46-142">跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="7eb46-142">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
