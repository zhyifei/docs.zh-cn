---
title: "基本活动组合"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8eb909ce50c5faebf48339b07e8565fcd7afc718
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="basic-activity-composition"></a>基本活动组合
此示例演示如何编写自定义活动和系统提供的活动来生成更多自定义活动。  
  
 使用 Survey 活动的工作流安排包含一系列问题的调查，然后输出接收到的响应。  
  
## <a name="sample-details"></a>示例详细信息  
 此示例使用三个自定义活动。 `ReadLine`是一个简单<xref:System.Activities.NativeActivity>\<字符串 > 创建<xref:System.Activities.Bookmark>时计划，并将`Return`<xref:System.Activities.OutArgument%601>为与其值<xref:System.Activities.Bookmark>恢复。 `Prompt`是<xref:System.Activities.Activity%601>\<字符串 > 采用<xref:System.Activities.InArgument%601>< 字符串\>名为`Text`，并返回响应中的用户`Result` <xref:System.Activities.OutArgument%601>\<字符串 >。 `Prompt` 活动使用作为 .NET Framework 的一部分提供的 <xref:System.Activities.Statements.Sequence> 和 <xref:System.Activities.Statements.WriteLine> 活动，并且该活动还集成了自定义 `ReadLine` 活动以获取用户输入。 最后一个自定义活动为 `Survey` 活动。 它是<xref:System.Activities.Activity>< ICollection\<字符串 >>。  此活动接受<xref:System.Activities.InArgument%601>< IEnumerable < 字符串\>> 名为`Questions`并填充`Result`out 使用响应的自变量。 `Survey` 活动使用 .NET Framework 中的 <xref:System.Activities.Statements.ForEach%601>、<xref:System.Activities.Statements.Sequence> 和 <xref:System.Activities.Statements.AddToCollection%601>，并使用 `Prompt` 活动询问调查问题并获取响应。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  打开**BasicActivityComposition.sln**示例中的解决方案[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。  
  
2.  生成和运行解决方案。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`