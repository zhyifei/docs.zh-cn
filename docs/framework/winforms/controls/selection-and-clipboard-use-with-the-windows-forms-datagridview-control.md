---
title: Windows 窗体 DataGridView 控件的选项和剪贴板使用
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: 1836fbc1887082ca685c49bef2bc42bdb167578f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105842"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="18fe2-102">Windows 窗体 DataGridView 控件的选项和剪贴板使用</span><span class="sxs-lookup"><span data-stu-id="18fe2-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="18fe2-103">`DataGridView`控件提供了各种用于配置如何，用户可以选择单元格、 行和列的选项。</span><span class="sxs-lookup"><span data-stu-id="18fe2-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="18fe2-104">例如，你可以启用单个或多个选定内容、 选择整个行或列，当用户单击单元格或选择整个行或列仅当用户单击其标头，从而使单元格选定区域。</span><span class="sxs-lookup"><span data-stu-id="18fe2-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="18fe2-105">如果你想要为所选内容提供您自己的用户界面，可以禁用普通所选内容并以编程方式处理所有选项。</span><span class="sxs-lookup"><span data-stu-id="18fe2-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="18fe2-106">此外，可以使用户能够将选定的值复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="18fe2-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18fe2-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="18fe2-107">In This Section</span></span>  
 [<span data-ttu-id="18fe2-108">Windows 窗体 DataGridView 控件中的选择模式</span><span class="sxs-lookup"><span data-stu-id="18fe2-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="18fe2-109">描述用户和控件中的以编程方式选择的选项。</span><span class="sxs-lookup"><span data-stu-id="18fe2-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="18fe2-110">如何：设置 Windows 窗体 DataGridView 控件的选择模式</span><span class="sxs-lookup"><span data-stu-id="18fe2-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="18fe2-111">介绍如何配置用于单行选择的控件，当用户单击一个单元格。</span><span class="sxs-lookup"><span data-stu-id="18fe2-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="18fe2-112">如何：获取 Windows 窗体 DataGridView 控件中选定的单元格、行和列</span><span class="sxs-lookup"><span data-stu-id="18fe2-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="18fe2-113">介绍如何处理与所选的单元格、 行和列集合。</span><span class="sxs-lookup"><span data-stu-id="18fe2-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="18fe2-114">如何：使用户能够将多个单元格从 Windows 窗体 DataGridView 控件复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="18fe2-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="18fe2-115">介绍如何启用控件中的剪贴板支持。</span><span class="sxs-lookup"><span data-stu-id="18fe2-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="18fe2-116">参考</span><span class="sxs-lookup"><span data-stu-id="18fe2-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="18fe2-117">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="18fe2-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="18fe2-118">为提供参考文档<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="18fe2-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="18fe2-119">为提供参考文档<xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="18fe2-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="18fe2-120">为提供参考文档<xref:System.Windows.Forms.DataGridViewSelectedCellCollection>类。</span><span class="sxs-lookup"><span data-stu-id="18fe2-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="18fe2-121">为提供参考文档<xref:System.Windows.Forms.DataGridViewSelectedRowCollection>类。</span><span class="sxs-lookup"><span data-stu-id="18fe2-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="18fe2-122">为提供参考文档<xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>类。</span><span class="sxs-lookup"><span data-stu-id="18fe2-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18fe2-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="18fe2-123">See also</span></span>

- [<span data-ttu-id="18fe2-124">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="18fe2-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="18fe2-125">Windows 窗体 DataGridView 控件中的默认键盘和鼠标处理</span><span class="sxs-lookup"><span data-stu-id="18fe2-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
