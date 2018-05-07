---
title: CommentOut 活动
ms.date: 03/30/2017
ms.assetid: 340204c3-f827-45fb-870e-55e2ac457ca5
ms.openlocfilehash: 7847f4e1d77c2927a27be6b83f4016a22e4e3b32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="commentout-activity"></a>CommentOut 活动
此示例演示如何编写一个自定义活动，该活动从执行路径中移除其他活动，从而有效注释掉这些活动。  
  
## <a name="the-commentout-activity"></a>CommentOut 活动  
 为了实现其目标，CommentOut 活动从 <xref:System.Activities.CodeActivity> 基类派生并实现空 <xref:System.Activities.CodeActivity.Execute%2A> 方法。  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
}  
```  
  
 按下面的示例中所示方式声明此类。  
  
```  
[Designer(typeof(CommentOutDesigner))]  
[ContentProperty("Body")]  
public sealed class CommentOut : CodeActivity  
```  
  
 `Designer` 特性指定在设计时实现活动的可视界面的类。 `ContentProperty` 特性声明可按此活动的实例的 XAML 表示形式跳过 `"Body"` 属性。  
  
```  
<Border x:Uid="Border_1" BorderThickness ="1">  
    <sad:WorkflowItemPresenter   
    x:Uid="sad:WorkflowItemPresenter_1" AutomationProperties.AutomationId="Body" Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
    AllowedItemType="{x:Type sa:Activity}"  
    HintText="Drop activity here"   
    Margin="5,5,5,5" />  
</Border>  
```  
  
 在设计器类中，XAML 用于创建活动的自定义可视表示形式。 <xref:System.Activities.Presentation.WorkflowItemPresenter> 是一个提供可视化编辑器的类。  
  
 可以将单个活动放置在 `CommentOut` 活动图面上。 若要向此图面添加多个活动，请先在此处拖动一个顺序活动。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 CommentOut.sln。  
  
2.  按 Ctrl+Shift+B 编辑解决方案。  
  
3.  按 Ctrl+F5 启动示例而不进行调试。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\CommentOut`
