---
title: 将变量用于 .NET Framework 3.5 规则集
ms.date: 03/30/2017
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
ms.openlocfilehash: 64d47564076e19e152e30b6ab0cb3900ce53cfa1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512849"
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a>将变量用于 .NET Framework 3.5 规则集
此示例演示如何创建一个工作流，该工作流使用 <xref:System.Activities.Statements.Interop> 活动来集成在 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 中编写并应用了策略和规则的自定义活动。 该工作流将数据传递给此自定义活动，采用的方式是将变量绑定到此自定义活动公开的依赖项属性。  
  
## <a name="sample-walkthrough"></a>示例演练  
  
#### <a name="to-examine-travelrulelibrary"></a>检查 TravelRuleLibrary  
  
1.  使用 Visual Studio，打开 InteropWith35RuleSet.sln 解决方案文件。  
  
2.  在工作流设计器中打开 TravelRuleSet.cs。  
  
     这将显示包含 <xref:System.Workflow.Activities.PolicyActivity> 的自定义顺序活动。  
  
3.  双击 DiscountPolicy 策略活动以检查规则。  
  
     规则编辑器将弹出，其中显示了规则。  
  
4.  右键单击`DiscountPolicy`，然后选择**查看代码**选项以检查活动的 C# 代码旁边的代码。  
  
     观察 `DiscountLevel` 的依赖项属性设置。 这等效于 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] 中的参数。 有关参数的详细信息，请参阅[变量和自变量](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md)。  
  
## <a name="interopwith35ruleset"></a>InteropWith35RuleSet  
 这是一个顺序工作流项目，该项目使用 <xref:System.Activities.Statements.Interop> 活动与 `TravelRuleLibrary` 项目中创建的自定义规则集集成。 变量是在顶级 <xref:System.Activities.Statements.Sequence> 活动上创建的。 <xref:System.Activities.Statements.Interop> 活动用于与 `TravelRuleSet` 活动进行的集成。 在 <xref:System.Activities.Statements.Sequence> 上声明的变量用于绑定到依赖项属性。  
  
## <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，打开 InteropWith35RuleSet.sln 解决方案文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  若要运行解决方案，请按 Ctrl+F5。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`