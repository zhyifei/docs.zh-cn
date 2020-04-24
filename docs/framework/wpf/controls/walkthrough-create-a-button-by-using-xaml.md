---
title: 演练：使用 XAML 创建按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a8cc227703e81e5de9dea7e44e10dfecca2cd05c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646469"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="66c88-102">演练：使用 XAML 创建按钮</span><span class="sxs-lookup"><span data-stu-id="66c88-102">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="66c88-103">本演练的目的是了解如何创建用于 Windows 演示文稿基础 （WPF） 应用程序的动画按钮。</span><span class="sxs-lookup"><span data-stu-id="66c88-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="66c88-104">本演练使用样式和模板创建自定义按钮资源，允许重用代码并将按钮逻辑与按钮声明分离。</span><span class="sxs-lookup"><span data-stu-id="66c88-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="66c88-105">本演练完全写在 中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="66c88-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66c88-106">本演练将指导您完成通过键入或复制并粘贴[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]到 Visual Studio 来创建应用程序的步骤。</span><span class="sxs-lookup"><span data-stu-id="66c88-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Visual Studio.</span></span> <span data-ttu-id="66c88-107">如果您希望了解如何使用设计器创建相同的应用程序，请参阅[使用 Microsoft 表达式混合创建按钮](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)。</span><span class="sxs-lookup"><span data-stu-id="66c88-107">If you would prefer to learn how to use a designer to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="66c88-108">下图显示了已完成的按钮。</span><span class="sxs-lookup"><span data-stu-id="66c88-108">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="66c88-109">![使用 XAML 创建的自定义按钮](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="66c88-109">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="66c88-110">创建基本按钮</span><span class="sxs-lookup"><span data-stu-id="66c88-110">Create Basic Buttons</span></span>

<span data-ttu-id="66c88-111">让我们从创建新项目并向窗口添加几个按钮开始。</span><span class="sxs-lookup"><span data-stu-id="66c88-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="66c88-112">创建新的 WPF 项目并将按钮添加到窗口</span><span class="sxs-lookup"><span data-stu-id="66c88-112">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="66c88-113">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="66c88-113">Start Visual Studio.</span></span>

2. <span data-ttu-id="66c88-114">**创建新的 WPF 项目：** 在 **"文件"** 菜单上，指向 **"新建**"，然后单击"**项目**"。</span><span class="sxs-lookup"><span data-stu-id="66c88-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="66c88-115">查找**Windows 应用程序 （WPF）** 模板并将项目命名为"动画按钮"。</span><span class="sxs-lookup"><span data-stu-id="66c88-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="66c88-116">这将为应用程序创建骨架。</span><span class="sxs-lookup"><span data-stu-id="66c88-116">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="66c88-117">**添加基本默认按钮：** 本演练所需的所有文件都由模板提供。</span><span class="sxs-lookup"><span data-stu-id="66c88-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="66c88-118">通过在解决方案资源管理器中双击 Window1.xaml 文件来打开该文件。</span><span class="sxs-lookup"><span data-stu-id="66c88-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="66c88-119">默认情况下，Window1.xaml 中存在一个<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="66c88-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="66c88-120">通过键入<xref:System.Windows.Controls.Grid>或复制并将以下突出显示的代码粘贴到[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]Window1.xaml，删除元素并将几个按钮添加到页面：</span><span class="sxs-lookup"><span data-stu-id="66c88-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     <span data-ttu-id="66c88-121">按 F5 运行应用程序;您应该会看到一组按钮，如下所示。</span><span class="sxs-lookup"><span data-stu-id="66c88-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="66c88-122">![三个基本按钮](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="66c88-122">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="66c88-123">现在，您已经创建了基本按钮，您已完成在 Window1.xaml 文件中的工作。</span><span class="sxs-lookup"><span data-stu-id="66c88-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="66c88-124">演练的其余部分将侧重于 app.xaml 文件，定义样式和按钮的模板。</span><span class="sxs-lookup"><span data-stu-id="66c88-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="66c88-125">设置基本属性</span><span class="sxs-lookup"><span data-stu-id="66c88-125">Set Basic Properties</span></span>

<span data-ttu-id="66c88-126">接下来，让我们在这些按钮上设置一些属性，以控制按钮的外观和布局。</span><span class="sxs-lookup"><span data-stu-id="66c88-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="66c88-127">您将使用资源为整个应用程序定义按钮属性，而不是单独设置按钮上的属性。</span><span class="sxs-lookup"><span data-stu-id="66c88-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="66c88-128">应用程序资源在概念上类似于网页的外部级联样式表 （CSS）;但是，资源比级联样式表 （CSS） 更强大，正如在本演练结束时看到的。</span><span class="sxs-lookup"><span data-stu-id="66c88-128">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="66c88-129">要了解有关资源的更多信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。</span><span class="sxs-lookup"><span data-stu-id="66c88-129">To learn more about resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="66c88-130">使用样式在按钮上设置基本属性</span><span class="sxs-lookup"><span data-stu-id="66c88-130">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="66c88-131">**定义应用程序.资源块：** 打开 app.xaml 并添加以下突出显示的标记（如果尚未出现）：</span><span class="sxs-lookup"><span data-stu-id="66c88-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

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

     <span data-ttu-id="66c88-132">资源范围由定义资源的位置确定。</span><span class="sxs-lookup"><span data-stu-id="66c88-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="66c88-133">在 app.xaml`Application.Resources`文件中定义资源，可以从应用程序中的任何位置使用资源。</span><span class="sxs-lookup"><span data-stu-id="66c88-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="66c88-134">要了解有关定义资源范围的更多信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。</span><span class="sxs-lookup"><span data-stu-id="66c88-134">To learn more about defining the scope of your resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

2. <span data-ttu-id="66c88-135">**创建样式并使用它定义基本属性值：** 将以下标记添加到块中`Application.Resources`。</span><span class="sxs-lookup"><span data-stu-id="66c88-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="66c88-136">此标记创建<xref:System.Windows.Style>应用于应用程序中的所有按钮，将按钮设置为 90，将<xref:System.Windows.FrameworkElement.Width%2A><xref:System.Windows.FrameworkElement.Margin%2A>设置为 10：</span><span class="sxs-lookup"><span data-stu-id="66c88-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="66c88-137">属性<xref:System.Windows.Style.TargetType%2A>指定样式应用于 类型<xref:System.Windows.Controls.Button>的所有对象。</span><span class="sxs-lookup"><span data-stu-id="66c88-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="66c88-138">每个<xref:System.Windows.Setter>设置 不同的属性值。 <xref:System.Windows.Style></span><span class="sxs-lookup"><span data-stu-id="66c88-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="66c88-139">因此，此时应用程序中的每个按钮的宽度为 90，边距为 10。</span><span class="sxs-lookup"><span data-stu-id="66c88-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="66c88-140">如果按 F5 运行应用程序，您将看到以下窗口。</span><span class="sxs-lookup"><span data-stu-id="66c88-140">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="66c88-141">![宽度为 90、边距为 10 的按钮](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="66c88-141">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="66c88-142">可以使用样式执行更多操作，包括调整目标对象、指定复杂属性值，甚至使用样式作为其他样式的输入的各种方法。</span><span class="sxs-lookup"><span data-stu-id="66c88-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="66c88-143">有关详细信息，请参阅[样式和模板](../../../desktop-wpf/fundamentals/styles-templates-overview.md)化。</span><span class="sxs-lookup"><span data-stu-id="66c88-143">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

3. <span data-ttu-id="66c88-144">**将样式属性值设置为资源：** 资源支持一种简单方法来重用通常定义的对象和值。</span><span class="sxs-lookup"><span data-stu-id="66c88-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="66c88-145">使用资源定义复杂值以使代码更加模块化尤其有用。</span><span class="sxs-lookup"><span data-stu-id="66c88-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="66c88-146">将以下突出显示的标记添加到 app.xaml。</span><span class="sxs-lookup"><span data-stu-id="66c88-146">Add the following highlighted markup to app.xaml.</span></span>

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

     <span data-ttu-id="66c88-147">直接在`Application.Resources`块下，您创建了一个名为"灰蓝渐变画笔"的资源。</span><span class="sxs-lookup"><span data-stu-id="66c88-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="66c88-148">此资源定义水平渐变。</span><span class="sxs-lookup"><span data-stu-id="66c88-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="66c88-149">此资源可以从应用程序的任何位置用作属性值，包括在<xref:System.Windows.Controls.Control.Background%2A>属性的按钮样式设置器内。</span><span class="sxs-lookup"><span data-stu-id="66c88-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="66c88-150">现在，所有按钮都有此渐变<xref:System.Windows.Controls.Control.Background%2A>的属性值。</span><span class="sxs-lookup"><span data-stu-id="66c88-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="66c88-151">按 F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="66c88-151">Press F5 to run the application.</span></span> <span data-ttu-id="66c88-152">它应该如下所示。</span><span class="sxs-lookup"><span data-stu-id="66c88-152">It should look like the following.</span></span>

     <span data-ttu-id="66c88-153">![具有渐变背景的按钮](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="66c88-153">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="66c88-154">创建定义按钮外观的模板</span><span class="sxs-lookup"><span data-stu-id="66c88-154">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="66c88-155">在本节中，您将创建一个模板，用于自定义按钮的外观（表示）。</span><span class="sxs-lookup"><span data-stu-id="66c88-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="66c88-156">按钮表示由多个对象组成，包括矩形和其他组件，使按钮的外观独一无二。</span><span class="sxs-lookup"><span data-stu-id="66c88-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="66c88-157">到目前为止，对按钮在应用程序中的外观的控制仅限于更改按钮的属性。</span><span class="sxs-lookup"><span data-stu-id="66c88-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="66c88-158">如果你想对按钮的外观进行更彻底的更改，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="66c88-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="66c88-159">模板能够对对象的表示进行强大的控制。</span><span class="sxs-lookup"><span data-stu-id="66c88-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="66c88-160">由于模板可以在样式中使用，因此可以将模板应用于样式应用于的所有对象（在本演练中，按钮）。</span><span class="sxs-lookup"><span data-stu-id="66c88-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="66c88-161">使用模板定义按钮的外观</span><span class="sxs-lookup"><span data-stu-id="66c88-161">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="66c88-162">**设置模板：** 由于控件（<xref:System.Windows.Controls.Button>如具有<xref:System.Windows.Controls.Control.Template%2A>属性）可以定义模板属性值，就像我们<xref:System.Windows.Style>使用 中设置的其他属性值一<xref:System.Windows.Setter>样。</span><span class="sxs-lookup"><span data-stu-id="66c88-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="66c88-163">将以下突出显示的标记添加到按钮样式中。</span><span class="sxs-lookup"><span data-stu-id="66c88-163">Add the following highlighted markup to your button style.</span></span>

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

2. <span data-ttu-id="66c88-164">**更改按钮演示文稿：** 此时，您需要定义模板。</span><span class="sxs-lookup"><span data-stu-id="66c88-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="66c88-165">添加以下突出显示的标记。</span><span class="sxs-lookup"><span data-stu-id="66c88-165">Add the following highlighted markup.</span></span> <span data-ttu-id="66c88-166">此标记指定两<xref:System.Windows.Shapes.Rectangle>个圆边元素，后跟 。 <xref:System.Windows.Controls.DockPanel></span><span class="sxs-lookup"><span data-stu-id="66c88-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="66c88-167"><xref:System.Windows.Controls.DockPanel>用于承载<xref:System.Windows.Controls.ContentPresenter>按钮的 。</span><span class="sxs-lookup"><span data-stu-id="66c88-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="66c88-168">显示<xref:System.Windows.Controls.ContentPresenter>按钮的内容。</span><span class="sxs-lookup"><span data-stu-id="66c88-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="66c88-169">在本演练中，内容是文本（"按钮 1"，"按钮 2"，"按钮 3"）。</span><span class="sxs-lookup"><span data-stu-id="66c88-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="66c88-170">所有模板组件（矩形和<xref:System.Windows.Controls.DockPanel>） 都位于 的<xref:System.Windows.Controls.Grid>内部。</span><span class="sxs-lookup"><span data-stu-id="66c88-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

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

     <span data-ttu-id="66c88-171">按 F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="66c88-171">Press F5 to run the application.</span></span> <span data-ttu-id="66c88-172">它应该如下所示。</span><span class="sxs-lookup"><span data-stu-id="66c88-172">It should look like the following.</span></span>

     ![带 3 个按钮的窗口](./media/custom-button-animatedbutton-4.gif)

3. <span data-ttu-id="66c88-174">**向模板添加玻璃效果：** 接下来，您将添加玻璃。</span><span class="sxs-lookup"><span data-stu-id="66c88-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="66c88-175">首先，创建一些创建玻璃渐变效果的资源。</span><span class="sxs-lookup"><span data-stu-id="66c88-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="66c88-176">在`Application.Resources`块内的任意位置添加这些渐变资源：</span><span class="sxs-lookup"><span data-stu-id="66c88-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     <span data-ttu-id="66c88-177">这些资源用作<xref:System.Windows.Shapes.Shape.Fill%2A>我们插入到按钮模板<xref:System.Windows.Controls.Grid>中的矩形。</span><span class="sxs-lookup"><span data-stu-id="66c88-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="66c88-178">向模板添加以下突出显示的标记。</span><span class="sxs-lookup"><span data-stu-id="66c88-178">Add the following highlighted markup to the template.</span></span>

    ```xaml
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
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
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
    </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="66c88-179">请注意，<xref:System.Windows.UIElement.Opacity%2A>具有"glassCube"`x:Name`属性的矩形为 0，因此当您运行示例时，您看不到覆盖在顶部的玻璃矩形。</span><span class="sxs-lookup"><span data-stu-id="66c88-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="66c88-180">这是因为我们稍后将向模板添加触发器，用于用户与按钮交互时。</span><span class="sxs-lookup"><span data-stu-id="66c88-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="66c88-181">但是，通过将<xref:System.Windows.UIElement.Opacity%2A>值更改为 1 并运行应用程序，您可以看到按钮现在的外观。</span><span class="sxs-lookup"><span data-stu-id="66c88-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="66c88-182">请参阅下图。</span><span class="sxs-lookup"><span data-stu-id="66c88-182">See the following figure.</span></span> <span data-ttu-id="66c88-183">在继续下一步之前，将<xref:System.Windows.UIElement.Opacity%2A>返回更改为 0。</span><span class="sxs-lookup"><span data-stu-id="66c88-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="66c88-184">![使用 XAML 创建的自定义按钮](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="66c88-184">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="66c88-185">创建按钮交互性</span><span class="sxs-lookup"><span data-stu-id="66c88-185">Create Button Interactivity</span></span>

<span data-ttu-id="66c88-186">在本节中，您将创建属性触发器和事件触发器以更改属性值并运行动画以响应用户操作，例如将鼠标指针移到按钮上并单击。</span><span class="sxs-lookup"><span data-stu-id="66c88-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="66c88-187">添加交互性（鼠标悬停、鼠标离开、单击等）的一种简单方法是在模板或样式中定义触发器。</span><span class="sxs-lookup"><span data-stu-id="66c88-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="66c88-188">要创建<xref:System.Windows.Trigger>，定义属性"条件"，例如：按钮<xref:System.Windows.UIElement.IsMouseOver%2A>属性值等于`true`。</span><span class="sxs-lookup"><span data-stu-id="66c88-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="66c88-189">然后定义在触发条件为 true 时发生的设置器（操作）。</span><span class="sxs-lookup"><span data-stu-id="66c88-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="66c88-190">创建按钮交互性</span><span class="sxs-lookup"><span data-stu-id="66c88-190">To create button interactivity</span></span>

1. <span data-ttu-id="66c88-191">**添加模板触发器：** 将突出显示的标记添加到模板中。</span><span class="sxs-lookup"><span data-stu-id="66c88-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>

    ```xaml
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

2. <span data-ttu-id="66c88-192">**添加属性触发器：** 将突出显示的标记添加到`ControlTemplate.Triggers`块：</span><span class="sxs-lookup"><span data-stu-id="66c88-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="66c88-193">按 F5 以运行应用程序，并在在按钮上运行鼠标指针时看到效果。</span><span class="sxs-lookup"><span data-stu-id="66c88-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="66c88-194">**添加焦点触发器：** 接下来，我们将添加一些类似的设置器来处理按钮具有焦点时（例如，在用户单击按钮后）的情况。</span><span class="sxs-lookup"><span data-stu-id="66c88-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

    ```xaml
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

     <span data-ttu-id="66c88-195">按 F5 运行应用程序，然后单击其中一个按钮。</span><span class="sxs-lookup"><span data-stu-id="66c88-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="66c88-196">请注意，单击该按钮后，该按钮将保持突出显示，因为它仍有焦点。</span><span class="sxs-lookup"><span data-stu-id="66c88-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="66c88-197">如果单击另一个按钮，则新按钮在上次按钮丢失时获得焦点。</span><span class="sxs-lookup"><span data-stu-id="66c88-197">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="66c88-198">**为**<xref:System.Windows.UIElement.MouseEnter>**和**<xref:System.Windows.UIElement.MouseLeave>添加动画 **：** 接下来，我们将一些动画添加到触发器中。  </span><span class="sxs-lookup"><span data-stu-id="66c88-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="66c88-199">在`ControlTemplate.Triggers`块内的任意位置添加以下标记。</span><span class="sxs-lookup"><span data-stu-id="66c88-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

    ```xaml
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

     <span data-ttu-id="66c88-200">当鼠标指针在按钮上移动时，玻璃矩形将缩小，当指针离开时返回正常大小。</span><span class="sxs-lookup"><span data-stu-id="66c88-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="66c88-201">指针超过按钮时将触发两个动画（<xref:System.Windows.UIElement.MouseEnter>引发事件）。</span><span class="sxs-lookup"><span data-stu-id="66c88-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="66c88-202">这些动画沿 X 轴和 Y 轴收缩玻璃矩形。</span><span class="sxs-lookup"><span data-stu-id="66c88-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="66c88-203">请注意<xref:System.Windows.Media.Animation.DoubleAnimation>元素和<xref:System.Windows.Media.Animation.Timeline.Duration%2A>和 上的属性<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>。</span><span class="sxs-lookup"><span data-stu-id="66c88-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="66c88-204">指定<xref:System.Windows.Media.Animation.Timeline.Duration%2A>动画在半秒以上发生，并<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>指定玻璃收缩 10%。</span><span class="sxs-lookup"><span data-stu-id="66c88-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="66c88-205">第二个事件触发器<xref:System.Windows.UIElement.MouseLeave>（ ） 只是停止第一个事件触发器。</span><span class="sxs-lookup"><span data-stu-id="66c88-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="66c88-206">停止 时，<xref:System.Windows.Media.Animation.Storyboard>所有动画属性将返回到其默认值。</span><span class="sxs-lookup"><span data-stu-id="66c88-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="66c88-207">因此，当用户将指针移出按钮时，该按钮将回到鼠标指针移到按钮之前的方式。</span><span class="sxs-lookup"><span data-stu-id="66c88-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="66c88-208">有关动画的详细信息，请参阅[动画概述](../graphics-multimedia/animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="66c88-208">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="66c88-209">**添加单击按钮时的动画：** 最后一步是添加用户单击按钮时的触发器。</span><span class="sxs-lookup"><span data-stu-id="66c88-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="66c88-210">在`ControlTemplate.Triggers`块内的任意位置添加以下标记：</span><span class="sxs-lookup"><span data-stu-id="66c88-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
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

     <span data-ttu-id="66c88-211">按 F5 运行应用程序，然后单击其中一个按钮。</span><span class="sxs-lookup"><span data-stu-id="66c88-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="66c88-212">单击按钮时，玻璃矩形会旋转。</span><span class="sxs-lookup"><span data-stu-id="66c88-212">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="66c88-213">总结</span><span class="sxs-lookup"><span data-stu-id="66c88-213">Summary</span></span>
 <span data-ttu-id="66c88-214">在本演练中，您执行以下练习：</span><span class="sxs-lookup"><span data-stu-id="66c88-214">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="66c88-215">将<xref:System.Windows.Style>目标对象类型 （<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="66c88-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="66c88-216">使用 控制整个应用程序中按钮的基本属性<xref:System.Windows.Style>。</span><span class="sxs-lookup"><span data-stu-id="66c88-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="66c88-217">创建的资源（如渐变）用于<xref:System.Windows.Style>设置器的属性值。</span><span class="sxs-lookup"><span data-stu-id="66c88-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="66c88-218">通过将模板应用于按钮，自定义整个应用程序中的按钮外观。</span><span class="sxs-lookup"><span data-stu-id="66c88-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="66c88-219">按钮的自定义行为，以响应包含动画效果的用户操作（如<xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave>、和<xref:System.Windows.Controls.Primitives.ButtonBase.Click>）。</span><span class="sxs-lookup"><span data-stu-id="66c88-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="66c88-220">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66c88-220">See also</span></span>

- [<span data-ttu-id="66c88-221">使用 Microsoft Expression Blend 创建按钮</span><span class="sxs-lookup"><span data-stu-id="66c88-221">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="66c88-222">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="66c88-222">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="66c88-223">动画概述</span><span class="sxs-lookup"><span data-stu-id="66c88-223">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="66c88-224">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="66c88-224">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="66c88-225">位图效果概述</span><span class="sxs-lookup"><span data-stu-id="66c88-225">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
