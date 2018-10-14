---
title: 活动库
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 7e8777d0068e6cca9c9324a6fd2668e6ff9e9da7
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123119"
---
# <a name="activity-library"></a>活动库
本节包含演示高级自定义活动在 Windows Workflow Foundation (WF) 的示例。  
  
## <a name="in-this-section"></a>本节内容

 [SendMail 自定义活动](../../../../docs/framework/windows-workflow-foundation/samples/sendmail-custom-activity.md)  
 演示如何创建派生自 <xref:System.Activities.AsyncCodeActivity> 的自定义活动，以使用 SMTP 发送邮件供在工作流应用程序内使用。  
  
 [限制并行 ForEach](../../../../docs/framework/windows-workflow-foundation/samples/throttled-parallel-foreach.md)  
 演示 `ThrottleParallelForEach` 活动与 <xref:System.Activities.Statements.ParallelForEach%601> 活动的相似之处，二者的不同之处在于，前者允许设置一个并发因子来限制要同时执行的分支的数量。
  
 [数据库访问活动](../../../../docs/framework/windows-workflow-foundation/samples/database-access-activities.md)  
 演示如何创建可以访问数据库以检索或修改信息并使用活动[ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081)来访问数据库。  
  
 [.NET Framework 4.5 中的外部化策略活动](../../../../docs/framework/windows-workflow-foundation/samples/externalized-policy-activity-in-net-framework-4-5.md)  
 演示 ExternalizedPolicy4 活动如何允许执行中的现有 Windows Workflow Foundation [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5)<xref:System.Workflow.Activities.Rules.RuleSet>中的 Windows Workflow Foundation 中的对象[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)](WF 4.5) 直接通过使用规则引擎，它是在 WF 3.5 中提供。 
  
 [非泛型 ForEach](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-foreach.md)  
 演示了如何创建非泛型版本的 <xref:System.Activities.Statements.ForEach%601> 活动。  
  
 [非泛型 ParallelForEach](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-parallelforeach.md)  
 演示了如何创建非泛型版本的 <xref:System.Activities.Statements.ParallelForEach%601> 活动。  
  
 [获取 WorkflowInstanceId](../../../../docs/framework/windows-workflow-foundation/samples/get-workflowinstanceid.md)  
 演示如何使用自定义活动 `GetWorkflowInstanceId` 返回工作流实例 ID。
