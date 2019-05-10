---
title: 如何：使用 WorkflowServiceHost 配置空闲行为
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
ms.openlocfilehash: 5b2ebf6ddc5f275bd499a8abf7e68e019a1e0cef
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586677"
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a><span data-ttu-id="305f3-102">如何：使用 WorkflowServiceHost 配置空闲行为</span><span class="sxs-lookup"><span data-stu-id="305f3-102">How to: Configure Idle Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="305f3-103">当工作流遇到必须由某种外部刺激恢复的书签时（例如，当工作流实例正在等待使用 <xref:System.ServiceModel.Activities.Receive> 活动传递消息时），将转入空闲状态。</span><span class="sxs-lookup"><span data-stu-id="305f3-103">Workflows go idle when they encounter a bookmark that must be resumed by some external stimulus, for example when the workflow instance is waiting for a message to be delivered using a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="305f3-104"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> 行为允许您指定服务实例进入空闲状态与保留或卸载服务实例之间的时间。</span><span class="sxs-lookup"><span data-stu-id="305f3-104"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> is a behavior that allows you to specify the time between when a service instance goes idle and when the instance is persisted or unloaded.</span></span> <span data-ttu-id="305f3-105">它包含两个使您能够设置这些时间跨度的属性。</span><span class="sxs-lookup"><span data-stu-id="305f3-105">It contains two properties that enable you to set these time spans.</span></span> <span data-ttu-id="305f3-106"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> 指定工作流服务实例进入空闲状态与保留工作流服务实例之间的时间跨度。</span><span class="sxs-lookup"><span data-stu-id="305f3-106"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="305f3-107"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> 指定工作流服务实例进入空闲状态与卸载工作流服务实例之间的时间跨度，其中，卸载意味着将实例保留到实例存储区中并从内存中将其删除。</span><span class="sxs-lookup"><span data-stu-id="305f3-107"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is unloaded, where unload means persisting the instance to the instance store and removing it from memory.</span></span> <span data-ttu-id="305f3-108">本主题解释如何在配置文件中配置 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> 。</span><span class="sxs-lookup"><span data-stu-id="305f3-108">This topic explains how to configure the <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> in a configuration file.</span></span>  
  
### <a name="to-configure-workflowidlebehavior"></a><span data-ttu-id="305f3-109">配置 WorkflowIdleBehavior</span><span class="sxs-lookup"><span data-stu-id="305f3-109">To configure WorkflowIdleBehavior</span></span>  
  
1. <span data-ttu-id="305f3-110">添加 <`workflowIdle`> 元素为 <`behavior`> 元素中的 <`serviceBehaviors`> 元素，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="305f3-110">Add a <`workflowIdle`> element to the <`behavior`> element within the <`serviceBehaviors`> element as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="305f3-111">`timeToUnload` 特性指定工作流服务实例进入空闲状态与卸载工作流服务之间的时间段。</span><span class="sxs-lookup"><span data-stu-id="305f3-111">The `timeToUnload` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service is unloaded.</span></span> <span data-ttu-id="305f3-112">`timeToPersist` 特性指定工作流服务实例进入空闲状态与保存该实例之间的时间段。</span><span class="sxs-lookup"><span data-stu-id="305f3-112">The `timeToPersist` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="305f3-113">`timeToUnload` 默认值为 1 分钟。</span><span class="sxs-lookup"><span data-stu-id="305f3-113">The default value for `timeToUnload` is 1 minute.</span></span> <span data-ttu-id="305f3-114">`timeToPersist` 的默认值为 <xref:System.TimeSpan.MaxValue>。</span><span class="sxs-lookup"><span data-stu-id="305f3-114">The default value for `timeToPersist` is <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="305f3-115">如果要在内存中保留空闲实例，但是为实现可靠性而保持这些实例，请设置值以使 `timeToPersist` < `timeToUnload`。</span><span class="sxs-lookup"><span data-stu-id="305f3-115">If you want to keep idle instances in memory but persist them for robustness, set values so that `timeToPersist` < `timeToUnload`.</span></span> <span data-ttu-id="305f3-116">如果要防止卸载空闲实例，请将 `timeToUnload` 设置为 <xref:System.TimeSpan.MaxValue>。</span><span class="sxs-lookup"><span data-stu-id="305f3-116">If you want to prevent idle instances from being unloaded, set `timeToUnload` to <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="305f3-117">有关详细信息<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>，请参阅[Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="305f3-117">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="305f3-118">上面的配置示例使用的是简化配置。</span><span class="sxs-lookup"><span data-stu-id="305f3-118">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="305f3-119">有关详细信息，请参阅[Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="305f3-119">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
### <a name="to-change-idle-behavior-in-code"></a><span data-ttu-id="305f3-120">在代码中更改空闲行为</span><span class="sxs-lookup"><span data-stu-id="305f3-120">To change idle behavior in code</span></span>  
  
- <span data-ttu-id="305f3-121">下面的示例以编程方式更改保持和卸载之前的等待时间。</span><span class="sxs-lookup"><span data-stu-id="305f3-121">The following example changes the time to wait before persisting and unloading programmatically.</span></span>  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="305f3-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="305f3-122">See also</span></span>

- [<span data-ttu-id="305f3-123">工作流服务主机扩展性</span><span class="sxs-lookup"><span data-stu-id="305f3-123">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [<span data-ttu-id="305f3-124">简化配置</span><span class="sxs-lookup"><span data-stu-id="305f3-124">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
- [<span data-ttu-id="305f3-125">工作流服务</span><span class="sxs-lookup"><span data-stu-id="305f3-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
