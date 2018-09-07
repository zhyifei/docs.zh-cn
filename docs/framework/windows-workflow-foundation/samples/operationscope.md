---
title: OperationScope
ms.date: 03/30/2017
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
ms.openlocfilehash: 562fd9c8ff964cb997012d49600bce73d4441465
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44075626"
---
# <a name="operationscope"></a>OperationScope
此示例演示如何使用消息传送活动（<xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply>），将现有的自定义活动作为工作流服务中的操作公开。 此示例包含一个名为 `OperationScope` 的新的自定义活动。 这样做的目的是，通过允许用户将其操作的主体作为自定义活动单独创作，然后使用 `OperationScope` 活动轻松地将这些活动作为服务操作公开，从而方便工作流服务的开发。 例如，对于一个采用两个 `Add` 参数并返回一个 `in` 参数的自定义 `out` 活动，可以通过将其拖放到 `Add` 中来将其作为工作流服务上的 `OperationScope` 操作公开。  
  
 范围用于检查作为其主体提供的活动。 任何未绑定的 `in` 参数都被认为是来自传入消息的输入。 所有 `out` 参数（无论它们是否已绑定）都被认为是后续回复消息中的输出。 公开的操作名称取自 `OperationScope` 活动的显示名称。 最终结果是，主体活动包装在 <xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply> 中，并且消息中的形参绑定到活动的实参。  
  
 此示例使用 HTTP 终结点公开一个工作流服务。 若要运行，必须添加合适的 URL ACL。 有关详细信息，请参阅[配置 HTTP 和 HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353)。 执行以下命令在提升的提示符添加适当的 Acl (确保你的域和用户名替换为 %域 %\\%username%)。  
  
 **netsh http add urlacl =http://+:8000/用户 = %域 %\\%username%**  
  
### <a name="to-run-the-sample"></a>运行示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 OperationScope.sln 解决方案。  
  
2.  右键单击解决方案资源管理器中的解决方案并选择设置多个启动项目**设置启动项目**。 添加“Scenario”和“Scenario_Client”（按此顺序）作为多个启动项目。  
  
3.  按 Ctrl+Shift+B 生成解决方案。  
  
    > [!WARNING]
    >  由于自定义活动 `OperationScope` 的原因，要求使用此步骤查看 BankService.xaml 工作流。  
  
4.  按 Ctrl+F5 运行应用程序。 Scenario_Client 控制台将提示您输入，而对应的输出将显示在 Scenario 控制台中。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`