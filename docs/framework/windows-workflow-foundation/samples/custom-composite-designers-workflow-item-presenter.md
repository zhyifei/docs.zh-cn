---
title: 自定义复合设计器 — 工作流项演示器
ms.date: 03/30/2017
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
ms.openlocfilehash: 7a3089f1b96cfc766143dd62d9f917fb014af636
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48776921"
---
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="3febb-102">自定义复合设计器 — 工作流项演示器</span><span class="sxs-lookup"><span data-stu-id="3febb-102">Custom Composite Designers - Workflow Item Presenter</span></span>
<span data-ttu-id="3febb-103"><xref:System.Activities.Presentation.WorkflowItemPresenter>是可在何处可放置任意活动的"放置区"创建的 WF 设计器编程模型中的密钥类型。</span><span class="sxs-lookup"><span data-stu-id="3febb-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="3febb-104">此示例演示如何生成活动设计器呈现此类的"放置区。"</span><span class="sxs-lookup"><span data-stu-id="3febb-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>

 <span data-ttu-id="3febb-105">此示例演示：</span><span class="sxs-lookup"><span data-stu-id="3febb-105">This sample demonstrates:</span></span>

## <a name="demonstrates"></a><span data-ttu-id="3febb-106">演示</span><span class="sxs-lookup"><span data-stu-id="3febb-106">Demonstrates</span></span>

-   <span data-ttu-id="3febb-107">使用 <xref:System.Activities.Presentation.WorkflowItemPresenter> 创建自定义活动设计器。</span><span class="sxs-lookup"><span data-stu-id="3febb-107">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

-   <span data-ttu-id="3febb-108">使用元数据存储区注册自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="3febb-108">Registering the custom designer using the metadata store.</span></span>

-   <span data-ttu-id="3febb-109">以声明方式和命令方式编程重新承载的工具箱。</span><span class="sxs-lookup"><span data-stu-id="3febb-109">Programming the rehosted toolbox declaratively and imperatively.</span></span>

## <a name="sample-details"></a><span data-ttu-id="3febb-110">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="3febb-110">Sample Details</span></span>
 <span data-ttu-id="3febb-111">此示例的代码演示：</span><span class="sxs-lookup"><span data-stu-id="3febb-111">The code for this sample shows:</span></span>

-   <span data-ttu-id="3febb-112">针对 `SimpleNativeActivity` 类生成自定义活动设计器。</span><span class="sxs-lookup"><span data-stu-id="3febb-112">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>

-   <span data-ttu-id="3febb-113">使用 <xref:System.Activities.Presentation.WorkflowItemPresenter> 创建自定义活动设计器。</span><span class="sxs-lookup"><span data-stu-id="3febb-113">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

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

 <span data-ttu-id="3febb-114">请注意，应使用 WPF 数据绑定来绑定到 `ModelItem.Body`。</span><span class="sxs-lookup"><span data-stu-id="3febb-114">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="3febb-115">`ModelItem` 该属性位于<xref:System.Activities.Presentation.ActivityDesigner>，是指在设计器正在使用，在这种情况下的基础对象**SimpleNativeActivity**。</span><span class="sxs-lookup"><span data-stu-id="3febb-115">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>

#### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="3febb-116">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="3febb-116">To setup, build, and run the sample</span></span>

1.  <span data-ttu-id="3febb-117">在 Visual Studio 2010 中打开的解决方案。</span><span class="sxs-lookup"><span data-stu-id="3febb-117">Open the solution in Visual Studio 2010.</span></span>

2.  <span data-ttu-id="3febb-118">按 F5 编译并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="3febb-118">Press F5 to compile and run the application.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="3febb-119">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="3febb-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3febb-120">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="3febb-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3febb-121">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="3febb-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3febb-122">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="3febb-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="3febb-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="3febb-123">See Also</span></span>  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 [<span data-ttu-id="3febb-124">使用工作流设计器开发应用程序</span><span class="sxs-lookup"><span data-stu-id="3febb-124">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
