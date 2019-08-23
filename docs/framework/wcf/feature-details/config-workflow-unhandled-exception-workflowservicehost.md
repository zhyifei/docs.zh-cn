---
title: 如何：使用 WorkflowServiceHost 配置工作流未经处理的异常行为
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: aec2fd80e10ae1959b29c0883d51c4045517d792
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957263"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="36cf7-102">如何：使用 WorkflowServiceHost 配置工作流未经处理的异常行为</span><span class="sxs-lookup"><span data-stu-id="36cf7-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="36cf7-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> 行为可用于指定 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载的工作流中出现未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="36cf7-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="36cf7-104">本主题演示如何在配置文件中配置此行为。</span><span class="sxs-lookup"><span data-stu-id="36cf7-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="36cf7-105">配置 WorkflowUnhandledExceptionBehavior</span><span class="sxs-lookup"><span data-stu-id="36cf7-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1. <span data-ttu-id="36cf7-106">`workflowUnhandledException`在 <`behavior` `action` > 元素内的 < > 元素中添加一个 < > 元素, 使用特性指定发生未经处理的异常时要执行的操作, 如下面的示例中所示。`serviceBehaviors`</span><span class="sxs-lookup"><span data-stu-id="36cf7-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="36cf7-107">上面的配置示例使用的是简化配置。</span><span class="sxs-lookup"><span data-stu-id="36cf7-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="36cf7-108">有关详细信息, 请参阅[简化配置](../../../../docs/framework/wcf/simplified-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="36cf7-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="36cf7-109">可在代码中配置该行为，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="36cf7-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="36cf7-110">可以将 <`workflowUnhandledException`> 元素的属性设置为以下值之一:`action`</span><span class="sxs-lookup"><span data-stu-id="36cf7-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="36cf7-111">**终止**</span><span class="sxs-lookup"><span data-stu-id="36cf7-111">**abandon**</span></span>  
     <span data-ttu-id="36cf7-112">中止内存中的实例，而不影响保存的实例状态（即回滚到上一个保存点）。</span><span class="sxs-lookup"><span data-stu-id="36cf7-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="36cf7-113">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="36cf7-113">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="36cf7-114">中止内存中的实例并将保存的实例更新为挂起。</span><span class="sxs-lookup"><span data-stu-id="36cf7-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="36cf7-115">**取消**</span><span class="sxs-lookup"><span data-stu-id="36cf7-115">**cancel**</span></span>  
     <span data-ttu-id="36cf7-116">为实例调用取消处理程序，然后在内存中完成该实例，此操作也有可能将实例从实例存储区中移除。</span><span class="sxs-lookup"><span data-stu-id="36cf7-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="36cf7-117">**terminate**</span><span class="sxs-lookup"><span data-stu-id="36cf7-117">**terminate**</span></span>  
     <span data-ttu-id="36cf7-118">在内存中完成实例并将其从实例存储区中移除。</span><span class="sxs-lookup"><span data-stu-id="36cf7-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="36cf7-119">有关的详细信息<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, 请参阅[工作流服务主机扩展性](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)。</span><span class="sxs-lookup"><span data-stu-id="36cf7-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36cf7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="36cf7-120">See also</span></span>

- [<span data-ttu-id="36cf7-121">工作流服务主机扩展性</span><span class="sxs-lookup"><span data-stu-id="36cf7-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [<span data-ttu-id="36cf7-122">工作流服务</span><span class="sxs-lookup"><span data-stu-id="36cf7-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
