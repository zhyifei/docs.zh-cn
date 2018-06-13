---
title: 在 Windows 窗体 DataGridView 控件中显示数据
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: 06df9bbcb1e8b1b53d061dbd219a25378a311072
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529423"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="786df-102">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="786df-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="786df-103">`DataGridView`控件用于显示不同的外部数据源中的数据。</span><span class="sxs-lookup"><span data-stu-id="786df-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="786df-104">或者，你可以向控件添加行和列并手动将其填充数据。</span><span class="sxs-lookup"><span data-stu-id="786df-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="786df-105">当将控件绑定到数据源时，你可以生成自动基于数据源的架构的列。</span><span class="sxs-lookup"><span data-stu-id="786df-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="786df-106">如果这些列未出现一样为所需，可以隐藏、 删除或重新排列它们。</span><span class="sxs-lookup"><span data-stu-id="786df-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="786df-107">你还可以添加要显示不是来自数据源的补充数据的未绑定的列。</span><span class="sxs-lookup"><span data-stu-id="786df-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="786df-108">此外，可以显示你的数据使用标准格式 （例如货币格式），或者你可以自定义显示格式以便展示你的数据，但你需要 （如更改负数的背景色或替换字符串值具有相应的图像）。</span><span class="sxs-lookup"><span data-stu-id="786df-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="786df-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="786df-109">In This Section</span></span>  
 [<span data-ttu-id="786df-110">Windows 窗体 DataGridView 控件中的数据显示模式</span><span class="sxs-lookup"><span data-stu-id="786df-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="786df-111">描述用于填充具有数据的控件的选项。</span><span class="sxs-lookup"><span data-stu-id="786df-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="786df-112">Windows 窗体 DataGridView 控件中的数据格式设置</span><span class="sxs-lookup"><span data-stu-id="786df-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="786df-113">描述用于单元格显示值的格式选项。</span><span class="sxs-lookup"><span data-stu-id="786df-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="786df-114">演练：创建未绑定 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="786df-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="786df-115">描述如何手动填充具有数据的控件。</span><span class="sxs-lookup"><span data-stu-id="786df-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="786df-116">如何：将数据绑定到 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="786df-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="786df-117">描述如何通过将其绑定到填充控件与数据`BindingSource`，其中包含从数据库中提取的信息。</span><span class="sxs-lookup"><span data-stu-id="786df-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="786df-118">如何：在已绑定数据的 Windows 窗体 DataGridView 控件中自动生成列</span><span class="sxs-lookup"><span data-stu-id="786df-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="786df-119">描述如何自动生成基于绑定的数据源的列。</span><span class="sxs-lookup"><span data-stu-id="786df-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="786df-120">如何：从 Windows 窗体 DataGridView 控件中删除自动生成的列</span><span class="sxs-lookup"><span data-stu-id="786df-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="786df-121">描述如何隐藏或删除从绑定的数据源自动生成的列。</span><span class="sxs-lookup"><span data-stu-id="786df-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="786df-122">如何：在 Windows 窗体 DataGridView 控件中更改列顺序</span><span class="sxs-lookup"><span data-stu-id="786df-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="786df-123">描述如何重新排列的绑定的数据源从自动生成的列。</span><span class="sxs-lookup"><span data-stu-id="786df-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="786df-124">如何：向已绑定数据的 Windows 窗体 DataGridView 控件添加未绑定列</span><span class="sxs-lookup"><span data-stu-id="786df-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="786df-125">描述如何通过显示未绑定的其他列来补充来自绑定的数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="786df-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="786df-126">如何：将对象绑定到 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="786df-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="786df-127">描述如何将控件绑定到的任意对象的集合，以便在其自己的行中显示每个对象。</span><span class="sxs-lookup"><span data-stu-id="786df-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="786df-128">如何：访问绑定到 Windows 窗体 DataGridView 行的对象</span><span class="sxs-lookup"><span data-stu-id="786df-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](../../../../docs/framework/winforms/controls/how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="786df-129">描述如何检索绑定到控件的特定行的对象。</span><span class="sxs-lookup"><span data-stu-id="786df-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="786df-130">演练：使用两个 Windows 窗体 DataGridView 控件创建主窗体/详细信息窗体</span><span class="sxs-lookup"><span data-stu-id="786df-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="786df-131">介绍如何显示从两个相关的数据库表的数据，以便在一个显示的值`DataGridView`控件依赖于另一个控件中的当前所选行。</span><span class="sxs-lookup"><span data-stu-id="786df-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="786df-132">如何：在 Windows 窗体 DataGridView 控件中自定义数据格式设置</span><span class="sxs-lookup"><span data-stu-id="786df-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="786df-133">描述如何处理<xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>事件来更改具体取决于它们的值的单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="786df-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="786df-134">参考</span><span class="sxs-lookup"><span data-stu-id="786df-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="786df-135">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="786df-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="786df-136">提供的参考文档<xref:System.Windows.Forms.DataGridView.DataSource%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="786df-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="786df-137">提供关于 <xref:System.Windows.Forms.BindingSource> 组件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="786df-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="786df-138">相关章节</span><span class="sxs-lookup"><span data-stu-id="786df-138">Related Sections</span></span>  
 [<span data-ttu-id="786df-139">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="786df-139">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="786df-140">提供一些主题，介绍如何改变用户添加和修改控件中数据的方式。</span><span class="sxs-lookup"><span data-stu-id="786df-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786df-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="786df-141">See Also</span></span>  
 [<span data-ttu-id="786df-142">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="786df-142">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="786df-143">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="786df-143">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
