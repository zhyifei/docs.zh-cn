---
title: 在 WPF - .NET 桌面中创建模板
description: 了解如何在 Windows 演示文稿基础和 .NET Core 中创建和引用控件模板。
author: thraka
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: c901864d387b8de976bbfa9a9b3c14a7d5a0b4d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432538"
---
# <a name="create-a-template-for-a-control"></a><span data-ttu-id="59810-103">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="59810-103">Create a template for a control</span></span>

<span data-ttu-id="59810-104">使用 Windows 演示文稿基础 （WPF），您可以使用自己的可重用模板自定义现有控件的可视结构和行为。</span><span class="sxs-lookup"><span data-stu-id="59810-104">With Windows Presentation Foundation (WPF), you can customize an existing control's visual structure and behavior with your own reusable template.</span></span> <span data-ttu-id="59810-105">模板可以全局应用于应用程序、窗口和页面，也可以直接应用于控件。</span><span class="sxs-lookup"><span data-stu-id="59810-105">Templates can be applied globally to your application, windows and pages, or directly to controls.</span></span> <span data-ttu-id="59810-106">通过为现有控件创建新模板，可以涵盖大多数需要您创建新控件的方案。</span><span class="sxs-lookup"><span data-stu-id="59810-106">Most scenarios that require you to create a new control can be covered by instead creating a new template for an existing control.</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="59810-107">在本文中，您将探讨<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Button>控件创建新控件。</span><span class="sxs-lookup"><span data-stu-id="59810-107">In this article, you'll explore creating a new <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>

## <a name="when-to-create-a-controltemplate"></a><span data-ttu-id="59810-108">何时创建控件模板</span><span class="sxs-lookup"><span data-stu-id="59810-108">When to create a ControlTemplate</span></span>

<span data-ttu-id="59810-109">控件具有许多属性，如<xref:System.Windows.Controls.Border.Background%2A>和<xref:System.Windows.Controls.Control.Foreground%2A>。 <xref:System.Windows.Controls.Control.FontFamily%2A></span><span class="sxs-lookup"><span data-stu-id="59810-109">Controls have many properties, such as <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, and <xref:System.Windows.Controls.Control.FontFamily%2A>.</span></span> <span data-ttu-id="59810-110">这些属性控制控件外观的不同方面，但通过设置这些属性可以进行的更改是有限的。</span><span class="sxs-lookup"><span data-stu-id="59810-110">These properties control different aspects of the control's appearance, but the changes that you can make by setting these properties are limited.</span></span> <span data-ttu-id="59810-111">例如，可以将<xref:System.Windows.Controls.Control.Foreground%2A>属性设置为蓝色，将<xref:System.Windows.Controls.Control.FontStyle%2A>属性设置为斜体。 <xref:System.Windows.Controls.CheckBox></span><span class="sxs-lookup"><span data-stu-id="59810-111">For example, you can set the <xref:System.Windows.Controls.Control.Foreground%2A> property to blue and <xref:System.Windows.Controls.Control.FontStyle%2A> to italic on a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="59810-112">如果要自定义控件的外观，超出控件上其他属性设置可以执行的内容，请创建 一个<xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="59810-112">When you want to customize the control's appearance beyond what setting the other properties on the control can do, you create a <xref:System.Windows.Controls.ControlTemplate>.</span></span>

<span data-ttu-id="59810-113">在大多数用户界面中，按钮具有相同的常规外观：带有某些文本的矩形。</span><span class="sxs-lookup"><span data-stu-id="59810-113">In most user interfaces, a button has the same general appearance: a rectangle with some text.</span></span> <span data-ttu-id="59810-114">如果要创建圆角按钮，可以创建从按钮继承的新控件或重新创建按钮的功能。</span><span class="sxs-lookup"><span data-stu-id="59810-114">If you wanted to create a rounded button, you could create a new control that inherits from the button or recreates the functionality of the button.</span></span> <span data-ttu-id="59810-115">此外，新的用户控件将提供圆形视觉对象。</span><span class="sxs-lookup"><span data-stu-id="59810-115">In addition, the new user control would provide the circular visual.</span></span>

<span data-ttu-id="59810-116">通过自定义现有控件的可视布局，可以避免创建新控件。</span><span class="sxs-lookup"><span data-stu-id="59810-116">You can avoid creating new controls by customizing the visual layout of an existing control.</span></span> <span data-ttu-id="59810-117">使用圆角按钮，创建<xref:System.Windows.Controls.ControlTemplate>具有所需可视布局的 。</span><span class="sxs-lookup"><span data-stu-id="59810-117">With a rounded button, you create a <xref:System.Windows.Controls.ControlTemplate> with the desired visual layout.</span></span>

<span data-ttu-id="59810-118">另一方面，如果需要具有新功能、不同属性和新设置的控件，则可以创建新<xref:System.Windows.Controls.UserControl>的 。</span><span class="sxs-lookup"><span data-stu-id="59810-118">On the other hand, if you need a control with new functionality, different properties, and new settings, you would create a new <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="59810-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="59810-119">Prerequisites</span></span>

<span data-ttu-id="59810-120">创建新的 WPF 应用程序，并在*MainWindow.xaml（* 或您选择的其他窗口）中设置**\<窗口>** 元素上的以下属性：</span><span class="sxs-lookup"><span data-stu-id="59810-120">Create a new WPF application and in *MainWindow.xaml* (or another window of your choice) set the following properties on the **\<Window>** element:</span></span>

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

<span data-ttu-id="59810-121">将**\<窗口>** 元素的内容设置为以下 XAML：</span><span class="sxs-lookup"><span data-stu-id="59810-121">Set the content of the **\<Window>** element to the following XAML:</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="59810-122">最后 *，MainWindow.xaml*文件应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="59810-122">In the end, the *MainWindow.xaml* file should look similar to the following:</span></span>

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

<span data-ttu-id="59810-123">如果运行该应用程序，它如下所示：</span><span class="sxs-lookup"><span data-stu-id="59810-123">If you run the application, it looks like the following:</span></span>

![带两个未样式按钮的 WPF 窗口](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a><span data-ttu-id="59810-125">创建 ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="59810-125">Create a ControlTemplate</span></span>

<span data-ttu-id="59810-126">声明<xref:System.Windows.Controls.ControlTemplate>的最常见方法是作为 XAML 文件中`Resources`的节中的资源。</span><span class="sxs-lookup"><span data-stu-id="59810-126">The most common way to declare a <xref:System.Windows.Controls.ControlTemplate> is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="59810-127">由于模板是资源，因此它们遵循适用于所有资源的相同范围规则。</span><span class="sxs-lookup"><span data-stu-id="59810-127">Because templates are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="59810-128">简单地说，声明模板的位置会影响模板的应用位置。</span><span class="sxs-lookup"><span data-stu-id="59810-128">Put simply, where you declare a template affects where the template can be applied.</span></span> <span data-ttu-id="59810-129">例如，如果在应用程序定义 XAML 文件的根元素中声明模板，则可以在应用程序中的任何位置使用该模板。</span><span class="sxs-lookup"><span data-stu-id="59810-129">For example, if you declare the template in the root element of your application definition XAML file, the template can be used anywhere in your application.</span></span> <span data-ttu-id="59810-130">如果在窗口中定义模板，则只有该窗口中的控件可以使用该模板。</span><span class="sxs-lookup"><span data-stu-id="59810-130">If you define the template in a window, only the controls in that window can use the template.</span></span>

<span data-ttu-id="59810-131">首先，向`Window.Resources`*MainWindow.xaml*文件添加元素：</span><span class="sxs-lookup"><span data-stu-id="59810-131">To start with, add a `Window.Resources` element to your *MainWindow.xaml* file:</span></span>

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

<span data-ttu-id="59810-132">使用以下属性集创建新**\<的 ControlTemplate>：**</span><span class="sxs-lookup"><span data-stu-id="59810-132">Create a new **\<ControlTemplate>** with the following properties set:</span></span>

|     |     |
| --- | --- |
| <span data-ttu-id="59810-133">**x:Key**</span><span class="sxs-lookup"><span data-stu-id="59810-133">**x:Key**</span></span>         | `roundbutton` |
| **TargetType**    | `Button` |

<span data-ttu-id="59810-134">此控件模板非常简单：</span><span class="sxs-lookup"><span data-stu-id="59810-134">This control template will be simple:</span></span>

- <span data-ttu-id="59810-135">控件的根元素，<xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="59810-135">a root element for the control, a <xref:System.Windows.Controls.Grid></span></span>
- <span data-ttu-id="59810-136">绘制<xref:System.Windows.Shapes.Ellipse>按钮的圆舍入外观</span><span class="sxs-lookup"><span data-stu-id="59810-136">an <xref:System.Windows.Shapes.Ellipse> to draw the rounded appearance of the button</span></span>
- <span data-ttu-id="59810-137">a<xref:System.Windows.Controls.ContentPresenter>以显示用户指定的按钮内容</span><span class="sxs-lookup"><span data-stu-id="59810-137">a <xref:System.Windows.Controls.ContentPresenter> to display the user-specified button content</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a><span data-ttu-id="59810-138">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="59810-138">TemplateBinding</span></span>

<span data-ttu-id="59810-139">创建新 时<xref:System.Windows.Controls.ControlTemplate>，仍可能仍要使用公共属性来更改控件的外观。</span><span class="sxs-lookup"><span data-stu-id="59810-139">When you create a new <xref:System.Windows.Controls.ControlTemplate>, you still might want to use the public properties to change the control's appearance.</span></span> <span data-ttu-id="59810-140">[模板绑定](../../framework/wpf/advanced/templatebinding-markup-extension.md)标记扩展将 元素的属性绑定<xref:System.Windows.Controls.ControlTemplate>到由控件定义的公共属性。</span><span class="sxs-lookup"><span data-stu-id="59810-140">The [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) markup extension binds a property of an element that is in the <xref:System.Windows.Controls.ControlTemplate> to a public property that is defined by the control.</span></span> <span data-ttu-id="59810-141">使用[模板绑定](../../framework/wpf/advanced/templatebinding-markup-extension.md)时，将启用控件上的属性作为模板的参数。</span><span class="sxs-lookup"><span data-stu-id="59810-141">When you use a [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), you enable properties on the control to act as parameters to the template.</span></span> <span data-ttu-id="59810-142">换言之，设置控件属性后，该值将传递到包含 [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) 的元素。</span><span class="sxs-lookup"><span data-stu-id="59810-142">That is, when a property on a control is set, that value is passed on to the element that has the [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) on it.</span></span>

### <a name="ellipse"></a><span data-ttu-id="59810-143">椭圆形</span><span class="sxs-lookup"><span data-stu-id="59810-143">Ellipse</span></span>

<span data-ttu-id="59810-144">**:::no-loc text="Fill":::** 请注意**:::no-loc text="Stroke":::**，<xref:System.Windows.Controls.Control.Foreground>**\<椭圆>** 元素的 和 属性绑定到控件和<xref:System.Windows.Controls.Control.Background>属性。</span><span class="sxs-lookup"><span data-stu-id="59810-144">Notice that the **:::no-loc text="Fill":::** and **:::no-loc text="Stroke":::** properties of the **\<Ellipse>** element are bound to the control's <xref:System.Windows.Controls.Control.Foreground> and <xref:System.Windows.Controls.Control.Background> properties.</span></span>

### <a name="contentpresenter"></a><span data-ttu-id="59810-145">ContentPresenter</span><span class="sxs-lookup"><span data-stu-id="59810-145">ContentPresenter</span></span>

<span data-ttu-id="59810-146">内容演示者>元素也会添加到模板中。 [ \<](xref:System.Windows.Controls.ContentPresenter)</span><span class="sxs-lookup"><span data-stu-id="59810-146">A [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) element is also added to the template.</span></span> <span data-ttu-id="59810-147">由于此模板是为按钮设计的，因此，考虑到该按钮从<xref:System.Windows.Controls.ContentControl>继承。</span><span class="sxs-lookup"><span data-stu-id="59810-147">Because this template is designed for a button, take into consideration that the button inherits from <xref:System.Windows.Controls.ContentControl>.</span></span> <span data-ttu-id="59810-148">该按钮显示元素的内容。</span><span class="sxs-lookup"><span data-stu-id="59810-148">The button presents the content of the element.</span></span> <span data-ttu-id="59810-149">您可以在按钮内设置任何内容，例如纯文本或其他控件。</span><span class="sxs-lookup"><span data-stu-id="59810-149">You can set anything inside of the button, such as plain text or even another control.</span></span> <span data-ttu-id="59810-150">以下两个按钮均为有效按钮：</span><span class="sxs-lookup"><span data-stu-id="59810-150">Both of the following are valid buttons:</span></span>

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

<span data-ttu-id="59810-151">在前面的两个示例中，文本和复选框都设置为[Button.Content](xref:System.Windows.Controls.ContentControl.Content)属性。</span><span class="sxs-lookup"><span data-stu-id="59810-151">In both of the previous examples, the text and the checkbox are set as the [Button.Content](xref:System.Windows.Controls.ContentControl.Content) property.</span></span> <span data-ttu-id="59810-152">任何设置为内容的内容都可以通过**\<ContentPresenter>**（即模板）显示，这是模板的作用。</span><span class="sxs-lookup"><span data-stu-id="59810-152">Whatever is set as the content can be presented through a **\<ContentPresenter>**, which is what the template does.</span></span>

<span data-ttu-id="59810-153">如果 应用于<xref:System.Windows.Controls.ContentControl>类型（如 ，`Button`如 元素树中搜索 。 <xref:System.Windows.Controls.ContentPresenter> <xref:System.Windows.Controls.ControlTemplate></span><span class="sxs-lookup"><span data-stu-id="59810-153">If the <xref:System.Windows.Controls.ControlTemplate> is applied to a <xref:System.Windows.Controls.ContentControl> type, such as a `Button`, a <xref:System.Windows.Controls.ContentPresenter> is searched for in the element tree.</span></span> <span data-ttu-id="59810-154">如果找到`ContentPresenter`，模板将自动将控件的属性<xref:System.Windows.Controls.ContentControl.Content>绑定到 。 `ContentPresenter`</span><span class="sxs-lookup"><span data-stu-id="59810-154">If the `ContentPresenter` is found, the template automatically binds the control's <xref:System.Windows.Controls.ContentControl.Content> property to the `ContentPresenter`.</span></span>

## <a name="use-the-template"></a><span data-ttu-id="59810-155">使用模板</span><span class="sxs-lookup"><span data-stu-id="59810-155">Use the template</span></span>

<span data-ttu-id="59810-156">查找本文开头声明的按钮。</span><span class="sxs-lookup"><span data-stu-id="59810-156">Find the buttons that were declared at the start of this article.</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="59810-157">将第二个按钮的属性<xref:System.Windows.Controls.Control.Template>设置为`roundbutton`资源：</span><span class="sxs-lookup"><span data-stu-id="59810-157">Set the second button's <xref:System.Windows.Controls.Control.Template> property to the `roundbutton` resource:</span></span>

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

<span data-ttu-id="59810-158">如果运行项目并查看结果，您将看到该按钮具有圆润的背景。</span><span class="sxs-lookup"><span data-stu-id="59810-158">If you run the project and look at the result, you'll see that the button has a rounded background.</span></span>

![带一个模板椭圆形按钮的 WPF 窗口](media/create-apply-template/styled-button.png)

<span data-ttu-id="59810-160">您可能已经注意到该按钮不是圆，而是偏斜的。</span><span class="sxs-lookup"><span data-stu-id="59810-160">You may have noticed that the button isn't a circle but is skewed.</span></span> <span data-ttu-id="59810-161">由于**\<椭圆>** 元素的工作方式，它总是展开以填充可用空间。</span><span class="sxs-lookup"><span data-stu-id="59810-161">Because of the way the **\<Ellipse>** element works, it always expands to fill the available space.</span></span> <span data-ttu-id="59810-162">通过将按钮**:::no-loc text="width":::** 和**:::no-loc text="height":::** 属性更改为相同的值，使圆均匀：</span><span class="sxs-lookup"><span data-stu-id="59810-162">Make the circle uniform by changing the button's  **:::no-loc text="width":::** and **:::no-loc text="height":::** properties to the same value:</span></span>

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![带一个模板圆形按钮的 WPF 窗口](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a><span data-ttu-id="59810-164">添加触发器</span><span class="sxs-lookup"><span data-stu-id="59810-164">Add a Trigger</span></span>

<span data-ttu-id="59810-165">即使应用了模板的按钮看起来不同，它的外观与任何其他按钮相同。</span><span class="sxs-lookup"><span data-stu-id="59810-165">Even though a button with a template applied looks different, it behaves the same as any other button.</span></span> <span data-ttu-id="59810-166">如果按下该按钮，事件将<xref:System.Windows.Controls.Primitives.ButtonBase.Click>触发。</span><span class="sxs-lookup"><span data-stu-id="59810-166">If you press the button, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event fires.</span></span> <span data-ttu-id="59810-167">但是，您可能已经注意到，当您将鼠标移到按钮上时，按钮的视觉效果不会更改。</span><span class="sxs-lookup"><span data-stu-id="59810-167">However, you may have noticed that when you move your mouse over the button, the button's visuals don't change.</span></span> <span data-ttu-id="59810-168">这些可视化交互都由模板定义。</span><span class="sxs-lookup"><span data-stu-id="59810-168">These visual interactions are all defined by the template.</span></span>

<span data-ttu-id="59810-169">使用 WPF 提供的动态事件和属性系统，可以监视值的特定属性，然后在适当的时候重新设置模板的样式。</span><span class="sxs-lookup"><span data-stu-id="59810-169">With the dynamic event and property systems that WPF provides, you can watch a specific property for a value and then restyle the template when appropriate.</span></span> <span data-ttu-id="59810-170">在此示例中，您将观看按钮的属性<xref:System.Windows.UIElement.IsMouseOver>。</span><span class="sxs-lookup"><span data-stu-id="59810-170">In this example, you'll watch the button's <xref:System.Windows.UIElement.IsMouseOver> property.</span></span> <span data-ttu-id="59810-171">当鼠标位于控件上时，使用新颜色对**\<椭圆>** 进行样式设置。</span><span class="sxs-lookup"><span data-stu-id="59810-171">When the mouse is over the control, style the **\<Ellipse>** with a new color.</span></span> <span data-ttu-id="59810-172">这种类型的触发器称为*属性触发器*。</span><span class="sxs-lookup"><span data-stu-id="59810-172">This type of trigger is known as a *PropertyTrigger*.</span></span>

<span data-ttu-id="59810-173">为此，您需要向**\<椭圆>** 添加一个名称，以便参考。</span><span class="sxs-lookup"><span data-stu-id="59810-173">For this to work, you'll need to add a name to the **\<Ellipse>** that you can reference.</span></span> <span data-ttu-id="59810-174">给它的背景**元素**的名称。</span><span class="sxs-lookup"><span data-stu-id="59810-174">Give it the name of **backgroundElement**.</span></span>

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

<span data-ttu-id="59810-175">接下来，<xref:System.Windows.Trigger>向[控件模板.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers)集合添加新。</span><span class="sxs-lookup"><span data-stu-id="59810-175">Next, add a new <xref:System.Windows.Trigger> to the [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) collection.</span></span> <span data-ttu-id="59810-176">触发器将监视值`IsMouseOver``true`的事件。</span><span class="sxs-lookup"><span data-stu-id="59810-176">The trigger will watch the `IsMouseOver` event for the value `true`.</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

<span data-ttu-id="59810-177">接下来，将**\<setter>** 添加到**\<将\*\*\*\*\<椭圆>** 的**填充**属性更改为新颜色的触发器>。</span><span class="sxs-lookup"><span data-stu-id="59810-177">Next, add a **\<Setter>** to the **\<Trigger>** that changes the **Fill** property of the **\<Ellipse>** to a new color.</span></span>

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

<span data-ttu-id="59810-178">运行该项目。</span><span class="sxs-lookup"><span data-stu-id="59810-178">Run the project.</span></span> <span data-ttu-id="59810-179">请注意，当您将鼠标移到按钮上时，**\<椭圆的颜色>** 更改。</span><span class="sxs-lookup"><span data-stu-id="59810-179">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** changes.</span></span>

![鼠标在 WPF 按钮上移动以更改填充颜色](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a><span data-ttu-id="59810-181">使用可视状态</span><span class="sxs-lookup"><span data-stu-id="59810-181">Use a VisualState</span></span>

<span data-ttu-id="59810-182">可视状态由控件定义和触发。</span><span class="sxs-lookup"><span data-stu-id="59810-182">Visual states are defined and triggered by a control.</span></span> <span data-ttu-id="59810-183">例如，当鼠标移动到控件的顶部时，`CommonStates.MouseOver`将触发状态。</span><span class="sxs-lookup"><span data-stu-id="59810-183">For example, when the mouse is moved on top of the control, the `CommonStates.MouseOver` state is triggered.</span></span> <span data-ttu-id="59810-184">您可以根据控件的当前状态为属性更改设置动画。</span><span class="sxs-lookup"><span data-stu-id="59810-184">You can animate property changes based on the current state of the control.</span></span> <span data-ttu-id="59810-185">在上一`AliceBlue``IsMouseOver``true`**\<节中，属性触发器>** 用于将按钮的前景更改为 属性为 时。</span><span class="sxs-lookup"><span data-stu-id="59810-185">In the previous section, a **\<PropertyTrigger>** was used to change the foreground of the button to `AliceBlue` when the `IsMouseOver` property was `true`.</span></span> <span data-ttu-id="59810-186">相反，创建一个可视状态，为更改此颜色设置动画，从而提供平滑过渡。</span><span class="sxs-lookup"><span data-stu-id="59810-186">Instead, create a visual state that animates the change of this color, providing a smooth transition.</span></span> <span data-ttu-id="59810-187">有关 Visual*状态*的详细信息，请参阅[WPF 中的样式和模板](../fundamentals/styles-templates-overview.md#visual-states)。</span><span class="sxs-lookup"><span data-stu-id="59810-187">For more information about *VisualStates*, see [Styles and templates in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span></span>

<span data-ttu-id="59810-188">要将**\<属性触发>** 转换为动画视觉状态，首先，请从模板中删除**\<ControlTemplate.Trigger>** 元素。</span><span class="sxs-lookup"><span data-stu-id="59810-188">To convert the **\<PropertyTrigger>** to an animated visual state, First, remove the **\<ControlTemplate.Triggers>** element from your template.</span></span>

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

<span data-ttu-id="59810-189">接下来，在**\<控件模板的网格>** 根中，添加**\<VisualStateManager.VisualStateGroup>** 元素，该元素具有**\<VisualStateGroup** `CommonStates`>。</span><span class="sxs-lookup"><span data-stu-id="59810-189">Next, in the **\<Grid>** root of the control template, add the **\<VisualStateManager.VisualStateGroups>** element with a **\<VisualStateGroup>** for `CommonStates`.</span></span> <span data-ttu-id="59810-190">定义两种状态`Normal`，`MouseOver`和 。</span><span class="sxs-lookup"><span data-stu-id="59810-190">Define two states, `Normal` and `MouseOver`.</span></span>

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

<span data-ttu-id="59810-191">触发**\<该**状态时，将应用 VisualState>中定义的任何动画。</span><span class="sxs-lookup"><span data-stu-id="59810-191">Any animations defined in a **\<VisualState>** are applied when that state is triggered.</span></span> <span data-ttu-id="59810-192">为每个状态创建动画。</span><span class="sxs-lookup"><span data-stu-id="59810-192">Create animations for each state.</span></span> <span data-ttu-id="59810-193">动画放在**\<情节提要>** 元素的内。</span><span class="sxs-lookup"><span data-stu-id="59810-193">Animations are put inside of a **\<Storyboard>** element.</span></span> <span data-ttu-id="59810-194">有关情节提要的详细信息，请参阅[情节提要概述](../../framework/wpf/graphics-multimedia/storyboards-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="59810-194">For more information about storyboards, see [Storyboards Overview](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>

- <span data-ttu-id="59810-195">一般</span><span class="sxs-lookup"><span data-stu-id="59810-195">Normal</span></span>

  <span data-ttu-id="59810-196">此状态为椭圆填充设置动画，将其还原到控件`Background`的颜色。</span><span class="sxs-lookup"><span data-stu-id="59810-196">This state animates the ellipse fill, restoring it to the control's `Background` color.</span></span>

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- <span data-ttu-id="59810-197">MouseOver</span><span class="sxs-lookup"><span data-stu-id="59810-197">MouseOver</span></span>

  <span data-ttu-id="59810-198">此状态将椭圆`Background`颜色动画为新颜色： `Yellow`。</span><span class="sxs-lookup"><span data-stu-id="59810-198">This state animates the ellipse `Background` color to a new color: `Yellow`.</span></span>

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

<span data-ttu-id="59810-199">控件模板>现在应如下所示。 \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="59810-199">The **\<ControlTemplate>** should now look like the following.</span></span>

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

<span data-ttu-id="59810-200">运行该项目。</span><span class="sxs-lookup"><span data-stu-id="59810-200">Run the project.</span></span> <span data-ttu-id="59810-201">请注意，当您将鼠标移到按钮上时，**\<椭圆的颜色>** 动画。</span><span class="sxs-lookup"><span data-stu-id="59810-201">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** animates.</span></span>

![鼠标在 WPF 按钮上移动以更改填充颜色](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a><span data-ttu-id="59810-203">后续步骤</span><span class="sxs-lookup"><span data-stu-id="59810-203">Next steps</span></span>

- [<span data-ttu-id="59810-204">为 WPF 中的控件创建样式</span><span class="sxs-lookup"><span data-stu-id="59810-204">Create a style for a control in WPF</span></span>](../fundamentals/styles-templates-create-apply-style.md)
- [<span data-ttu-id="59810-205">WPF 中的样式和模板</span><span class="sxs-lookup"><span data-stu-id="59810-205">Styles and templates in WPF</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="59810-206">XAML 资源概述</span><span class="sxs-lookup"><span data-stu-id="59810-206">Overview of XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
