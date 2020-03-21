---
title: 如何：针对 WorkflowServiceHost 配置工作流的未经处理异常行为
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 69c6b1ce11d735181390a0c67df2f8dbea4f906c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185313"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>如何：针对 WorkflowServiceHost 配置工作流的未经处理异常行为
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> 行为可用于指定 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载的工作流中出现未经处理的异常时所采取的操作。 本主题演示如何在配置文件中配置此行为。  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>配置 WorkflowUnhandledExceptionBehavior  
  
1. 在<>`workflowUnhandledException``behavior``serviceBehaviors`元素中<>元素中添加<>元素，使用 该`action`属性指定在未处理异常发生时要执行的操作，如以下示例所示。  
  
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
    > 上面的配置示例使用的是简化配置。 有关详细信息，请参阅[简化配置](../../../../docs/framework/wcf/simplified-configuration.md)。  
  
     可在代码中配置该行为，如下面的示例所示。  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <>`action``workflowUnhandledException`元素的属性可以设置为以下值之一：  
  
     **放弃**  
     中止内存中的实例，而不影响保存的实例状态（即回滚到上一个保存点）。  
  
     **abandonAndSuspend**  
     中止内存中的实例并将保存的实例更新为挂起。  
  
     **取消**  
     为实例调用取消处理程序，然后在内存中完成该实例，此操作也有可能将实例从实例存储区中移除。  
  
     **终止**  
     在内存中完成实例并将其从实例存储区中移除。  
  
     有关 的详细信息<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>，请参阅[工作流服务主机扩展性](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)。  
  
## <a name="see-also"></a>另请参阅

- [工作流服务主机扩展性](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [工作流服务](../../../../docs/framework/wcf/feature-details/workflow-services.md)
