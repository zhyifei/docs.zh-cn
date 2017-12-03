---
title: "自定义复合设计器 — 工作流项演示器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bba89e9da78fd96d0cd7d61e825e4792729bae5b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="b2e0e-102">自定义复合设计器 — 工作流项演示器</span><span class="sxs-lookup"><span data-stu-id="b2e0e-102">Custom Composite Designers - Workflow Item Presenter</span></span>
<span data-ttu-id="b2e0e-103"><xref:System.Activities.Presentation.WorkflowItemPresenter>是 WF 设计器编程模型，可以创建可在其中放置任意活动的"放置区"中的一个重要类型。</span><span class="sxs-lookup"><span data-stu-id="b2e0e-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="b2e0e-104">此示例演示如何生成呈现这样一个"放置区。"的活动设计器</span><span class="sxs-lookup"><span data-stu-id="b2e0e-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>  
  
 <span data-ttu-id="b2e0e-105">此示例演示：</span><span class="sxs-lookup"><span data-stu-id="b2e0e-105">This sample demonstrates:</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b2e0e-106">演示</span><span class="sxs-lookup"><span data-stu-id="b2e0e-106">Demonstrates</span></span>  
  
-   <span data-ttu-id="b2e0e-107">使用 <xref:System.Activities.Presentation.WorkflowItemPresenter> 创建自定义活动设计器。</span><span class="sxs-lookup"><span data-stu-id="b2e0e-107">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>  
  
-   <span data-ttu-id="b2e0e-108">使用元数据存储区注册自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="b2e0e-108">Registering the custom designer using the metadata store.</span></span>  
  
-   <span data-ttu-id="b2e0e-109">以声明方式和命令方式编程重新承载的工具箱。</span><span class="sxs-lookup"><span data-stu-id="b2e0e-109">Programming the rehosted toolbox declaratively and imperatively.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="b2e0e-110">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="b2e0e-110">Sample Details</span></span>  
 <span data-ttu-id="b2e0e-111">此示例的代码演示：</span><span class="sxs-lookup"><span data-stu-id="b2e0e-111">The code for this sample shows:</span></span>  
  
-   <span data-ttu-id="b2e0e-112">针对 `SimpleNativeActivity` 类生成自定义活动设计器。</span><span class="sxs-lookup"><span data-stu-id="b2e0e-112">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>  
  
-   <span data-ttu-id="b2e0e-113">使用 <xref:System.Activities.Presentation.WorkflowItemPresenter> 创建自定义活动设计器。</span><span class="sxs-lookup"><span data-stu-id="b2e0e-113">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>  
  
```xaml  
<sap:ActivityDesigner x:Class="Microsoft.Samples.UsingWorkflowItemPresenter.SimpleNativeDesigner"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
    xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
    <sap:ActivityDesigner.Resources>  
        <DataTemplate x:Key="Collapsed">  
            <StackPanel>  
                <TextBlock>This is the collapsed view</TextBlock>  
            </StackPanel>  
        </DataTemplate>  
        <DataTemplate x:Key="Expanded">  
            <StackPanel>  
                <TextBlock>Custom Text</TextBlock>  
                <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
                                        HintText="Please drop an activity here" />  
            </StackPanel>  
        </DataTemplate>  
        <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
            <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
            <Style.Triggers>  
                <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">  
                    <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
                </DataTrigger>  
            </Style.Triggers>  
        </Style>  
    </sap:ActivityDesigner.Resources>  
    <Grid>  
        <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />  
    </Grid>  
</sap:ActivityDesigner>  
```  
  
 <span data-ttu-id="b2e0e-114">请注意，应使用 WPF 数据绑定来绑定到 `ModelItem.Body`。</span><span class="sxs-lookup"><span data-stu-id="b2e0e-114">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="b2e0e-115">`ModelItem`位于属性<xref:System.Activities.Presentation.ActivityDesigner>它引用设计器正在使用，在这种情况下，基础对象**SimpleNativeActivity**。</span><span class="sxs-lookup"><span data-stu-id="b2e0e-115">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>  
  
#### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="b2e0e-116">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="b2e0e-116">To setup, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b2e0e-117">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开解决方案。</span><span class="sxs-lookup"><span data-stu-id="b2e0e-117">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="b2e0e-118">按 F5 编译并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2e0e-118">Press F5 to compile and run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b2e0e-119">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="b2e0e-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b2e0e-120">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="b2e0e-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b2e0e-121">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="b2e0e-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b2e0e-122">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="b2e0e-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="b2e0e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2e0e-123">See Also</span></span>  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 [<span data-ttu-id="b2e0e-124">使用工作流设计器开发应用程序</span><span class="sxs-lookup"><span data-stu-id="b2e0e-124">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
