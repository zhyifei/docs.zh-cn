---
title: 带规则的 IfElse
ms.date: 03/30/2017
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
ms.openlocfilehash: 31906f04149a0ca7659201965ca565c7fa2af305
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483001"
---
# <a name="ifelse-with-rules"></a>带规则的 IfElse
此示例演示如何将规则条件用于 <xref:System.Workflow.Activities.IfElseActivity> 活动。  
  
 示例从宿主中传入一个 `OrderValue` 参数。 该参数的值用在 <xref:System.Workflow.Activities.IfElseActivity> 活动第一个分支上的规则条件中。 如果值小于 10000，将执行第一个分支，并<xref:System.Workflow.Activities.CodeActivity>中的第一个分支的活动将打印**获得经理批准**到控制台。 如果值大于 10000，<xref:System.Workflow.Activities.CodeActivity>第二个分支中的活动执行，并打印**获取副总裁批准**。  
  
### <a name="to-build-the-sample"></a>生成示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开解决方案。  
  
2.  按 Ctrl+Shift+B 生成解决方案。  
  
3.  按 Ctrl+F5 运行解决方案而不进行调试。  
  
### <a name="to-run-the-sample"></a>运行示例  
  
-   在 SDK 命令提示窗口中，运行 IfElseWithRules\bin\debug 文件夹（对于该示例的 Visual Basic 版本为 IfElseWithRules\bin 文件夹）中的 .exe 文件，该文件夹位于该示例的主文件夹下。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Workflow.Activities.Rules>  
 <xref:System.Workflow.Activities.IfElseActivity>  
 <xref:System.Workflow.Activities.CodeActivity>  
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>
