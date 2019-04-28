---
title: 如何：在 Windows 窗体上绘制垂直文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- StringFormat.FormatFlags
- Graphics.DrawString
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- strings [Windows Forms], drawing vertical
- text [Windows Forms], drawing
- text [Windows Forms], vertical text
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
ms.openlocfilehash: eb00928205a318b068d49ea3f6f71c398f77bbcd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61722908"
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a><span data-ttu-id="3724c-102">如何：在 Windows 窗体上绘制垂直文本</span><span class="sxs-lookup"><span data-stu-id="3724c-102">How to: Draw Vertical Text on a Windows Form</span></span>
<span data-ttu-id="3724c-103">下面的代码示例演示如何使用窗体上绘制垂直文本<xref:System.Drawing.Graphics.DrawString%2A>方法的<xref:System.Drawing.Graphics>。</span><span class="sxs-lookup"><span data-stu-id="3724c-103">The following code example shows how to draw vertical text on a form by using the <xref:System.Drawing.Graphics.DrawString%2A> method of <xref:System.Drawing.Graphics>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3724c-104">示例</span><span class="sxs-lookup"><span data-stu-id="3724c-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3724c-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="3724c-105">Compiling the Code</span></span>  
 <span data-ttu-id="3724c-106">不能在调用此方法<xref:System.Windows.Forms.Form.Load>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="3724c-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="3724c-107">不会重新绘制的内容的绘制，如果窗体进行大小调整或另一个窗体被遮盖。</span><span class="sxs-lookup"><span data-stu-id="3724c-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="3724c-108">若要使你自动重绘的内容，应重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="3724c-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3724c-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="3724c-109">Robust Programming</span></span>  
 <span data-ttu-id="3724c-110">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="3724c-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="3724c-111">未安装 Arial 字体。</span><span class="sxs-lookup"><span data-stu-id="3724c-111">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3724c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3724c-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="3724c-113">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="3724c-113">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="3724c-114">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="3724c-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
