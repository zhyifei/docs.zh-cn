---
title: 活动库
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: fae2a94b5e5e776625aa7f26700980640b66afd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142896"
---
# <a name="activity-library"></a>活动库
本节包含演示 Windows 工作流基础 （WF） 中高级自定义活动的示例。  
  
## <a name="in-this-section"></a>本节内容

 [SendMail 自定义活动](sendmail-custom-activity.md)  
 演示如何创建派生自 <xref:System.Activities.AsyncCodeActivity> 的自定义活动，以使用 SMTP 发送邮件供在工作流应用程序内使用。  
  
 [限制并行 ForEach](throttled-parallel-foreach.md)  
 演示 `ThrottleParallelForEach` 活动与 <xref:System.Activities.Statements.ParallelForEach%601> 活动的相似之处，二者的不同之处在于，前者允许设置一个并发因子来限制要同时执行的分支的数量。
  
 [数据库访问活动](database-access-activities.md)  
 演示如何创建允许访问数据库以检索或修改信息并使用[ADO.NET](../../data/adonet/index.md)访问数据库的活动。  
  
 [.NET Framework 4.5 中的外部化策略活动](externalized-policy-activity-in-net-framework-4-5.md)  
 演示外化策略4活动如何允许使用 WF 3.5 中随附的规则引擎直接在 （WF 4.5） 中的 Windows 工作流基础 （WF <xref:System.Workflow.Activities.Rules.RuleSet> 4.5） 中的[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]Windows 工作流基础中执行现有的 Windows 工作流基础。
  
 [非泛型 ForEach](non-generic-foreach.md)  
 演示了如何创建非泛型版本的 <xref:System.Activities.Statements.ForEach%601> 活动。  
  
 [非泛型 ParallelForEach](non-generic-parallelforeach.md)  
 演示了如何创建非泛型版本的 <xref:System.Activities.Statements.ParallelForEach%601> 活动。  
  
 [获取 WorkflowInstanceId](get-workflowinstanceid.md)  
 演示如何使用自定义活动 `GetWorkflowInstanceId` 返回工作流实例 ID。
