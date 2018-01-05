---
title: "演练：使用 XAML 创建按钮"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c5efa9f8787e65d59e1b544632e806bf3fbbc81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="136c1-102">演练：使用 XAML 创建按钮</span><span class="sxs-lookup"><span data-stu-id="136c1-102">Walkthrough: Create a Button by Using XAML</span></span>
<span data-ttu-id="136c1-103">本演练的目的是了解如何创建用于动画的按钮[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="136c1-103">The objective of this walkthrough is to learn how to create an animated button for use in a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] application.</span></span> <span data-ttu-id="136c1-104">本演练使用样式和模板来创建自定义的按钮资源允许的代码重用，并从按钮声明的按钮逻辑分离。</span><span class="sxs-lookup"><span data-stu-id="136c1-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="136c1-105">本演练完全在编写[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="136c1-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="136c1-106">本演练将指导你逐步完成创建应用程序，通过键入或复制并粘贴[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]到 Microsoft [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="136c1-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Microsoft [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="136c1-107">如果你想要了解如何使用设计工具 (Microsoft Expression Blend) 来创建相同的应用程序，请参阅[创建通过使用 Microsoft Expression Blend 按钮](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)。</span><span class="sxs-lookup"><span data-stu-id="136c1-107">If you would prefer to learn how to use a design tool (Microsoft Expression Blend) to create the same application, see [Create a Button by Using Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>  
  
 <span data-ttu-id="136c1-108">下图显示已完成的按钮。</span><span class="sxs-lookup"><span data-stu-id="136c1-108">The following figure shows the finished buttons.</span></span>  
  
 <span data-ttu-id="136c1-109">![使用 XAML 创建的自定义按钮](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="136c1-109">![Custom buttons that were created by using XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>  
  
## <a name="create-basic-buttons"></a><span data-ttu-id="136c1-110">创建基本按钮</span><span class="sxs-lookup"><span data-stu-id="136c1-110">Create Basic Buttons</span></span>  
 <span data-ttu-id="136c1-111">让我们开始通过创建新的项目并将几个按钮添加到窗口。</span><span class="sxs-lookup"><span data-stu-id="136c1-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="136c1-112">创建新的 WPF 项目并将按钮添加到窗口</span><span class="sxs-lookup"><span data-stu-id="136c1-112">To create a new WPF project and add buttons to the window</span></span>  
  
1.  <span data-ttu-id="136c1-113">启动[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="136c1-113">Start[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="136c1-114">**创建新的 WPF 项目：**上**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="136c1-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="136c1-115">查找**Windows 应用程序 (WPF)**模板和名称的项目"AnimatedButton"。</span><span class="sxs-lookup"><span data-stu-id="136c1-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="136c1-116">这将创建应用程序的主干。</span><span class="sxs-lookup"><span data-stu-id="136c1-116">This will create the skeleton for the application.</span></span>  
  
3.  <span data-ttu-id="136c1-117">**添加基本的默认按钮：**对于本演练需要的所有文件都会都提供模板。</span><span class="sxs-lookup"><span data-stu-id="136c1-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="136c1-118">通过在解决方案资源管理器中单击双打开 Window1.xaml 文件。</span><span class="sxs-lookup"><span data-stu-id="136c1-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="136c1-119">默认情况下，没有<xref:System.Windows.Controls.Grid>Window1.xaml 中的元素。</span><span class="sxs-lookup"><span data-stu-id="136c1-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="136c1-120">删除<xref:System.Windows.Controls.Grid>元素和几个将按钮添加到[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]页上通过键入或者复制并粘贴到 Window1.xaml 以下突出显示的代码：</span><span class="sxs-lookup"><span data-stu-id="136c1-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>  
  
    ```xaml  
    <Window x:Class="AnimatedButton.Window1"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      Title="AnimatedButton" Height="300" Width="300"   
      Background="Black">   <!-- Buttons arranged vertically inside a StackPanel. -->   <StackPanel HorizontalAlignment="Left">     <Button>Button 1</Button>     <Button>Button 2</Button>     <Button>Button 3</Button>   </StackPanel>  
  
    </Window>  
    ```  
  
     <span data-ttu-id="136c1-121">按 F5 运行该应用程序;你应看到一组类似于下图的按钮。</span><span class="sxs-lookup"><span data-stu-id="136c1-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>  
  
     <span data-ttu-id="136c1-122">![三个基本按钮](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="136c1-122">![Three basic buttons](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>  
  
     <span data-ttu-id="136c1-123">既然你已经创建基本的按钮，您已完成 Window1.xaml 文件中的工作。</span><span class="sxs-lookup"><span data-stu-id="136c1-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="136c1-124">本演练的其余部分重点介绍 app.xaml 文件中，定义样式和模板的按钮。</span><span class="sxs-lookup"><span data-stu-id="136c1-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>  
  
## <a name="set-basic-properties"></a><span data-ttu-id="136c1-125">设置基本属性</span><span class="sxs-lookup"><span data-stu-id="136c1-125">Set Basic Properties</span></span>  
 <span data-ttu-id="136c1-126">接下来，让我们在这些按钮来控制按钮外观和布局上设置某些属性。</span><span class="sxs-lookup"><span data-stu-id="136c1-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="136c1-127">而不是单独在按钮上设置属性，你将使用资源定义整个应用程序按钮属性。</span><span class="sxs-lookup"><span data-stu-id="136c1-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="136c1-128">应用程序资源是从概念上讲类似于外部[!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)]Web 页; 但是，资源是比功能更强大[!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)]，如你将看到按本演练结束。</span><span class="sxs-lookup"><span data-stu-id="136c1-128">Application resources are conceptually similar to external [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] for Web pages; however, resources are much more powerful than [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="136c1-129">若要了解有关资源的详细信息，请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="136c1-129">To learn more about resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="136c1-130">若要使用样式设置在按钮上的基本属性</span><span class="sxs-lookup"><span data-stu-id="136c1-130">To use styles to set basic properties on the buttons</span></span>  
  
1.  <span data-ttu-id="136c1-131">**定义 Application.Resources 块：**打开 app.xaml 并添加以下突出显示的标记，如果它尚不存在：</span><span class="sxs-lookup"><span data-stu-id="136c1-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>  
  
    ```xaml  
    <Application x:Class="AnimatedButton.App"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      StartupUri="Window1.xaml"  
      >  
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>  
    </Application>  
    ```  
  
     <span data-ttu-id="136c1-132">资源作用域取决于你在其中定义该资源。</span><span class="sxs-lookup"><span data-stu-id="136c1-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="136c1-133">定义中的资源`Application.Resources`在 app.xaml 文件允许使用从任何位置应用程序中的资源。</span><span class="sxs-lookup"><span data-stu-id="136c1-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="136c1-134">若要了解有关定义你的资源的作用域的详细信息，请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="136c1-134">To learn more about defining the scope of your resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
2.  <span data-ttu-id="136c1-135">**创建一个样式，并定义基本属性值，其值：**添加到以下标记`Application.Resources`块。</span><span class="sxs-lookup"><span data-stu-id="136c1-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="136c1-136">此标记将创建<xref:System.Windows.Style>指示应用于应用程序设置中的所有按钮<xref:System.Windows.FrameworkElement.Width%2A>为 90 的按钮和<xref:System.Windows.FrameworkElement.Margin%2A>到 10:</span><span class="sxs-lookup"><span data-stu-id="136c1-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     <span data-ttu-id="136c1-137"><xref:System.Windows.Style.TargetType%2A>属性指定该样式应用于类型的所有对象<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="136c1-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="136c1-138">每个<xref:System.Windows.Setter>设置不同的属性值为<xref:System.Windows.Style>。</span><span class="sxs-lookup"><span data-stu-id="136c1-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="136c1-139">因此，在此时应用程序中的每个按钮的宽度为 90，都边距为 10。</span><span class="sxs-lookup"><span data-stu-id="136c1-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="136c1-140">如果按 F5 运行该应用程序时，你将看到下面的窗口。</span><span class="sxs-lookup"><span data-stu-id="136c1-140">If you press F5 to run the application, you see the following window.</span></span>  
  
     <span data-ttu-id="136c1-141">![宽度为 90、 边距为 10 的按钮](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="136c1-141">![Buttons with a width of 90 and a margin of 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>  
  
     <span data-ttu-id="136c1-142">没有你可以进行更多使用样式，包括各种方法来微调对象的目标，从而指定复杂的属性值，并甚至将用作输入其他样式的样式。</span><span class="sxs-lookup"><span data-stu-id="136c1-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="136c1-143">有关详细信息，请参阅[样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)。</span><span class="sxs-lookup"><span data-stu-id="136c1-143">For more information, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>  
  
3.  <span data-ttu-id="136c1-144">**样式属性值设置为资源：**资源，可以通过一种简单的方法，能够重复使用通常定义的对象和值。</span><span class="sxs-lookup"><span data-stu-id="136c1-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="136c1-145">它是特别有用，可以定义复杂值使用资源以使代码更加模块化。</span><span class="sxs-lookup"><span data-stu-id="136c1-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="136c1-146">将以下突出显示的标记添加到 app.xaml。</span><span class="sxs-lookup"><span data-stu-id="136c1-146">Add the following highlighted markup to app.xaml.</span></span>  
  
    ```xaml  
    <Application.Resources>  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>  
      <Style TargetType="{x:Type Button}">  
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
      </Style>  
    </Application.Resources>  
    ```  
  
     <span data-ttu-id="136c1-147">直接在`Application.Resources`块中，创建名为"GrayBlueGradientBrush"的资源。</span><span class="sxs-lookup"><span data-stu-id="136c1-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="136c1-148">该资源定义的水平的渐变。</span><span class="sxs-lookup"><span data-stu-id="136c1-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="136c1-149">可以从任何位置的属性值作为使用此资源应用程序，包括内部的按钮样式 setter 中<xref:System.Windows.Controls.Control.Background%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="136c1-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="136c1-150">现在，所有按钮都有<xref:System.Windows.Controls.Control.Background%2A>此渐变的属性值。</span><span class="sxs-lookup"><span data-stu-id="136c1-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>  
  
     <span data-ttu-id="136c1-151">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="136c1-151">Press F5 to run the application.</span></span> <span data-ttu-id="136c1-152">其外观应如下所示。</span><span class="sxs-lookup"><span data-stu-id="136c1-152">It should look like the following.</span></span>  
  
     <span data-ttu-id="136c1-153">![具有渐变背景的按钮](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="136c1-153">![Buttons with a gradient background](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="136c1-154">创建定义按钮的外观的模板。</span><span class="sxs-lookup"><span data-stu-id="136c1-154">Create a Template That Defines the Look of the Button</span></span>  
 <span data-ttu-id="136c1-155">在本部分中，你将创建自定义按钮的外观 (presentation) 的模板。</span><span class="sxs-lookup"><span data-stu-id="136c1-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="136c1-156">按钮演示文稿组成包括矩形和其他组件的多个对象以使具有唯一外观的按钮。</span><span class="sxs-lookup"><span data-stu-id="136c1-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>  
  
 <span data-ttu-id="136c1-157">到目前为止，应用程序中的按钮外观的控件已限制为更改该按钮的属性。</span><span class="sxs-lookup"><span data-stu-id="136c1-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="136c1-158">如果你想要按钮的外观做出更根本的更改？</span><span class="sxs-lookup"><span data-stu-id="136c1-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="136c1-159">模板启用功能强大控制表示法的对象。</span><span class="sxs-lookup"><span data-stu-id="136c1-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="136c1-160">因为样式中，可以使用模板，你可以将模板应用于 （在本演练中，按钮），该样式应用到的所有对象。</span><span class="sxs-lookup"><span data-stu-id="136c1-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="136c1-161">若要使用模板来定义按钮的外观</span><span class="sxs-lookup"><span data-stu-id="136c1-161">To use the template to define the look of the button</span></span>  
  
1.  <span data-ttu-id="136c1-162">**设置模板：**由于控件喜欢<xref:System.Windows.Controls.Button>具有<xref:System.Windows.Controls.Control.Template%2A>属性，可以定义模板属性值，就像我们已经设置了中的其他属性值一样<xref:System.Windows.Style>使用<xref:System.Windows.Setter>。</span><span class="sxs-lookup"><span data-stu-id="136c1-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="136c1-163">将以下突出显示的标记添加到按钮样式。</span><span class="sxs-lookup"><span data-stu-id="136c1-163">Add the following highlighted markup to your button style.</span></span>  
  
    ```xaml
    <Application.Resources>  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"   
        StartPoint="0,0" EndPoint="1,1">  
        <GradientStop Color="DarkGray" Offset="0" />  
        <GradientStop Color="#CCCCFF" Offset="0.5" />  
        <GradientStop Color="DarkGray" Offset="1" />  
      </LinearGradientBrush>  
      <Style TargetType="{x:Type Button}">  
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>  
      </Style>  
    </Application.Resources>  
    ```  
  
2.  <span data-ttu-id="136c1-164">**Alter 按钮演示文稿：**此时，你需要定义模板。</span><span class="sxs-lookup"><span data-stu-id="136c1-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="136c1-165">添加以下突出显示的标记。</span><span class="sxs-lookup"><span data-stu-id="136c1-165">Add the following highlighted markup.</span></span> <span data-ttu-id="136c1-166">此标记指定的两个<xref:System.Windows.Shapes.Rectangle>具有圆角的元素后跟<xref:System.Windows.Controls.DockPanel>。</span><span class="sxs-lookup"><span data-stu-id="136c1-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="136c1-167"><xref:System.Windows.Controls.DockPanel>使用到主机<xref:System.Windows.Controls.ContentPresenter>的按钮。</span><span class="sxs-lookup"><span data-stu-id="136c1-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="136c1-168">A<xref:System.Windows.Controls.ContentPresenter>显示按钮的内容。</span><span class="sxs-lookup"><span data-stu-id="136c1-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="136c1-169">在本演练中，内容是文本 （"按钮 1"、"按钮 2"、"按钮 3"）。</span><span class="sxs-lookup"><span data-stu-id="136c1-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="136c1-170">所有模板组件 (矩形和<xref:System.Windows.Controls.DockPanel>) 的内部布局<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="136c1-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>  
  
    ```xaml  
    <Setter.Value>  
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     <span data-ttu-id="136c1-171">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="136c1-171">Press F5 to run the application.</span></span> <span data-ttu-id="136c1-172">其外观应如下所示。</span><span class="sxs-lookup"><span data-stu-id="136c1-172">It should look like the following.</span></span>  
  
     <span data-ttu-id="136c1-173">![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span><span class="sxs-lookup"><span data-stu-id="136c1-173">![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span></span>  
  
3.  <span data-ttu-id="136c1-174">**向模板添加玻璃：**接下来，您将添加玻璃。</span><span class="sxs-lookup"><span data-stu-id="136c1-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="136c1-175">首先创建某些资源的创建玻璃渐变效果。</span><span class="sxs-lookup"><span data-stu-id="136c1-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="136c1-176">添加这些渐变中的资源任意位置`Application.Resources`块：</span><span class="sxs-lookup"><span data-stu-id="136c1-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>  
  
    ```xaml  
    <Application.Resources>  
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">     <GradientStop Color="WhiteSmoke" Offset="0.2" />     <GradientStop Color="Transparent" Offset="0.4" />     <GradientStop Color="WhiteSmoke" Offset="0.5" />     <GradientStop Color="Transparent" Offset="0.75" />     <GradientStop Color="WhiteSmoke" Offset="0.9" />     <GradientStop Color="Transparent" Offset="1" />   </GradientStopCollection>   <LinearGradientBrush x:Key="MyGlassBrushResource"     StartPoint="0,0" EndPoint="1,1" Opacity="0.75"     GradientStops="{StaticResource MyGlassGradientStopsResource}" />  
    <!-- Styles and other resources below here. -->  
    ```  
  
     <span data-ttu-id="136c1-177">这些资源将用作<xref:System.Windows.Shapes.Shape.Fill%2A>我们插入矩形<xref:System.Windows.Controls.Grid>的按钮模板。</span><span class="sxs-lookup"><span data-stu-id="136c1-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="136c1-178">向模板添加以下突出显示的标记。</span><span class="sxs-lookup"><span data-stu-id="136c1-178">Add the following highlighted markup to the template.</span></span>  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="{x:Type Button}">  
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"  
    ClipToBounds="True">  
  
        <!-- Outer Rectangle with rounded corners. -->  
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"   
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />  
  
        <!-- Inner Rectangle with rounded corners. -->  
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"   
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />  
  
        <!-- Glass Rectangle -->     <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"       VerticalAlignment="Stretch"       StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"       Fill="{StaticResource MyGlassBrushResource}"       RenderTransformOrigin="0.5,0.5">       <Rectangle.Stroke>         <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">           <LinearGradientBrush.GradientStops>             <GradientStop Offset="0.0" Color="LightBlue" />             <GradientStop Offset="1.0" Color="Gray" />           </LinearGradientBrush.GradientStops>         </LinearGradientBrush>       </Rectangle.Stroke>       <!-- These transforms have no effect as they are declared here.             The reason the transforms are included is to be targets             for animation (see later). -->       <Rectangle.RenderTransform>         <TransformGroup>           <ScaleTransform />           <RotateTransform />         </TransformGroup>       </Rectangle.RenderTransform>       <!-- A BevelBitmapEffect is applied to give the button a             "Beveled" look. -->       <Rectangle.BitmapEffect>         <BevelBitmapEffect />       </Rectangle.BitmapEffect>     </Rectangle>  
  
        <!-- Present Text of the button. -->  
        <DockPanel Name="myContentPresenterDockPanel">  
          <ContentPresenter x:Name="myContentPresenter" Margin="20"   
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
        </DockPanel>  
      </Grid>  
    </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     <span data-ttu-id="136c1-179">请注意，<xref:System.Windows.UIElement.Opacity%2A>的矩形`x:Name`"glassCube"属性为 0，当运行示例时，你看不到上面的玻璃矩形。</span><span class="sxs-lookup"><span data-stu-id="136c1-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="136c1-180">这是因为我们将更高版本将触发器添加到的模板使用按钮在用户交互时。</span><span class="sxs-lookup"><span data-stu-id="136c1-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="136c1-181">但是，你可以看到该按钮如下所示现在通过更改<xref:System.Windows.UIElement.Opacity%2A>到 1 和运行应用程序的值。</span><span class="sxs-lookup"><span data-stu-id="136c1-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="136c1-182">请参见下图。</span><span class="sxs-lookup"><span data-stu-id="136c1-182">See the following figure.</span></span> <span data-ttu-id="136c1-183">在继续之前执行下一步，更改<xref:System.Windows.UIElement.Opacity%2A>回 0。</span><span class="sxs-lookup"><span data-stu-id="136c1-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>  
  
     <span data-ttu-id="136c1-184">![使用 XAML 创建的自定义按钮](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="136c1-184">![Custom buttons that were created by using XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>  
  
## <a name="create-button-interactivity"></a><span data-ttu-id="136c1-185">创建按钮交互性</span><span class="sxs-lookup"><span data-stu-id="136c1-185">Create Button Interactivity</span></span>  
 <span data-ttu-id="136c1-186">在本部分中，你将创建属性触发器和事件触发器以更改属性值并响应用户操作，例如将鼠标指针移到按钮上方和单击运行动画。</span><span class="sxs-lookup"><span data-stu-id="136c1-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>  
  
 <span data-ttu-id="136c1-187">添加交互性 （鼠标悬停、 鼠标离开、 单击，依次类推） 的简单方法是定义模板或样式中的触发器。</span><span class="sxs-lookup"><span data-stu-id="136c1-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="136c1-188">若要创建<xref:System.Windows.Trigger>，如定义属性"条件": 按钮<xref:System.Windows.UIElement.IsMouseOver%2A>属性值等于`true`。</span><span class="sxs-lookup"><span data-stu-id="136c1-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="136c1-189">随后，你定义的触发器条件为 true 时要发生的 setter （操作）。</span><span class="sxs-lookup"><span data-stu-id="136c1-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>  
  
#### <a name="to-create-button-interactivity"></a><span data-ttu-id="136c1-190">若要创建按钮交互性</span><span class="sxs-lookup"><span data-stu-id="136c1-190">To create button interactivity</span></span>  
  
1.  <span data-ttu-id="136c1-191">**添加模板触发器：**将突出显示的标记添加到你的模板。</span><span class="sxs-lookup"><span data-stu-id="136c1-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="{x:Type Button}">  
        <Grid Width="{TemplateBinding Width}"   
          Height="{TemplateBinding Height}" ClipToBounds="True">  
  
          <!-- Outer Rectangle with rounded corners. -->  
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"   
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />  
  
          <!-- Inner Rectangle with rounded corners. -->  
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch" Stroke="Transparent"   
            StrokeThickness="20"   
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"   
          />  
  
          <!-- Glass Rectangle -->  
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"  
            VerticalAlignment="Stretch"  
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"  
            Fill="{StaticResource MyGlassBrushResource}"  
            RenderTransformOrigin="0.5,0.5">  
            <Rectangle.Stroke>  
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">  
                <LinearGradientBrush.GradientStops>  
                  <GradientStop Offset="0.0" Color="LightBlue" />  
                  <GradientStop Offset="1.0" Color="Gray" />  
                </LinearGradientBrush.GradientStops>  
              </LinearGradientBrush>  
            </Rectangle.Stroke>  
  
            <!-- These transforms have no effect as they   
                 are declared here.   
                 The reason the transforms are included is to be targets   
                 for animation (see later). -->  
            <Rectangle.RenderTransform>  
              <TransformGroup>  
                <ScaleTransform />  
                <RotateTransform />  
              </TransformGroup>  
            </Rectangle.RenderTransform>  
  
              <!-- A BevelBitmapEffect is applied to give the button a   
                   "Beveled" look. -->  
            <Rectangle.BitmapEffect>  
              <BevelBitmapEffect />  
            </Rectangle.BitmapEffect>  
          </Rectangle>  
  
          <!-- Present Text of the button. -->  
          <DockPanel Name="myContentPresenterDockPanel">  
            <ContentPresenter x:Name="myContentPresenter" Margin="20"   
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
          </DockPanel>  
        </Grid>  
  
        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
2.  <span data-ttu-id="136c1-192">**添加属性触发器：**添加到突出显示的标记`ControlTemplate.Triggers`块：</span><span class="sxs-lookup"><span data-stu-id="136c1-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     <span data-ttu-id="136c1-193">按 F5 运行应用程序，然后在你运行鼠标指针在按钮上查看的效果。</span><span class="sxs-lookup"><span data-stu-id="136c1-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>  
  
3.  <span data-ttu-id="136c1-194">**将焦点触发器添加：**接下来，我们将添加一些类似的 setter 以处理的情况，在按钮获得焦点 （例如，在用户单击它） 时。</span><span class="sxs-lookup"><span data-stu-id="136c1-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->  
      <Trigger Property="IsMouseOver" Value="True">  
  
        <!-- Below are three property settings that occur when the   
             condition is met (user mouses over button).  -->  
        <!-- Change the color of the outer rectangle when user          mouses over it. -->  
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
  
        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->  
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />  
  
        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->  
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">  
          <Setter.Value>  
            <BlurBitmapEffect Radius="1" />  
          </Setter.Value>  
        </Setter>  
      </Trigger>  
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>  
  
    </ControlTemplate.Triggers>  
    ```  
  
     <span data-ttu-id="136c1-195">按 F5 运行应用程序，然后单击一个按钮。</span><span class="sxs-lookup"><span data-stu-id="136c1-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="136c1-196">请注意后单击因为它仍然具有焦点的按钮始终保持突出显示。</span><span class="sxs-lookup"><span data-stu-id="136c1-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="136c1-197">如果单击另一个按钮时，新建按钮将获得焦点，而最后一个失去它。</span><span class="sxs-lookup"><span data-stu-id="136c1-197">If you click another button, the new button gains focus while the last one loses it.</span></span>  
  
4.  <span data-ttu-id="136c1-198">**添加的动画效果**<xref:System.Windows.UIElement.MouseEnter> **和** <xref:System.Windows.UIElement.MouseLeave> **:**接下来我们将某些动画添加到触发器。</span><span class="sxs-lookup"><span data-stu-id="136c1-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="136c1-199">添加以下标记内部的任意位置`ControlTemplate.Triggers`块。</span><span class="sxs-lookup"><span data-stu-id="136c1-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>  
  
    ```  
    <!-- Animations that start when mouse enters and leaves button. -->  
    <EventTrigger RoutedEvent="Mouse.MouseEnter">  
      <EventTrigger.Actions>  
        <BeginStoryboard Name="mouseEnterBeginStoryboard">  
          <Storyboard>  
          <!-- This animation makes the glass rectangle shrink in the X direction. -->  
            <DoubleAnimation Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"  
              By="-0.1" Duration="0:0:0.5" />  
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->  
            <DoubleAnimation  
            Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"   
              By="-0.1" Duration="0:0:0.5" />  
          </Storyboard>  
        </BeginStoryboard>  
      </EventTrigger.Actions>  
    </EventTrigger>  
    <EventTrigger RoutedEvent="Mouse.MouseLeave">  
      <EventTrigger.Actions>  
        <!-- Stopping the storyboard sets all animated properties back to default. -->  
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />  
      </EventTrigger.Actions>  
    </EventTrigger>  
    ```  
  
     <span data-ttu-id="136c1-200">玻璃矩形收缩当鼠标指针移到按钮，并将返回到正常大小，当指针离开。</span><span class="sxs-lookup"><span data-stu-id="136c1-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>  
  
     <span data-ttu-id="136c1-201">有两个指针移到该按钮时，触发的动画 (<xref:System.Windows.UIElement.MouseEnter>引发事件)。</span><span class="sxs-lookup"><span data-stu-id="136c1-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="136c1-202">这些动画收缩沿 X 和 Y 轴的玻璃矩形。</span><span class="sxs-lookup"><span data-stu-id="136c1-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="136c1-203">请注意，属性在<xref:System.Windows.Media.Animation.DoubleAnimation>元素-<xref:System.Windows.Media.Animation.Timeline.Duration%2A>和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>。</span><span class="sxs-lookup"><span data-stu-id="136c1-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="136c1-204"><xref:System.Windows.Media.Animation.Timeline.Duration%2A>指定动画发生超过半秒，和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>指定玻璃收缩 10%。</span><span class="sxs-lookup"><span data-stu-id="136c1-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>  
  
     <span data-ttu-id="136c1-205">第二个事件触发器 (<xref:System.Windows.UIElement.MouseLeave>) 就会停止运行的第一个。</span><span class="sxs-lookup"><span data-stu-id="136c1-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="136c1-206">当您停止<xref:System.Windows.Media.Animation.Storyboard>，所有动画的属性将返回到其默认值。</span><span class="sxs-lookup"><span data-stu-id="136c1-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="136c1-207">因此，当用户将指针离开按钮，该按钮将返回前鼠标指针移到按钮它所处的方式。</span><span class="sxs-lookup"><span data-stu-id="136c1-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="136c1-208">有关动画的详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="136c1-208">For more information about animations, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
5.  <span data-ttu-id="136c1-209">**添加动画时单击该按钮：**的最后一步是添加当用户单击按钮的触发器。</span><span class="sxs-lookup"><span data-stu-id="136c1-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="136c1-210">添加以下标记内部的任意位置`ControlTemplate.Triggers`块：</span><span class="sxs-lookup"><span data-stu-id="136c1-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>  
  
    ```  
    <!-- Animation fires when button is clicked, causing glass to spin.  -->  
    <EventTrigger RoutedEvent="Button.Click">  
      <EventTrigger.Actions>  
        <BeginStoryboard>  
          <Storyboard>  
            <DoubleAnimation Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"   
              By="360" Duration="0:0:0.5" />  
          </Storyboard>  
        </BeginStoryboard>  
      </EventTrigger.Actions>  
    </EventTrigger>  
    ```  
  
     <span data-ttu-id="136c1-211">按 f5 键以运行该应用程序，并单击一个按钮。</span><span class="sxs-lookup"><span data-stu-id="136c1-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="136c1-212">当你单击按钮时，会旋转玻璃矩形。</span><span class="sxs-lookup"><span data-stu-id="136c1-212">When you click a button, the glass rectangle spins around.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="136c1-213">摘要</span><span class="sxs-lookup"><span data-stu-id="136c1-213">Summary</span></span>  
 <span data-ttu-id="136c1-214">在本演练中，您可以执行以下练习：</span><span class="sxs-lookup"><span data-stu-id="136c1-214">In this walkthrough, you performed the following exercises:</span></span>  
  
-   <span data-ttu-id="136c1-215">目标<xref:System.Windows.Style>到对象类型 (<xref:System.Windows.Controls.Button>)。</span><span class="sxs-lookup"><span data-stu-id="136c1-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>  
  
-   <span data-ttu-id="136c1-216">控制在整个应用程序中使用的按钮的基本属性<xref:System.Windows.Style>。</span><span class="sxs-lookup"><span data-stu-id="136c1-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>  
  
-   <span data-ttu-id="136c1-217">创建资源，如渐变来对属性值的使用<xref:System.Windows.Style>setter。</span><span class="sxs-lookup"><span data-stu-id="136c1-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>  
  
-   <span data-ttu-id="136c1-218">通过将模板应用于按钮自定义在整个应用程序中的按钮的外观。</span><span class="sxs-lookup"><span data-stu-id="136c1-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>  
  
-   <span data-ttu-id="136c1-219">自定义以响应用户操作的按钮的行为 (如<xref:System.Windows.UIElement.MouseEnter>， <xref:System.Windows.UIElement.MouseLeave>，和<xref:System.Windows.Controls.Primitives.ButtonBase.Click>)，包含动画效果。</span><span class="sxs-lookup"><span data-stu-id="136c1-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="136c1-220">请参阅</span><span class="sxs-lookup"><span data-stu-id="136c1-220">See Also</span></span>  
 [<span data-ttu-id="136c1-221">使用 Microsoft Expression Blend 创建按钮</span><span class="sxs-lookup"><span data-stu-id="136c1-221">Create a Button by Using Microsoft Expression Blend</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 [<span data-ttu-id="136c1-222">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="136c1-222">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="136c1-223">动画概述</span><span class="sxs-lookup"><span data-stu-id="136c1-223">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="136c1-224">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="136c1-224">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="136c1-225">位图效果概述</span><span class="sxs-lookup"><span data-stu-id="136c1-225">Bitmap Effects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)
