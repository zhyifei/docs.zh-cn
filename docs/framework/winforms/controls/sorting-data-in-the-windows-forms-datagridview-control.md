---
title: 对 Windows 窗体 DataGridView 控件中的数据进行排序
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 606ffc7bd6136b775adaaaa79cf5042cf1e2dd70
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724916"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e5460-102">对 Windows 窗体 DataGridView 控件中的数据进行排序</span><span class="sxs-lookup"><span data-stu-id="e5460-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="e5460-103">默认情况下，用户可以对中的数据排序<xref:System.Windows.Forms.DataGridView>控件通过单击文本框列标题 （或通过按 f3 键时文本框单元格侧重于.NET Framework 4.7.2 及更高版本）。</span><span class="sxs-lookup"><span data-stu-id="e5460-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="e5460-104">您可以修改<xref:System.Windows.Forms.DataGridViewColumn.SortMode>要允许用户若要按其他列类型时最好这样做的特定列的属性。</span><span class="sxs-lookup"><span data-stu-id="e5460-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="e5460-105">您可以还对数据进行排序以编程方式按任何列，或按多个列。</span><span class="sxs-lookup"><span data-stu-id="e5460-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e5460-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="e5460-106">In this section</span></span>

[<span data-ttu-id="e5460-107">Windows 窗体 DataGridView 控件中的列排序模式</span><span class="sxs-lookup"><span data-stu-id="e5460-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="e5460-108">介绍了用于对控件中的数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="e5460-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="e5460-109">如何：设置 Windows 窗体 DataGridView 控件中的列排序模式</span><span class="sxs-lookup"><span data-stu-id="e5460-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="e5460-110">介绍如何使用户能够按不是默认情况下可排序的列进行排序。</span><span class="sxs-lookup"><span data-stu-id="e5460-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="e5460-111">如何：自定义 Windows 窗体 DataGridView 控件中的排序</span><span class="sxs-lookup"><span data-stu-id="e5460-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="e5460-112">介绍如何以编程方式对数据进行排序以及如何自定义使用的排序<xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType>事件或通过实现<xref:System.Collections.IComparer>接口。</span><span class="sxs-lookup"><span data-stu-id="e5460-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="e5460-113">参考</span><span class="sxs-lookup"><span data-stu-id="e5460-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="e5460-114">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="e5460-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="e5460-115">为提供参考文档<xref:System.Windows.Forms.DataGridView.Sort%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e5460-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="e5460-116">为提供参考文档<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e5460-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="e5460-117">为提供参考文档<xref:System.Windows.Forms.DataGridViewColumnSortMode>枚举。</span><span class="sxs-lookup"><span data-stu-id="e5460-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5460-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5460-118">See also</span></span>

- [<span data-ttu-id="e5460-119">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="e5460-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="e5460-120">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="e5460-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
