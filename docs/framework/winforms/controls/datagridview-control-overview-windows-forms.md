---
title: DataGridView 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- DataGridView
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- grid controls [Windows Forms]
- tables [Windows Forms], displaying in DataGridView control
- tables [Windows Forms], binding to DataGridView control
- columns [Windows Forms], DataGridView control
- bound controls [Windows Forms], dataGridView control
- datasets [Windows Forms], binding to DataGridView control
- data grids [Windows Forms], about data grids
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- grids [Windows Forms]
- data binding [Windows Forms], DataGridView control
- data sources [Windows Forms], binding to DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
ms.openlocfilehash: 03ba4e13cb014ca03f80781e6630d41c01ae6251
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529959"
---
# <a name="datagridview-control-overview-windows-forms"></a><span data-ttu-id="e02d9-102">DataGridView 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="e02d9-102">DataGridView Control Overview (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="e02d9-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="e02d9-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="e02d9-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="e02d9-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="e02d9-105">与<xref:System.Windows.Forms.DataGridView>控件，可以显示和编辑从许多不同类型的数据源的表格数据。</span><span class="sxs-lookup"><span data-stu-id="e02d9-105">With the <xref:System.Windows.Forms.DataGridView> control, you can display and edit tabular data from many different kinds of data sources.</span></span>  
  
 <span data-ttu-id="e02d9-106">将数据绑定到<xref:System.Windows.Forms.DataGridView>简单、 直观，编写控件的本质和在许多情况下非常简单，只设置<xref:System.Windows.Forms.DataGridView.DataSource%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e02d9-106">Binding data to the <xref:System.Windows.Forms.DataGridView> control is straightforward and intuitive, and in many cases it is as simple as setting the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span> <span data-ttu-id="e02d9-107">当你将绑定到数据源包含多个列表或表时，请设置<xref:System.Windows.Forms.DataGridView.DataMember%2A>属性设置为一个字符串，指定要绑定到表的列表。</span><span class="sxs-lookup"><span data-stu-id="e02d9-107">When you bind to a data source that contains multiple lists or tables, set the <xref:System.Windows.Forms.DataGridView.DataMember%2A> property to a string that specifies the list or table to bind to.</span></span>  
  
 <span data-ttu-id="e02d9-108"><xref:System.Windows.Forms.DataGridView>控件支持标准 Windows 窗体数据绑定模型，因此它可以绑定到以下列表中所述的类的实例：</span><span class="sxs-lookup"><span data-stu-id="e02d9-108">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to instances of classes described in the following list:</span></span>  
  
-   <span data-ttu-id="e02d9-109">实现任何类<xref:System.Collections.IList>接口，包括一维数组。</span><span class="sxs-lookup"><span data-stu-id="e02d9-109">Any class that implements the <xref:System.Collections.IList> interface, including one-dimensional arrays.</span></span>  
  
-   <span data-ttu-id="e02d9-110">实现任何类<xref:System.ComponentModel.IListSource>接口，如<xref:System.Data.DataTable>和<xref:System.Data.DataSet>类。</span><span class="sxs-lookup"><span data-stu-id="e02d9-110">Any class that implements the <xref:System.ComponentModel.IListSource> interface, such as the <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes.</span></span>  
  
-   <span data-ttu-id="e02d9-111">实现任何类<xref:System.ComponentModel.IBindingList>接口，如<xref:System.ComponentModel.BindingList%601>类。</span><span class="sxs-lookup"><span data-stu-id="e02d9-111">Any class that implements the <xref:System.ComponentModel.IBindingList> interface, such as the <xref:System.ComponentModel.BindingList%601> class.</span></span>  
  
-   <span data-ttu-id="e02d9-112">实现任何类<xref:System.ComponentModel.IBindingListView>接口，如<xref:System.Windows.Forms.BindingSource>类。</span><span class="sxs-lookup"><span data-stu-id="e02d9-112">Any class that implements the <xref:System.ComponentModel.IBindingListView> interface, such as the <xref:System.Windows.Forms.BindingSource> class.</span></span>  
  
 <span data-ttu-id="e02d9-113"><xref:System.Windows.Forms.DataGridView>控件支持数据绑定到这些接口返回的对象的公共属性或返回的属性集合<xref:System.ComponentModel.ICustomTypeDescriptor>接口，如果在返回的对象上实现。</span><span class="sxs-lookup"><span data-stu-id="e02d9-113">The <xref:System.Windows.Forms.DataGridView> control supports data binding to the public properties of the objects returned by these interfaces or to the properties collection returned by an <xref:System.ComponentModel.ICustomTypeDescriptor> interface, if implemented on the returned objects.</span></span>  
  
 <span data-ttu-id="e02d9-114">通常情况下，将绑定到<xref:System.Windows.Forms.BindingSource>组件和绑定<xref:System.Windows.Forms.BindingSource>组件与另一个数据源，或者使用业务对象填充它。</span><span class="sxs-lookup"><span data-stu-id="e02d9-114">Typically, you will bind to a <xref:System.Windows.Forms.BindingSource> component and bind the <xref:System.Windows.Forms.BindingSource> component to another data source or populate it with business objects.</span></span> <span data-ttu-id="e02d9-115"><xref:System.Windows.Forms.BindingSource>组件是首选的数据源，因为它可以将绑定到各种数据源，并可以自动解决许多数据绑定问题。</span><span class="sxs-lookup"><span data-stu-id="e02d9-115">The <xref:System.Windows.Forms.BindingSource> component is the preferred data source because it can bind to a wide variety of data sources and can resolve many data binding issues automatically.</span></span> <span data-ttu-id="e02d9-116">有关详细信息，请参阅[BindingSource 组件](../../../../docs/framework/winforms/controls/bindingsource-component.md)。</span><span class="sxs-lookup"><span data-stu-id="e02d9-116">For more information, see [BindingSource Component](../../../../docs/framework/winforms/controls/bindingsource-component.md).</span></span>  
  
 <span data-ttu-id="e02d9-117"><xref:System.Windows.Forms.DataGridView>控件还可在*未绑定*模式，具有任何基础数据存储区。</span><span class="sxs-lookup"><span data-stu-id="e02d9-117">The <xref:System.Windows.Forms.DataGridView> control can also be used in *unbound* mode, with no underlying data store.</span></span> <span data-ttu-id="e02d9-118">有关使用未绑定的代码示例<xref:System.Windows.Forms.DataGridView>控制，请参阅[演练： 创建未绑定的 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="e02d9-118">For a code example that uses an unbound <xref:System.Windows.Forms.DataGridView> control, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="e02d9-119"><xref:System.Windows.Forms.DataGridView>控件是高度可配置和可扩展的并且它提供许多属性、 方法和事件，以自定义其外观和行为。</span><span class="sxs-lookup"><span data-stu-id="e02d9-119">The <xref:System.Windows.Forms.DataGridView> control is highly configurable and extensible, and it provides many properties, methods, and events to customize its appearance and behavior.</span></span> <span data-ttu-id="e02d9-120">如果你想 Windows 窗体应用程序，以显示表格数据，请考虑使用<xref:System.Windows.Forms.DataGridView>之前其他控件 (例如， <xref:System.Windows.Forms.DataGrid>)。</span><span class="sxs-lookup"><span data-stu-id="e02d9-120">When you want your Windows Forms application to display tabular data, consider using the <xref:System.Windows.Forms.DataGridView> control before others (for example, <xref:System.Windows.Forms.DataGrid>).</span></span> <span data-ttu-id="e02d9-121">如果您要显示小的网格的只读的值，或如果要启用用户若要编辑的表数以百万计的记录，<xref:System.Windows.Forms.DataGridView>控制将为你提供轻松可编程、 高效利用内存的解决方案。</span><span class="sxs-lookup"><span data-stu-id="e02d9-121">If you are displaying a small grid of read-only values, or if you are enabling a user to edit a table with millions of records, the <xref:System.Windows.Forms.DataGridView> control will provide you with a readily programmable, memory-efficient solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e02d9-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="e02d9-122">In This Section</span></span>  
 [<span data-ttu-id="e02d9-123">DataGridView 控件技术摘要</span><span class="sxs-lookup"><span data-stu-id="e02d9-123">DataGridView Control Technology Summary</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-technology-summary-windows-forms.md)  
 <span data-ttu-id="e02d9-124">总结了<xref:System.Windows.Forms.DataGridView>控件的概念和相关类使用。</span><span class="sxs-lookup"><span data-stu-id="e02d9-124">Summarizes <xref:System.Windows.Forms.DataGridView> control concepts and the use of related classes.</span></span>  
  
 [<span data-ttu-id="e02d9-125">DataGridView 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="e02d9-125">DataGridView Control Architecture</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 <span data-ttu-id="e02d9-126">描述的体系结构<xref:System.Windows.Forms.DataGridView>控件，以解释其类型层次结构和继承结构。</span><span class="sxs-lookup"><span data-stu-id="e02d9-126">Describes the architecture of the <xref:System.Windows.Forms.DataGridView> control, explaining its type hierarchy and inheritance structure.</span></span>  
  
 [<span data-ttu-id="e02d9-127">DataGridView 控件应用场景</span><span class="sxs-lookup"><span data-stu-id="e02d9-127">DataGridView Control Scenarios</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-scenarios-windows-forms.md)  
 <span data-ttu-id="e02d9-128">描述在其中最常见的方案<xref:System.Windows.Forms.DataGridView>控件用于。</span><span class="sxs-lookup"><span data-stu-id="e02d9-128">Describes the most common scenarios in which <xref:System.Windows.Forms.DataGridView> controls are used.</span></span>  
  
 [<span data-ttu-id="e02d9-129">DataGridView 控件代码目录</span><span class="sxs-lookup"><span data-stu-id="e02d9-129">DataGridView Control Code Directory</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-code-directory-windows-forms.md)  
 <span data-ttu-id="e02d9-130">提供有关各种的文档中的代码示例的链接<xref:System.Windows.Forms.DataGridView>任务。</span><span class="sxs-lookup"><span data-stu-id="e02d9-130">Provides links to code examples in the documentation for various <xref:System.Windows.Forms.DataGridView> tasks.</span></span> <span data-ttu-id="e02d9-131">这些示例按任务类型进行分类。</span><span class="sxs-lookup"><span data-stu-id="e02d9-131">These examples are categorized by task type.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e02d9-132">相关章节</span><span class="sxs-lookup"><span data-stu-id="e02d9-132">Related Sections</span></span>  
 [<span data-ttu-id="e02d9-133">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="e02d9-133">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e02d9-134">讨论 Windows 窗体中的列类型<xref:System.Windows.Forms.DataGridView>控件用于显示信息，并且允许用户修改或添加信息。</span><span class="sxs-lookup"><span data-stu-id="e02d9-134">Discusses the column types in the Windows Forms <xref:System.Windows.Forms.DataGridView> control used to display information and allow users to modify or add information.</span></span>  
  
 [<span data-ttu-id="e02d9-135">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="e02d9-135">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e02d9-136">提供一些主题，描述如何手动或从外部数据源向控件填充数据。</span><span class="sxs-lookup"><span data-stu-id="e02d9-136">Provides topics that describe how to populate the control with data either manually, or from an external data source.</span></span>  
  
 [<span data-ttu-id="e02d9-137">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="e02d9-137">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e02d9-138">提供一些主题，介绍自定义绘制 <xref:System.Windows.Forms.DataGridView> 单元格和行，以及创建派生的单元、列和行类型。</span><span class="sxs-lookup"><span data-stu-id="e02d9-138">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="e02d9-139">Windows 窗体 DataGridView 控件中的性能调整</span><span class="sxs-lookup"><span data-stu-id="e02d9-139">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e02d9-140">提供一些主题，介绍如何在使用大量数据时，有效地使用控件以避免性能问题。</span><span class="sxs-lookup"><span data-stu-id="e02d9-140">Provides topics that describe how to use the control efficiently to avoid performance problems when working with large amounts of data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e02d9-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="e02d9-141">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="e02d9-142">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="e02d9-142">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="e02d9-143">Windows 窗体 DataGridView 控件中的默认功能</span><span class="sxs-lookup"><span data-stu-id="e02d9-143">Default Functionality in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="e02d9-144">Windows 窗体 DataGridView 控件中的默认键盘和鼠标处理</span><span class="sxs-lookup"><span data-stu-id="e02d9-144">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
