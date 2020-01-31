---
title: 使用填充在控件周围创建边框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
ms.openlocfilehash: 114186ab5784cf892cb01e9fe2648ce22cecc4b7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742198"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a><span data-ttu-id="69787-102">방법: 안쪽 여백을 사용하여 Windows Forms 컨트롤 주위에 테두리 만들기</span><span class="sxs-lookup"><span data-stu-id="69787-102">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>
<span data-ttu-id="69787-103">下面的代码示例演示如何在 <xref:System.Windows.Forms.RichTextBox> 控件周围创建边框或边框。</span><span class="sxs-lookup"><span data-stu-id="69787-103">The following code example demonstrates how to create a border or outline around a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="69787-104">该示例将 <xref:System.Windows.Forms.Panel> 控件的 <xref:System.Windows.Forms.Padding> 属性的值设置为5，并将子 <xref:System.Windows.Forms.RichTextBox> 控件的 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="69787-104">The example sets the value of a <xref:System.Windows.Forms.Panel> control’s <xref:System.Windows.Forms.Padding> property to 5 and sets the <xref:System.Windows.Forms.Control.Dock%2A> property of a child <xref:System.Windows.Forms.RichTextBox> control to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="69787-105"><xref:System.Windows.Forms.Panel> 控件的 <xref:System.Windows.Forms.Control.BackColor%2A> 设置为 <xref:System.Drawing.Color.Blue%2A>，这会在 <xref:System.Windows.Forms.RichTextBox> 控件周围创建一个蓝色边框。</span><span class="sxs-lookup"><span data-stu-id="69787-105">The <xref:System.Windows.Forms.Control.BackColor%2A> of the <xref:System.Windows.Forms.Panel> control is set to <xref:System.Drawing.Color.Blue%2A>, which creates a blue border around the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69787-106">示例</span><span class="sxs-lookup"><span data-stu-id="69787-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="69787-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69787-107">See also</span></span>

- <xref:System.Windows.Forms.Padding>
- [<span data-ttu-id="69787-108">Windows Forms 컨트롤의 여백 및 안쪽 여백</span><span class="sxs-lookup"><span data-stu-id="69787-108">Margin and Padding in Windows Forms Controls</span></span>](margin-and-padding-in-windows-forms-controls.md)
