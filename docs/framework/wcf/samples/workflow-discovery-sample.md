---
title: "工作流发现示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bba400a4476ffd2589af1d5e7d3e0ca5661102f3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="workflow-discovery-sample"></a>工作流发现示例
此示例演示如何使工作流服务可发现，以及如何编写搜索特定服务的自定义代码活动。  
  
## <a name="demonstrates"></a>演示  
 发现查找活动和工作流使用情况  
  
## <a name="discussion"></a>讨论  
 在示例的第一部分中，使用配置使工作流服务可发现。 使用配置还可以正确地通过自定义元数据（如范围）应用服务。 在客户端中，该示例使用了一个自定义代码活动，该活动使用发现来搜索与特定协定匹配的服务。 该代码活动输出供发送活动在以后使用的 URI。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  此示例使用 HTTP 终结点，其必须具有正确的 URL Acl 运行 (请参阅[配置 HTTP 和 HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353)有关详细信息)。 在具有提升权限的命令提示符下执行下面的命令应添加相应的 ACL。 如果 shell 无法理解变量格式，请使用你的域和用户名替换以下自变量。  
  
     **netsh http 添加 urlacl url = http: / / +: 8000 / 用户 = %域 %\\%username%**  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
