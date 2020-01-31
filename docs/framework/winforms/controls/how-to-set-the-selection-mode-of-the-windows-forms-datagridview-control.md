---
title: 设置 DataGridView 控件的选择模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
- data grids [Windows Forms], selection mode
ms.assetid: 2f241643-7f82-4583-8757-03494f63b465
ms.openlocfilehash: da866aac3ac5b08a06ec71744aadb4260bd0cfc4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743499"
---
# <a name="how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="c8c3c-102">방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정</span><span class="sxs-lookup"><span data-stu-id="c8c3c-102">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c8c3c-103">下面的代码示例演示如何配置 <xref:System.Windows.Forms.DataGridView> 控件以便单击行中的任意位置自动选择整行，以便每次只能选择一行。</span><span class="sxs-lookup"><span data-stu-id="c8c3c-103">The following code example demonstrates how to configure a <xref:System.Windows.Forms.DataGridView> control so that clicking anywhere within a row automatically selects the entire row, and so that only one row at a time can be selected.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8c3c-104">示例</span><span class="sxs-lookup"><span data-stu-id="c8c3c-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#065)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#065)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c8c3c-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c8c3c-105">Compiling the Code</span></span>  
 <span data-ttu-id="c8c3c-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8c3c-106">This example requires:</span></span>  
  
- <span data-ttu-id="c8c3c-107">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c8c3c-107">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="c8c3c-108"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="c8c3c-108">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c3c-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8c3c-109">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [<span data-ttu-id="c8c3c-110">Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용</span><span class="sxs-lookup"><span data-stu-id="c8c3c-110">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="c8c3c-111">Windows Forms DataGridView 컨트롤의 선택 모드</span><span class="sxs-lookup"><span data-stu-id="c8c3c-111">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
