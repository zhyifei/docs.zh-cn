---
title: "与外部数据交换结合使用互操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b777cab4caf5b2b02c66e8378a7efce265157df0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-interop-with-external-data-exchange"></a>与外部数据交换结合使用互操作
可使用 <xref:System.Activities.Statements.Interop> 活动从 [!INCLUDE[wf](../../../../includes/wf-md.md)] 和 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] (WF3) 中的 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 执行活动以及在 [!INCLUDE[wf2](../../../../includes/wf2-md.md)] (WF4) 中的 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 内执行工作流。 此示例演示如何通过使用 WF4 工作流服务中的 <xref:System.Workflow.Activities.ExternalDataExchangeService> 活动配置和运行 WF3 工作流，该工作流使用 <xref:System.Activities.Statements.Interop> 及对应的自定义活动进行方法调用和事件处理。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 ExternalDataExchange.sln 文件。  
  
2.  要生成此示例，按 Ctrl+Shift+B。  
  
3.  要运行此示例，按 F5。
