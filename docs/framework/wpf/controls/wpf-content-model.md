---
title: WPF 内容模型
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
ms.openlocfilehash: 751cbcc3a3b70f0937a8fe84c0fad5d8771a32ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718151"
---
# <a name="wpf-content-model"></a><span data-ttu-id="90e0c-102">WPF 内容模型</span><span class="sxs-lookup"><span data-stu-id="90e0c-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="90e0c-103">是一个演示平台，提供了许多控件和类似控件的类型，主要用于显示不同类型的内容。</span><span class="sxs-lookup"><span data-stu-id="90e0c-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="90e0c-104">若要确定所要使用的控件或要从其派生的控件，应该了解特定控件可以最佳效果显示的对象类型。</span><span class="sxs-lookup"><span data-stu-id="90e0c-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="90e0c-105">本主题概述了适用于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件和类似控件的类型的内容模型。</span><span class="sxs-lookup"><span data-stu-id="90e0c-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="90e0c-106">内容模型描述可在控件中使用的内容。</span><span class="sxs-lookup"><span data-stu-id="90e0c-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="90e0c-107">本主题还列出了每个内容模型的内容属性。</span><span class="sxs-lookup"><span data-stu-id="90e0c-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="90e0c-108">内容属性是一种用于存储对象内容的属性。</span><span class="sxs-lookup"><span data-stu-id="90e0c-108">A content property is a property that is used to store the content of the object.</span></span>  
  
 
  
<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="90e0c-109">包含任意内容的类</span><span class="sxs-lookup"><span data-stu-id="90e0c-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="90e0c-110">某些控件可以包含的任何类型，如字符串、 对象<xref:System.DateTime>对象，或<xref:System.Windows.UIElement>，它是其他项的容器。</span><span class="sxs-lookup"><span data-stu-id="90e0c-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="90e0c-111">例如，<xref:System.Windows.Controls.Button>可以包含图像和一些文本，或<xref:System.Windows.Controls.CheckBox>可以包含的值<xref:System.DateTime.Now%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="90e0c-112">有四个可包含任意内容的类。</span><span class="sxs-lookup"><span data-stu-id="90e0c-112">has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="90e0c-113">下表列出了继承的类<xref:System.Windows.Controls.Control>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="90e0c-114">包含任意内容的类</span><span class="sxs-lookup"><span data-stu-id="90e0c-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="90e0c-115">内容</span><span class="sxs-lookup"><span data-stu-id="90e0c-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="90e0c-116">一个任意对象。</span><span class="sxs-lookup"><span data-stu-id="90e0c-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="90e0c-117">一个标头和一个项（两者都是任意对象）。</span><span class="sxs-lookup"><span data-stu-id="90e0c-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="90e0c-118">一个任意对象集合。</span><span class="sxs-lookup"><span data-stu-id="90e0c-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="90e0c-119">一个标头和一个项集合（全部都是任意对象）。</span><span class="sxs-lookup"><span data-stu-id="90e0c-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="90e0c-120">继承自这些类的控件可以包含相同类型的内容，并可以采用相同方式处理该内容。</span><span class="sxs-lookup"><span data-stu-id="90e0c-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="90e0c-121">下图显示了来自每个内容模型的一个控件，该控件包含了图像和一些文本。</span><span class="sxs-lookup"><span data-stu-id="90e0c-121">The following illustration shows one control from each content model that contains an image and some text.</span></span>  
  
 <span data-ttu-id="90e0c-122">![Button、GroupBox、Listbax、TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span><span class="sxs-lookup"><span data-stu-id="90e0c-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span></span>  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="90e0c-123">包含一个任意对象的控件</span><span class="sxs-lookup"><span data-stu-id="90e0c-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="90e0c-124"><xref:System.Windows.Controls.ContentControl>类包含一段任意内容。</span><span class="sxs-lookup"><span data-stu-id="90e0c-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="90e0c-125">它的内容属性是<xref:System.Windows.Controls.ContentControl.Content%2A>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="90e0c-126">以下控件继承自<xref:System.Windows.Controls.ContentControl>并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="90e0c-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Button>  
  
-   <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBoxItem>  
  
-   <xref:System.Windows.Controls.ContentControl>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GroupItem>  
  
-   <xref:System.Windows.Controls.Label>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Navigation.NavigationWindow>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
-   <xref:System.Windows.Controls.ScrollViewer>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
-   <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
-   <xref:System.Windows.Controls.ToolTip>  
  
-   <xref:System.Windows.Controls.UserControl>  
  
-   <xref:System.Windows.Window>  
  
 <span data-ttu-id="90e0c-127">下图显示四个按钮，其<xref:System.Windows.Controls.ContentControl.Content%2A>设置为字符串，<xref:System.DateTime>对象， <xref:System.Windows.Shapes.Rectangle>，和一个<xref:System.Windows.Controls.Panel>，其中包含<xref:System.Windows.Shapes.Ellipse>和<xref:System.Windows.Controls.TextBlock>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="90e0c-128">![四个按钮](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span><span class="sxs-lookup"><span data-stu-id="90e0c-128">![Four buttons](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span></span>  
<span data-ttu-id="90e0c-129">具有不同类型内容的四个按钮</span><span class="sxs-lookup"><span data-stu-id="90e0c-129">Four buttons that have different types of content</span></span>  
  
 <span data-ttu-id="90e0c-130">有关如何设置的示例<xref:System.Windows.Controls.ContentControl.Content%2A>属性，请参阅<xref:System.Windows.Controls.ContentControl>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-130">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="90e0c-131">包含一个标头和一个任意对象的控件</span><span class="sxs-lookup"><span data-stu-id="90e0c-131">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="90e0c-132"><xref:System.Windows.Controls.HeaderedContentControl>类继承自<xref:System.Windows.Controls.ContentControl>并显示一个标头的内容。</span><span class="sxs-lookup"><span data-stu-id="90e0c-132">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="90e0c-133">它将继承的 content 属性<xref:System.Windows.Controls.ContentControl.Content%2A>，从<xref:System.Windows.Controls.ContentControl>，并定义<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>的类型的属性<xref:System.Object>; 因此，都可以为任意对象。</span><span class="sxs-lookup"><span data-stu-id="90e0c-133">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="90e0c-134">以下控件继承自<xref:System.Windows.Controls.HeaderedContentControl>并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="90e0c-134">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="90e0c-135">下图显示了两个<xref:System.Windows.Controls.TabItem>对象。</span><span class="sxs-lookup"><span data-stu-id="90e0c-135">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="90e0c-136">第一个<xref:System.Windows.Controls.TabItem>已<xref:System.Windows.UIElement>对象作为<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>和<xref:System.Windows.Controls.ContentControl.Content%2A>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-136">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="90e0c-137"><xref:System.Windows.Controls.HeaderedContentControl.Header%2A>设置为<xref:System.Windows.Controls.StackPanel>，其中包含<xref:System.Windows.Shapes.Ellipse>和一个<xref:System.Windows.Controls.TextBlock>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-137">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="90e0c-138"><xref:System.Windows.Controls.ContentControl.Content%2A>设置为<xref:System.Windows.Controls.StackPanel>，其中包含<xref:System.Windows.Controls.TextBlock>和一个<xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-138">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="90e0c-139">第二个<xref:System.Windows.Controls.TabItem>具有一个字符串<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>和一个<xref:System.Windows.Controls.TextBlock>中<xref:System.Windows.Controls.ContentControl.Content%2A>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-139">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 <span data-ttu-id="90e0c-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span><span class="sxs-lookup"><span data-stu-id="90e0c-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span></span>  
<span data-ttu-id="90e0c-141">在 Header 属性中使用不同类型的 TabControl</span><span class="sxs-lookup"><span data-stu-id="90e0c-141">TabControl that uses different types in the Header property</span></span>  
  
 <span data-ttu-id="90e0c-142">有关如何创建的示例<xref:System.Windows.Controls.TabItem>对象，请参阅<xref:System.Windows.Controls.HeaderedContentControl>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-142">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="90e0c-143">包含一个任意对象集合的控件</span><span class="sxs-lookup"><span data-stu-id="90e0c-143">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="90e0c-144"><xref:System.Windows.Controls.ItemsControl>类继承自<xref:System.Windows.Controls.Control>，可以包含多个项，如字符串、 对象或其他元素。</span><span class="sxs-lookup"><span data-stu-id="90e0c-144">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="90e0c-145">其内容属性为<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>和<xref:System.Windows.Controls.ItemsControl.Items%2A>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-145">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="90e0c-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 通常用于填充<xref:System.Windows.Controls.ItemsControl>与数据收集。</span><span class="sxs-lookup"><span data-stu-id="90e0c-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="90e0c-147">如果您不想要使用集合来填充<xref:System.Windows.Controls.ItemsControl>，可以通过使用添加项<xref:System.Windows.Controls.ItemsControl.Items%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="90e0c-147">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="90e0c-148">以下控件继承自<xref:System.Windows.Controls.ItemsControl>并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="90e0c-148">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Menu>  
  
-   <xref:System.Windows.Controls.Primitives.MenuBase>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ItemsControl>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
-   <xref:System.Windows.Controls.Primitives.Selector>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="90e0c-149">下图显示<xref:System.Windows.Controls.ListBox>，其中包含这些类型的项：</span><span class="sxs-lookup"><span data-stu-id="90e0c-149">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
-   <span data-ttu-id="90e0c-150">一个字符串。</span><span class="sxs-lookup"><span data-stu-id="90e0c-150">A string.</span></span>  
  
-   <span data-ttu-id="90e0c-151">一个 <xref:System.DateTime> 对象。</span><span class="sxs-lookup"><span data-stu-id="90e0c-151">A <xref:System.DateTime> object.</span></span>  
  
-   <span data-ttu-id="90e0c-152"><xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-152">A <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="90e0c-153">一个<xref:System.Windows.Controls.Panel>，其中包含<xref:System.Windows.Shapes.Ellipse>和一个<xref:System.Windows.Controls.TextBlock>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-153">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="90e0c-154">![具有四种类型的内容的 ListBox](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span><span class="sxs-lookup"><span data-stu-id="90e0c-154">![ListBox with four types of content](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span></span>  
<span data-ttu-id="90e0c-155">包含多种类型对象的 ListBox</span><span class="sxs-lookup"><span data-stu-id="90e0c-155">ListBox that contains multiple types of objects</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="90e0c-156">包含一个标头和一个任意对象集合的控件</span><span class="sxs-lookup"><span data-stu-id="90e0c-156">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="90e0c-157"><xref:System.Windows.Controls.HeaderedItemsControl>类继承自<xref:System.Windows.Controls.ItemsControl>，可以包含多个项，如字符串、 对象或其他元素和一个标头。</span><span class="sxs-lookup"><span data-stu-id="90e0c-157">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="90e0c-158">它将继承<xref:System.Windows.Controls.ItemsControl>内容属性， <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>，并<xref:System.Windows.Controls.ItemsControl.Items%2A>，它定义<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>可以是任意对象的属性。</span><span class="sxs-lookup"><span data-stu-id="90e0c-158">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="90e0c-159">以下控件继承自<xref:System.Windows.Controls.HeaderedItemsControl>并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="90e0c-159">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="90e0c-160">包含一个 UIElement 对象集合的类</span><span class="sxs-lookup"><span data-stu-id="90e0c-160">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="90e0c-161"><xref:System.Windows.Controls.Panel>类进行定位并排列子<xref:System.Windows.UIElement>对象。</span><span class="sxs-lookup"><span data-stu-id="90e0c-161">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="90e0c-162">它的内容属性是<xref:System.Windows.Controls.Panel.Children%2A>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-162">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="90e0c-163">以下类继承自<xref:System.Windows.Controls.Panel>类并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="90e0c-163">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.Primitives.TabPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
-   <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="90e0c-164">有关详细信息，请参阅[面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="90e0c-164">For more information, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="90e0c-165">影响 UIElement 外观的类</span><span class="sxs-lookup"><span data-stu-id="90e0c-165">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="90e0c-166"><xref:System.Windows.Controls.Decorator>类应用视觉效果上或周围单个子<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-166">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="90e0c-167">它的内容属性是<xref:System.Windows.Controls.Decorator.Child%2A>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-167">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="90e0c-168">以下类继承自<xref:System.Windows.Controls.Decorator>并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="90e0c-168">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="90e0c-169">如下图所示<xref:System.Windows.Controls.TextBox>具有 （即装饰有）<xref:System.Windows.Controls.Border>围绕它。</span><span class="sxs-lookup"><span data-stu-id="90e0c-169">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="90e0c-170">![具有黑色边框的 TextBox](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="90e0c-170">![TextBox with black border](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="90e0c-171">具有边框的 TextBlock</span><span class="sxs-lookup"><span data-stu-id="90e0c-171">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="90e0c-172">提供 UIElement 相关视觉反馈的类</span><span class="sxs-lookup"><span data-stu-id="90e0c-172">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="90e0c-173"><xref:System.Windows.Documents.Adorner>类向用户提供可视化提示。</span><span class="sxs-lookup"><span data-stu-id="90e0c-173">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="90e0c-174">例如，使用<xref:System.Windows.Documents.Adorner>向元素添加功能句柄或提供有关控件的状态信息。</span><span class="sxs-lookup"><span data-stu-id="90e0c-174">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="90e0c-175"><xref:System.Windows.Documents.Adorner>类提供一个框架，以便您可以创建自己的装饰器。</span><span class="sxs-lookup"><span data-stu-id="90e0c-175">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="90e0c-176">不会提供任何实现的装饰器。</span><span class="sxs-lookup"><span data-stu-id="90e0c-176">does not provide any implemented adorners.</span></span> <span data-ttu-id="90e0c-177">有关详细信息，请参阅[装饰器概述](../../../../docs/framework/wpf/controls/adorners-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="90e0c-177">For more information, see [Adorners Overview](../../../../docs/framework/wpf/controls/adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="90e0c-178">可让用户输入文本的类</span><span class="sxs-lookup"><span data-stu-id="90e0c-178">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="90e0c-179">WPF 提供了三个可让用户输入文本的主要控件。</span><span class="sxs-lookup"><span data-stu-id="90e0c-179">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="90e0c-180">每个控件都以不同方式显示文本。</span><span class="sxs-lookup"><span data-stu-id="90e0c-180">Each control displays the text differently.</span></span> <span data-ttu-id="90e0c-181">下表列出了这三个与文本相关的控件、显示文本时的功能以及包含控件文本的属性。</span><span class="sxs-lookup"><span data-stu-id="90e0c-181">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="90e0c-182">控件</span><span class="sxs-lookup"><span data-stu-id="90e0c-182">Control</span></span>|<span data-ttu-id="90e0c-183">文本显示方式</span><span class="sxs-lookup"><span data-stu-id="90e0c-183">Text is displayed as</span></span>|<span data-ttu-id="90e0c-184">内容属性</span><span class="sxs-lookup"><span data-stu-id="90e0c-184">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="90e0c-185">纯文本</span><span class="sxs-lookup"><span data-stu-id="90e0c-185">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="90e0c-186">带格式文本</span><span class="sxs-lookup"><span data-stu-id="90e0c-186">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="90e0c-187">隐藏文本（字符已屏蔽）</span><span class="sxs-lookup"><span data-stu-id="90e0c-187">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="90e0c-188">显示文本的类</span><span class="sxs-lookup"><span data-stu-id="90e0c-188">Classes That Display Your Text</span></span>  
 <span data-ttu-id="90e0c-189">某些类可用于显示纯文本或带格式文本。</span><span class="sxs-lookup"><span data-stu-id="90e0c-189">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="90e0c-190">可以使用<xref:System.Windows.Controls.TextBlock>显示少量文本。</span><span class="sxs-lookup"><span data-stu-id="90e0c-190">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="90e0c-191">如果你想要显示大量文本，使用<xref:System.Windows.Controls.FlowDocumentReader>， <xref:System.Windows.Controls.FlowDocumentPageViewer>，或<xref:System.Windows.Controls.FlowDocumentScrollViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="90e0c-191">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="90e0c-192"><xref:System.Windows.Controls.TextBlock>具有两个内容属性：<xref:System.Windows.Controls.TextBlock.Text%2A>和<xref:System.Windows.Controls.TextBlock.Inlines%2A>。</span><span class="sxs-lookup"><span data-stu-id="90e0c-192">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="90e0c-193">如果想要显示使用一致格式的文本<xref:System.Windows.Controls.TextBlock.Text%2A>属性通常是最佳选择。</span><span class="sxs-lookup"><span data-stu-id="90e0c-193">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="90e0c-194">如果你打算使用不同的格式设置在整个文本，使用<xref:System.Windows.Controls.TextBlock.Inlines%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="90e0c-194">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="90e0c-195"><xref:System.Windows.Controls.TextBlock.Inlines%2A>属性是一系列<xref:System.Windows.Documents.Inline>对象，指定如何设置文本的格式。</span><span class="sxs-lookup"><span data-stu-id="90e0c-195">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="90e0c-196">下表列出的内容属性<xref:System.Windows.Controls.FlowDocumentReader>， <xref:System.Windows.Controls.FlowDocumentPageViewer>，和<xref:System.Windows.Controls.FlowDocumentScrollViewer>类。</span><span class="sxs-lookup"><span data-stu-id="90e0c-196">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="90e0c-197">控件</span><span class="sxs-lookup"><span data-stu-id="90e0c-197">Control</span></span>|<span data-ttu-id="90e0c-198">内容属性</span><span class="sxs-lookup"><span data-stu-id="90e0c-198">Content property</span></span>|<span data-ttu-id="90e0c-199">内容属性类型</span><span class="sxs-lookup"><span data-stu-id="90e0c-199">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="90e0c-200">Document</span><span class="sxs-lookup"><span data-stu-id="90e0c-200">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="90e0c-201">Document</span><span class="sxs-lookup"><span data-stu-id="90e0c-201">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="90e0c-202">Document</span><span class="sxs-lookup"><span data-stu-id="90e0c-202">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="90e0c-203"><xref:System.Windows.Documents.FlowDocument>实现<xref:System.Windows.Documents.IDocumentPaginatorSource>接口; 因此，所有三个类，可能需要<xref:System.Windows.Documents.FlowDocument>作为内容。</span><span class="sxs-lookup"><span data-stu-id="90e0c-203">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="90e0c-204">设置文本格式的类</span><span class="sxs-lookup"><span data-stu-id="90e0c-204">Classes That Format Your Text</span></span>  
 <span data-ttu-id="90e0c-205"><xref:System.Windows.Documents.TextElement> 和及其相关的类可用于设置文本的格式。</span><span class="sxs-lookup"><span data-stu-id="90e0c-205"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="90e0c-206"><xref:System.Windows.Documents.TextElement> 对象包含和中的文本格式<xref:System.Windows.Controls.TextBlock>和<xref:System.Windows.Documents.FlowDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="90e0c-206"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="90e0c-207">两种主要类型的<xref:System.Windows.Documents.TextElement>对象是<xref:System.Windows.Documents.Block>元素和<xref:System.Windows.Documents.Inline>元素。</span><span class="sxs-lookup"><span data-stu-id="90e0c-207">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="90e0c-208">一个<xref:System.Windows.Documents.Block>元素表示的文本，例如段落或列表的块。</span><span class="sxs-lookup"><span data-stu-id="90e0c-208">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="90e0c-209"><xref:System.Windows.Documents.Inline>元素表示块中的文本的一部分。</span><span class="sxs-lookup"><span data-stu-id="90e0c-209">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="90e0c-210">许多<xref:System.Windows.Documents.Inline>类指定应用于中文本的格式。</span><span class="sxs-lookup"><span data-stu-id="90e0c-210">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="90e0c-211">每个<xref:System.Windows.Documents.TextElement>具有其自己的内容模型。</span><span class="sxs-lookup"><span data-stu-id="90e0c-211">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="90e0c-212">有关详细信息，请参阅 [TextElement 内容模型概述](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="90e0c-212">For more information, see the [TextElement Content Model Overview](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e0c-213">请参阅</span><span class="sxs-lookup"><span data-stu-id="90e0c-213">See also</span></span>
- [<span data-ttu-id="90e0c-214">高级</span><span class="sxs-lookup"><span data-stu-id="90e0c-214">Advanced</span></span>](../../../../docs/framework/wpf/advanced/index.md)
