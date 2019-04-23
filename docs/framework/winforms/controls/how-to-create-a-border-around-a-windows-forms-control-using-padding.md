---
title: 如何：使用填充在 Windows 窗体控件周围创建边框
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
ms.openlocfilehash: e3bbf43dbe45e675df172a6c3e1db16a3ba9caa8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124016"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a><span data-ttu-id="94e75-102">如何：使用填充在 Windows 窗体控件周围创建边框</span><span class="sxs-lookup"><span data-stu-id="94e75-102">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>
<span data-ttu-id="94e75-103">下面的代码示例演示如何创建一个边框或周围的轮廓<xref:System.Windows.Forms.RichTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="94e75-103">The following code example demonstrates how to create a border or outline around a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="94e75-104">该示例设置的值<xref:System.Windows.Forms.Panel>控件的<xref:System.Windows.Forms.Padding>属性设置为 5 和集<xref:System.Windows.Forms.Control.Dock%2A>的子属性<xref:System.Windows.Forms.RichTextBox>控制对<xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="94e75-104">The example sets the value of a <xref:System.Windows.Forms.Panel> control’s <xref:System.Windows.Forms.Padding> property to 5 and sets the <xref:System.Windows.Forms.Control.Dock%2A> property of a child <xref:System.Windows.Forms.RichTextBox> control to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="94e75-105"><xref:System.Windows.Forms.Control.BackColor%2A>的<xref:System.Windows.Forms.Panel>控件设置为<xref:System.Drawing.Color.Blue%2A>，这将创建周围的蓝色边框<xref:System.Windows.Forms.RichTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="94e75-105">The <xref:System.Windows.Forms.Control.BackColor%2A> of the <xref:System.Windows.Forms.Panel> control is set to <xref:System.Drawing.Color.Blue%2A>, which creates a blue border around the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94e75-106">示例</span><span class="sxs-lookup"><span data-stu-id="94e75-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="94e75-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="94e75-107">See also</span></span>

- <xref:System.Windows.Forms.Padding>
- [<span data-ttu-id="94e75-108">Windows 窗体控件中的边距和填充</span><span class="sxs-lookup"><span data-stu-id="94e75-108">Margin and Padding in Windows Forms Controls</span></span>](margin-and-padding-in-windows-forms-controls.md)
