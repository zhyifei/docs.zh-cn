---
title: 对 Windows 窗体 DataGridView 控件中的数据进行排序
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1cbfb4a19e9bb0db5cbb595a91a254a3a8e3f309
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536008"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="6393d-102">对 Windows 窗体 DataGridView 控件中的数据进行排序</span><span class="sxs-lookup"><span data-stu-id="6393d-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="6393d-103">默认情况下，用户可以对数据进行排序在<xref:System.Windows.Forms.DataGridView>控制通过单击文本框列的标头 （或文本框单元格中侧重于.NET Framework 4.7.2 和更高版本时，按 F3）。</span><span class="sxs-lookup"><span data-stu-id="6393d-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="6393d-104">你可以修改<xref:System.Windows.Forms.DataGridViewColumn.SortMode>要允许用户若要按其他列类型，有必要这样做时的特定列的属性。</span><span class="sxs-lookup"><span data-stu-id="6393d-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="6393d-105">你也可以进行排序的数据以编程方式按任意列或多个列。</span><span class="sxs-lookup"><span data-stu-id="6393d-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6393d-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="6393d-106">In this section</span></span>

[<span data-ttu-id="6393d-107">Windows 窗体 DataGridView 控件中的列排序模式</span><span class="sxs-lookup"><span data-stu-id="6393d-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="6393d-108">描述对控件中的数据进行排序的选项。</span><span class="sxs-lookup"><span data-stu-id="6393d-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="6393d-109">如何：设置 Windows 窗体 DataGridView 控件中列的排序模式</span><span class="sxs-lookup"><span data-stu-id="6393d-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="6393d-110">描述如何使用户能够通过不是默认情况下可排序的列进行排序。</span><span class="sxs-lookup"><span data-stu-id="6393d-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="6393d-111">如何：在 Windows 窗体 DataGridView 控件中自定义排序</span><span class="sxs-lookup"><span data-stu-id="6393d-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="6393d-112">描述如何以编程方式对数据进行排序以及如何自定义排序通过使用<xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType>事件或通过实现<xref:System.Collections.IComparer>接口。</span><span class="sxs-lookup"><span data-stu-id="6393d-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="6393d-113">参考</span><span class="sxs-lookup"><span data-stu-id="6393d-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="6393d-114">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="6393d-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="6393d-115">提供的参考文档<xref:System.Windows.Forms.DataGridView.Sort%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="6393d-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="6393d-116">提供的参考文档<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6393d-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="6393d-117">提供的参考文档<xref:System.Windows.Forms.DataGridViewColumnSortMode>枚举。</span><span class="sxs-lookup"><span data-stu-id="6393d-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="6393d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6393d-118">See also</span></span>

[<span data-ttu-id="6393d-119">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="6393d-119">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
[<span data-ttu-id="6393d-120">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="6393d-120">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  