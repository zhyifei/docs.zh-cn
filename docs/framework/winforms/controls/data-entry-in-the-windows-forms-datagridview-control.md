---
title: DataGridView 控件中的数据输入
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], data entry
- data entry [Windows Forms], dataGridView control
- data grids [Windows Forms], data entry
ms.assetid: 4a6d4676-d4e7-4b0e-9c22-50ce65ffe0d6
ms.openlocfilehash: e95095624f45cc1507735083a87293730e9133e9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743998"
---
# <a name="data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2fef5-102">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="2fef5-102">Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2fef5-103">`DataGridView` 控件提供了多项功能，使你可以更改用户在控件中添加或修改数据的方式。</span><span class="sxs-lookup"><span data-stu-id="2fef5-103">The `DataGridView` control provides several features that let you change how users add or modify data in the control.</span></span> <span data-ttu-id="2fef5-104">例如，你可以通过提供新行的默认值并在发生错误时提醒用户来使数据输入更有效。</span><span class="sxs-lookup"><span data-stu-id="2fef5-104">For example, you can make data entry more efficient by providing default values for new rows and by alerting users when errors occur.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2fef5-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="2fef5-105">In This Section</span></span>  
 [<span data-ttu-id="2fef5-106">如何：指定 Windows 窗体 DataGridView 控件的编辑模式</span><span class="sxs-lookup"><span data-stu-id="2fef5-106">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>](how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2fef5-107">介绍如何更改用户开始编辑单元格的方式。</span><span class="sxs-lookup"><span data-stu-id="2fef5-107">Describes how to change the way users start editing cells.</span></span>  
  
 [<span data-ttu-id="2fef5-108">如何：指定 Windows 窗体 DataGridView 控件中新行的默认值</span><span class="sxs-lookup"><span data-stu-id="2fef5-108">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>](specify-default-values-for-new-rows-in-the-datagrid.md)  
 <span data-ttu-id="2fef5-109">介绍如何为新记录预填充行，以节省数据输入时间。</span><span class="sxs-lookup"><span data-stu-id="2fef5-109">Describes how to prepopulate the row for new records to save data-entry time.</span></span>  
  
 [<span data-ttu-id="2fef5-110">在 Windows 窗体 DataGridView 控件中对新记录使用行</span><span class="sxs-lookup"><span data-stu-id="2fef5-110">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2fef5-111">详细说明了新记录的行，包括有关隐藏它的信息、自定义其外观以及它与 <xref:System.Windows.Forms.DataGridView.Rows%2A> 集合的关联方式。</span><span class="sxs-lookup"><span data-stu-id="2fef5-111">Describes the row for new records in detail, including information on hiding it, on customizing its appearance, and on how it relates to the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span>  
  
 [<span data-ttu-id="2fef5-112">演练：在 Windows 窗体 DataGridView 控件中验证数据</span><span class="sxs-lookup"><span data-stu-id="2fef5-112">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2fef5-113">描述如何验证用户输入以防止出现数据输入格式错误。</span><span class="sxs-lookup"><span data-stu-id="2fef5-113">Describes how to validate user input to prevent data-entry formatting errors.</span></span>  
  
 [<span data-ttu-id="2fef5-114">演练：处理在 Windows 窗体 DataGridView 控件有数据输入时发生的错误</span><span class="sxs-lookup"><span data-stu-id="2fef5-114">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 <span data-ttu-id="2fef5-115">描述如何在用户尝试提交新值时处理源自数据源的数据输入错误。</span><span class="sxs-lookup"><span data-stu-id="2fef5-115">Describes how to handle data-entry errors that originate from the data source when the user attempts to commit a new value.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2fef5-116">参考</span><span class="sxs-lookup"><span data-stu-id="2fef5-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2fef5-117">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="2fef5-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="2fef5-118">提供 <xref:System.Windows.Forms.DataGridView.EditMode%2A> 属性的参考文档。</span><span class="sxs-lookup"><span data-stu-id="2fef5-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.EditMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 <span data-ttu-id="2fef5-119">提供 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 事件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="2fef5-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataError?displayProperty=nameWithType>  
 <span data-ttu-id="2fef5-120">提供 <xref:System.Windows.Forms.DataGridView.DataError> 事件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="2fef5-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataError> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellValidating?displayProperty=nameWithType>  
 <span data-ttu-id="2fef5-121">提供 <xref:System.Windows.Forms.DataGridView.CellValidating> 事件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="2fef5-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellValidating> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2fef5-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="2fef5-122">Related Sections</span></span>  
 [<span data-ttu-id="2fef5-123">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="2fef5-123">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2fef5-124">提供一些主题，这些主题介绍如何使用数据手动或从外部数据源填充控件。</span><span class="sxs-lookup"><span data-stu-id="2fef5-124">Provides topics that describe how to populate the control with data either manually or from an external data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fef5-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fef5-125">See also</span></span>

- [<span data-ttu-id="2fef5-126">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="2fef5-126">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="2fef5-127">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="2fef5-127">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
