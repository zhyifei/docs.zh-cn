---
title: 基本活动组合
ms.date: 03/30/2017
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
ms.openlocfilehash: ade8187ca44a8182b55cf0f01e5bfe5a9a747255
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518371"
---
# <a name="basic-activity-composition"></a>基本活动组合
此示例演示如何编写自定义活动和系统提供的活动来生成更多自定义活动。  
  
 使用 Survey 活动的工作流安排包含一系列问题的调查，然后输出接收到的响应。  
  
## <a name="sample-details"></a>示例详细信息  
 此示例使用三个自定义活动。 `ReadLine` 是一个简单<xref:System.Activities.NativeActivity>\<字符串 > 这将创建<xref:System.Activities.Bookmark>时安排，，然后设置`Return`<xref:System.Activities.OutArgument%601>使用的值为<xref:System.Activities.Bookmark>恢复。 `Prompt` 是<xref:System.Activities.Activity%601>\<字符串 > 采用<xref:System.Activities.InArgument%601>< 字符串\>名为`Text`，并返回响应中的用户`Result` <xref:System.Activities.OutArgument%601>\<字符串 >。 `Prompt` 活动使用作为 .NET Framework 的一部分提供的 <xref:System.Activities.Statements.Sequence> 和 <xref:System.Activities.Statements.WriteLine> 活动，并且该活动还集成了自定义 `ReadLine` 活动以获取用户输入。 最后一个自定义活动为 `Survey` 活动。 它是<xref:System.Activities.Activity>< ICollection\<字符串 >>。  此活动接受<xref:System.Activities.InArgument%601>< IEnumerable < 字符串\>> 命名`Questions`，并填充`Result`out 自变量的响应。 `Survey` 活动使用 .NET Framework 中的 <xref:System.Activities.Statements.ForEach%601>、<xref:System.Activities.Statements.Sequence> 和 <xref:System.Activities.Statements.AddToCollection%601>，并使用 `Prompt` 活动询问调查问题并获取响应。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  打开**BasicActivityComposition.sln**示例解决方案中的[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。  
  
2.  生成和运行解决方案。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`