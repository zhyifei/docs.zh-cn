---
title: 使用过程性活动
ms.date: 03/30/2017
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
ms.openlocfilehash: bd83f1a0fa9f3af7c22cee73fbc4f984a9ebf53c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43804736"
---
# <a name="using-procedural-activities"></a>使用过程性活动
此示例使用 <xref:System.Activities.Statements.Sequence>、<xref:System.Activities.Statements.Assign>、<xref:System.Activities.Statements.If>、<xref:System.Activities.Statements.While>、<xref:System.Activities.Statements.Switch%601>、<xref:System.Activities.Statements.TryCatch> 和 <xref:System.Activities.Statements.WriteLine> 活动实现猜谜游戏。 猜谜游戏将选择一个随机数，然后玩家必须猜出该数字。 当玩家所猜测的数字错误时，工作流会给出一个提示，指示所猜的数字是过大还是过小。 如果玩家在 7 次之内猜出该数字，则将为其显示特定的祝贺语。  
  
## <a name="custom-activities-in-this-sample"></a>此示例中的自定义活动  
  
### <a name="readline"></a>ReadLine  
 从控制台读取一行文本。 此活动派生自 <xref:System.Activities.NativeActivity> 类，并创建一个书签，控制台应用程序在读取行时将恢复该书签。  
  
### <a name="promptint"></a>PromptInt  
 提示用户键入一个数字，然后从控制台窗口读取该数字。 此活动派生自 <xref:System.Activities.Activity%601> 并使用 <xref:System.Activities.Statements.WriteLine> 和 `ReadLine` 活动。  
  
##### <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，打开 GuessingGame.sln 解决方案文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  若要运行解决方案，请按 Ctrl+F5。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`