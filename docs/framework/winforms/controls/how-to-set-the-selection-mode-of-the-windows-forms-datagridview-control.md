---
title: 如何：设置 Windows 窗体 DataGridView 控件的选择模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
- data grids [Windows Forms], selection mode
ms.assetid: 2f241643-7f82-4583-8757-03494f63b465
ms.openlocfilehash: 2e430dfb170943178f6db27c0bd2c1ef0f972882
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200553"
---
# <a name="how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="9ab18-102">如何：设置 Windows 窗体 DataGridView 控件的选择模式</span><span class="sxs-lookup"><span data-stu-id="9ab18-102">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9ab18-103">下面的代码示例演示如何配置<xref:System.Windows.Forms.DataGridView>控件，以便单击的任意位置的行自动选择整行，并且可以选择一次只有一个行。</span><span class="sxs-lookup"><span data-stu-id="9ab18-103">The following code example demonstrates how to configure a <xref:System.Windows.Forms.DataGridView> control so that clicking anywhere within a row automatically selects the entire row, and so that only one row at a time can be selected.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ab18-104">示例</span><span class="sxs-lookup"><span data-stu-id="9ab18-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#065)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#065)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ab18-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="9ab18-105">Compiling the Code</span></span>  
 <span data-ttu-id="9ab18-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="9ab18-106">This example requires:</span></span>  
  
-   <span data-ttu-id="9ab18-107">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="9ab18-107">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="9ab18-108">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="9ab18-108">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab18-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ab18-109">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [<span data-ttu-id="9ab18-110">Windows 窗体 DataGridView 控件的选项和剪贴板使用</span><span class="sxs-lookup"><span data-stu-id="9ab18-110">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9ab18-111">Windows 窗体 DataGridView 控件中的选择模式</span><span class="sxs-lookup"><span data-stu-id="9ab18-111">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
