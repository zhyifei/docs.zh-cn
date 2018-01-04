---
title: "条件活动组"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7049f0ab787264893f334b8fe6aa0036e240a73f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="conditioned-activity-group"></a>条件活动组
此示例演示一个旅行预订应用程序。 <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) 有两个代码活动：Car 活动和 Airline 活动。 在 `SimpleCAGWorkflow` 构造函数中，已用所需旅行预订的类型填充了“travelNeedType”ArrayList 对象。 通过注释掉其中一个或全部两个 `travelNeeds.Add` 语句，将会相应地修改 CAG 行为。 Car 和 Airline 活动在它们的 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> 条件中都填充有 <xref:System.Workflow.Activities.CodeCondition>。 只有当 `travelNeeds` 集合具有 `TravelNeeds.Car` 项时，Car 活动才会执行，并且，只有当 `travelNeeds` 集合具有 `TravelNeeds.Airline` 项时，Airline 活动才会执行。  
  
 每个活动执行时都会从集合中移除对应的项。 默认的 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> 条件指定：当没有子项在执行或者准备好执行时（根据其 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> 条件），CAG 应退出。 在此示例中，这意味着 CAG 在 `travelNeeds` 集合为空时会退出。  
  
### <a name="to-build-the-sample"></a>生成示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开解决方案。  
  
2.  按 Ctrl+Shift+B 生成解决方案。  
  
3.  按 Ctrl+F5 运行解决方案而不进行调试。  
  
### <a name="to-run-the-sample"></a>运行示例  
  
-   在 SDK 命令提示窗口中，运行 SimpleCAG\bin\debug 文件夹（对于该示例的 Visual Basic 版本为 SimpleCAG\bin 文件夹）中的 .exe 文件，该文件夹位于该示例的主文件夹下。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
