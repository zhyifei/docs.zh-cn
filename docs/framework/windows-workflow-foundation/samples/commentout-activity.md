---
title: "CommentOut 活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340204c3-f827-45fb-870e-55e2ac457ca5
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: df5faa2aacf6b86d708dad4b157b27d2609a0a93
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="commentout-activity"></a><span data-ttu-id="ec173-102">CommentOut 活动</span><span class="sxs-lookup"><span data-stu-id="ec173-102">CommentOut Activity</span></span>
<span data-ttu-id="ec173-103">此示例演示如何编写一个自定义活动，该活动从执行路径中移除其他活动，从而有效注释掉这些活动。</span><span class="sxs-lookup"><span data-stu-id="ec173-103">This sample demonstrates how to write a custom activity that removes other activities from the path of execution, effectively commenting them out.</span></span>  
  
## <a name="the-commentout-activity"></a><span data-ttu-id="ec173-104">CommentOut 活动</span><span class="sxs-lookup"><span data-stu-id="ec173-104">The CommentOut Activity</span></span>  
 <span data-ttu-id="ec173-105">为了实现其目标，CommentOut 活动从 <xref:System.Activities.CodeActivity> 基类派生并实现空 <xref:System.Activities.CodeActivity.Execute%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ec173-105">To achieve its goal, the CommentOut activity derives from the <xref:System.Activities.CodeActivity> base class and implements an empty <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
}  
```  
  
 <span data-ttu-id="ec173-106">按下面的示例中所示方式声明此类。</span><span class="sxs-lookup"><span data-stu-id="ec173-106">The class is declared as shown in the following example.</span></span>  
  
```  
[Designer(typeof(CommentOutDesigner))]  
[ContentProperty("Body")]  
public sealed class CommentOut : CodeActivity  
```  
  
 <span data-ttu-id="ec173-107">`Designer` 特性指定在设计时实现活动的可视界面的类。</span><span class="sxs-lookup"><span data-stu-id="ec173-107">The `Designer` attribute specifies the class that implements the visual interface of the activity at design time.</span></span> <span data-ttu-id="ec173-108">`ContentProperty` 特性声明可按此活动的实例的 XAML 表示形式跳过 `"Body"` 属性。</span><span class="sxs-lookup"><span data-stu-id="ec173-108">The `ContentProperty` attribute declares that the `"Body"` property can be skipped in the XAML representation of an instance of this activity.</span></span>  
  
```  
<Border x:Uid="Border_1" BorderThickness ="1">  
    <sad:WorkflowItemPresenter   
    x:Uid="sad:WorkflowItemPresenter_1" AutomationProperties.AutomationId="Body" Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
    AllowedItemType="{x:Type sa:Activity}"  
    HintText="Drop activity here"   
    Margin="5,5,5,5" />  
</Border>  
```  
  
 <span data-ttu-id="ec173-109">在设计器类中，XAML 用于创建活动的自定义可视表示形式。</span><span class="sxs-lookup"><span data-stu-id="ec173-109">In the designer class, XAML is used to create a custom visual representation of the activity.</span></span> <span data-ttu-id="ec173-110"><xref:System.Activities.Presentation.WorkflowItemPresenter> 是一个提供可视化编辑器的类。</span><span class="sxs-lookup"><span data-stu-id="ec173-110"><xref:System.Activities.Presentation.WorkflowItemPresenter> is a class that provides the visual editor.</span></span>  
  
 <span data-ttu-id="ec173-111">可以将单个活动放置在 `CommentOut` 活动图面上。</span><span class="sxs-lookup"><span data-stu-id="ec173-111">A single activity can be dropped onto the `CommentOut` activity surface.</span></span> <span data-ttu-id="ec173-112">若要向此图面添加多个活动，请先在此处拖动一个顺序活动。</span><span class="sxs-lookup"><span data-stu-id="ec173-112">If you want to add multiple activities to this surface, drag a sequence activity here first.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ec173-113">使用此示例</span><span class="sxs-lookup"><span data-stu-id="ec173-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="ec173-114">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 CommentOut.sln。</span><span class="sxs-lookup"><span data-stu-id="ec173-114">Open CommentOut.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ec173-115">按 Ctrl+Shift+B 编辑解决方案。</span><span class="sxs-lookup"><span data-stu-id="ec173-115">Compile the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ec173-116">按 Ctrl+F5 启动示例而不进行调试。</span><span class="sxs-lookup"><span data-stu-id="ec173-116">Start the sample without debugging by pressing CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ec173-117">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="ec173-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ec173-118">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="ec173-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ec173-119">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="ec173-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ec173-120">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="ec173-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\CommentOut`
