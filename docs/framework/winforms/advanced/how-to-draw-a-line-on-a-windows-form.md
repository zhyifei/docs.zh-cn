---
title: 如何：在 Windows 窗体上绘制直线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: aab04b9236175cedd154b817db5a6f6450503105
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074440"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="4e2ac-102">如何：在 Windows 窗体上绘制直线</span><span class="sxs-lookup"><span data-stu-id="4e2ac-102">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="4e2ac-103">此示例窗体上绘制直线。</span><span class="sxs-lookup"><span data-stu-id="4e2ac-103">This example draws a line on a form.</span></span> <span data-ttu-id="4e2ac-104">通常情况下，在窗体上绘制，当您处理该窗体<xref:System.Windows.Forms.Control.Paint>事件并执行绘制使用<xref:System.Windows.Forms.PaintEventArgs.Graphics%2A>属性的<xref:System.Windows.Forms.PaintEventArgs>，在此示例中所示</span><span class="sxs-lookup"><span data-stu-id="4e2ac-104">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e2ac-105">示例</span><span class="sxs-lookup"><span data-stu-id="4e2ac-105">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4e2ac-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="4e2ac-106">Compiling the Code</span></span>  
 <span data-ttu-id="4e2ac-107">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="4e2ac-107">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4e2ac-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="4e2ac-108">Robust Programming</span></span>  
 <span data-ttu-id="4e2ac-109">应始终调用<xref:System.IDisposable.Dispose%2A>占用系统资源，如任何对象<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="4e2ac-109">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2ac-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e2ac-110">See also</span></span>

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="4e2ac-111">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="4e2ac-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="4e2ac-112">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="4e2ac-112">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="4e2ac-113">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="4e2ac-113">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
