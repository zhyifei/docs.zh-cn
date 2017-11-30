---
title: "执行属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab7c81f051e6e65509d232479fd9f4ebe00ac99d
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
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
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`