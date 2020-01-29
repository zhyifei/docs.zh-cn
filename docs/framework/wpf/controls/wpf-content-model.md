---
title: 콘텐츠 모델
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
ms.openlocfilehash: a84ab2e66b4e373591fc9365b1c17d0bb0c66713
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738285"
---
# <a name="wpf-content-model"></a><span data-ttu-id="8ae09-102">WPF 콘텐츠 모델</span><span class="sxs-lookup"><span data-stu-id="8ae09-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="8ae09-103">는 다양한 형식의 콘텐츠를 표시하는 것을 기본 용도로 하는 많은 컨트롤 형식 및 컨트롤과 유사한 형식을 제공하는 프레젠테이션 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="8ae09-104">사용할 컨트롤이나 파생시킬 컨트롤을 결정하려면 특정 컨트롤이 가장 잘 표시할 수 있는 개체 유형을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="8ae09-105">이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 형식 및 컨트롤과 비슷한 형식에 대한 콘텐츠 모델을 요약하여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="8ae09-106">콘텐츠 모델은 컨트롤에 사용될 수 있는 컨트롤에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="8ae09-107">또한 이 항목에서는 각 컨트롤 모델에 대한 콘텐츠 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="8ae09-108">콘텐츠 속성은 개체의 콘텐츠를 저장하는 데 사용되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-108">A content property is a property that is used to store the content of the object.</span></span>  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="8ae09-109">임의의 콘텐츠가 들어 있는 클래스</span><span class="sxs-lookup"><span data-stu-id="8ae09-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="8ae09-110">某些控件可以包含任何类型的对象，例如字符串、<xref:System.DateTime> 对象或作为附加项的容器的 <xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="8ae09-111">例如，<xref:System.Windows.Controls.Button> 可以包含图像和某些文本;或 <xref:System.Windows.Controls.CheckBox> 可以包含 <xref:System.DateTime.Now%2A?displayProperty=nameWithType>的值。</span><span class="sxs-lookup"><span data-stu-id="8ae09-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="8ae09-112">에는 임의의 콘텐츠가 들어 있는 네 개의 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-112">has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="8ae09-113">下表列出了从 <xref:System.Windows.Controls.Control>继承的类。</span><span class="sxs-lookup"><span data-stu-id="8ae09-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="8ae09-114">임의의 콘텐츠가 들어 있는 클래스</span><span class="sxs-lookup"><span data-stu-id="8ae09-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="8ae09-115">콘텐츠</span><span class="sxs-lookup"><span data-stu-id="8ae09-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="8ae09-116">임의의 단일 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="8ae09-117">헤더 및 단일 항목이며 둘 모두 임의의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="8ae09-118">임의 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="8ae09-119">헤더와 항목 컬렉션이며 모두 임의의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="8ae09-120">이러한 클래스에서 상속하는 컨트롤은 동일한 형식의 콘텐츠를 포함하며 콘텐츠를 동일한 방식으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="8ae09-121">下图显示了一个来自每个包含图像和文本的内容模型的控件：</span><span class="sxs-lookup"><span data-stu-id="8ae09-121">The following illustration shows one control from each content model that contains an image and some text:</span></span>  
  
 ![显示四个不同控件的屏幕截图，每个内容模型一个。](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="8ae09-123">임의의 단일 개체가 들어 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8ae09-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="8ae09-124"><xref:System.Windows.Controls.ContentControl> 类包含一段任意内容。</span><span class="sxs-lookup"><span data-stu-id="8ae09-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="8ae09-125">它的内容属性为 <xref:System.Windows.Controls.ContentControl.Content%2A>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="8ae09-126">以下控件从 <xref:System.Windows.Controls.ContentControl> 继承，并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="8ae09-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="8ae09-127">下图显示了将 <xref:System.Windows.Controls.ContentControl.Content%2A> 设置为字符串、<xref:System.DateTime> 对象、<xref:System.Windows.Shapes.Rectangle>以及包含 <xref:System.Windows.Shapes.Ellipse> 和 <xref:System.Windows.Controls.TextBlock>的 <xref:System.Windows.Controls.Panel> 的四个按钮：</span><span class="sxs-lookup"><span data-stu-id="8ae09-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>:</span></span>  
  
 ![显示具有不同内容类型的四个按钮的屏幕截图。](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <span data-ttu-id="8ae09-129">有关如何设置 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性的示例，请参阅 <xref:System.Windows.Controls.ContentControl>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-129">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="8ae09-130">헤더와 임의의 단일 개체가 들어 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8ae09-130">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="8ae09-131"><xref:System.Windows.Controls.HeaderedContentControl> 类继承自 <xref:System.Windows.Controls.ContentControl> 并显示带有标头的内容。</span><span class="sxs-lookup"><span data-stu-id="8ae09-131">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="8ae09-132">它从 <xref:System.Windows.Controls.ContentControl> 继承 content 属性 <xref:System.Windows.Controls.ContentControl.Content%2A>，并定义类型 <xref:System.Object>的 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 属性;因此，两者都可以是任意对象。</span><span class="sxs-lookup"><span data-stu-id="8ae09-132">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="8ae09-133">以下控件从 <xref:System.Windows.Controls.HeaderedContentControl> 继承，并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="8ae09-133">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="8ae09-134">下图显示了两个 <xref:System.Windows.Controls.TabItem> 的对象。</span><span class="sxs-lookup"><span data-stu-id="8ae09-134">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="8ae09-135">第一个 <xref:System.Windows.Controls.TabItem> 具有 <xref:System.Windows.UIElement> 对象作为 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 和 <xref:System.Windows.Controls.ContentControl.Content%2A>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-135">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="8ae09-136"><xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 设置为包含 <xref:System.Windows.Shapes.Ellipse> 和 <xref:System.Windows.Controls.TextBlock>的 <xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-136">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="8ae09-137"><xref:System.Windows.Controls.ContentControl.Content%2A> 设置为包含 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Controls.Label>的 <xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-137">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="8ae09-138">第二个 <xref:System.Windows.Controls.TabItem> 在 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 中有一个字符串，<xref:System.Windows.Controls.TextBlock> 在 <xref:System.Windows.Controls.ContentControl.Content%2A>中。</span><span class="sxs-lookup"><span data-stu-id="8ae09-138">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 ![在标头属性中使用不同类型的 TabControl。](./media/wpf-content-model/control-content-model-tab.png)  
  
 <span data-ttu-id="8ae09-140">有关如何创建 <xref:System.Windows.Controls.TabItem> 对象的示例，请参阅 <xref:System.Windows.Controls.HeaderedContentControl>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-140">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="8ae09-141">임의 개체의 컬렉션을 포함하는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8ae09-141">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="8ae09-142"><xref:System.Windows.Controls.ItemsControl> 类继承自 <xref:System.Windows.Controls.Control>，可以包含多个项，例如字符串、对象或其他元素。</span><span class="sxs-lookup"><span data-stu-id="8ae09-142">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="8ae09-143">它的内容属性是 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 和 <xref:System.Windows.Controls.ItemsControl.Items%2A>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-143">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="8ae09-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 通常用于填充包含数据集合的 <xref:System.Windows.Controls.ItemsControl>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="8ae09-145">如果不想使用集合来填充 <xref:System.Windows.Controls.ItemsControl>，则可以通过使用 <xref:System.Windows.Controls.ItemsControl.Items%2A> 属性添加项。</span><span class="sxs-lookup"><span data-stu-id="8ae09-145">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="8ae09-146">以下控件从 <xref:System.Windows.Controls.ItemsControl> 继承，并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="8ae09-146">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="8ae09-147">下图显示了包含以下类型的项的 <xref:System.Windows.Controls.ListBox>：</span><span class="sxs-lookup"><span data-stu-id="8ae09-147">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
- <span data-ttu-id="8ae09-148">문자열</span><span class="sxs-lookup"><span data-stu-id="8ae09-148">A string.</span></span>  
  
- <span data-ttu-id="8ae09-149"><xref:System.DateTime> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-149">A <xref:System.DateTime> object.</span></span>  
  
- <span data-ttu-id="8ae09-150"><xref:System.Windows.UIElement></span><span class="sxs-lookup"><span data-stu-id="8ae09-150">A <xref:System.Windows.UIElement>.</span></span>  
  
- <span data-ttu-id="8ae09-151">包含 <xref:System.Windows.Shapes.Ellipse> 和 <xref:System.Windows.Controls.TextBlock>的 <xref:System.Windows.Controls.Panel>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-151">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 ![显示具有四种内容类型的列表框的屏幕截图。](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="8ae09-153">헤더와 임의 개체의 컬렉션을 포함하는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8ae09-153">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="8ae09-154"><xref:System.Windows.Controls.HeaderedItemsControl> 类继承自 <xref:System.Windows.Controls.ItemsControl>，可以包含多个项，例如字符串、对象或其他元素以及标头。</span><span class="sxs-lookup"><span data-stu-id="8ae09-154">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="8ae09-155">它继承 <xref:System.Windows.Controls.ItemsControl> 内容属性、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>和 <xref:System.Windows.Controls.ItemsControl.Items%2A>，并定义可以为任意对象的 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="8ae09-155">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="8ae09-156">以下控件从 <xref:System.Windows.Controls.HeaderedItemsControl> 继承，并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="8ae09-156">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="8ae09-157">UIElement 개체 컬렉션을 포함하는 클래스</span><span class="sxs-lookup"><span data-stu-id="8ae09-157">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="8ae09-158"><xref:System.Windows.Controls.Panel> 类定位和排列子 <xref:System.Windows.UIElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="8ae09-158">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="8ae09-159">它的内容属性为 <xref:System.Windows.Controls.Panel.Children%2A>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-159">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="8ae09-160">下面的类从 <xref:System.Windows.Controls.Panel> 类继承并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="8ae09-160">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="8ae09-161">자세한 내용은 [패널 개요](panels-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ae09-161">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="8ae09-162">UIElement의 모양에 영향을 주는 클래스</span><span class="sxs-lookup"><span data-stu-id="8ae09-162">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="8ae09-163"><xref:System.Windows.Controls.Decorator> 类将视觉效果应用于单个子 <xref:System.Windows.UIElement>或围绕单个子。</span><span class="sxs-lookup"><span data-stu-id="8ae09-163">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="8ae09-164">它的内容属性为 <xref:System.Windows.Controls.Decorator.Child%2A>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-164">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="8ae09-165">以下类从 <xref:System.Windows.Controls.Decorator> 继承，并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="8ae09-165">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="8ae09-166">下图显示了一个围绕它的 <xref:System.Windows.Controls.Border> 的 <xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-166">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="8ae09-167">![검은색 테두리가 있는 TextBox](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="8ae09-167">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="8ae09-168">테두리가 있는 TextBlock</span><span class="sxs-lookup"><span data-stu-id="8ae09-168">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="8ae09-169">UIElement에 대한 시각적 피드백을 제공하는 클래스</span><span class="sxs-lookup"><span data-stu-id="8ae09-169">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="8ae09-170"><xref:System.Windows.Documents.Adorner> 类向用户提供视觉提示。</span><span class="sxs-lookup"><span data-stu-id="8ae09-170">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="8ae09-171">例如，使用 <xref:System.Windows.Documents.Adorner> 向元素添加功能句柄，或提供有关控件的状态信息。</span><span class="sxs-lookup"><span data-stu-id="8ae09-171">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="8ae09-172"><xref:System.Windows.Documents.Adorner> 类提供了一个框架，以便您可以创建自己的装饰器。</span><span class="sxs-lookup"><span data-stu-id="8ae09-172">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="8ae09-173">는 구현된 표시기를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-173">does not provide any implemented adorners.</span></span> <span data-ttu-id="8ae09-174">자세한 내용은 [표시기 개요](adorners-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ae09-174">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="8ae09-175">사용자가 텍스트를 입력할 수 있는 클래스</span><span class="sxs-lookup"><span data-stu-id="8ae09-175">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="8ae09-176">WPF는 사용자가 텍스트를 입력할 수 있는 세 개의 기본 컨트롤을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-176">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="8ae09-177">각 컨트롤에는 텍스트가 다르게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-177">Each control displays the text differently.</span></span> <span data-ttu-id="8ae09-178">다음 표에서는 이 세 가지 텍스트 관련 컨트롤과 텍스트를 표시할 때의 기능 및 컨트롤 텍스트를 포함하는 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-178">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="8ae09-179">Control</span><span class="sxs-lookup"><span data-stu-id="8ae09-179">Control</span></span>|<span data-ttu-id="8ae09-180">텍스트 표시</span><span class="sxs-lookup"><span data-stu-id="8ae09-180">Text is displayed as</span></span>|<span data-ttu-id="8ae09-181">콘텐츠 속성</span><span class="sxs-lookup"><span data-stu-id="8ae09-181">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="8ae09-182">일반 텍스트</span><span class="sxs-lookup"><span data-stu-id="8ae09-182">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="8ae09-183">서식 있는 텍스트</span><span class="sxs-lookup"><span data-stu-id="8ae09-183">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="8ae09-184">숨겨진 텍스트(문자가 마스킹됨)</span><span class="sxs-lookup"><span data-stu-id="8ae09-184">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="8ae09-185">텍스트를 표시하는 클래스</span><span class="sxs-lookup"><span data-stu-id="8ae09-185">Classes That Display Your Text</span></span>  
 <span data-ttu-id="8ae09-186">여러 클래스를 사용하여 일반 텍스트나 서식이 지정된 텍스트를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae09-186">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="8ae09-187">您可以使用 <xref:System.Windows.Controls.TextBlock> 显示少量文本。</span><span class="sxs-lookup"><span data-stu-id="8ae09-187">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="8ae09-188">如果要显示大量文本，请使用 <xref:System.Windows.Controls.FlowDocumentReader>、<xref:System.Windows.Controls.FlowDocumentPageViewer>或 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 控件。</span><span class="sxs-lookup"><span data-stu-id="8ae09-188">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="8ae09-189"><xref:System.Windows.Controls.TextBlock> 具有两个内容属性： <xref:System.Windows.Controls.TextBlock.Text%2A> 和 <xref:System.Windows.Controls.TextBlock.Inlines%2A>。</span><span class="sxs-lookup"><span data-stu-id="8ae09-189">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="8ae09-190">如果要显示使用一致格式的文本，则 <xref:System.Windows.Controls.TextBlock.Text%2A> 属性通常是最佳选择。</span><span class="sxs-lookup"><span data-stu-id="8ae09-190">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="8ae09-191">如果计划在整个文本中使用不同的格式，请使用 <xref:System.Windows.Controls.TextBlock.Inlines%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="8ae09-191">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="8ae09-192"><xref:System.Windows.Controls.TextBlock.Inlines%2A> 属性是 <xref:System.Windows.Documents.Inline> 对象的集合，这些对象指定如何设置文本格式。</span><span class="sxs-lookup"><span data-stu-id="8ae09-192">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="8ae09-193">下表列出了 <xref:System.Windows.Controls.FlowDocumentReader>、<xref:System.Windows.Controls.FlowDocumentPageViewer>和 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 类的 content 属性。</span><span class="sxs-lookup"><span data-stu-id="8ae09-193">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="8ae09-194">Control</span><span class="sxs-lookup"><span data-stu-id="8ae09-194">Control</span></span>|<span data-ttu-id="8ae09-195">콘텐츠 속성</span><span class="sxs-lookup"><span data-stu-id="8ae09-195">Content property</span></span>|<span data-ttu-id="8ae09-196">콘텐츠 속성 형식</span><span class="sxs-lookup"><span data-stu-id="8ae09-196">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="8ae09-197">문서</span><span class="sxs-lookup"><span data-stu-id="8ae09-197">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="8ae09-198">문서</span><span class="sxs-lookup"><span data-stu-id="8ae09-198">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="8ae09-199">문서</span><span class="sxs-lookup"><span data-stu-id="8ae09-199">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="8ae09-200"><xref:System.Windows.Documents.FlowDocument> 实现 <xref:System.Windows.Documents.IDocumentPaginatorSource> 接口;因此，这三个类都可以将 <xref:System.Windows.Documents.FlowDocument> 作为内容。</span><span class="sxs-lookup"><span data-stu-id="8ae09-200">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="8ae09-201">텍스트 서식을 지정하는 클래스</span><span class="sxs-lookup"><span data-stu-id="8ae09-201">Classes That Format Your Text</span></span>  
 <span data-ttu-id="8ae09-202"><xref:System.Windows.Documents.TextElement> 及其相关类允许您设置文本格式。</span><span class="sxs-lookup"><span data-stu-id="8ae09-202"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="8ae09-203"><xref:System.Windows.Documents.TextElement> 对象包含 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Documents.FlowDocument> 对象中的文本并设置其格式。</span><span class="sxs-lookup"><span data-stu-id="8ae09-203"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="8ae09-204"><xref:System.Windows.Documents.TextElement> 对象的两个主要类型是 <xref:System.Windows.Documents.Block> 元素和 <xref:System.Windows.Documents.Inline> 元素。</span><span class="sxs-lookup"><span data-stu-id="8ae09-204">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="8ae09-205"><xref:System.Windows.Documents.Block> 元素表示文本块，如段落或列表。</span><span class="sxs-lookup"><span data-stu-id="8ae09-205">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="8ae09-206"><xref:System.Windows.Documents.Inline> 元素表示块中的部分文本。</span><span class="sxs-lookup"><span data-stu-id="8ae09-206">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="8ae09-207">许多 <xref:System.Windows.Documents.Inline> 类指定其应用到的文本的格式设置。</span><span class="sxs-lookup"><span data-stu-id="8ae09-207">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="8ae09-208">每个 <xref:System.Windows.Documents.TextElement> 都有其自己的内容模型。</span><span class="sxs-lookup"><span data-stu-id="8ae09-208">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="8ae09-209">자세한 내용은 [TextElement 콘텐츠 모델 개요](../advanced/textelement-content-model-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ae09-209">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ae09-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ae09-210">See also</span></span>

- [<span data-ttu-id="8ae09-211">고급</span><span class="sxs-lookup"><span data-stu-id="8ae09-211">Advanced</span></span>](../advanced/index.md)
