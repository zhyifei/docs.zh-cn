---
title: 使用 FlowChart 与 Pick 的组合的 StateMachine 方案
ms.date: 03/30/2017
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
ms.openlocfilehash: b0f8e884a8a6c62c4e7edaf5cc9727bf7bfe8603
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44195674"
---
# <a name="statemachine-scenario-using-a-combination-of-flowchart-and-pick"></a>使用 FlowChart 与 Pick 的组合的 StateMachine 方案
此示例演示如何使用 <xref:System.Activities.Statements.Flowchart> 和 <xref:System.Activities.Statements.Pick> 活动的组合实现一个简单的秒表方案。 它使用 Pick 活动中的 Receive 和 Send 来侦听秒表事件。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到 （下载页） 以下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="sample-details"></a>示例详细信息  
 下表列出了此示例中的项目。  
  
|项目名称|描述|  
|-|-|  
|StopWatchService|此项目包含秒表示例的状态计算机的实现，其中使用了 <xref:System.Activities.Statements.Flowchart> 和 <xref:System.Activities.Statements.Pick> 活动的组合。<br /><br /> <xref:System.Activities.Statements.Pick> 活动在 <xref:System.Activities.Statements.PickBranch> 属性中具有 3 条 <xref:System.Activities.Statements.Pick.Branches%2A> 语句，分别用于侦听 `GetStart`、`GetStop` 和 `GetOff` 事件。 根据传入的事件，这三个分支中的一个分支的触发器将会激活并触发对应的 <xref:System.Activities.Statements.PickBranch.Action%2A>。 在 <xref:System.Activities.Statements.PickBranch.Action%2A> 属性中，有一条用于计算转换是否为合法转换的 <xref:System.Activities.Statements.Switch%601> 语句，如果它是合法的转换，则将 `currentState` 属性更新为正在转换状态并将其发送到客户端。<br /><br /> <xref:System.Activities.Statements.FlowDecision> 末尾的 <xref:System.Activities.Statements.Flowchart> 活动计算 `currentState` 属性来确定此状态是否为最终状态。 如果它是最终状态，则工作流结束；否则，将控制权回送到 <xref:System.Activities.Statements.Pick> 活动的开始位置，工作流在此处等待更多秒表事件。|  
|StopWatchClient|这是一个简单的顺序工作流控制台应用程序，它用简单的 Send 或 Receive 活动组合发送各种秒表事件。|  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 StateMachineWithPick.sln 解决方案文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  启动从 StopWatchService.exe[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]以管理员身份通过右键单击.exe 文件并选择**以管理员身份运行**。  
  
    1.  导航到 StateMachineWithPick\CS\StopWatchService\bin\Debug 文件夹。  
  
    2.  右击 StopWatchService.exe 文件，然后选择**以管理员身份运行**。  
  
4.  从 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中启动 StopWatchClient 客户端应用程序。  
  
    1.  在中**解决方案资源管理器**，选择**StopWatchClient**项目，然后右键单击**设为启动项目**。  
  
    2.  若要运行解决方案，请按 Ctrl+F5。  
  
5.  切换回 StopWatchService.exe 的控制台窗口以查看状态转换。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`