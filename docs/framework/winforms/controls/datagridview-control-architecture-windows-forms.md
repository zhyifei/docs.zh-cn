---
title: DataGridView 控件体系结构（Windows 窗体）
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: d215eeaa367156c6228615a8f6e0a7f889efdf60
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713808"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="8b024-102">DataGridView 控件体系结构（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="8b024-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="8b024-103"><xref:System.Windows.Forms.DataGridView>控件和及其相关的类设计用于灵活、 可扩展的系统，用于显示和编辑表格数据。</span><span class="sxs-lookup"><span data-stu-id="8b024-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="8b024-104">这些类都包含在<xref:System.Windows.Forms?displayProperty=nameWithType>命名空间，并且它们都命名为"DataGridView"前缀。</span><span class="sxs-lookup"><span data-stu-id="8b024-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="8b024-105">体系结构元素</span><span class="sxs-lookup"><span data-stu-id="8b024-105">Architecture Elements</span></span>  
 <span data-ttu-id="8b024-106">在主<xref:System.Windows.Forms.DataGridView>伴生类派生<xref:System.Windows.Forms.DataGridViewElement>。</span><span class="sxs-lookup"><span data-stu-id="8b024-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="8b024-107">下面的对象模型说明了<xref:System.Windows.Forms.DataGridViewElement>继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="8b024-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="8b024-108">![DataGridViewElement 对象模型](./media/datagridviewelement.gif "DataGridViewElement")</span><span class="sxs-lookup"><span data-stu-id="8b024-108">![DataGridViewElement Object Model](./media/datagridviewelement.gif "DataGridViewElement")</span></span>  
<span data-ttu-id="8b024-109">DataGridViewElement 对象模型</span><span class="sxs-lookup"><span data-stu-id="8b024-109">DataGridViewElement object model</span></span>  
  
 <span data-ttu-id="8b024-110"><xref:System.Windows.Forms.DataGridViewElement>类提供了对父级的引用<xref:System.Windows.Forms.DataGridView>控件并具有<xref:System.Windows.Forms.DataGridViewElement.State%2A>属性，其中包含一个值，表示中值的组合<xref:System.Windows.Forms.DataGridViewElementStates>枚举。</span><span class="sxs-lookup"><span data-stu-id="8b024-110">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="8b024-111">以下各节介绍<xref:System.Windows.Forms.DataGridView>伴生类中更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="8b024-111">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="8b024-112">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="8b024-112">DataGridViewElementStates</span></span>  
 <span data-ttu-id="8b024-113"><xref:System.Windows.Forms.DataGridViewElementStates>枚举包含的以下值：</span><span class="sxs-lookup"><span data-stu-id="8b024-113">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="8b024-114">此枚举的值可以组合使用按位逻辑运算，因此<xref:System.Windows.Forms.DataGridViewElement.State%2A>属性可以表示多个状态在一次。</span><span class="sxs-lookup"><span data-stu-id="8b024-114">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="8b024-115">例如，<xref:System.Windows.Forms.DataGridViewElement>可同时处于<xref:System.Windows.Forms.DataGridViewElementStates.Frozen>， <xref:System.Windows.Forms.DataGridViewElementStates.Selected>，和<xref:System.Windows.Forms.DataGridViewElementStates.Visible>。</span><span class="sxs-lookup"><span data-stu-id="8b024-115">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="8b024-116">单元格和带区</span><span class="sxs-lookup"><span data-stu-id="8b024-116">Cells and Bands</span></span>  
 <span data-ttu-id="8b024-117"><xref:System.Windows.Forms.DataGridView>控件包含两种基本类型的对象： 单元格和带区。</span><span class="sxs-lookup"><span data-stu-id="8b024-117">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="8b024-118">从派生的所有单元格<xref:System.Windows.Forms.DataGridViewCell>基类。</span><span class="sxs-lookup"><span data-stu-id="8b024-118">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="8b024-119">两种类型的带区，<xref:System.Windows.Forms.DataGridViewColumn>并<xref:System.Windows.Forms.DataGridViewRow>，同时从派生<xref:System.Windows.Forms.DataGridViewBand>基类。</span><span class="sxs-lookup"><span data-stu-id="8b024-119">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="8b024-120"><xref:System.Windows.Forms.DataGridView>控件与多个类，互操作，但最常见<xref:System.Windows.Forms.DataGridViewCell>， <xref:System.Windows.Forms.DataGridViewColumn>，和<xref:System.Windows.Forms.DataGridViewRow>。</span><span class="sxs-lookup"><span data-stu-id="8b024-120">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="8b024-121">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="8b024-121">DataGridViewCell</span></span>  
 <span data-ttu-id="8b024-122">该单元格是交互的基本单位<xref:System.Windows.Forms.DataGridView>。</span><span class="sxs-lookup"><span data-stu-id="8b024-122">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="8b024-123">显示围绕单元格，并通过的单元格通常执行数据输入。</span><span class="sxs-lookup"><span data-stu-id="8b024-123">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="8b024-124">可以通过使用访问的单元格<xref:System.Windows.Forms.DataGridViewRow.Cells%2A>的集合<xref:System.Windows.Forms.DataGridViewRow>类，并且你可以通过使用访问选定的单元格<xref:System.Windows.Forms.DataGridView.SelectedCells%2A>的集合<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="8b024-124">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8b024-125">下面的对象模型说明了这种用法，并显示<xref:System.Windows.Forms.DataGridViewCell>继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="8b024-125">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="8b024-126">![DataGridViewCell 对象模型](./media/datagridviewcell.gif "DataGridViewCell")</span><span class="sxs-lookup"><span data-stu-id="8b024-126">![DataGridViewCell Object Model](./media/datagridviewcell.gif "DataGridViewCell")</span></span>  
<span data-ttu-id="8b024-127">DataGridViewCell 对象模型</span><span class="sxs-lookup"><span data-stu-id="8b024-127">DataGridViewCell object model</span></span>  
  
 <span data-ttu-id="8b024-128"><xref:System.Windows.Forms.DataGridViewCell>类型是一个抽象基类，从中派生所有单元格类型。</span><span class="sxs-lookup"><span data-stu-id="8b024-128">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="8b024-129"><xref:System.Windows.Forms.DataGridViewCell> 和其派生的类型不是 Windows 窗体控件，而某些承载 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="8b024-129"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="8b024-130">通常由托管控件处理任何支持的单元格的编辑功能。</span><span class="sxs-lookup"><span data-stu-id="8b024-130">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="8b024-131"><xref:System.Windows.Forms.DataGridViewCell> 对象不会控制其自己的外观和绘制功能相同的方式作为 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="8b024-131"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="8b024-132">相反，<xref:System.Windows.Forms.DataGridView>负责的外观及其<xref:System.Windows.Forms.DataGridViewCell>对象。</span><span class="sxs-lookup"><span data-stu-id="8b024-132">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="8b024-133">您可以会极大地影响的外观和行为的单元格与交互<xref:System.Windows.Forms.DataGridView>控件的属性和事件。</span><span class="sxs-lookup"><span data-stu-id="8b024-133">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="8b024-134">当具有特殊要求的自定义项的功能超出<xref:System.Windows.Forms.DataGridView>控件，可以实现自己的类派生自<xref:System.Windows.Forms.DataGridViewCell>或其子类之一。</span><span class="sxs-lookup"><span data-stu-id="8b024-134">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="8b024-135">以下列表列出了派生自的类<xref:System.Windows.Forms.DataGridViewCell>:</span><span class="sxs-lookup"><span data-stu-id="8b024-135">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   <span data-ttu-id="8b024-136">自定义单元格类型</span><span class="sxs-lookup"><span data-stu-id="8b024-136">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="8b024-137">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="8b024-137">DataGridViewColumn</span></span>  
 <span data-ttu-id="8b024-138">架构<xref:System.Windows.Forms.DataGridView>以表示控件的附加的数据存储区<xref:System.Windows.Forms.DataGridView>控件的列。</span><span class="sxs-lookup"><span data-stu-id="8b024-138">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="8b024-139">您可以访问<xref:System.Windows.Forms.DataGridView>控件的列使用<xref:System.Windows.Forms.DataGridView.Columns%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="8b024-139">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="8b024-140">可以使用访问所选的列<xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="8b024-140">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="8b024-141">下面的对象模型说明了这种用法，并显示<xref:System.Windows.Forms.DataGridViewColumn>继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="8b024-141">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="8b024-142">![DataGridViewColumn 对象模型](./media/datagridviewcolumn.gif "DataGridViewColumn")</span><span class="sxs-lookup"><span data-stu-id="8b024-142">![DataGridViewColumn Object Model](./media/datagridviewcolumn.gif "DataGridViewColumn")</span></span>  
<span data-ttu-id="8b024-143">DataGridViewColumn 对象模型</span><span class="sxs-lookup"><span data-stu-id="8b024-143">DataGridViewColumn object model</span></span>  
  
 <span data-ttu-id="8b024-144">某些关键的单元格类型具有相应的列类型。</span><span class="sxs-lookup"><span data-stu-id="8b024-144">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="8b024-145">这些派生自<xref:System.Windows.Forms.DataGridViewColumn>基类。</span><span class="sxs-lookup"><span data-stu-id="8b024-145">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="8b024-146">以下列表列出了派生自的类<xref:System.Windows.Forms.DataGridViewColumn>:</span><span class="sxs-lookup"><span data-stu-id="8b024-146">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   <span data-ttu-id="8b024-147">自定义列类型</span><span class="sxs-lookup"><span data-stu-id="8b024-147">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="8b024-148">DataGridView 编辑控件</span><span class="sxs-lookup"><span data-stu-id="8b024-148">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="8b024-149">通常支持高级编辑功能的单元格使用派生自的 Windows 窗体控件的托管的控件。</span><span class="sxs-lookup"><span data-stu-id="8b024-149">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="8b024-150">这些控件还实现<xref:System.Windows.Forms.IDataGridViewEditingControl>接口。</span><span class="sxs-lookup"><span data-stu-id="8b024-150">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="8b024-151">下面的对象模型演示了这些控件的用法。</span><span class="sxs-lookup"><span data-stu-id="8b024-151">The following object model illustrates the usage of these controls.</span></span>  
  
 <span data-ttu-id="8b024-152">![DataGridView 编辑控件对象模型](./media/datagridviewediting.gif "DataGridViewEditing")</span><span class="sxs-lookup"><span data-stu-id="8b024-152">![DataGridView Editing Control Object Model](./media/datagridviewediting.gif "DataGridViewEditing")</span></span>  
<span data-ttu-id="8b024-153">DataGridView 编辑控件对象模型</span><span class="sxs-lookup"><span data-stu-id="8b024-153">DataGridView editing control object model</span></span>  
  
 <span data-ttu-id="8b024-154">以下的编辑控件提供了<xref:System.Windows.Forms.DataGridView>控件：</span><span class="sxs-lookup"><span data-stu-id="8b024-154">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="8b024-155">有关创建自己的编辑控件的信息，请参阅[如何：Windows 窗体 DataGridView 单元格中承载控件](how-to-host-controls-in-windows-forms-datagridview-cells.md)。</span><span class="sxs-lookup"><span data-stu-id="8b024-155">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="8b024-156">下表说明了单元格类型、 列类型和编辑控件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="8b024-156">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="8b024-157">单元格类型</span><span class="sxs-lookup"><span data-stu-id="8b024-157">Cell type</span></span>|<span data-ttu-id="8b024-158">承载的控件</span><span class="sxs-lookup"><span data-stu-id="8b024-158">Hosted control</span></span>|<span data-ttu-id="8b024-159">列类型</span><span class="sxs-lookup"><span data-stu-id="8b024-159">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="8b024-160">n/a</span><span class="sxs-lookup"><span data-stu-id="8b024-160">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="8b024-161">不可用</span><span class="sxs-lookup"><span data-stu-id="8b024-161">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="8b024-162">不可用</span><span class="sxs-lookup"><span data-stu-id="8b024-162">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="8b024-163">n/a</span><span class="sxs-lookup"><span data-stu-id="8b024-163">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="8b024-164">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="8b024-164">DataGridViewRow</span></span>  
 <span data-ttu-id="8b024-165"><xref:System.Windows.Forms.DataGridViewRow>类显示记录的数据字段从数据存储到<xref:System.Windows.Forms.DataGridView>附加控件。</span><span class="sxs-lookup"><span data-stu-id="8b024-165">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="8b024-166">您可以访问<xref:System.Windows.Forms.DataGridView>通过使用控件的行<xref:System.Windows.Forms.DataGridView.Rows%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="8b024-166">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="8b024-167">可以使用访问所选的行<xref:System.Windows.Forms.DataGridView.SelectedRows%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="8b024-167">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="8b024-168">下面的对象模型说明了这种用法，并显示<xref:System.Windows.Forms.DataGridViewRow>继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="8b024-168">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="8b024-169">![DataGridViewRow 对象模型](./media/datagridviewrow.gif "DataGridViewRow")</span><span class="sxs-lookup"><span data-stu-id="8b024-169">![DataGridViewRow Object Model](./media/datagridviewrow.gif "DataGridViewRow")</span></span>  
<span data-ttu-id="8b024-170">DataGridViewRow 对象模型</span><span class="sxs-lookup"><span data-stu-id="8b024-170">DataGridViewRow object model</span></span>  
  
 <span data-ttu-id="8b024-171">可以派生您自己的类型从<xref:System.Windows.Forms.DataGridViewRow>类，尽管这通常不需要。</span><span class="sxs-lookup"><span data-stu-id="8b024-171">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="8b024-172"><xref:System.Windows.Forms.DataGridView>控件具有多个与行相关的事件和自定义的行为的属性及其<xref:System.Windows.Forms.DataGridViewRow>对象。</span><span class="sxs-lookup"><span data-stu-id="8b024-172">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="8b024-173">如果启用<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>属性，用于添加新行的特殊行显示为最后一行。</span><span class="sxs-lookup"><span data-stu-id="8b024-173">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="8b024-174">此行属于<xref:System.Windows.Forms.DataGridView.Rows%2A>集合，但它具有您需要注意的特殊功能。</span><span class="sxs-lookup"><span data-stu-id="8b024-174">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="8b024-175">有关详细信息，请参阅[使用 Windows 窗体 DataGridView 控件中的新记录行](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="8b024-175">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b024-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b024-176">See also</span></span>
- [<span data-ttu-id="8b024-177">DataGridView 控件概述</span><span class="sxs-lookup"><span data-stu-id="8b024-177">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="8b024-178">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="8b024-178">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8b024-179">在 Windows 窗体 DataGridView 控件中对新记录使用行</span><span class="sxs-lookup"><span data-stu-id="8b024-179">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
