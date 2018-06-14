---
title: 执行属性
ms.date: 03/30/2017
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
ms.openlocfilehash: 201fe222de1cb2029696a1694ae97815db5f913d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513017"
---
# <a name="execution-properties"></a>执行属性
此示例演示如何在自定义活动中定义并使用执行属性。 在此示例中，执行属性可确定控制台的前景色。 示例工作流演示执行的各个逻辑路径（<xref:System.Activities.Statements.Parallel> 活动的分支）如何保留不同的控制台颜色，而不管活动的交错执行（跨 <xref:System.Activities.Statements.Parallel> 活动的分支）。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 ExecutionProperties.sln 示例解决方案。  
  
    > [!NOTE]
    >  由于必须在生成解决方案的同时生成使用的自定义活动，因此在生成解决方案前查看 ThreeColors.xaml 会显示错误。  
  
2.  生成和运行解决方案。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`