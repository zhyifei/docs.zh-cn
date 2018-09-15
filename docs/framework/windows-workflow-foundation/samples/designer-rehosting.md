---
title: 重新承载设计器
ms.date: 03/30/2017
ms.assetid: b676ad31-5f64-4d84-9a36-b4d7113a2f4d
ms.openlocfilehash: 1901df62ccdeec3f75ce0d8cd85484f46fac4541
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2018
ms.locfileid: "45652919"
---
# <a name="designer-rehosting"></a><span data-ttu-id="66552-102">重新承载设计器</span><span class="sxs-lookup"><span data-stu-id="66552-102">Designer ReHosting</span></span>
<span data-ttu-id="66552-103">设计器重新承载是一个常用方案，它是指在自定义应用程序内部承载工作流设计画布。</span><span class="sxs-lookup"><span data-stu-id="66552-103">Designer rehosting is a common scenario that refers to hosting the workflow design canvas inside of a custom application.</span></span> <span data-ttu-id="66552-104">Visual Studio 是大多数人所熟知的承载应用程序，然而在很多方案中，应用程序中的工作流设计器可能会很有用：</span><span class="sxs-lookup"><span data-stu-id="66552-104">The hosting application most people are familiar with is Visual Studio, however there are a number of scenarios where showing the workflow designer in an application may be useful:</span></span>  
  
-   <span data-ttu-id="66552-105">监视应用程序（允许最终用户直观地查看进程以及有关进程的运行时数据，例如，当前活动状态、聚合执行时间数据或其他关于工作流实例的信息）。</span><span class="sxs-lookup"><span data-stu-id="66552-105">Monitoring applications (allowing an end user to visualize the process, as well as runtime data about the process such as the currently active state, aggregate execution time data, or other information about an instance of the workflow).</span></span>  
  
-   <span data-ttu-id="66552-106">允许用户使用有限的活动集合自定义进程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="66552-106">Applications that allow a user to customize the process with a limited set of activities.</span></span>  
  
 <span data-ttu-id="66552-107">为了支持这些类型的应用程序，.NET Framework 内附带了工作流设计器，它可以在 WPF 应用程序内或在具有适当的 WPF 承载编码的 WinForms 应用程序内承载。</span><span class="sxs-lookup"><span data-stu-id="66552-107">To support these types of applications, the workflow designer ships inside the .NET Framework, and can be hosted inside a WPF application, or in a WinForms application with the appropriate WPF hosting code.</span></span> <span data-ttu-id="66552-108">此示例演示：</span><span class="sxs-lookup"><span data-stu-id="66552-108">This sample demonstrates:</span></span>  
  
-   <span data-ttu-id="66552-109">重新承载 WF 设计器。</span><span class="sxs-lookup"><span data-stu-id="66552-109">Rehosting the WF designer.</span></span>  
  
-   <span data-ttu-id="66552-110">使用重新承载的工具箱和属性网格。</span><span class="sxs-lookup"><span data-stu-id="66552-110">Using the rehosted toolbox and property grid as well.</span></span>  
  
## <a name="rehosting-the-designer"></a><span data-ttu-id="66552-111">重新承载设计器</span><span class="sxs-lookup"><span data-stu-id="66552-111">Rehosting the designer</span></span>  
 <span data-ttu-id="66552-112">此示例演示如何创建 WPF 布局以包含在以下网格布局中可见的设计器（因空间有限，省略工具箱编码）。</span><span class="sxs-lookup"><span data-stu-id="66552-112">This sample shows how to create the WPF layout to contain the designer, seen in the following grid layout (Toolbox code omitted for space concerns).</span></span> <span data-ttu-id="66552-113">需注意包含设计器和属性网格的边框的命名。</span><span class="sxs-lookup"><span data-stu-id="66552-113">Note the naming of the borders which contain the designer and property grid.</span></span>  
  
```xaml  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition Width="2*"/>  
        <ColumnDefinition Width="7*"/>  
        <ColumnDefinition Width="3*"/>  
    </Grid.ColumnDefinitions>  
    <Border Grid.Column="0">  
        <sapt:ToolboxControl>...</sapt:ToolboxControl>  
    </Border>  
    <Border Grid.Column="1" Name="DesignerBorder"/>  
    <Border Grid.Column="2" Name="PropertyBorder"/>  
</Grid>  
```  
  
 <span data-ttu-id="66552-114">接下来，此示例创建设计器，并将其主 <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> 和 <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> 与用户界面中适当的容器相关联。</span><span class="sxs-lookup"><span data-stu-id="66552-114">Next the sample creates the designer, and associates its primary <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> with the appropriate container in the user interface.</span></span> <span data-ttu-id="66552-115">以下示例中有几行额外的代码需要解释一下。</span><span class="sxs-lookup"><span data-stu-id="66552-115">There are a few additional lines of code in the following example that merit some explanation.</span></span> <span data-ttu-id="66552-116">需要调用 <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> 来为 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 附带的活动关联默认的活动设计器。</span><span class="sxs-lookup"><span data-stu-id="66552-116">The <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> call is required to associate the default activity designers for the activities shipped with [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="66552-117">调用 <xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> 传入要编辑的 WF 项。</span><span class="sxs-lookup"><span data-stu-id="66552-117"><xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> is called to pass in the WF item to be edited.</span></span> <span data-ttu-id="66552-118">最后，将 <xref:System.Activities.Presentation.WorkflowDesigner.View%2A>（主画布）和 <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A>（属性网格）放置在用户界面的图面上。</span><span class="sxs-lookup"><span data-stu-id="66552-118">Finally, the <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (primary canvas) and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (property grid) are placed onto the user interface surface.</span></span>  
  
```csharp  
protected override void OnInitialized(EventArgs e)  
{  
   base.OnInitialized(e);  
   // register metadata  
   (new DesignerMetadata()).Register();  
  
   // create the workflow designer  
   WorkflowDesigner wd = new WorkflowDesigner();  
   wd.Load(new Sequence());  
   DesignerBorder.Child = wd.View;  
   PropertyBorder.Child = wd.PropertyInspectorView;  
}  
```  
  
## <a name="using-the-rehosted-toolbox"></a><span data-ttu-id="66552-119">使用重新承载的工具栏</span><span class="sxs-lookup"><span data-stu-id="66552-119">Using the rehosted toolbox</span></span>  
 <span data-ttu-id="66552-120">此示例在 XAML 中以声明方式使用重新承载的工具箱控件。</span><span class="sxs-lookup"><span data-stu-id="66552-120">This sample uses the rehosted toolbox control declaratively in XAML.</span></span> <span data-ttu-id="66552-121">请注意，在代码中可以将一个类型传递给 <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper> 构造函数。</span><span class="sxs-lookup"><span data-stu-id="66552-121">Note that in code, one can pass a type to the <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper> constructor.</span></span>  
  
```xaml  
<!-- Copyright (c) Microsoft Corporation. All rights reserved-->  
<Window x:Class="Microsoft.Samples.DesignerRehosting.RehostingWfDesigner"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:sapt="clr-namespace:System.Activities.Presentation.Toolbox;assembly=System.Activities.Presentation"  
        xmlns:sys="clr-namespace:System;assembly=mscorlib"  
        Title="Window1" Height="600" Width="900">  
    <Window.Resources>  
        <sys:String x:Key="AssemblyName">System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35</sys:String>  
    </Window.Resources>  
    <Grid>  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition Width="2*"/>  
            <ColumnDefinition Width="7*"/>  
            <ColumnDefinition Width="3*"/>  
        </Grid.ColumnDefinitions>  
        <Border Grid.Column="0">  
            <sapt:ToolboxControl>  
                <sapt:ToolboxCategory CategoryName="Basic">  
                    <sapt:ToolboxItemWrapper AssemblyName="{StaticResource AssemblyName}" >  
                        <sapt:ToolboxItemWrapper.ToolName>  
                            System.Activities.Statements.Sequence  
                        </sapt:ToolboxItemWrapper.ToolName>  
                       </sapt:ToolboxItemWrapper>  
                    <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                        <sapt:ToolboxItemWrapper.ToolName>  
                            System.Activities.Statements.WriteLine  
                        </sapt:ToolboxItemWrapper.ToolName>  
  
                    </sapt:ToolboxItemWrapper>  
                    <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                        <sapt:ToolboxItemWrapper.ToolName>  
                            System.Activities.Statements.If  
                        </sapt:ToolboxItemWrapper.ToolName>  
  
                    </sapt:ToolboxItemWrapper>  
                    <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                        <sapt:ToolboxItemWrapper.ToolName>  
                            System.Activities.Statements.While  
                        </sapt:ToolboxItemWrapper.ToolName>  
  
                    </sapt:ToolboxItemWrapper>  
                </sapt:ToolboxCategory>  
            </sapt:ToolboxControl>  
        </Border>  
        <Border Grid.Column="1" Name="DesignerBorder"/>  
        <Border Grid.Column="2" Name="PropertyBorder"/>  
    </Grid>  
</Window>  
```  
  
#### <a name="using-the-sample"></a><span data-ttu-id="66552-122">使用示例</span><span class="sxs-lookup"><span data-stu-id="66552-122">Using the sample</span></span>  
  
1.  <span data-ttu-id="66552-123">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 DesignerRehosting.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="66552-123">Open the DesignerRehosting.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="66552-124">按 F5 编译并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="66552-124">Press F5 to compile and run the application.</span></span>  
  
3.  <span data-ttu-id="66552-125">一个 WPF 应用程序启动并显示一个重新承载的设计器。</span><span class="sxs-lookup"><span data-stu-id="66552-125">A WPF application starts with a rehosted designer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="66552-126">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="66552-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="66552-127">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="66552-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="66552-128">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="66552-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="66552-129">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="66552-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\DesignerRehosting\Basic`