---
title: 在.NET Framework 4.5 工作流中使用.NET Framework 3.0 或.NET Framework 3.5 活动
ms.date: 03/30/2017
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
ms.openlocfilehash: ab2e93918617bd1ca21fb32878d446db0dd2ef16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514894"
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a>在.NET Framework 4.5 工作流中使用.NET Framework 3.0 或.NET Framework 3.5 活动
<xref:System.Activities.Statements.Interop>活动允许您运行中的某个.NET Framework 3.0 Windows Workflow Foundation (WF) 活动[!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]工作流。 此示例演示如何使用 <xref:System.Activities.Statements.Interop> 活动来将字符串作为参数传递到自定义 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 活动。  
  
## <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 SimpleInterop.sln 解决方案文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  若要运行解决方案，请按 Ctrl+F5。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a>请参阅
