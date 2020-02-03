---
title: 对 DataGridView 控件中的数据进行排序
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742947"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0d08a-102">对 Windows 窗体 DataGridView 控件中的数据进行排序</span><span class="sxs-lookup"><span data-stu-id="0d08a-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="0d08a-103">默认情况下，用户可以通过单击文本框列的标题来对 <xref:System.Windows.Forms.DataGridView> 控件中的数据进行排序（或者通过在文本框单元格集中于 .NET Framework 4.7.2 和更高版本时按 F3）来对数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="0d08a-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="0d08a-104">您可以修改特定列的 <xref:System.Windows.Forms.DataGridViewColumn.SortMode> 属性，以允许用户在执行此操作时按其他列类型进行排序。</span><span class="sxs-lookup"><span data-stu-id="0d08a-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="0d08a-105">还可以通过编程方式按任何列或多个列对数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="0d08a-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0d08a-106">在本节中</span><span class="sxs-lookup"><span data-stu-id="0d08a-106">In this section</span></span>

[<span data-ttu-id="0d08a-107">Windows 窗体 DataGridView 控件中的列排序模式</span><span class="sxs-lookup"><span data-stu-id="0d08a-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="0d08a-108">描述用于对控件中的数据进行排序的选项。</span><span class="sxs-lookup"><span data-stu-id="0d08a-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="0d08a-109">如何：设置 Windows 窗体 DataGridView 控件中列的排序模式</span><span class="sxs-lookup"><span data-stu-id="0d08a-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="0d08a-110">介绍如何使用户能够按默认情况下不可排序的列排序。</span><span class="sxs-lookup"><span data-stu-id="0d08a-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="0d08a-111">如何：在 Windows 窗体 DataGridView 控件中自定义排序</span><span class="sxs-lookup"><span data-stu-id="0d08a-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="0d08a-112">描述如何以编程方式对数据进行排序，以及如何通过使用 <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> 事件或通过实现 <xref:System.Collections.IComparer> 接口自定义排序。</span><span class="sxs-lookup"><span data-stu-id="0d08a-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="0d08a-113">参考</span><span class="sxs-lookup"><span data-stu-id="0d08a-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="0d08a-114">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="0d08a-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="0d08a-115">提供 <xref:System.Windows.Forms.DataGridView.Sort%2A> 方法的参考文档。</span><span class="sxs-lookup"><span data-stu-id="0d08a-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="0d08a-116">提供 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 属性的参考文档。</span><span class="sxs-lookup"><span data-stu-id="0d08a-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="0d08a-117">提供 <xref:System.Windows.Forms.DataGridViewColumnSortMode> 枚举的参考文档。</span><span class="sxs-lookup"><span data-stu-id="0d08a-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d08a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d08a-118">See also</span></span>

- [<span data-ttu-id="0d08a-119">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="0d08a-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="0d08a-120">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="0d08a-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
