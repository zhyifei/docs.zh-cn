---
title: 演练：使用 XAML 创建按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 6738b9e66c1223ea4ec50c070a421d119fd30bc4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458695"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="67152-102">演练：使用 XAML 创建按钮</span><span class="sxs-lookup"><span data-stu-id="67152-102">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="67152-103">本演练的目的是了解如何创建在 Windows Presentation Foundation （WPF）应用程序中使用的动画按钮。</span><span class="sxs-lookup"><span data-stu-id="67152-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="67152-104">本演练使用样式和模板来创建自定义的按钮资源，以允许在按钮声明中重复使用代码和按钮逻辑分离。</span><span class="sxs-lookup"><span data-stu-id="67152-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="67152-105">本演练完全以 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]编写。</span><span class="sxs-lookup"><span data-stu-id="67152-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67152-106">本演练将指导你完成创建应用程序的步骤，方法是在 Visual Studio 中键入或复制并粘贴 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="67152-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Visual Studio.</span></span> <span data-ttu-id="67152-107">如果希望了解如何使用设计器创建相同的应用程序，请参阅[使用 Microsoft Expression Blend 创建按钮](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)。</span><span class="sxs-lookup"><span data-stu-id="67152-107">If you would prefer to learn how to use a designer to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="67152-108">下图显示了 "已完成" 按钮。</span><span class="sxs-lookup"><span data-stu-id="67152-108">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="67152-109">![使用 XAML 创建的自定义按钮](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="67152-109">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="67152-110">创建基本按钮</span><span class="sxs-lookup"><span data-stu-id="67152-110">Create Basic Buttons</span></span>

<span data-ttu-id="67152-111">首先创建一个新项目，并向该窗口添加几个按钮。</span><span class="sxs-lookup"><span data-stu-id="67152-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="67152-112">创建新的 WPF 项目并向窗口中添加按钮</span><span class="sxs-lookup"><span data-stu-id="67152-112">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="67152-113">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="67152-113">Start Visual Studio.</span></span>

2. <span data-ttu-id="67152-114">**创建新的 WPF 项目：** 在 "**文件**" 菜单上，指向 "**新建**"，然后单击 "**项目**"。</span><span class="sxs-lookup"><span data-stu-id="67152-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="67152-115">找到**Windows 应用程序（WPF）** 模板，并将项目命名为 "AnimatedButton"。</span><span class="sxs-lookup"><span data-stu-id="67152-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="67152-116">这将创建应用程序的主干。</span><span class="sxs-lookup"><span data-stu-id="67152-116">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="67152-117">**添加基本的默认按钮：** 此演练所需的所有文件都由模板提供。</span><span class="sxs-lookup"><span data-stu-id="67152-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="67152-118">在解决方案资源管理器中双击 Window1.xaml 文件，将其打开。</span><span class="sxs-lookup"><span data-stu-id="67152-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="67152-119">默认情况下，Window1.xaml 中有一个 <xref:System.Windows.Controls.Grid> 元素。</span><span class="sxs-lookup"><span data-stu-id="67152-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="67152-120">通过键入或复制以下突出显示的代码并将其粘贴到 Window1.xaml，删除 <xref:System.Windows.Controls.Grid> 元素并向 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 页添加几个按钮：</span><span class="sxs-lookup"><span data-stu-id="67152-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

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

     <span data-ttu-id="67152-121">按 F5 运行该应用程序;应会看到如下图所示的一组按钮。</span><span class="sxs-lookup"><span data-stu-id="67152-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="67152-122">![三个基本按钮](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="67152-122">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="67152-123">现在，您已创建了基本按钮，接下来在 Window1.xaml 文件中完成工作。</span><span class="sxs-lookup"><span data-stu-id="67152-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="67152-124">本演练的其余部分侧重于 app.xaml 文件，为按钮定义样式和模板。</span><span class="sxs-lookup"><span data-stu-id="67152-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="67152-125">设置基本属性</span><span class="sxs-lookup"><span data-stu-id="67152-125">Set Basic Properties</span></span>

<span data-ttu-id="67152-126">接下来，让我们在这些按钮上设置一些属性，以控制按钮的外观和布局。</span><span class="sxs-lookup"><span data-stu-id="67152-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="67152-127">您将使用资源来定义整个应用程序的按钮属性，而不是单独设置按钮的属性。</span><span class="sxs-lookup"><span data-stu-id="67152-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="67152-128">应用程序资源在概念上类似于网页的外部级联样式表（CSS）;但是，资源比级联样式表（CSS）要强大得多，如本演练结束时所见。</span><span class="sxs-lookup"><span data-stu-id="67152-128">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="67152-129">若要了解有关资源的详细信息，请参阅[XAML 资源](../advanced/xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="67152-129">To learn more about resources, see [XAML Resources](../advanced/xaml-resources.md).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="67152-130">使用样式设置按钮的基本属性</span><span class="sxs-lookup"><span data-stu-id="67152-130">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="67152-131">**定义应用程序 .resources 块：** 打开 app.xaml 并添加以下突出显示的标记（如果尚未存在）：</span><span class="sxs-lookup"><span data-stu-id="67152-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

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

     <span data-ttu-id="67152-132">资源范围由定义资源的位置确定。</span><span class="sxs-lookup"><span data-stu-id="67152-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="67152-133">在 app.xaml 文件的 `Application.Resources` 中定义资源后，可在应用程序中的任何位置使用资源。</span><span class="sxs-lookup"><span data-stu-id="67152-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="67152-134">若要了解有关定义资源范围的详细信息，请参阅[XAML 资源](../advanced/xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="67152-134">To learn more about defining the scope of your resources, see [XAML Resources](../advanced/xaml-resources.md).</span></span>

2. <span data-ttu-id="67152-135">**创建样式，并使用它定义基本属性值：** 将以下标记添加到 `Application.Resources` 块。</span><span class="sxs-lookup"><span data-stu-id="67152-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="67152-136">此标记将创建一个应用于应用程序中所有按钮的 <xref:System.Windows.Style>，并将这些按钮的 <xref:System.Windows.FrameworkElement.Width%2A> 设置为90，将 <xref:System.Windows.FrameworkElement.Margin%2A> 设置为10：</span><span class="sxs-lookup"><span data-stu-id="67152-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="67152-137"><xref:System.Windows.Style.TargetType%2A> 属性指定样式应用于 <xref:System.Windows.Controls.Button>类型的所有对象。</span><span class="sxs-lookup"><span data-stu-id="67152-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="67152-138">每个 <xref:System.Windows.Setter> 为 <xref:System.Windows.Style>设置不同的属性值。</span><span class="sxs-lookup"><span data-stu-id="67152-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="67152-139">因此，应用程序中的每个按钮的宽度均为90，边距为10。</span><span class="sxs-lookup"><span data-stu-id="67152-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="67152-140">如果按 F5 运行该应用程序，将看到以下窗口。</span><span class="sxs-lookup"><span data-stu-id="67152-140">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="67152-141">![宽度为90，边距为10的按钮](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="67152-141">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="67152-142">您还可以对样式进行更多的操作，其中包括多种方法来微调目标对象、指定复杂的属性值，甚至使用样式作为其他样式的输入。</span><span class="sxs-lookup"><span data-stu-id="67152-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="67152-143">有关详细信息，请参阅[样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="67152-143">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

3. <span data-ttu-id="67152-144">**将样式属性值设置为资源：** 通过资源，可以使用一种简单的方法来重复使用通常定义的对象和值。</span><span class="sxs-lookup"><span data-stu-id="67152-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="67152-145">使用资源来定义复杂值非常有用，使代码更具模块化。</span><span class="sxs-lookup"><span data-stu-id="67152-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="67152-146">将以下突出显示的标记添加到 app.config。</span><span class="sxs-lookup"><span data-stu-id="67152-146">Add the following highlighted markup to app.xaml.</span></span>

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

     <span data-ttu-id="67152-147">直接在 `Application.Resources` 块下创建名为 "GrayBlueGradientBrush" 的资源。</span><span class="sxs-lookup"><span data-stu-id="67152-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="67152-148">此资源定义水平渐变。</span><span class="sxs-lookup"><span data-stu-id="67152-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="67152-149">此资源可用作应用程序中任何位置的属性值，包括 <xref:System.Windows.Controls.Control.Background%2A> 属性的按钮样式 setter 内。</span><span class="sxs-lookup"><span data-stu-id="67152-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="67152-150">现在，所有按钮都具有此渐变的 <xref:System.Windows.Controls.Control.Background%2A> 属性值。</span><span class="sxs-lookup"><span data-stu-id="67152-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="67152-151">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="67152-151">Press F5 to run the application.</span></span> <span data-ttu-id="67152-152">其外观应如下所示。</span><span class="sxs-lookup"><span data-stu-id="67152-152">It should look like the following.</span></span>

     <span data-ttu-id="67152-153">![带有渐变背景的按钮](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="67152-153">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="67152-154">创建定义按钮外观的模板</span><span class="sxs-lookup"><span data-stu-id="67152-154">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="67152-155">在本部分中，将创建一个自定义按钮外观（表示）的模板。</span><span class="sxs-lookup"><span data-stu-id="67152-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="67152-156">按钮表示由多个对象组成，其中包括矩形和其他组件，用于为按钮指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="67152-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="67152-157">到目前为止，控件在应用程序中的外观控件限制为更改按钮的属性。</span><span class="sxs-lookup"><span data-stu-id="67152-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="67152-158">如果要对按钮的外观进行更多的根式更改，会怎么样？</span><span class="sxs-lookup"><span data-stu-id="67152-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="67152-159">模板可以强大地控制对象的表示形式。</span><span class="sxs-lookup"><span data-stu-id="67152-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="67152-160">由于可以在样式内使用模板，因此可以将模板应用于样式应用到的所有对象（在本演练中为按钮）。</span><span class="sxs-lookup"><span data-stu-id="67152-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="67152-161">使用模板定义按钮的外观</span><span class="sxs-lookup"><span data-stu-id="67152-161">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="67152-162">**设置模板：** 由于 <xref:System.Windows.Controls.Button> 的控件具有 <xref:System.Windows.Controls.Control.Template%2A> 属性，因此可以像定义使用 <xref:System.Windows.Setter>在 <xref:System.Windows.Style> 中设置的其他属性值一样定义模板属性值。</span><span class="sxs-lookup"><span data-stu-id="67152-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="67152-163">将以下突出显示的标记添加到按钮样式。</span><span class="sxs-lookup"><span data-stu-id="67152-163">Add the following highlighted markup to your button style.</span></span>

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

2. <span data-ttu-id="67152-164">**更改按钮演示：** 此时，需要定义模板。</span><span class="sxs-lookup"><span data-stu-id="67152-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="67152-165">添加以下突出显示的标记。</span><span class="sxs-lookup"><span data-stu-id="67152-165">Add the following highlighted markup.</span></span> <span data-ttu-id="67152-166">此标记指定两个带圆角的 <xref:System.Windows.Shapes.Rectangle> 元素，后跟一个 <xref:System.Windows.Controls.DockPanel>。</span><span class="sxs-lookup"><span data-stu-id="67152-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="67152-167"><xref:System.Windows.Controls.DockPanel> 用于承载按钮的 <xref:System.Windows.Controls.ContentPresenter>。</span><span class="sxs-lookup"><span data-stu-id="67152-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="67152-168"><xref:System.Windows.Controls.ContentPresenter> 显示按钮的内容。</span><span class="sxs-lookup"><span data-stu-id="67152-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="67152-169">在本演练中，内容是文本（"Button 1"、"Button 2"、"Button 3"）。</span><span class="sxs-lookup"><span data-stu-id="67152-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="67152-170">所有模板组件（矩形和 <xref:System.Windows.Controls.DockPanel>）都在 <xref:System.Windows.Controls.Grid>内进行布局。</span><span class="sxs-lookup"><span data-stu-id="67152-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

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

     <span data-ttu-id="67152-171">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="67152-171">Press F5 to run the application.</span></span> <span data-ttu-id="67152-172">其外观应如下所示。</span><span class="sxs-lookup"><span data-stu-id="67152-172">It should look like the following.</span></span>

     ![具有3个按钮的窗口](./media/custom-button-animatedbutton-4.gif)

3. <span data-ttu-id="67152-174">**将 Glasseffect 添加到模板：** 接下来，你将添加玻璃。</span><span class="sxs-lookup"><span data-stu-id="67152-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="67152-175">首先，创建一些创建玻璃渐变效果的资源。</span><span class="sxs-lookup"><span data-stu-id="67152-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="67152-176">将这些渐变资源添加到 `Application.Resources` 块中的任何位置：</span><span class="sxs-lookup"><span data-stu-id="67152-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

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

     <span data-ttu-id="67152-177">这些资源用作在按钮模板的 <xref:System.Windows.Controls.Grid> 中插入的矩形的 <xref:System.Windows.Shapes.Shape.Fill%2A>。</span><span class="sxs-lookup"><span data-stu-id="67152-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="67152-178">将以下突出显示的标记添加到模板。</span><span class="sxs-lookup"><span data-stu-id="67152-178">Add the following highlighted markup to the template.</span></span>

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

     <span data-ttu-id="67152-179">请注意，`x:Name` 属性为 "glassCube" 的矩形的 <xref:System.Windows.UIElement.Opacity%2A> 为0，因此，在运行该示例时，看不到顶部显示的玻璃矩形。</span><span class="sxs-lookup"><span data-stu-id="67152-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="67152-180">这是因为，稍后我们会将触发器添加到模板中，以便用户与按钮交互时。</span><span class="sxs-lookup"><span data-stu-id="67152-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="67152-181">不过，现在可以通过将 <xref:System.Windows.UIElement.Opacity%2A> 值更改为1并运行应用程序来查看按钮的外观。</span><span class="sxs-lookup"><span data-stu-id="67152-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="67152-182">请参见下图。</span><span class="sxs-lookup"><span data-stu-id="67152-182">See the following figure.</span></span> <span data-ttu-id="67152-183">继续下一步之前，请将 <xref:System.Windows.UIElement.Opacity%2A> 更改回0。</span><span class="sxs-lookup"><span data-stu-id="67152-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="67152-184">![使用 XAML 创建的自定义按钮](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="67152-184">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="67152-185">创建按钮交互性</span><span class="sxs-lookup"><span data-stu-id="67152-185">Create Button Interactivity</span></span>

<span data-ttu-id="67152-186">在本部分中，你将创建属性触发器和事件触发器，以更改属性值，并运行动画来响应用户操作，例如，将鼠标指针移到按钮上并单击。</span><span class="sxs-lookup"><span data-stu-id="67152-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="67152-187">添加交互（鼠标悬停、鼠标离开、单击等）的一种简单方法是在模板或样式中定义触发器。</span><span class="sxs-lookup"><span data-stu-id="67152-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="67152-188">若要创建 <xref:System.Windows.Trigger>，请定义属性 "条件"，如：按钮 <xref:System.Windows.UIElement.IsMouseOver%2A> 属性值等于 `true`。</span><span class="sxs-lookup"><span data-stu-id="67152-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="67152-189">然后，定义在触发器条件为 true 时执行的 setter （操作）。</span><span class="sxs-lookup"><span data-stu-id="67152-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="67152-190">若要创建按钮交互性</span><span class="sxs-lookup"><span data-stu-id="67152-190">To create button interactivity</span></span>

1. <span data-ttu-id="67152-191">**添加模板触发器：** 将突出显示的标记添加到模板。</span><span class="sxs-lookup"><span data-stu-id="67152-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>

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

2. <span data-ttu-id="67152-192">**添加属性触发器：** 将突出显示的标记添加到 `ControlTemplate.Triggers` 块：</span><span class="sxs-lookup"><span data-stu-id="67152-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="67152-193">按 F5 运行应用程序，并在按钮上运行鼠标指针时查看效果。</span><span class="sxs-lookup"><span data-stu-id="67152-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="67152-194">**添加焦点触发器：** 接下来，我们将添加一些类似的 setter 来处理按钮有焦点的情况（例如，用户单击后）。</span><span class="sxs-lookup"><span data-stu-id="67152-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

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

     <span data-ttu-id="67152-195">按 F5 运行应用程序，并单击其中一个按钮。</span><span class="sxs-lookup"><span data-stu-id="67152-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="67152-196">请注意，单击按钮后，按钮会保持突出显示，因为它仍有焦点。</span><span class="sxs-lookup"><span data-stu-id="67152-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="67152-197">如果单击另一个按钮，新按钮会获得焦点，而最后一个按钮丢失。</span><span class="sxs-lookup"><span data-stu-id="67152-197">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="67152-198">为 <xref:System.Windows.UIElement.MouseEnter>**和**<xref:System.Windows.UIElement.MouseLeave>**添加动画** **：** 接下来，我们向触发器添加一些动画。</span><span class="sxs-lookup"><span data-stu-id="67152-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="67152-199">将以下标记添加到 `ControlTemplate.Triggers` 块内部的任意位置。</span><span class="sxs-lookup"><span data-stu-id="67152-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

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

     <span data-ttu-id="67152-200">当鼠标指针移到按钮上并在指针离开时返回到正常大小时，玻璃矩形会收缩。</span><span class="sxs-lookup"><span data-stu-id="67152-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="67152-201">当指针悬停在按钮上方时（引发<xref:System.Windows.UIElement.MouseEnter> 事件），会触发两个动画。</span><span class="sxs-lookup"><span data-stu-id="67152-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="67152-202">这些动画沿 X 和 Y 轴收缩玻璃矩形。</span><span class="sxs-lookup"><span data-stu-id="67152-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="67152-203">请注意 <xref:System.Windows.Media.Animation.DoubleAnimation> 元素上的属性，<xref:System.Windows.Media.Animation.Timeline.Duration%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>。</span><span class="sxs-lookup"><span data-stu-id="67152-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="67152-204"><xref:System.Windows.Media.Animation.Timeline.Duration%2A> 指定动画每半秒发生一次，<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 指定玻璃缩小10%。</span><span class="sxs-lookup"><span data-stu-id="67152-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="67152-205">第二个事件触发器（<xref:System.Windows.UIElement.MouseLeave>）只是停止第一个触发器。</span><span class="sxs-lookup"><span data-stu-id="67152-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="67152-206">停止 <xref:System.Windows.Media.Animation.Storyboard>时，所有动画属性都将恢复为其默认值。</span><span class="sxs-lookup"><span data-stu-id="67152-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="67152-207">因此，当用户将指针移到按钮上时，按钮返回到鼠标指针移到按钮上之前的状态。</span><span class="sxs-lookup"><span data-stu-id="67152-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="67152-208">有关动画的详细信息，请参阅[动画概述](../graphics-multimedia/animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="67152-208">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="67152-209">在**单击按钮时添加动画：** 最后一步是在用户单击按钮时添加触发器。</span><span class="sxs-lookup"><span data-stu-id="67152-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="67152-210">将以下标记添加到 `ControlTemplate.Triggers` 块内部的任意位置：</span><span class="sxs-lookup"><span data-stu-id="67152-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

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

     <span data-ttu-id="67152-211">按 F5 运行应用程序，然后单击其中一个按钮。</span><span class="sxs-lookup"><span data-stu-id="67152-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="67152-212">单击按钮时，玻璃矩形会旋转。</span><span class="sxs-lookup"><span data-stu-id="67152-212">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="67152-213">总结</span><span class="sxs-lookup"><span data-stu-id="67152-213">Summary</span></span>
 <span data-ttu-id="67152-214">在本演练中，您执行了以下练习：</span><span class="sxs-lookup"><span data-stu-id="67152-214">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="67152-215">目标为对象类型的 <xref:System.Windows.Style> （<xref:System.Windows.Controls.Button>）。</span><span class="sxs-lookup"><span data-stu-id="67152-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="67152-216">使用 <xref:System.Windows.Style>的整个应用程序中的按钮的受控基本属性。</span><span class="sxs-lookup"><span data-stu-id="67152-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="67152-217">创建了一些资源，如渐变要用于 <xref:System.Windows.Style> 资源库的属性值。</span><span class="sxs-lookup"><span data-stu-id="67152-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="67152-218">通过将模板应用于按钮，自定义了整个应用程序中的按钮的外观。</span><span class="sxs-lookup"><span data-stu-id="67152-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="67152-219">用于响应用户操作（例如 <xref:System.Windows.UIElement.MouseEnter>、<xref:System.Windows.UIElement.MouseLeave>和 <xref:System.Windows.Controls.Primitives.ButtonBase.Click>）的按钮的自定义行为，这些操作包含了动画效果。</span><span class="sxs-lookup"><span data-stu-id="67152-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="67152-220">请参阅</span><span class="sxs-lookup"><span data-stu-id="67152-220">See also</span></span>

- [<span data-ttu-id="67152-221">使用 Microsoft Expression Blend 创建按钮</span><span class="sxs-lookup"><span data-stu-id="67152-221">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="67152-222">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="67152-222">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="67152-223">动画概述</span><span class="sxs-lookup"><span data-stu-id="67152-223">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="67152-224">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="67152-224">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="67152-225">位图效果概述</span><span class="sxs-lookup"><span data-stu-id="67152-225">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
