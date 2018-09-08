---
title: 与外部数据交换结合使用互操作
ms.date: 03/30/2017
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
ms.openlocfilehash: 534321e5b5568e0dd0988333dc98ccc18ff33df8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44135030"
---
# <a name="using-interop-with-external-data-exchange"></a>与外部数据交换结合使用互操作
<xref:System.Activities.Statements.Interop>活动可用于执行 Windows Workflow Foundation (WF) 中的活动[!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]并[!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)](WF3) 和工作流中的 Windows Workflow Foundation 中[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)](WF4)。 此示例演示如何通过使用 WF4 工作流服务中的 <xref:System.Workflow.Activities.ExternalDataExchangeService> 活动配置和运行 WF3 工作流，该工作流使用 <xref:System.Activities.Statements.Interop> 及对应的自定义活动进行方法调用和事件处理。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 ExternalDataExchange.sln 文件。  
  
2.  要生成此示例，按 Ctrl+Shift+B。  
  
3.  要运行此示例，按 F5。
