---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: 12589ab7c6cb65618a5f53a3e4be49d85a2ffbb7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358959"
---
# <a name="etwtracking"></a><span data-ttu-id="2eeb2-101">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="2eeb2-101">\<etwTracking></span></span>
<span data-ttu-id="2eeb2-102">一种服务行为，允许服务来利用 ETW 跟踪使用<xref:System.Activities.Tracking.EtwTrackingParticipant>。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="2eeb2-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2eeb2-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2eeb2-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2eeb2-104">\<behaviors></span></span>  
<span data-ttu-id="2eeb2-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2eeb2-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="2eeb2-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2eeb2-106">\<behavior></span></span>  
<span data-ttu-id="2eeb2-107">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="2eeb2-107">\<etwTracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eeb2-108">语法</span><span class="sxs-lookup"><span data-stu-id="2eeb2-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2eeb2-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2eeb2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2eeb2-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2eeb2-111">特性</span><span class="sxs-lookup"><span data-stu-id="2eeb2-111">Attributes</span></span>  
  
|<span data-ttu-id="2eeb2-112">特性</span><span class="sxs-lookup"><span data-stu-id="2eeb2-112">Attribute</span></span>|<span data-ttu-id="2eeb2-113">描述</span><span class="sxs-lookup"><span data-stu-id="2eeb2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2eeb2-114">profileName</span><span class="sxs-lookup"><span data-stu-id="2eeb2-114">profileName</span></span>|<span data-ttu-id="2eeb2-115">一个字符串，指定与此行为关联的跟踪配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-115">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2eeb2-116">子元素</span><span class="sxs-lookup"><span data-stu-id="2eeb2-116">Child Elements</span></span>  
 <span data-ttu-id="2eeb2-117">无。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2eeb2-118">父元素</span><span class="sxs-lookup"><span data-stu-id="2eeb2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2eeb2-119">元素</span><span class="sxs-lookup"><span data-stu-id="2eeb2-119">Element</span></span>|<span data-ttu-id="2eeb2-120">描述</span><span class="sxs-lookup"><span data-stu-id="2eeb2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2eeb2-121">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2eeb2-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="2eeb2-122">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-122">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2eeb2-123">备注</span><span class="sxs-lookup"><span data-stu-id="2eeb2-123">Remarks</span></span>  
 <span data-ttu-id="2eeb2-124">在添加到服务的行为配置后，此配置元素对工作流服务配置跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-124">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="2eeb2-125">跟踪参与者用于获取从工作流发出的跟踪数据并将其存储在不同的媒体中。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="2eeb2-126">同样，也可以在跟踪参与者中执行对跟踪记录的任何后续处理。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2eeb2-127">示例</span><span class="sxs-lookup"><span data-stu-id="2eeb2-127">Example</span></span>  
 <span data-ttu-id="2eeb2-128">下面的配置示例演示在 Web.config 文件中配置的标准 ETW 跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-128">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="2eeb2-129">中定义 ETW 跟踪参与者使用跟踪记录写入 ETW 的提供程序 Id **\<诊断 >** 部分。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-129">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="2eeb2-130">跟踪参与者具有一个与其关联的配置文件，用来指定跟踪参与者已订阅的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-130">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="2eeb2-131">这由 **profileName** 的属性 **\<添加>** 元素。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-131">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="2eeb2-132">这些定义后，跟踪参与者添加到 **\<etwTracking >** 服务行为。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-132">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="2eeb2-133">这会将所选跟踪参与者添加到工作流实例的扩展中，以便它们开始接收跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="2eeb2-133">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2eeb2-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="2eeb2-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="2eeb2-135">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="2eeb2-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2eeb2-136">跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="2eeb2-136">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
