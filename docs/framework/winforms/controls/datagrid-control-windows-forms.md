---
title: "DataGrid 控件（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- datasets [Windows Forms], user interface
- DataGrid control [Windows Forms]
- datasets [Windows Forms], displaying in DataGrid control
- displaying data [Windows Forms], on forms
- data [Windows Forms], displaying on Windows Forms
ms.assetid: 1d9d5683-43d2-42dd-b6c3-e43f4cf0de99
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c60927451ad4350ef507f2e2a661bcfaab4ea788
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="96267-102">DataGrid 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="96267-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="96267-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 `DataGrid` 控件并添加了功能；但是，可以选择保留 `DataGrid` 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="96267-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="96267-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="96267-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="96267-105">Windows 窗体 `DataGrid` 控件向 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 数据集提供用户界面，以显示表格数据和实现数据源更新。</span><span class="sxs-lookup"><span data-stu-id="96267-105">The Windows Forms `DataGrid` control provides a user interface to [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="96267-106">`DataGrid` 控件设置为有效数据源时，则自动填充该控件，同时根据数据的形状创建列和行。</span><span class="sxs-lookup"><span data-stu-id="96267-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="96267-107">`DataGrid` 控件可用于显示单个表或显示一组表之间的分层关系。</span><span class="sxs-lookup"><span data-stu-id="96267-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96267-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="96267-108">In This Section</span></span>  
 [<span data-ttu-id="96267-109">DataGrid 控件概述</span><span class="sxs-lookup"><span data-stu-id="96267-109">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="96267-110">描述 `DataGrid` 控件的基本功能。</span><span class="sxs-lookup"><span data-stu-id="96267-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="96267-111">如何：使用设计器向 Windows 窗体 DataGrid 控件添加表和列</span><span class="sxs-lookup"><span data-stu-id="96267-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="96267-112">描述如何使用设计器向 `DataGrid` 控件添加表和列。</span><span class="sxs-lookup"><span data-stu-id="96267-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="96267-113">如何：向 Windows 窗体 DataGrid 控件添加表和列</span><span class="sxs-lookup"><span data-stu-id="96267-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="96267-114">描述如何以编程方式向 `DataGrid` 控件添加表和列。</span><span class="sxs-lookup"><span data-stu-id="96267-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="96267-115">如何：使用设计器将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="96267-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="96267-116">描述如何使用设计器将 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 数据集绑定到 `DataGrid` 控件。</span><span class="sxs-lookup"><span data-stu-id="96267-116">Describes how to bind an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="96267-117">如何：将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="96267-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="96267-118">描述如何将 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 数据集绑定到 `DataGrid` 控件。</span><span class="sxs-lookup"><span data-stu-id="96267-118">Describes how to bind an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="96267-119">如何：在运行时更改 Windows 窗体 DataGrid 控件中显示的数据</span><span class="sxs-lookup"><span data-stu-id="96267-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="96267-120">描述如何在 `DataGrid` 控件中以编程方式更改数据。</span><span class="sxs-lookup"><span data-stu-id="96267-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="96267-121">如何：使用设计器用 Windows 窗体 DataGrid 控件创建主/从列表</span><span class="sxs-lookup"><span data-stu-id="96267-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="96267-122">描述如何使用设计器在两个独立的 `DataGrid` 控件中显示以父/子关系关联在一起的两个表。</span><span class="sxs-lookup"><span data-stu-id="96267-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="96267-123">如何：使用 Windows 窗体 DataGrid 控件创建主/从列表</span><span class="sxs-lookup"><span data-stu-id="96267-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="96267-124">描述如何在两个独立的 `DataGrid` 控件中显示以父/子关系关联在一起的两个表。</span><span class="sxs-lookup"><span data-stu-id="96267-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="96267-125">如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列</span><span class="sxs-lookup"><span data-stu-id="96267-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="96267-126">描述如何在 `DataGrid` 控件中删除列。</span><span class="sxs-lookup"><span data-stu-id="96267-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="96267-127">如何：使用设计器设置 Windows 窗体 DataGrid 控件的格式</span><span class="sxs-lookup"><span data-stu-id="96267-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="96267-128">描述如何使用设计器更改 `DataGrid` 控件与外观相关的属性。</span><span class="sxs-lookup"><span data-stu-id="96267-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="96267-129">如何：设置 Windows 窗体 DataGrid 控件的格式</span><span class="sxs-lookup"><span data-stu-id="96267-129">How to: Format the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="96267-130">描述如何更改 `DataGrid` 控件与外观相关的属性。</span><span class="sxs-lookup"><span data-stu-id="96267-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="96267-131">Windows 窗体 DataGrid 控件的键盘快捷键</span><span class="sxs-lookup"><span data-stu-id="96267-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="96267-132">列出通过 `DataGrid` 控件进行导航的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="96267-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="96267-133">如何：响应 Windows 窗体 DataGrid 控件中的单击</span><span class="sxs-lookup"><span data-stu-id="96267-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="96267-134">描述如何确定用户在 `DataGrid` 控件中单击的单元格。</span><span class="sxs-lookup"><span data-stu-id="96267-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="96267-135">如何：用 Windows 窗体 DataGrid 控件验证输入</span><span class="sxs-lookup"><span data-stu-id="96267-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="96267-136">描述如何验证绑定到 `DataGrid` 控件的数据集中的输入。</span><span class="sxs-lookup"><span data-stu-id="96267-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="96267-137">参考</span><span class="sxs-lookup"><span data-stu-id="96267-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="96267-138">提供的概述<xref:System.Windows.Forms.DataGrid>类。</span><span class="sxs-lookup"><span data-stu-id="96267-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="96267-139">提供有关使用此属性将绑定的详细信息<xref:System.Windows.Forms.DataGrid>控件的数据。</span><span class="sxs-lookup"><span data-stu-id="96267-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="96267-140">相关章节</span><span class="sxs-lookup"><span data-stu-id="96267-140">Related Sections</span></span>  
 [<span data-ttu-id="96267-141">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="96267-141">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 <span data-ttu-id="96267-142">提供有关 Windows 窗体中数据绑定的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="96267-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96267-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96267-143">See Also</span></span>  
 [<span data-ttu-id="96267-144">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="96267-144">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="96267-145">Windows 窗体 DataGridView 控件和 DataGrid 控件之间的区别</span><span class="sxs-lookup"><span data-stu-id="96267-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)
