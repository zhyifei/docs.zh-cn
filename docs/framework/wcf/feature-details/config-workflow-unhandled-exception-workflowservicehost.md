---
title: 如何：配置工作流未经处理的异常行为使用 WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 9a13bb9390e891295491722898bd780bc1cac587
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636152"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="2cf68-102">如何：配置工作流未经处理的异常行为使用 WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="2cf68-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="2cf68-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> 行为可用于指定 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载的工作流中出现未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="2cf68-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="2cf68-104">本主题演示如何在配置文件中配置此行为。</span><span class="sxs-lookup"><span data-stu-id="2cf68-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="2cf68-105">配置 WorkflowUnhandledExceptionBehavior</span><span class="sxs-lookup"><span data-stu-id="2cf68-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1.  <span data-ttu-id="2cf68-106">添加 <`workflowUnhandledException`> 元素中的 <`behavior`> 元素中的 <`serviceBehaviors`> 元素中，使用`action`特性以指定要执行下面的示例中所示发生未处理的异常时的操作。</span><span class="sxs-lookup"><span data-stu-id="2cf68-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
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
    >  <span data-ttu-id="2cf68-107">上面的配置示例使用的是简化配置。</span><span class="sxs-lookup"><span data-stu-id="2cf68-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="2cf68-108">有关详细信息，请参阅[Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="2cf68-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="2cf68-109">可在代码中配置该行为，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="2cf68-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="2cf68-110">`action`属性的 <`workflowUnhandledException`> 元素可以设置为以下值之一：</span><span class="sxs-lookup"><span data-stu-id="2cf68-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="2cf68-111">**abandon**</span><span class="sxs-lookup"><span data-stu-id="2cf68-111">**abandon**</span></span>  
     <span data-ttu-id="2cf68-112">中止内存中的实例，而不影响保存的实例状态（即回滚到上一个保存点）。</span><span class="sxs-lookup"><span data-stu-id="2cf68-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="2cf68-113">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="2cf68-113">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="2cf68-114">中止内存中的实例并将保存的实例更新为挂起。</span><span class="sxs-lookup"><span data-stu-id="2cf68-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="2cf68-115">**cancel**</span><span class="sxs-lookup"><span data-stu-id="2cf68-115">**cancel**</span></span>  
     <span data-ttu-id="2cf68-116">为实例调用取消处理程序，然后在内存中完成该实例，此操作也有可能将实例从实例存储区中移除。</span><span class="sxs-lookup"><span data-stu-id="2cf68-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="2cf68-117">**terminate**</span><span class="sxs-lookup"><span data-stu-id="2cf68-117">**terminate**</span></span>  
     <span data-ttu-id="2cf68-118">在内存中完成实例并将其从实例存储区中移除。</span><span class="sxs-lookup"><span data-stu-id="2cf68-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="2cf68-119">有关详细信息<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>，请参阅[Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)。</span><span class="sxs-lookup"><span data-stu-id="2cf68-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf68-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2cf68-120">See also</span></span>
- [<span data-ttu-id="2cf68-121">工作流服务主机扩展性</span><span class="sxs-lookup"><span data-stu-id="2cf68-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [<span data-ttu-id="2cf68-122">工作流服务</span><span class="sxs-lookup"><span data-stu-id="2cf68-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
