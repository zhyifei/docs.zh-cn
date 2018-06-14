---
title: 使用 Send 的通道缓存
ms.date: 03/30/2017
ms.assetid: e69a2502-25cb-43bf-b8d2-95fbdecb41cb
ms.openlocfilehash: c26d81b9cd85ba75189fafddd82c3fb4673c7fae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514034"
---
# <a name="channel-caching-with-send"></a>使用 Send 的通道缓存
<xref:System.ServiceModel.Activities.SendMessageChannelCache> 使用户能够对 <xref:System.ServiceModel.Activities.Send> 和 <xref:System.ServiceModel.Activities.SendParametersContent> 活动使用不同级别的通道缓存。 默认情况下将启用实例级别的缓存，此示例将演示以下功能：  
  
1.  跨应用程序域共享 <xref:System.ServiceModel.Activities.SendMessageChannelCache>。  
  
2.  禁用通道缓存。  
  
3.  在 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 中的工作流实例之间共享 <xref:System.ServiceModel.Activities.WorkflowServiceHost>。  
  
## <a name="demonstrates"></a>演示  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 扩展、<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.ReceiveContent> 和 <xref:System.ServiceModel.Activities.SendReply> 活动。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中加载项目解决方案，然后生成项目。  
  
2.  运行在 \EchoWorkflowService\bin\debug 中生成的 EchoWorkflowService 应用程序。  
  
3.  运行在 \EchoWorkflowService\bin\debug 中生成的 EchoWorkflowClient 应用程序。  
  
4.  客户端对服务调用 Echo 操作，并输出结果。 输出结果后，按 Enter 退出客户端和服务。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ChannelCache`
