---
title: "如何：指定 Windows 窗体 DataGridView 控件的编辑模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 42773e29d7071c5bc5f3d5de3660c9891788b422
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="a0928-102">如何：指定 Windows 窗体 DataGridView 控件的编辑模式</span><span class="sxs-lookup"><span data-stu-id="a0928-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a0928-103">默认情况下，用户可以编辑的当前内容<xref:System.Windows.Forms.DataGridView>文本框单元格中通过键入它，或按 f2 键。</span><span class="sxs-lookup"><span data-stu-id="a0928-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="a0928-104">这将单元格置于编辑模式为如果满足所有以下条件：</span><span class="sxs-lookup"><span data-stu-id="a0928-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
-   <span data-ttu-id="a0928-105">基础数据源支持编辑。</span><span class="sxs-lookup"><span data-stu-id="a0928-105">The underlying data source supports editing.</span></span>  
  
-   <span data-ttu-id="a0928-106"><xref:System.Windows.Forms.DataGridView>启用控制。</span><span class="sxs-lookup"><span data-stu-id="a0928-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
-   <span data-ttu-id="a0928-107"><xref:System.Windows.Forms.DataGridView.EditMode%2A>属性值不是<xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>。</span><span class="sxs-lookup"><span data-stu-id="a0928-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
-   <span data-ttu-id="a0928-108">`ReadOnly`的单元格、 行、 列和控件的属性都设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="a0928-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="a0928-109">在编辑模式下，用户可以更改单元格的值，然后按 enter 键以提交更改或按 ESC 键还原到其原始值的单元格。</span><span class="sxs-lookup"><span data-stu-id="a0928-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="a0928-110">你可以配置<xref:System.Windows.Forms.DataGridView>控制，以便在单元格进入编辑模式，只要它成为当前的单元格。</span><span class="sxs-lookup"><span data-stu-id="a0928-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="a0928-111">ENTER 和 ESC 键的行为是在这种情况下，不变，但此单元格处于编辑模式后的值是提交或还原。</span><span class="sxs-lookup"><span data-stu-id="a0928-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="a0928-112">以便单元格进入编辑模式，仅在单元格或仅当用户按 F2 用户键入时，还可以配置控件。</span><span class="sxs-lookup"><span data-stu-id="a0928-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="a0928-113">最后，可以防止单元格进入编辑模式，除非当调用<xref:System.Windows.Forms.DataGridView.BeginEdit%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="a0928-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="a0928-114">更改 DataGridView 控件的编辑模式</span><span class="sxs-lookup"><span data-stu-id="a0928-114">To change the edit mode of a DataGridView control</span></span>  
  
-   <span data-ttu-id="a0928-115">设置<xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>到适当的属性<xref:System.Windows.Forms.DataGridViewEditMode>枚举。</span><span class="sxs-lookup"><span data-stu-id="a0928-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a0928-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="a0928-116">Compiling the Code</span></span>  
 <span data-ttu-id="a0928-117">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="a0928-117">This example requires:</span></span>  
  
-   <span data-ttu-id="a0928-118">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="a0928-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="a0928-119">对 <xref:System> 和 <xref:System.Windows.Forms> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="a0928-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0928-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0928-120">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="a0928-121">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="a0928-121">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
