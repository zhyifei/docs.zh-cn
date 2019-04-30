---
title: 在 Windows 窗体 DataGridView 控件中显示数据
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: c153d422470ff20491567aed70557e461dc2b4e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972219"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8157d-102">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="8157d-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8157d-103">`DataGridView`控件用于显示来自各种外部数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="8157d-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="8157d-104">或者，可以向控件添加行和列，并手动填充数据。</span><span class="sxs-lookup"><span data-stu-id="8157d-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="8157d-105">当将控件绑定到数据源时，可以生成自动基于数据源的架构的列。</span><span class="sxs-lookup"><span data-stu-id="8157d-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="8157d-106">如果您会希望为其未显示这些列，可以隐藏、 删除或重新排列它们。</span><span class="sxs-lookup"><span data-stu-id="8157d-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="8157d-107">此外可以添加要显示不是来自数据源的补充数据的未绑定的列。</span><span class="sxs-lookup"><span data-stu-id="8157d-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="8157d-108">此外，可以显示你的数据使用标准格式 （例如货币格式），也可以自定义显示格式来呈现数据，但你需要 （如更改背景色为负数，或替换的字符串值具有相应的图像）。</span><span class="sxs-lookup"><span data-stu-id="8157d-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8157d-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="8157d-109">In This Section</span></span>  
 [<span data-ttu-id="8157d-110">Windows 窗体 DataGridView 控件中的数据显示模式</span><span class="sxs-lookup"><span data-stu-id="8157d-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8157d-111">介绍了用于填充数据控件。</span><span class="sxs-lookup"><span data-stu-id="8157d-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="8157d-112">Windows 窗体 DataGridView 控件中的数据格式设置</span><span class="sxs-lookup"><span data-stu-id="8157d-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8157d-113">介绍了用于设置单元格显示值的格式。</span><span class="sxs-lookup"><span data-stu-id="8157d-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="8157d-114">演练：创建未绑定的 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="8157d-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8157d-115">介绍如何手动填充数据控件。</span><span class="sxs-lookup"><span data-stu-id="8157d-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="8157d-116">如何：将数据绑定到 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="8157d-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8157d-117">介绍如何通过将其绑定到填充此控件与数据`BindingSource`，其中包含从数据库中提取的信息。</span><span class="sxs-lookup"><span data-stu-id="8157d-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="8157d-118">如何：数据绑定 Windows 窗体 DataGridView 控件中自动生成列</span><span class="sxs-lookup"><span data-stu-id="8157d-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="8157d-119">介绍如何自动生成基于绑定的数据源的列。</span><span class="sxs-lookup"><span data-stu-id="8157d-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="8157d-120">如何：从 Windows 窗体 DataGridView 控件中删除自动生成的列</span><span class="sxs-lookup"><span data-stu-id="8157d-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="8157d-121">介绍如何隐藏或删除从绑定的数据源自动生成的列。</span><span class="sxs-lookup"><span data-stu-id="8157d-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="8157d-122">如何：更改 Windows 窗体 DataGridView 控件中的列顺序</span><span class="sxs-lookup"><span data-stu-id="8157d-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8157d-123">介绍如何重新排列从绑定的数据源自动生成的列。</span><span class="sxs-lookup"><span data-stu-id="8157d-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="8157d-124">如何：向数据绑定 Windows 窗体 DataGridView 控件中添加未绑定的列</span><span class="sxs-lookup"><span data-stu-id="8157d-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="8157d-125">介绍如何通过显示未绑定的其他列来补充从绑定的数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="8157d-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="8157d-126">如何：将对象绑定到 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="8157d-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="8157d-127">介绍如何将控件绑定到任意对象的集合，以便在其自己的行中显示每个对象。</span><span class="sxs-lookup"><span data-stu-id="8157d-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="8157d-128">如何：访问对象绑定到 Windows 窗体 DataGridView 行</span><span class="sxs-lookup"><span data-stu-id="8157d-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="8157d-129">说明如何检索绑定到控件中的特定行的对象。</span><span class="sxs-lookup"><span data-stu-id="8157d-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="8157d-130">演练：创建母版/详细信息窗体使用两个 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="8157d-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="8157d-131">介绍如何显示两个相关的数据库表中的数据，以便显示一个中的值`DataGridView`控件依赖于另一个控件中当前所选行。</span><span class="sxs-lookup"><span data-stu-id="8157d-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="8157d-132">如何：自定义 Windows 窗体 DataGridView 控件中的数据格式设置</span><span class="sxs-lookup"><span data-stu-id="8157d-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8157d-133">描述如何处理<xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>事件以更改具体取决于它们的值的单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="8157d-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8157d-134">参考</span><span class="sxs-lookup"><span data-stu-id="8157d-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="8157d-135">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="8157d-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="8157d-136">为提供参考文档<xref:System.Windows.Forms.DataGridView.DataSource%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="8157d-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="8157d-137">提供关于 <xref:System.Windows.Forms.BindingSource> 组件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="8157d-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8157d-138">相关章节</span><span class="sxs-lookup"><span data-stu-id="8157d-138">Related Sections</span></span>  
 [<span data-ttu-id="8157d-139">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="8157d-139">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8157d-140">提供一些主题，介绍如何改变用户添加和修改控件中数据的方式。</span><span class="sxs-lookup"><span data-stu-id="8157d-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8157d-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="8157d-141">See also</span></span>

- [<span data-ttu-id="8157d-142">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="8157d-142">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="8157d-143">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="8157d-143">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
