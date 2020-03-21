---
title: 内容模型
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: ec4e96c0883489135b77f09a3c19f144cb4d30bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187394"
---
# <a name="wpf-content-model"></a><span data-ttu-id="8c7b0-102">WPF 内容模型</span><span class="sxs-lookup"><span data-stu-id="8c7b0-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="8c7b0-103">是一个演示平台，提供了许多控件和类似控件的类型，主要用于显示不同类型的内容。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="8c7b0-104">若要确定所要使用的控件或要从其派生的控件，应该了解特定控件可以最佳效果显示的对象类型。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="8c7b0-105">本主题概述了适用于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件和类似控件的类型的内容模型。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="8c7b0-106">内容模型描述可在控件中使用的内容。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="8c7b0-107">本主题还列出了每个内容模型的内容属性。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="8c7b0-108">内容属性是一种用于存储对象内容的属性。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-108">A content property is a property that is used to store the content of the object.</span></span>  

<a name="classes_that_contain_arbitrary_content"></a>
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="8c7b0-109">包含任意内容的类</span><span class="sxs-lookup"><span data-stu-id="8c7b0-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="8c7b0-110">某些控件可以包含任何类型的对象，例如字符串、<xref:System.DateTime>对象或<xref:System.Windows.UIElement>作为其他项的容器的对象。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="8c7b0-111">例如，可以包含<xref:System.Windows.Controls.Button>图像和某些文本;例如，可以包含图像和某些文本。或<xref:System.Windows.Controls.CheckBox>可以包含 的值<xref:System.DateTime.Now%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="8c7b0-112">有四个可包含任意内容的类。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-112">has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="8c7b0-113">下表列出了从 继承的<xref:System.Windows.Controls.Control>类。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="8c7b0-114">包含任意内容的类</span><span class="sxs-lookup"><span data-stu-id="8c7b0-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="8c7b0-115">内容</span><span class="sxs-lookup"><span data-stu-id="8c7b0-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="8c7b0-116">一个任意对象。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="8c7b0-117">一个标头和一个项（两者都是任意对象）。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="8c7b0-118">一个任意对象集合。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="8c7b0-119">一个标头和一个项集合（全部都是任意对象）。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="8c7b0-120">继承自这些类的控件可以包含相同类型的内容，并可以采用相同方式处理该内容。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="8c7b0-121">下图显示了每个内容模型中包含图像和某些文本的控件：</span><span class="sxs-lookup"><span data-stu-id="8c7b0-121">The following illustration shows one control from each content model that contains an image and some text:</span></span>  
  
 ![显示四个不同控件的屏幕截图，每个内容模型一个。](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="8c7b0-123">包含一个任意对象的控件</span><span class="sxs-lookup"><span data-stu-id="8c7b0-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="8c7b0-124">该<xref:System.Windows.Controls.ContentControl>类包含一段任意内容。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="8c7b0-125">其内容属性为<xref:System.Windows.Controls.ContentControl.Content%2A>。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="8c7b0-126">以下控件继承<xref:System.Windows.Controls.ContentControl>并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="8c7b0-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 <span data-ttu-id="8c7b0-127"><xref:System.Windows.Controls.ContentControl.Content%2A>下图显示了四个按钮，其设置为字符串、<xref:System.DateTime>对象、和<xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Controls.Panel> ， 包含 和<xref:System.Windows.Shapes.Ellipse>： <xref:System.Windows.Controls.TextBlock></span><span class="sxs-lookup"><span data-stu-id="8c7b0-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>:</span></span>  
  
 ![显示四个不同内容类型的按钮的屏幕截图。](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <span data-ttu-id="8c7b0-129">有关如何设置<xref:System.Windows.Controls.ContentControl.Content%2A>属性的示例，请参阅<xref:System.Windows.Controls.ContentControl>。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-129">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="8c7b0-130">包含一个标头和一个任意对象的控件</span><span class="sxs-lookup"><span data-stu-id="8c7b0-130">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="8c7b0-131">类<xref:System.Windows.Controls.HeaderedContentControl>继承<xref:System.Windows.Controls.ContentControl>并显示具有标头的内容。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-131">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="8c7b0-132">它继承<xref:System.Windows.Controls.ContentControl.Content%2A>内容属性 ， 和<xref:System.Windows.Controls.ContentControl>定义<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>类型<xref:System.Object>的属性 ;因此，两者都可以是任意对象。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-132">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="8c7b0-133">以下控件继承<xref:System.Windows.Controls.HeaderedContentControl>并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="8c7b0-133">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="8c7b0-134">下图显示了两<xref:System.Windows.Controls.TabItem>个对象。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-134">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="8c7b0-135">第一<xref:System.Windows.Controls.TabItem>个<xref:System.Windows.UIElement>对象为<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>和<xref:System.Windows.Controls.ContentControl.Content%2A>。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-135">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="8c7b0-136"><xref:System.Windows.Controls.HeaderedContentControl.Header%2A>设置为<xref:System.Windows.Controls.StackPanel>包含 和<xref:System.Windows.Shapes.Ellipse>的 。 <xref:System.Windows.Controls.TextBlock></span><span class="sxs-lookup"><span data-stu-id="8c7b0-136">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="8c7b0-137"><xref:System.Windows.Controls.ContentControl.Content%2A>设置为<xref:System.Windows.Controls.StackPanel>包含 和<xref:System.Windows.Controls.TextBlock>的 。 <xref:System.Windows.Controls.Label></span><span class="sxs-lookup"><span data-stu-id="8c7b0-137">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="8c7b0-138">第二<xref:System.Windows.Controls.TabItem>个在 和<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>中有<xref:System.Windows.Controls.TextBlock>一个<xref:System.Windows.Controls.ContentControl.Content%2A>字符串。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-138">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 ![在"标头"属性中使用不同类型的 TabControl。](./media/wpf-content-model/control-content-model-tab.png)  
  
 <span data-ttu-id="8c7b0-140">有关如何创建<xref:System.Windows.Controls.TabItem>对象的示例，请参阅<xref:System.Windows.Controls.HeaderedContentControl>。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-140">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="8c7b0-141">包含一个任意对象集合的控件</span><span class="sxs-lookup"><span data-stu-id="8c7b0-141">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="8c7b0-142">类<xref:System.Windows.Controls.ItemsControl>继承 from<xref:System.Windows.Controls.Control>可以包含多个项，如字符串、对象或其他元素。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-142">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="8c7b0-143">其内容属性为<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>和<xref:System.Windows.Controls.ItemsControl.Items%2A>。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-143">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="8c7b0-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>通常用于使用数据收集填充 。 <xref:System.Windows.Controls.ItemsControl></span><span class="sxs-lookup"><span data-stu-id="8c7b0-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="8c7b0-145">如果不想使用集合填充 ，<xref:System.Windows.Controls.ItemsControl>则可以使用 属性<xref:System.Windows.Controls.ItemsControl.Items%2A>添加项。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-145">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="8c7b0-146">以下控件继承<xref:System.Windows.Controls.ItemsControl>并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="8c7b0-146">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="8c7b0-147">下图显示了包含这些类型的项<xref:System.Windows.Controls.ListBox>的 图所示：</span><span class="sxs-lookup"><span data-stu-id="8c7b0-147">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
- <span data-ttu-id="8c7b0-148">一个字符串。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-148">A string.</span></span>  
  
- <span data-ttu-id="8c7b0-149"><xref:System.DateTime> 对象。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-149">A <xref:System.DateTime> object.</span></span>  
  
- <span data-ttu-id="8c7b0-150">一个 <xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-150">A <xref:System.Windows.UIElement>.</span></span>  
  
- <span data-ttu-id="8c7b0-151">包含<xref:System.Windows.Controls.Panel>和<xref:System.Windows.Shapes.Ellipse>的 A。 <xref:System.Windows.Controls.TextBlock></span><span class="sxs-lookup"><span data-stu-id="8c7b0-151">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 ![显示包含四种类型的内容的 ListBox 的屏幕截图。](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="8c7b0-153">包含一个标头和一个任意对象集合的控件</span><span class="sxs-lookup"><span data-stu-id="8c7b0-153">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="8c7b0-154">类<xref:System.Windows.Controls.HeaderedItemsControl>继承和<xref:System.Windows.Controls.ItemsControl>可以包含多个项，如字符串、对象或其他元素以及标头。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-154">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="8c7b0-155">它继承<xref:System.Windows.Controls.ItemsControl>内容属性<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>和<xref:System.Windows.Controls.ItemsControl.Items%2A>，并定义可以是任意对象<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>的属性。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-155">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="8c7b0-156">以下控件继承<xref:System.Windows.Controls.HeaderedItemsControl>并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="8c7b0-156">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="8c7b0-157">包含一个 UIElement 对象集合的类</span><span class="sxs-lookup"><span data-stu-id="8c7b0-157">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="8c7b0-158">类<xref:System.Windows.Controls.Panel>位置并排列子<xref:System.Windows.UIElement>对象。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-158">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="8c7b0-159">其内容属性为<xref:System.Windows.Controls.Panel.Children%2A>。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-159">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="8c7b0-160">以下类从<xref:System.Windows.Controls.Panel>类继承并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="8c7b0-160">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="8c7b0-161">有关详细信息，请参阅[面板概述](panels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-161">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="8c7b0-162">影响 UIElement 外观的类</span><span class="sxs-lookup"><span data-stu-id="8c7b0-162">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="8c7b0-163">该<xref:System.Windows.Controls.Decorator>类对单个子项<xref:System.Windows.UIElement>或周围应用视觉效果。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-163">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="8c7b0-164">其内容属性为<xref:System.Windows.Controls.Decorator.Child%2A>。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-164">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="8c7b0-165">以下类继承<xref:System.Windows.Controls.Decorator>并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="8c7b0-165">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="8c7b0-166">下图显示了一个<xref:System.Windows.Controls.TextBox>（用）其周围装饰<xref:System.Windows.Controls.Border>的。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-166">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="8c7b0-167">![具有黑色边框的 TextBox](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="8c7b0-167">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="8c7b0-168">具有边框的 TextBlock</span><span class="sxs-lookup"><span data-stu-id="8c7b0-168">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="8c7b0-169">提供 UIElement 相关视觉反馈的类</span><span class="sxs-lookup"><span data-stu-id="8c7b0-169">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="8c7b0-170">类<xref:System.Windows.Documents.Adorner>向用户提供可视提示。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-170">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="8c7b0-171">例如，使用<xref:System.Windows.Documents.Adorner>将函数句柄添加到元素或提供有关控件的状态信息。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-171">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="8c7b0-172">该<xref:System.Windows.Documents.Adorner>类提供了一个框架，以便您可以创建自己的修饰器。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-172">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="8c7b0-173">不会提供任何实现的装饰器。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-173">does not provide any implemented adorners.</span></span> <span data-ttu-id="8c7b0-174">有关详细信息，请参阅[装饰器概述](adorners-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-174">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="8c7b0-175">可让用户输入文本的类</span><span class="sxs-lookup"><span data-stu-id="8c7b0-175">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="8c7b0-176">WPF 提供了三个可让用户输入文本的主要控件。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-176">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="8c7b0-177">每个控件都以不同方式显示文本。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-177">Each control displays the text differently.</span></span> <span data-ttu-id="8c7b0-178">下表列出了这三个与文本相关的控件、显示文本时的功能以及包含控件文本的属性。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-178">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="8c7b0-179">控制</span><span class="sxs-lookup"><span data-stu-id="8c7b0-179">Control</span></span>|<span data-ttu-id="8c7b0-180">文本显示方式</span><span class="sxs-lookup"><span data-stu-id="8c7b0-180">Text is displayed as</span></span>|<span data-ttu-id="8c7b0-181">内容属性</span><span class="sxs-lookup"><span data-stu-id="8c7b0-181">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="8c7b0-182">纯文本</span><span class="sxs-lookup"><span data-stu-id="8c7b0-182">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="8c7b0-183">带格式文本</span><span class="sxs-lookup"><span data-stu-id="8c7b0-183">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="8c7b0-184">隐藏文本（字符已屏蔽）</span><span class="sxs-lookup"><span data-stu-id="8c7b0-184">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>
## <a name="classes-that-display-your-text"></a><span data-ttu-id="8c7b0-185">显示文本的类</span><span class="sxs-lookup"><span data-stu-id="8c7b0-185">Classes That Display Your Text</span></span>  
 <span data-ttu-id="8c7b0-186">某些类可用于显示纯文本或带格式文本。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-186">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="8c7b0-187">您可以使用<xref:System.Windows.Controls.TextBlock>来显示少量的文本。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-187">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="8c7b0-188">如果要显示大量文本，请使用 。 <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.FlowDocumentScrollViewer></span><span class="sxs-lookup"><span data-stu-id="8c7b0-188">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="8c7b0-189">具有<xref:System.Windows.Controls.TextBlock>两个内容属性： <xref:System.Windows.Controls.TextBlock.Text%2A> <xref:System.Windows.Controls.TextBlock.Inlines%2A>和 。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-189">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="8c7b0-190">当您要显示使用一致格式的文本时，该<xref:System.Windows.Controls.TextBlock.Text%2A>属性通常是最佳选择。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-190">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="8c7b0-191">如果计划在整个文本中使用不同的格式，请使用 该<xref:System.Windows.Controls.TextBlock.Inlines%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-191">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="8c7b0-192">该<xref:System.Windows.Controls.TextBlock.Inlines%2A>属性是<xref:System.Windows.Documents.Inline>对象的集合，它指定如何设置文本的格式。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-192">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="8c7b0-193">下表列出了<xref:System.Windows.Controls.FlowDocumentReader>和<xref:System.Windows.Controls.FlowDocumentPageViewer><xref:System.Windows.Controls.FlowDocumentScrollViewer>类的内容属性。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-193">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="8c7b0-194">控制</span><span class="sxs-lookup"><span data-stu-id="8c7b0-194">Control</span></span>|<span data-ttu-id="8c7b0-195">内容属性</span><span class="sxs-lookup"><span data-stu-id="8c7b0-195">Content property</span></span>|<span data-ttu-id="8c7b0-196">内容属性类型</span><span class="sxs-lookup"><span data-stu-id="8c7b0-196">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="8c7b0-197">Document</span><span class="sxs-lookup"><span data-stu-id="8c7b0-197">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="8c7b0-198">Document</span><span class="sxs-lookup"><span data-stu-id="8c7b0-198">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="8c7b0-199">Document</span><span class="sxs-lookup"><span data-stu-id="8c7b0-199">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="8c7b0-200">实现<xref:System.Windows.Documents.FlowDocument><xref:System.Windows.Documents.IDocumentPaginatorSource>接口;因此，所有三个类都可以以<xref:System.Windows.Documents.FlowDocument>作为内容。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-200">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>
## <a name="classes-that-format-your-text"></a><span data-ttu-id="8c7b0-201">设置文本格式的类</span><span class="sxs-lookup"><span data-stu-id="8c7b0-201">Classes That Format Your Text</span></span>  
 <span data-ttu-id="8c7b0-202"><xref:System.Windows.Documents.TextElement>及其相关类允许您设置文本格式。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-202"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="8c7b0-203"><xref:System.Windows.Documents.TextElement>对象在 和 中<xref:System.Windows.Controls.TextBlock>包含<xref:System.Windows.Documents.FlowDocument>和设置文本的格式。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-203"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="8c7b0-204">对象的两种主要类型<xref:System.Windows.Documents.TextElement>是<xref:System.Windows.Documents.Block>元素和<xref:System.Windows.Documents.Inline>元素。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-204">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="8c7b0-205">元素<xref:System.Windows.Documents.Block>表示文本块，如段落或列表。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-205">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="8c7b0-206">元素<xref:System.Windows.Documents.Inline>表示块中文本的一部分。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-206">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="8c7b0-207">许多<xref:System.Windows.Documents.Inline>类指定应用它们的文本的格式。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-207">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="8c7b0-208">每个<xref:System.Windows.Documents.TextElement>都有自己的内容模型。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-208">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="8c7b0-209">有关详细信息，请参阅 [TextElement 内容模型概述](../advanced/textelement-content-model-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8c7b0-209">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c7b0-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c7b0-210">See also</span></span>

- [<span data-ttu-id="8c7b0-211">高级</span><span class="sxs-lookup"><span data-stu-id="8c7b0-211">Advanced</span></span>](../advanced/index.md)
