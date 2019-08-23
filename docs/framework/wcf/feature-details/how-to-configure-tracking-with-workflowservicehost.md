---
title: 如何：使用 WorkflowServiceHost 配置跟踪
ms.date: 03/30/2017
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
ms.openlocfilehash: 5781878270272f5ef894c68dc23b9433029e1d41
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968495"
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a><span data-ttu-id="a9b75-102">如何：使用 WorkflowServiceHost 配置跟踪</span><span class="sxs-lookup"><span data-stu-id="a9b75-102">How to: Configure Tracking with WorkflowServiceHost</span></span>
<span data-ttu-id="a9b75-103">本主题说明如何为 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 中承载的 <xref:System.ServiceModel.Activities.WorkflowServiceHost>工作流配置跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9b75-103">This topic explains how to configure tracking for a [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="a9b75-104">可以通过指定服务行为使用 Web.config 文件进行配置。</span><span class="sxs-lookup"><span data-stu-id="a9b75-104">It is configured through a Web.config file by specifying a service behavior.</span></span>  
  
### <a name="configure-tracking-in-configuration"></a><span data-ttu-id="a9b75-105">在配置中配置跟踪</span><span class="sxs-lookup"><span data-stu-id="a9b75-105">Configure Tracking in Configuration</span></span>  
  
1. <span data-ttu-id="a9b75-106">在配置文件中`behavior`使用<>元素添加,如下面的示例中所示。<xref:System.Activities.Tracking.EtwTrackingParticipant></span><span class="sxs-lookup"><span data-stu-id="a9b75-106">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>              
       </serviceBehaviors>  
    <behaviors>  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="a9b75-107">上面的配置示例使用的是简化配置。</span><span class="sxs-lookup"><span data-stu-id="a9b75-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="a9b75-108">有关详细信息, 请参阅[简化配置](../../../../docs/framework/wcf/simplified-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="a9b75-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="a9b75-109">上面的配置示例添加一个 <xref:System.Activities.Tracking.EtwTrackingParticipant>，并指定一个跟踪配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="a9b75-109">The preceding configuration sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="a9b75-110">跟踪配置文件是在 <`trackingProfile``tracking`> 元素内的 < > 元素中创建的。</span><span class="sxs-lookup"><span data-stu-id="a9b75-110">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element.</span></span> <span data-ttu-id="a9b75-111">跟踪配置文件包含跟踪查询，这些查询允许跟踪参与者订阅工作流实例的状态在运行时发生更改时发出的工作流事件。</span><span class="sxs-lookup"><span data-stu-id="a9b75-111">The tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="a9b75-112">下面的示例演示如何创建跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="a9b75-112">The following example shows how to create a tracking profile.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <tracking>   
         <trackingProfile name="Sample Tracking Profile">  
            <workflow activityDefinitionId="*">  
               <workflowInstanceQueries>  
                 <workflowInstanceQuery>  
                    <states>  
                       <state name="Started"/>  
                       <state name="Completed"/>  
                    </states>  
                </workflowInstanceQuery>  
             </workflowInstanceQueries>  
           </workflow>  
         </trackingProfile>   
       </tracking>  
    </system.serviceModel>  
    ```  
  
     <span data-ttu-id="a9b75-113">有关跟踪配置文件的详细信息, 请参阅[跟踪配置文件](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="a9b75-113">For more information about tracking profiles, see [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="a9b75-114">有关常规跟踪的详细信息, 请参阅[工作流跟踪和跟踪](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)。</span><span class="sxs-lookup"><span data-stu-id="a9b75-114">For more information about tracking in general, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
### <a name="configure-tracking-in-code"></a><span data-ttu-id="a9b75-115">在代码中配置跟踪</span><span class="sxs-lookup"><span data-stu-id="a9b75-115">Configure Tracking in Code</span></span>  
  
1. <span data-ttu-id="a9b75-116">在代码中使用 <xref:System.Activities.Tracking.EtwTrackingParticipant> 行为添加 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a9b75-116">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> behavior in code, as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     <span data-ttu-id="a9b75-117">上面的代码示例添加一个 <xref:System.Activities.Tracking.EtwTrackingParticipant>，并指定一个跟踪配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="a9b75-117">The preceding code sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="a9b75-118">跟踪配置文件是在 <`trackingProfile``tracking`> 元素内的 < > 元素中创建的, 如上一节所示。</span><span class="sxs-lookup"><span data-stu-id="a9b75-118">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element as shown in the previous section.</span></span>  
  
     <span data-ttu-id="a9b75-119">有关跟踪配置文件的详细信息, 请参阅[跟踪配置文件](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="a9b75-119">For more information about tracking profiles, see [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="a9b75-120">有关常规跟踪的详细信息, 请参阅[工作流跟踪和跟踪](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)。</span><span class="sxs-lookup"><span data-stu-id="a9b75-120">For more information about tracking in general, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span> <span data-ttu-id="a9b75-121">有关以编程方式配置跟踪的示例, 请参阅为[工作流配置跟踪](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="a9b75-121">For an example of configuring tracking programmatically see [Configuring Tracking for a Workflow](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9b75-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9b75-122">See also</span></span>

- [<span data-ttu-id="a9b75-123">WCF 服务的简化配置</span><span class="sxs-lookup"><span data-stu-id="a9b75-123">Simplified Configuration for WCF Services</span></span>](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)
- [<span data-ttu-id="a9b75-124">工作流服务</span><span class="sxs-lookup"><span data-stu-id="a9b75-124">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="a9b75-125">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="a9b75-125">Tracking Profiles</span></span>](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
