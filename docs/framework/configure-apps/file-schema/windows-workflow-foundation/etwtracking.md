---
title: '&lt;etwTracking&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b989cd4a757b3da9371fdeb3a7e42ca00d7d28f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltetwtrackinggt"></a><span data-ttu-id="ff095-102">&lt;etwTracking&gt;</span><span class="sxs-lookup"><span data-stu-id="ff095-102">&lt;etwTracking&gt;</span></span>
<span data-ttu-id="ff095-103">允许服务，以利用 ETW 跟踪使用的服务行为<xref:System.Activities.Tracking.EtwTrackingParticipant>。</span><span class="sxs-lookup"><span data-stu-id="ff095-103">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="ff095-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ff095-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ff095-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="ff095-105">\<behaviors></span></span>  
<span data-ttu-id="ff095-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ff095-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ff095-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="ff095-107">\<behavior></span></span>  
<span data-ttu-id="ff095-108">\<etwTracking ></span><span class="sxs-lookup"><span data-stu-id="ff095-108">\<etwTracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff095-109">语法</span><span class="sxs-lookup"><span data-stu-id="ff095-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff095-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ff095-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ff095-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ff095-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff095-112">特性</span><span class="sxs-lookup"><span data-stu-id="ff095-112">Attributes</span></span>  
  
|<span data-ttu-id="ff095-113">特性</span><span class="sxs-lookup"><span data-stu-id="ff095-113">Attribute</span></span>|<span data-ttu-id="ff095-114">描述</span><span class="sxs-lookup"><span data-stu-id="ff095-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff095-115">profileName</span><span class="sxs-lookup"><span data-stu-id="ff095-115">profileName</span></span>|<span data-ttu-id="ff095-116">一个字符串，指定与此行为关联的跟踪配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ff095-116">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff095-117">子元素</span><span class="sxs-lookup"><span data-stu-id="ff095-117">Child Elements</span></span>  
 <span data-ttu-id="ff095-118">无。</span><span class="sxs-lookup"><span data-stu-id="ff095-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff095-119">父元素</span><span class="sxs-lookup"><span data-stu-id="ff095-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ff095-120">元素</span><span class="sxs-lookup"><span data-stu-id="ff095-120">Element</span></span>|<span data-ttu-id="ff095-121">描述</span><span class="sxs-lookup"><span data-stu-id="ff095-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff095-122">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ff095-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="ff095-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="ff095-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff095-124">备注</span><span class="sxs-lookup"><span data-stu-id="ff095-124">Remarks</span></span>  
 <span data-ttu-id="ff095-125">在添加到服务的行为配置后，此配置元素对工作流服务配置跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="ff095-125">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="ff095-126">跟踪参与者用于获取从工作流发出的跟踪数据并将其存储在不同的媒体中。</span><span class="sxs-lookup"><span data-stu-id="ff095-126">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="ff095-127">同样，也可以在跟踪参与者中执行对跟踪记录的任何后续处理。</span><span class="sxs-lookup"><span data-stu-id="ff095-127">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff095-128">示例</span><span class="sxs-lookup"><span data-stu-id="ff095-128">Example</span></span>  
 <span data-ttu-id="ff095-129">下面的配置示例演示在 Web.config 文件中配置的标准 ETW 跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="ff095-129">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="ff095-130">在中定义 ETW 跟踪参与者使用跟踪记录写入 ETW 提供程序 Id **\<诊断 >**部分。</span><span class="sxs-lookup"><span data-stu-id="ff095-130">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="ff095-131">跟踪参与者具有一个与其关联的配置文件，用来指定跟踪参与者已订阅的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="ff095-131">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="ff095-132">这定义由**profileName**属性**\<添加 >**元素。</span><span class="sxs-lookup"><span data-stu-id="ff095-132">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="ff095-133">这些定义后，跟踪参与者添加到 **\<etwTracking >**服务行为。</span><span class="sxs-lookup"><span data-stu-id="ff095-133">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="ff095-134">这会将所选跟踪参与者添加到工作流实例的扩展中，以便它们开始接收跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="ff095-134">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ff095-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff095-135">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>  
 [<span data-ttu-id="ff095-136">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="ff095-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ff095-137">跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="ff095-137">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
