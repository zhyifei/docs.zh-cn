---
title: "具有内置所有者描述支持的控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8fb699a93effcdf0b5f88606419479d51754125b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="controls-with-built-in-owner-drawing-support"></a><span data-ttu-id="6c74e-102">具有内置所有者描述支持的控件</span><span class="sxs-lookup"><span data-stu-id="6c74e-102">Controls with Built-In Owner-Drawing Support</span></span>
<span data-ttu-id="6c74e-103">Windows 窗体中的所有者描述（也称为自定义绘图）是一种更改特定控件的可视外观的技术。</span><span class="sxs-lookup"><span data-stu-id="6c74e-103">Owner drawing in Windows Forms, which is also known as custom drawing, is a technique for changing the visual appearance of certain controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c74e-104">本主题中的"控件"一词用于表示从派生的类<xref:System.Windows.Forms.Control>或<xref:System.ComponentModel.Component>。</span><span class="sxs-lookup"><span data-stu-id="6c74e-104">The word "control" in this topic is used to mean classes that derive from either <xref:System.Windows.Forms.Control> or <xref:System.ComponentModel.Component>.</span></span>  
  
 <span data-ttu-id="6c74e-105">通常情况下，Windows 绘制自动处理通过使用属性设置，例如<xref:System.Windows.Forms.Control.BackColor%2A>以确定控件的外观。</span><span class="sxs-lookup"><span data-stu-id="6c74e-105">Typically, Windows handles painting automatically by using property settings such as <xref:System.Windows.Forms.Control.BackColor%2A> to determine the appearance of a control.</span></span> <span data-ttu-id="6c74e-106">使用所有者描述，可接管绘制进程，更改无法使用属性更改的外观元素。</span><span class="sxs-lookup"><span data-stu-id="6c74e-106">With owner drawing, you take over the painting process, changing elements of appearance that are not available by using properties.</span></span> <span data-ttu-id="6c74e-107">例如，许多控件都允许设置文本的显示颜色，但仅限于一种颜色。</span><span class="sxs-lookup"><span data-stu-id="6c74e-107">For example, many controls let you set the color of the text that is displayed, but you are limited to a single color.</span></span> <span data-ttu-id="6c74e-108">通过所有者描述，可执行诸如用黑色和红色分别显示部分文本等操作。</span><span class="sxs-lookup"><span data-stu-id="6c74e-108">Owner drawing enables you to do things like display part of the text in black and part in red.</span></span>  
  
 <span data-ttu-id="6c74e-109">实际上，所有者描述类似于在窗体上绘制图形。</span><span class="sxs-lookup"><span data-stu-id="6c74e-109">In practice, owner drawing is similar to drawing graphics on a form.</span></span> <span data-ttu-id="6c74e-110">例如，你可以使用图形方法在处理程序中窗体的<xref:System.Windows.Forms.Control.Paint>事件来模拟`ListBox`控件，但你必须编写你自己的代码以处理所有用户交互。</span><span class="sxs-lookup"><span data-stu-id="6c74e-110">For example, you could use graphics methods in a handler for the form's <xref:System.Windows.Forms.Control.Paint> event to emulate a `ListBox` control, but you would have to write your own code to handle all user interaction.</span></span> <span data-ttu-id="6c74e-111">借助所有者描述，该控件可使用代码来绘制其内容，但仍保留其所有固有功能。</span><span class="sxs-lookup"><span data-stu-id="6c74e-111">With owner drawing, the control uses your code to draw its contents but otherwise retains all its intrinsic capabilities.</span></span> <span data-ttu-id="6c74e-112">可使用图形方法绘制控件中的每一项，或在每一项的其他方面使用默认外观时自定义每一项的某些方面。</span><span class="sxs-lookup"><span data-stu-id="6c74e-112">You can use graphics methods to draw each item in the control or to customize some aspects of each item while you use the default appearance for other aspects of each item.</span></span>  
  
## <a name="owner-drawing-in-windows-forms-controls"></a><span data-ttu-id="6c74e-113">Windows 窗体控件中的所有者描述</span><span class="sxs-lookup"><span data-stu-id="6c74e-113">Owner Drawing in Windows Forms Controls</span></span>  
 <span data-ttu-id="6c74e-114">若要在支持所有者描述的控件中执行此功能，通常需设置一个属性并处理一个或多个事件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-114">To perform owner drawing in controls that support it, you will typically set one property and handle one or more events.</span></span>  
  
 <span data-ttu-id="6c74e-115">支持所有者描述的大多数控件都具有 `OwnerDraw` 或 `DrawMode` 属性，用于指示控件对自身进行绘制时是否引发其绘制相关事件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-115">Most controls that support owner drawing have an `OwnerDraw` or `DrawMode` property that indicates whether the control will raise its drawing-related event or events when it paints itself.</span></span>  
  
 <span data-ttu-id="6c74e-116">不具有 `OwnerDraw` 或 `DrawMode` 属性的控件包括 `DataGridView` 控件（提供自动发生的绘制事件）和 `ToolStrip` 事件（使用具有其自身绘制相关事件的外部呈现类绘制而成）。</span><span class="sxs-lookup"><span data-stu-id="6c74e-116">Controls that do not have an `OwnerDraw` or `DrawMode` property include the `DataGridView` control, which provides drawing events that occur automatically, and the `ToolStrip` control, which is drawn using an external rendering class that has its own drawing-related events.</span></span>  
  
 <span data-ttu-id="6c74e-117">有许多不同类型的绘制事件，但通常发生的典型绘制事件是在控件中绘制单个项。</span><span class="sxs-lookup"><span data-stu-id="6c74e-117">There are many different kinds of drawing events, but a typical drawing event occurs in order to draw a single item within a control.</span></span> <span data-ttu-id="6c74e-118">事件处理程序接收一个 `EventArgs` 对象，其中包含与要绘制的项以及可用于绘制该项的工具有关的信息。</span><span class="sxs-lookup"><span data-stu-id="6c74e-118">The event handler receives an `EventArgs` object that contains information about the item being drawn and tools you can use to draw it.</span></span> <span data-ttu-id="6c74e-119">例如，此对象通常包含在其父集合中的项的索引号<xref:System.Drawing.Rectangle>，该值指示项的显示边界，和一个<xref:System.Drawing.Graphics>用于调用绘制方法的对象。</span><span class="sxs-lookup"><span data-stu-id="6c74e-119">For example, this object typically contains the item's index number within its parent collection, a <xref:System.Drawing.Rectangle> that indicates the item's display boundaries, and a <xref:System.Drawing.Graphics> object for calling paint methods.</span></span> <span data-ttu-id="6c74e-120">对于某些事件，`EventArgs` 对象提供有关项和方法的附加信息，默认情况下可调用这些方法来绘制该项的某些方面，例如背景和聚焦框。</span><span class="sxs-lookup"><span data-stu-id="6c74e-120">For some events, the `EventArgs` object provides additional information about the item and methods that you can call to paint some aspects of the item by default, such as the background or a focus rectangle.</span></span>  
  
 <span data-ttu-id="6c74e-121">若要创建包含所有者描述的自定义项的可重用控件，请创建一个派生自控件类（支持所有者描述）的新类。</span><span class="sxs-lookup"><span data-stu-id="6c74e-121">To create a reusable control that contains your owner-drawn customizations, create a new class that derives from a control class that supports owner drawing.</span></span> <span data-ttu-id="6c74e-122">不需要对绘制事件进行处理，只需在新类中包含所有者描述代码，并替代相应的 `On`*EventName* 方法。</span><span class="sxs-lookup"><span data-stu-id="6c74e-122">Rather than handling drawing events, include your owner-drawing code in overrides for the appropriate `On`*EventName* method or methods in the new class.</span></span> <span data-ttu-id="6c74e-123">在这种情况下，务必调用基类 `On`*EventName* 方法，以便使用该控件的用户能够处理所有者描述事件并提供其他自定义内容。</span><span class="sxs-lookup"><span data-stu-id="6c74e-123">Make sure that you call the base class `On`*EventName* method or methods in this case so that users of your control can handle owner-drawing events and provide additional customization.</span></span>  
  
 <span data-ttu-id="6c74e-124">以下 Windows 窗体控件在所有版本的 .NET Framework 中都支持所有者描述：</span><span class="sxs-lookup"><span data-stu-id="6c74e-124">The following Windows Forms controls support owner drawing in all versions of the .NET Framework:</span></span>  
  
-   <xref:System.Windows.Forms.ListBox>  
  
-   <xref:System.Windows.Forms.ComboBox>  
  
-   <span data-ttu-id="6c74e-125"><xref:System.Windows.Forms.MenuItem>(使用<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>)</span><span class="sxs-lookup"><span data-stu-id="6c74e-125"><xref:System.Windows.Forms.MenuItem> (used by <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu>)</span></span>  
  
-   <xref:System.Windows.Forms.TabControl>  
  
 <span data-ttu-id="6c74e-126">以下控件仅在 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 中支持所有者描述：</span><span class="sxs-lookup"><span data-stu-id="6c74e-126">The following controls support owner drawing only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span></span>  
  
-   <xref:System.Windows.Forms.ToolTip>  
  
-   <xref:System.Windows.Forms.ListView>  
  
-   <xref:System.Windows.Forms.TreeView>  
  
 <span data-ttu-id="6c74e-127">以下控件支持所有者描述且是 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 中的新增功能：</span><span class="sxs-lookup"><span data-stu-id="6c74e-127">The following controls support owner drawing and are new in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridView>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
 <span data-ttu-id="6c74e-128">以下各节进一步详述了以上每个控件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-128">The following sections provide additional details for each of these controls.</span></span>  
  
### <a name="listbox-and-combobox-controls"></a><span data-ttu-id="6c74e-129">ListBox 和 ComboBox 控件</span><span class="sxs-lookup"><span data-stu-id="6c74e-129">ListBox and ComboBox Controls</span></span>  
 <span data-ttu-id="6c74e-130"><xref:System.Windows.Forms.ListBox>和<xref:System.Windows.Forms.ComboBox>控件，可以绘制控件都在一个大小，或采用不同的大小中的各个项。</span><span class="sxs-lookup"><span data-stu-id="6c74e-130">The <xref:System.Windows.Forms.ListBox> and <xref:System.Windows.Forms.ComboBox> controls enable you to draw individual items in the control either all in one size, or in varying sizes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c74e-131">尽管<xref:System.Windows.Forms.CheckedListBox>控件派生自<xref:System.Windows.Forms.ListBox>控件，它不支持所有者描述。</span><span class="sxs-lookup"><span data-stu-id="6c74e-131">Although the <xref:System.Windows.Forms.CheckedListBox> control is derived from the <xref:System.Windows.Forms.ListBox> control, it does not support owner drawing.</span></span>  
  
 <span data-ttu-id="6c74e-132">若要绘制每个项相同的大小，请设置`DrawMode`属性<xref:System.Windows.Forms.DrawMode.OwnerDrawFixed>并处理`DrawItem`事件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-132">To draw each item the same size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="6c74e-133">若要绘制每个项使用不同的大小，请设置`DrawMode`属性<xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>和同时处理`MeasureItem`和`DrawItem`事件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-133">To draw each item using a different size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> and handle both the `MeasureItem` and `DrawItem` events.</span></span> <span data-ttu-id="6c74e-134">使用 `MeasureItem` 事件可在项发生 `DrawItem` 事件之前指示该项的大小。</span><span class="sxs-lookup"><span data-stu-id="6c74e-134">The `MeasureItem` event lets you indicate the size of an item before the `DrawItem` event occurs for that item.</span></span>  
  
 <span data-ttu-id="6c74e-135">有关详细信息（包括代码示例），请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="6c74e-135">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
-   [<span data-ttu-id="6c74e-136">如何：在 ComboBox 控件中创建大小可变的文本</span><span class="sxs-lookup"><span data-stu-id="6c74e-136">How to: Create Variable Sized Text in a ComboBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a><span data-ttu-id="6c74e-137">MenuItem 组件</span><span class="sxs-lookup"><span data-stu-id="6c74e-137">MenuItem Component</span></span>  
 <span data-ttu-id="6c74e-138"><xref:System.Windows.Forms.MenuItem>组件表示中的单个菜单项<xref:System.Windows.Forms.MainMenu>或<xref:System.Windows.Forms.ContextMenu>组件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-138">The <xref:System.Windows.Forms.MenuItem> component represents a single menu item in a <xref:System.Windows.Forms.MainMenu> or <xref:System.Windows.Forms.ContextMenu> component.</span></span>  
  
 <span data-ttu-id="6c74e-139">若要绘制<xref:System.Windows.Forms.MenuItem>，将其`OwnerDraw`属性`true`并处理其`DrawItem`事件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-139">To draw a <xref:System.Windows.Forms.MenuItem>, set its `OwnerDraw` property to `true` and handle its `DrawItem` event.</span></span> <span data-ttu-id="6c74e-140">若要在发生 `DrawItem` 事件之前自定义菜单项的大小，请处理该项的 `MeasureItem` 事件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-140">To customize the size of the menu item before the `DrawItem` event occurs, handle the item's `MeasureItem` event.</span></span>  
  
 <span data-ttu-id="6c74e-141">有关详细信息（包括代码示例），请参阅以下参考主题：</span><span class="sxs-lookup"><span data-stu-id="6c74e-141">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a><span data-ttu-id="6c74e-142">TabControl 控件</span><span class="sxs-lookup"><span data-stu-id="6c74e-142">TabControl Control</span></span>  
 <span data-ttu-id="6c74e-143"><xref:System.Windows.Forms.TabControl>控制，你可以绘制控件中的单独的选项卡。</span><span class="sxs-lookup"><span data-stu-id="6c74e-143">The <xref:System.Windows.Forms.TabControl> control enables you to draw individual tabs in the control.</span></span> <span data-ttu-id="6c74e-144">所有者描述影响只有选项卡;<xref:System.Windows.Forms.TabPage>内容不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="6c74e-144">Owner drawing affects only the tabs; the <xref:System.Windows.Forms.TabPage> contents are not affected.</span></span>  
  
 <span data-ttu-id="6c74e-145">若要在绘制每个选项卡<xref:System.Windows.Forms.TabControl>，将其设置`DrawMode`属性<xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>并处理`DrawItem`事件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-145">To draw each tab in a <xref:System.Windows.Forms.TabControl>, set the `DrawMode` property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span> <span data-ttu-id="6c74e-146">如果选项卡在控件中可见，则对于每个选项卡，此事件只发生一次。</span><span class="sxs-lookup"><span data-stu-id="6c74e-146">This event occurs once for each tab only when the tab is visible in the control.</span></span>  
  
 <span data-ttu-id="6c74e-147">有关详细信息（包括代码示例），请参阅以下参考主题：</span><span class="sxs-lookup"><span data-stu-id="6c74e-147">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a><span data-ttu-id="6c74e-148">ToolTip 组件</span><span class="sxs-lookup"><span data-stu-id="6c74e-148">ToolTip Component</span></span>  
 <span data-ttu-id="6c74e-149"><xref:System.Windows.Forms.ToolTip>组件，可以显示时绘制整个工具提示。</span><span class="sxs-lookup"><span data-stu-id="6c74e-149">The <xref:System.Windows.Forms.ToolTip> component enables you to draw the entire ToolTip when it is displayed.</span></span>  
  
 <span data-ttu-id="6c74e-150">若要绘制<xref:System.Windows.Forms.ToolTip>，将其`OwnerDraw`属性`true`并处理其`Draw`事件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-150">To draw a <xref:System.Windows.Forms.ToolTip>, set its `OwnerDraw` property to `true` and handle its `Draw` event.</span></span> <span data-ttu-id="6c74e-151">若要自定义的大小<xref:System.Windows.Forms.ToolTip>之前`Draw`发生事件时，处理`Popup`事件并设置<xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A>事件处理程序中的属性。</span><span class="sxs-lookup"><span data-stu-id="6c74e-151">To customize the size of the <xref:System.Windows.Forms.ToolTip> before the `Draw` event occurs, handle the `Popup` event and set the <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> property in the event handler.</span></span>  
  
 <span data-ttu-id="6c74e-152">有关详细信息（包括代码示例），请参阅以下参考主题：</span><span class="sxs-lookup"><span data-stu-id="6c74e-152">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a><span data-ttu-id="6c74e-153">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="6c74e-153">ListView Control</span></span>  
 <span data-ttu-id="6c74e-154"><xref:System.Windows.Forms.ListView>控制，你可以绘制控件中的各个项、 子项和列标题。</span><span class="sxs-lookup"><span data-stu-id="6c74e-154">The <xref:System.Windows.Forms.ListView> control enables you to draw individual items, subitems, and column headers in the control.</span></span>  
  
 <span data-ttu-id="6c74e-155">若要在控件中启用所有者描述，请将 `OwnerDraw` 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="6c74e-155">To enable owner drawing in the control, set the `OwnerDraw` property to `true`.</span></span>  
  
 <span data-ttu-id="6c74e-156">若要绘制控件中的每个项，请处理 `DrawItem` 事件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-156">To draw each item in the control, handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="6c74e-157">若要绘制控件中的每个子项或列的标头时<xref:System.Windows.Forms.ListView.View%2A>属性设置为<xref:System.Windows.Forms.View.Details>，处理`DrawSubItem`和`DrawColumnHeader`事件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-157">To draw each subitem or column header in the control when the <xref:System.Windows.Forms.ListView.View%2A> property is set to <xref:System.Windows.Forms.View.Details>, handle the `DrawSubItem` and `DrawColumnHeader` events.</span></span>  
  
 <span data-ttu-id="6c74e-158">有关详细信息（包括代码示例），请参阅以下参考主题：</span><span class="sxs-lookup"><span data-stu-id="6c74e-158">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a><span data-ttu-id="6c74e-159">TreeView 控件</span><span class="sxs-lookup"><span data-stu-id="6c74e-159">TreeView Control</span></span>  
 <span data-ttu-id="6c74e-160"><xref:System.Windows.Forms.TreeView>控制，你可以绘制控件中的各个节点。</span><span class="sxs-lookup"><span data-stu-id="6c74e-160">The <xref:System.Windows.Forms.TreeView> control enables you to draw individual nodes in the control.</span></span>  
  
 <span data-ttu-id="6c74e-161">若要绘制仅显示每个节点中的文本，设置`DrawMode`属性<xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText>并处理`DrawNode`事件来绘制文本。</span><span class="sxs-lookup"><span data-stu-id="6c74e-161">To draw only the text displayed in each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> and handle the `DrawNode` event to draw the text.</span></span>  
  
 <span data-ttu-id="6c74e-162">若要绘制的每个节点的所有元素，设置`DrawMode`属性<xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll>并处理`DrawNode`事件以便都绘制无论你将需要如文本、 图标、 复选框，加号和减号情况下，和连接节点的行的元素。</span><span class="sxs-lookup"><span data-stu-id="6c74e-162">To draw all elements of each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> and handle the `DrawNode` event to draw whichever elements you need, such as text, icons, check boxes, plus and minus signs, and lines connecting the nodes.</span></span>  
  
 <span data-ttu-id="6c74e-163">有关详细信息（包括代码示例），请参阅以下参考主题：</span><span class="sxs-lookup"><span data-stu-id="6c74e-163">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a><span data-ttu-id="6c74e-164">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="6c74e-164">DataGridView Control</span></span>  
 <span data-ttu-id="6c74e-165"><xref:System.Windows.Forms.DataGridView>控制，你可以绘制控件中的各个单元格和行。</span><span class="sxs-lookup"><span data-stu-id="6c74e-165">The <xref:System.Windows.Forms.DataGridView> control enables you to draw individual cells and rows in the control.</span></span>  
  
 <span data-ttu-id="6c74e-166">若要绘制各个单元格，请处理 `CellPainting` 事件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-166">To draw individual cells, handle the `CellPainting` event.</span></span>  
  
 <span data-ttu-id="6c74e-167">若要绘制各个行或行的元素，请择一/同时处理 `RowPrePaint` 和 `RowPostPaint` 事件。</span><span class="sxs-lookup"><span data-stu-id="6c74e-167">To draw individual rows or elements of rows, handle one or both of the `RowPrePaint` and `RowPostPaint` events.</span></span> <span data-ttu-id="6c74e-168">`RowPrePaint` 事件发生在绘制行中的单元格之前，`RowPostPaint` 事件发生在绘制单元格之后。</span><span class="sxs-lookup"><span data-stu-id="6c74e-168">The `RowPrePaint` event occurs before the cells in a row are painted, and the `RowPostPaint` event occurs after the cells are painted.</span></span> <span data-ttu-id="6c74e-169">可同时处理这两个事件和 `CellPainting` 事件以分别绘制行背景、各个单元格和行前景，或者可在需要的位置提供特定自定义内容并对行中的其他元素使用默认显示。</span><span class="sxs-lookup"><span data-stu-id="6c74e-169">You can handle both events and the `CellPainting` event to paint row background, individual cells, and row foreground separately, or you can provide specific customizations where you need them and use the default display for other elements of the row.</span></span>  
  
 <span data-ttu-id="6c74e-170">有关详细信息（包括代码示例），请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="6c74e-170">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
-   [<span data-ttu-id="6c74e-171">如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观</span><span class="sxs-lookup"><span data-stu-id="6c74e-171">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
  
-   [<span data-ttu-id="6c74e-172">如何：自定义 Windows 窗体 DataGridView 控件中行的外观</span><span class="sxs-lookup"><span data-stu-id="6c74e-172">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a><span data-ttu-id="6c74e-173">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="6c74e-173">ToolStrip Control</span></span>  
 <span data-ttu-id="6c74e-174"><xref:System.Windows.Forms.ToolStrip>和派生的控件，可以自定义其外观的任何方面。</span><span class="sxs-lookup"><span data-stu-id="6c74e-174"><xref:System.Windows.Forms.ToolStrip> and derived controls enable you to customize any aspect of their appearance.</span></span>  
  
 <span data-ttu-id="6c74e-175">若要提供自定义呈现<xref:System.Windows.Forms.ToolStrip>控件中，设置`Renderer`属性<xref:System.Windows.Forms.ToolStrip>， <xref:System.Windows.Forms.ToolStripManager>， <xref:System.Windows.Forms.ToolStripPanel>，或<xref:System.Windows.Forms.ToolStripContentPanel>到`ToolStripRenderer`对象，然后处理一个或多个由提供的许多绘图事件`ToolStripRenderer`类。</span><span class="sxs-lookup"><span data-stu-id="6c74e-175">To provide custom rendering for <xref:System.Windows.Forms.ToolStrip> controls, set the `Renderer` property of a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, or <xref:System.Windows.Forms.ToolStripContentPanel> to a `ToolStripRenderer` object and handle one or more of the many drawing events provided by the `ToolStripRenderer` class.</span></span> <span data-ttu-id="6c74e-176">或者，设置`Renderer`指向你自己的类的实例的属性派生自`ToolStripRenderer`， <xref:System.Windows.Forms.ToolStripProfessionalRenderer>，或<xref:System.Windows.Forms.ToolStripSystemRenderer>，实现或重写特定`On` *EventName*方法。</span><span class="sxs-lookup"><span data-stu-id="6c74e-176">Alternatively, set a `Renderer` property to an instance of your own class derived from `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, or <xref:System.Windows.Forms.ToolStripSystemRenderer> that implements or overrides specific `On`*EventName* methods.</span></span>  
  
 <span data-ttu-id="6c74e-177">有关详细信息（包括代码示例），请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="6c74e-177">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>  
  
-   [<span data-ttu-id="6c74e-178">如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="6c74e-178">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
-   [<span data-ttu-id="6c74e-179">如何：自定义绘制 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="6c74e-179">How to: Custom Draw a ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a><span data-ttu-id="6c74e-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c74e-180">See Also</span></span>  
 [<span data-ttu-id="6c74e-181">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="6c74e-181">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
