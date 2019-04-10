---
title: 创建和运行工作流实例
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: f2bdfce0b311da6dd20aac5e0fe4f5fbcd14f68a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210088"
---
# <a name="creating-and-running-a-workflow-instance"></a>创建和运行工作流实例
此示例演示如何运行工作流实例。 它演示如何以同步方式和异步方式执行这一操作。  
  
## <a name="demonstrates"></a>演示  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## <a name="discussion"></a>讨论  
 此示例的第一部分使用 <xref:System.Activities.WorkflowInvoker.Invoke%2A>。 这是执行工作流的最基本方法。 使用 <xref:System.Activities.WorkflowInvoker.Invoke%2A> 执行的工作流以同步方式执行。  
  
 该示例的第二部分使用 <xref:System.Activities.WorkflowApplication> 类。 <xref:System.Activities.WorkflowApplication> 使你能够更好地控制每个实例，包括与正在运行的工作流进行交互，并以异步方式运行工作流的功能。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>请参阅

- [使用 WorkflowInvoker 和 WorkflowApplication](../using-workflowinvoker-and-workflowapplication.md)
