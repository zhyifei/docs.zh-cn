---
title: 如何：隐藏 Windows 窗体 DataGridView 控件中的列标题
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: 80377aa598938031f9708c4b7657594985ec0746
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717059"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="524ab-102">如何：隐藏 Windows 窗体 DataGridView 控件中的列标题</span><span class="sxs-lookup"><span data-stu-id="524ab-102">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="524ab-103">有时你会想要显示<xref:System.Windows.Forms.DataGridView>无列标题。</span><span class="sxs-lookup"><span data-stu-id="524ab-103">Sometimes you will want to display a <xref:System.Windows.Forms.DataGridView> without column headers.</span></span> <span data-ttu-id="524ab-104">在中<xref:System.Windows.Forms.DataGridView>控件，<xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A>属性值确定是否显示列标题。</span><span class="sxs-lookup"><span data-stu-id="524ab-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> property value determines whether the column headers are displayed.</span></span>  
  
### <a name="to-hide-the-column-headers"></a><span data-ttu-id="524ab-105">若要隐藏的列标题</span><span class="sxs-lookup"><span data-stu-id="524ab-105">To hide the column headers</span></span>  
  
-   <span data-ttu-id="524ab-106">将 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="524ab-106">Set the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="524ab-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="524ab-107">Compiling the Code</span></span>  
 <span data-ttu-id="524ab-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="524ab-108">This example requires:</span></span>  
  
-   <span data-ttu-id="524ab-109">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="524ab-109">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="524ab-110">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="524ab-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524ab-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="524ab-111">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="524ab-112">Windows 窗体 DataGridView 控件中的列、行和单元格基本功能</span><span class="sxs-lookup"><span data-stu-id="524ab-112">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
