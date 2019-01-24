---
title: 自定义复合设计器 — 工作流项演示器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70055c4b-1173-47a3-be80-b5bce6f59e9a
ms.openlocfilehash: 13d1a76779877bc2ab6d1cbd9c892bf14781e788
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705937"
---
# <a name="custom-composite-designers---workflow-items-presenter"></a><span data-ttu-id="0200a-102">自定义复合设计器 — 工作流项演示器</span><span class="sxs-lookup"><span data-stu-id="0200a-102">Custom Composite Designers - Workflow Items Presenter</span></span>
<span data-ttu-id="0200a-103"><xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> 是 WF 设计器编程模型中的一个重要类型，可用于编辑包含元素的集合。</span><span class="sxs-lookup"><span data-stu-id="0200a-103">The <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> is a key type in the WF designer programming model that allows for the editing of a collection of contained elements.</span></span> <span data-ttu-id="0200a-104">此示例演示如何生成一个呈现此类可编辑集合的活动设计器。</span><span class="sxs-lookup"><span data-stu-id="0200a-104">This sample shows how to build an activity designer that surfaces such an editable collection.</span></span>

 <span data-ttu-id="0200a-105">此示例演示：</span><span class="sxs-lookup"><span data-stu-id="0200a-105">This sample demonstrates:</span></span>

-   <span data-ttu-id="0200a-106">使用 <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> 创建自定义活动设计器。</span><span class="sxs-lookup"><span data-stu-id="0200a-106">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span>

-   <span data-ttu-id="0200a-107">使用"折叠"和"展开"视图中创建活动设计器。</span><span class="sxs-lookup"><span data-stu-id="0200a-107">Creating an activity designer with a "collapsed" and "expanded" view.</span></span>

-   <span data-ttu-id="0200a-108">在重新承载的应用程序中重写默认设计器。</span><span class="sxs-lookup"><span data-stu-id="0200a-108">Overriding a default designer in a rehosted application.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0200a-109">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="0200a-109">To set up, build, and run the sample</span></span>

1.  <span data-ttu-id="0200a-110">打开**UsingWorkflowItemsPresenter.sln**适用于 C# 或 Visual Studio 2010 中的 VB 示例解决方案。</span><span class="sxs-lookup"><span data-stu-id="0200a-110">Open the **UsingWorkflowItemsPresenter.sln** sample solution for C# or for VB in Visual Studio 2010.</span></span>

2.  <span data-ttu-id="0200a-111">生成和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="0200a-111">Build and run the solution.</span></span> <span data-ttu-id="0200a-112">重写承载的工作流设计器应用程序应会打开，并且您可以将活动拖动到画布上。</span><span class="sxs-lookup"><span data-stu-id="0200a-112">A rehosted workflow designer application should open, and you can drag activities onto the canvas.</span></span>

## <a name="sample-highlights"></a><span data-ttu-id="0200a-113">示例重点</span><span class="sxs-lookup"><span data-stu-id="0200a-113">Sample Highlights</span></span>
 <span data-ttu-id="0200a-114">此示例的代码演示了以下内容：</span><span class="sxs-lookup"><span data-stu-id="0200a-114">The code for this sample shows the following:</span></span>

-   <span data-ttu-id="0200a-115">构建的设计器所针对的活动：`Parallel`</span><span class="sxs-lookup"><span data-stu-id="0200a-115">The activity a designer is built for:  `Parallel`</span></span>

-   <span data-ttu-id="0200a-116">使用 <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> 创建自定义活动设计器。</span><span class="sxs-lookup"><span data-stu-id="0200a-116">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0200a-117">需要指出的一些事项：</span><span class="sxs-lookup"><span data-stu-id="0200a-117">A few things to point out:</span></span>

    -   <span data-ttu-id="0200a-118">请注意，应使用 WPF 数据绑定来绑定到 `ModelItem.Branches`。</span><span class="sxs-lookup"><span data-stu-id="0200a-118">Note the use of WPF data binding to bind to `ModelItem.Branches`.</span></span> <span data-ttu-id="0200a-119">`ModelItem` 是 `WorkflowElementDesigner` 的属性，它引用设计器所用于的基础对象，在此例中为 `Parallel`。</span><span class="sxs-lookup"><span data-stu-id="0200a-119">`ModelItem` is the property on `WorkflowElementDesigner` that refers to the underlying object the designer is being used for, in this case, our `Parallel`.</span></span>

    -   <span data-ttu-id="0200a-120"><xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> 可用于在集合中的各个项之间显示一个可视对象。</span><span class="sxs-lookup"><span data-stu-id="0200a-120">The <xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> can be used to put a visual to display between the individual items in the collection.</span></span>

    -   <span data-ttu-id="0200a-121"><xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> 是一个模板，可用于确定集合中的项的布局。</span><span class="sxs-lookup"><span data-stu-id="0200a-121"><xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> is a template that can be provided to determine the layout of the items in the collection.</span></span> <span data-ttu-id="0200a-122">在此例中，使用水平堆叠面板。</span><span class="sxs-lookup"><span data-stu-id="0200a-122">In this case, a horizontal stack panel is used.</span></span>

 <span data-ttu-id="0200a-123">下面的示例代码演示了此过程。</span><span class="sxs-lookup"><span data-stu-id="0200a-123">This following example code shows this.</span></span>

```xaml
<sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                              Items="{Binding Path=ModelItem.Branches}">
    <sad:WorkflowItemsPresenter.SpacerTemplate>
      <DataTemplate>
        <Ellipse Width="10" Height="10" Fill="Black"/>
      </DataTemplate>
    </sad:WorkflowItemsPresenter.SpacerTemplate>
    <sad:WorkflowItemsPresenter.ItemsPanel>
      <ItemsPanelTemplate>
        <StackPanel Orientation="Horizontal"/>
      </ItemsPanelTemplate>
    </sad:WorkflowItemsPresenter.ItemsPanel>
  </sad:WorkflowItemsPresenter>
```

-   <span data-ttu-id="0200a-124">执行 `DesignerAttribute` 与 `Parallel` 类型的关联，然后输出报告的特性。</span><span class="sxs-lookup"><span data-stu-id="0200a-124">Perform an association of the `DesignerAttribute` to the `Parallel` type and then output the attributes reported.</span></span>

    -   <span data-ttu-id="0200a-125">首先，注册所有默认的设计器。</span><span class="sxs-lookup"><span data-stu-id="0200a-125">First, register all of the default designers.</span></span>

 <span data-ttu-id="0200a-126">以下是代码示例。</span><span class="sxs-lookup"><span data-stu-id="0200a-126">The following is the code example.</span></span>

```csharp
// register metadata
(new DesignerMetadata()).Register();
RegisterCustomMetadata();
```

```vb
' register metadata
Dim metadata = New DesignerMetadata()
metadata.Register()
' register custom metadata
RegisterCustomMetadata()
```

    -   <span data-ttu-id="0200a-127">然后，在 `RegisterCustomMetadata` 方法中重写此并行处理。</span><span class="sxs-lookup"><span data-stu-id="0200a-127">Then, override the parallel in `RegisterCustomMetadata` method.</span></span>

 <span data-ttu-id="0200a-128">下面的代码分别使用 C# 和 Visual Basic 演示了此过程。</span><span class="sxs-lookup"><span data-stu-id="0200a-128">The following code shows this in C# and Visual Basic.</span></span>

```csharp
void RegisterCustomMetadata()
{
      AttributeTableBuilder builder = new AttributeTableBuilder();
      builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
      MetadataStore.AddAttributeTable(builder.CreateTable());
}
```

```vb
Sub RegisterCustomMetadata()
   Dim builder As New AttributeTableBuilder()
   builder.AddCustomAttributes(GetType(Parallel), New DesignerAttribute(GetType(CustomParallelDesigner)))
   MetadataStore.AddAttributeTable(builder.CreateTable())
End Sub
```

-   <span data-ttu-id="0200a-129">最后，请注意使用不同的数据模板和触发器来基于 `IsRootDesigner` 属性选择适当的模板。</span><span class="sxs-lookup"><span data-stu-id="0200a-129">Finally, note the use of differing data templates and triggers to select the appropriate template based on the `IsRootDesigner` property.</span></span>

 <span data-ttu-id="0200a-130">以下是代码示例。</span><span class="sxs-lookup"><span data-stu-id="0200a-130">The following is the code example.</span></span>

```xaml
<sad:ActivityDesigner x:Class="Microsoft.Samples.CustomParallelDesigner"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:sad="clr-namespace:System.Activities.Design;assembly=System.Activities.Design"
    xmlns:sadv="clr-namespace:System.Activities.Design.View;assembly=System.Activities.Design">
  <sad:ActivityDesigner.Resources>
    <DataTemplate x:Key="Expanded">
      <StackPanel>
        <TextBlock>This is the Expanded View</TextBlock>
        <sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                                    Items="{Binding Path=ModelItem.Branches}">
          <sad:WorkflowItemsPresenter.SpacerTemplate>
            <DataTemplate>
              <Ellipse Width="10" Height="10" Fill="Black"/>
            </DataTemplate>
          </sad:WorkflowItemsPresenter.SpacerTemplate>
          <sad:WorkflowItemsPresenter.ItemsPanel>
            <ItemsPanelTemplate>
              <StackPanel Orientation="Horizontal"/>
            </ItemsPanelTemplate>
          </sad:WorkflowItemsPresenter.ItemsPanel>
        </sad:WorkflowItemsPresenter>
      </StackPanel>
    </DataTemplate>
    <DataTemplate x:Key="Collapsed">
      <TextBlock>This is the Collapsed View</TextBlock>
    </DataTemplate>
    <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
      <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
      <Style.Triggers>
        <DataTrigger Binding="{Binding Path=IsRootDesigner}" Value="true">
          <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
        </DataTrigger>
      </Style.Triggers>
    </Style>
  </sad: ActivityDesigner.Resources>
  <Grid>
    <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>
  </Grid>
</sad: ActivityDesigner>
```

> [!IMPORTANT]
>  <span data-ttu-id="0200a-131">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="0200a-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0200a-132">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="0200a-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0200a-133">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="0200a-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0200a-134">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="0200a-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemsPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="0200a-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="0200a-135">See also</span></span>
- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- [<span data-ttu-id="0200a-136">使用工作流设计器开发应用程序</span><span class="sxs-lookup"><span data-stu-id="0200a-136">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
