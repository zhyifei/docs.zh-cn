---
title: "演练：设置 WPF 内容的样式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0fa4772ebb321f927087fe13d0d50a6ae8145e55
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-styling-wpf-content"></a><span data-ttu-id="aff1e-102">演练：设置 WPF 内容的样式</span><span class="sxs-lookup"><span data-stu-id="aff1e-102">Walkthrough: Styling WPF Content</span></span>
<span data-ttu-id="aff1e-103">本演练显示了如何将样式应用到 Windows 窗体上承载的 Windows Presentation Foundation (WPF) 控件中。</span><span class="sxs-lookup"><span data-stu-id="aff1e-103">This walkthrough show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>  
  
 <span data-ttu-id="aff1e-104">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="aff1e-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="aff1e-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="aff1e-105">Create the project.</span></span>  
  
-   <span data-ttu-id="aff1e-106">创建 WPF 控件类型。</span><span class="sxs-lookup"><span data-stu-id="aff1e-106">Create the WPF control type.</span></span>  
  
-   <span data-ttu-id="aff1e-107">将样式应用到 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="aff1e-107">Apply a style to the WPF control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aff1e-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="aff1e-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="aff1e-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="aff1e-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="aff1e-110">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="aff1e-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aff1e-111">系统必备</span><span class="sxs-lookup"><span data-stu-id="aff1e-111">Prerequisites</span></span>  
 <span data-ttu-id="aff1e-112">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="aff1e-112">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="aff1e-113">。</span><span class="sxs-lookup"><span data-stu-id="aff1e-113">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="aff1e-114">创建项目</span><span class="sxs-lookup"><span data-stu-id="aff1e-114">Creating the Project</span></span>  
 <span data-ttu-id="aff1e-115">第一步是创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="aff1e-115">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aff1e-116">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="aff1e-116">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="aff1e-117">要创建项目</span><span class="sxs-lookup"><span data-stu-id="aff1e-117">To create the project</span></span>  
  
-   <span data-ttu-id="aff1e-118">创建新的 Windows 窗体应用程序项目中 Visual Basic 或 Visual C# 名为`StylingWpfContent`。</span><span class="sxs-lookup"><span data-stu-id="aff1e-118">Create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="aff1e-119">创建 WPF 控件类型</span><span class="sxs-lookup"><span data-stu-id="aff1e-119">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="aff1e-120">将 WPF 控件类型添加到项目后，就可在 <xref:System.Windows.Forms.Integration.ElementHost> 控件中托管它。</span><span class="sxs-lookup"><span data-stu-id="aff1e-120">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="aff1e-121">创建 WPF 控件类型</span><span class="sxs-lookup"><span data-stu-id="aff1e-121">To create WPF control types</span></span>  
  
1.  <span data-ttu-id="aff1e-122">将新的 WPF <xref:System.Windows.Controls.UserControl> 项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="aff1e-122">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="aff1e-123">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="aff1e-123">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="aff1e-124">有关详细信息，请参阅[演练： 创建新 WPF 内容在设计时的 Windows 窗体上](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="aff1e-124">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="aff1e-125">在设计视图中，请确保已选中 `UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="aff1e-125">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="aff1e-126">有关详细信息，请参阅[如何： 选择和设计图面上移动元素](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474)。</span><span class="sxs-lookup"><span data-stu-id="aff1e-126">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="aff1e-127">在**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性设置为`200`。</span><span class="sxs-lookup"><span data-stu-id="aff1e-127">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="aff1e-128">添加<xref:System.Windows.Controls.Button?displayProperty=nameWithType>控制转移到<xref:System.Windows.Controls.UserControl>和设置的值<xref:System.Windows.Controls.ContentControl.Content%2A>属性**取消**。</span><span class="sxs-lookup"><span data-stu-id="aff1e-128">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>  
  
5.  <span data-ttu-id="aff1e-129">添加第二个<xref:System.Windows.Controls.Button?displayProperty=nameWithType>控制转移到<xref:System.Windows.Controls.UserControl>和设置的值<xref:System.Windows.Controls.ContentControl.Content%2A>属性**确定**。</span><span class="sxs-lookup"><span data-stu-id="aff1e-129">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>  
  
6.  <span data-ttu-id="aff1e-130">生成项目。</span><span class="sxs-lookup"><span data-stu-id="aff1e-130">Build the project.</span></span>  
  
## <a name="applying-a-style-to-a-wpf-control"></a><span data-ttu-id="aff1e-131">将样式应用到 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="aff1e-131">Applying a Style to a WPF Control</span></span>  
 <span data-ttu-id="aff1e-132">可对 WPF 控件应用不同样式以更改它的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="aff1e-132">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>  
  
#### <a name="to-apply-a-style-to-a-wpf-control"></a><span data-ttu-id="aff1e-133">将样式应用到 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="aff1e-133">To apply a style to a WPF control</span></span>  
  
1.  <span data-ttu-id="aff1e-134">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="aff1e-134">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="aff1e-135">在**工具箱**，双击`UserControl1`若要创建的实例`UserControl1`窗体上。</span><span class="sxs-lookup"><span data-stu-id="aff1e-135">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="aff1e-136">`UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="aff1e-136">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="aff1e-137">在智能标记面板中`elementHost1`，单击**编辑所承载的内容**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="aff1e-137">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>  
  
     <span data-ttu-id="aff1e-138">`UserControl1` 将在 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] 中打开。</span><span class="sxs-lookup"><span data-stu-id="aff1e-138">`UserControl1` opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="aff1e-139">在 XAML 视图中，将以下 XAML 插到 `<UserControl>` 开始标记后面。</span><span class="sxs-lookup"><span data-stu-id="aff1e-139">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span>  
  
     <span data-ttu-id="aff1e-140">此 XAML 创建具有对比渐变边框的渐变。</span><span class="sxs-lookup"><span data-stu-id="aff1e-140">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="aff1e-141">单击此控件后，将更改渐变以生成按下按钮的外观。</span><span class="sxs-lookup"><span data-stu-id="aff1e-141">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="aff1e-142">有关详细信息，请参阅[样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)。</span><span class="sxs-lookup"><span data-stu-id="aff1e-142">For more information, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>  
  
```xaml  
<UserControl.Resources>  
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#FFF" Offset="0.0"/>  
        <GradientStop Color="#CCC" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#BBB" Offset="0.0"/>  
        <GradientStop Color="#EEE" Offset="0.1"/>  
        <GradientStop Color="#EEE" Offset="0.9"/>  
        <GradientStop Color="#FFF" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#444" Offset="0.0"/>  
        <GradientStop Color="#888" Offset="1.0"/>  
    </LinearGradientBrush>  
  
    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">  
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>  
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>  
        <Setter Property="Template">  
            <Setter.Value>  
                <ControlTemplate TargetType="{x:Type Button}">  
                    <Grid x:Name="Grid">  
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>  
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>  
                    </Grid>  
                    <ControlTemplate.Triggers>  
                        <Trigger Property="IsPressed" Value="true">  
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>  
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>  
                        </Trigger>  
                    </ControlTemplate.Triggers>  
                </ControlTemplate>  
            </Setter.Value>  
        </Setter>  
    </Style>  
</UserControl.Resources>  
```  
  
1.  <span data-ttu-id="aff1e-143">通过插入“取消”按钮的 `<Button>` 标记中的以下 XAML，将上一步中定义的 `SimpleButton` 样式应用到“取消”按钮。</span><span class="sxs-lookup"><span data-stu-id="aff1e-143">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the Cancel button.</span></span>  
  
    ```  
    Style="{StaticResource SimpleButton}  
    ```  
  
     <span data-ttu-id="aff1e-144">按钮声明将类似于以下 XAML。</span><span class="sxs-lookup"><span data-stu-id="aff1e-144">Your button declaration will resemble the following XAML.</span></span>  
  
```xaml  
<Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"  
                Style="{StaticResource SimpleButton}">Cancel</Button>  
```  
  
1.  <span data-ttu-id="aff1e-145">生成项目。</span><span class="sxs-lookup"><span data-stu-id="aff1e-145">Build the project.</span></span>  
  
2.  <span data-ttu-id="aff1e-146">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="aff1e-146">Open `Form1` in the Windows Forms Designer.</span></span>  
  
3.  <span data-ttu-id="aff1e-147">将新样式应用到按钮控件中。</span><span class="sxs-lookup"><span data-stu-id="aff1e-147">The new style is applied to the button control.</span></span>  
  
4.  <span data-ttu-id="aff1e-148">从**调试**菜单上，选择**启动调试**运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="aff1e-148">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>  
  
5.  <span data-ttu-id="aff1e-149">单击“确定”和“取消”按钮并查看差异。</span><span class="sxs-lookup"><span data-stu-id="aff1e-149">Click the OK and Cancel buttons and view the differences.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff1e-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="aff1e-150">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="aff1e-151">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="aff1e-151">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="aff1e-152">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="aff1e-152">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="aff1e-153">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="aff1e-153">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="aff1e-154">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="aff1e-154">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="aff1e-155">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="aff1e-155">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
