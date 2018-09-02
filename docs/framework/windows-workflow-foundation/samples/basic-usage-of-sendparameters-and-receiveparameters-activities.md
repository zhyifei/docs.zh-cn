---
title: SendParameters 和 ReceiveParameters 活动的基本用法
ms.date: 03/30/2017
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
ms.openlocfilehash: c13999ad1571a6413e30e801b6c642000f8e4654
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467690"
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a>SendParameters 和 ReceiveParameters 活动的基本用法
此示例演示如何使用 <xref:System.ServiceModel.Activities.SendParametersContent> 和 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 活动。 此服务公开了一个操作，该操作获取一个字符串参数并将输入回显到客户端。 此示例演示如何设置这些消息传递活动的参数。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a>使用此示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中加载项目解决方案，然后生成项目。  
  
2.  首先运行 [解决方案基目录]\EchoWorkflowService\bin\debug 中生成的 EchoWorkflowService 应用程序。  
  
3.  然后运行 [解决方案基目录]\EchoWorkflowClient\bin\debug 中生成的 EchoWorkflowClient 应用程序。  
  
4.  客户端对服务调用 Echo 操作，并输出结果。 完成后，请按 Enter 退出客户端，然后退出服务。