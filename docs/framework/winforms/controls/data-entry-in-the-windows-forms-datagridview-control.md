---
title: Windows 窗体 DataGridView 控件中的数据输入
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], data entry
- data entry [Windows Forms], dataGridView control
- data grids [Windows Forms], data entry
ms.assetid: 4a6d4676-d4e7-4b0e-9c22-50ce65ffe0d6
ms.openlocfilehash: 4f0dbb99b1005cfea165439f4c08db64ecb18fed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550339"
---
# <a name="data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fe104-102">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="fe104-102">Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fe104-103">`DataGridView`控件提供了多项功能，可用于更改用户添加或修改控件中的数据的方式。</span><span class="sxs-lookup"><span data-stu-id="fe104-103">The `DataGridView` control provides several features that let you change how users add or modify data in the control.</span></span> <span data-ttu-id="fe104-104">例如，您可以使数据输入效率更高通过新行提供默认值，并且发生错误时通知用户。</span><span class="sxs-lookup"><span data-stu-id="fe104-104">For example, you can make data entry more efficient by providing default values for new rows and by alerting users when errors occur.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe104-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="fe104-105">In This Section</span></span>  
 [<span data-ttu-id="fe104-106">如何：Windows 窗体 DataGridView 控件中指定的编辑模式</span><span class="sxs-lookup"><span data-stu-id="fe104-106">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fe104-107">介绍如何更改用户开始编辑单元格的方式。</span><span class="sxs-lookup"><span data-stu-id="fe104-107">Describes how to change the way users start editing cells.</span></span>  
  
 [<span data-ttu-id="fe104-108">如何：指定 Windows 窗体 DataGridView 控件中的新行的默认值</span><span class="sxs-lookup"><span data-stu-id="fe104-108">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)  
 <span data-ttu-id="fe104-109">介绍如何预填充新记录以节省数据输入时间所对应的行。</span><span class="sxs-lookup"><span data-stu-id="fe104-109">Describes how to prepopulate the row for new records to save data-entry time.</span></span>  
  
 [<span data-ttu-id="fe104-110">在 Windows 窗体 DataGridView 控件中对新记录使用行</span><span class="sxs-lookup"><span data-stu-id="fe104-110">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fe104-111">介绍用于在详细信息，包括它隐藏、 自定义其外观，以及它如何与相关的信息的新记录的行<xref:System.Windows.Forms.DataGridView.Rows%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="fe104-111">Describes the row for new records in detail, including information on hiding it, on customizing its appearance, and on how it relates to the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span>  
  
 [<span data-ttu-id="fe104-112">演练：验证 Windows 窗体 DataGridView 控件中的数据</span><span class="sxs-lookup"><span data-stu-id="fe104-112">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fe104-113">介绍如何验证用户输入，以防止数据输入格式设置错误。</span><span class="sxs-lookup"><span data-stu-id="fe104-113">Describes how to validate user input to prevent data-entry formatting errors.</span></span>  
  
 [<span data-ttu-id="fe104-114">演练：Windows 窗体 DataGridView 控件中的数据输入时发生的错误处理</span><span class="sxs-lookup"><span data-stu-id="fe104-114">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 <span data-ttu-id="fe104-115">介绍如何处理来自数据源，当用户尝试提交新值时的数据输入错误。</span><span class="sxs-lookup"><span data-stu-id="fe104-115">Describes how to handle data-entry errors that originate from the data source when the user attempts to commit a new value.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fe104-116">参考</span><span class="sxs-lookup"><span data-stu-id="fe104-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="fe104-117">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="fe104-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="fe104-118">为提供参考文档<xref:System.Windows.Forms.DataGridView.EditMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="fe104-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.EditMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 <span data-ttu-id="fe104-119">为提供参考文档<xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>事件。</span><span class="sxs-lookup"><span data-stu-id="fe104-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataError?displayProperty=nameWithType>  
 <span data-ttu-id="fe104-120">为提供参考文档<xref:System.Windows.Forms.DataGridView.DataError>事件。</span><span class="sxs-lookup"><span data-stu-id="fe104-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataError> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellValidating?displayProperty=nameWithType>  
 <span data-ttu-id="fe104-121">为提供参考文档<xref:System.Windows.Forms.DataGridView.CellValidating>事件。</span><span class="sxs-lookup"><span data-stu-id="fe104-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellValidating> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fe104-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="fe104-122">Related Sections</span></span>  
 [<span data-ttu-id="fe104-123">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="fe104-123">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fe104-124">提供一些主题，介绍如何手动或从外部数据源填充的数据控件。</span><span class="sxs-lookup"><span data-stu-id="fe104-124">Provides topics that describe how to populate the control with data either manually or from an external data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe104-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe104-125">See also</span></span>
- [<span data-ttu-id="fe104-126">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="fe104-126">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
- [<span data-ttu-id="fe104-127">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="fe104-127">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
