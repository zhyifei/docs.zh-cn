---
title: 如何：对文本使用抗锯齿效果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182475"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="f4390-102">如何：对文本使用抗锯齿效果</span><span class="sxs-lookup"><span data-stu-id="f4390-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="f4390-103">*抗锯齿*是指平滑绘制图形和文本的锯齿边缘，以提高其外观或可读性。</span><span class="sxs-lookup"><span data-stu-id="f4390-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="f4390-104">使用托管 GDI+ 类，您可以呈现高质量的反锯齿文本以及较低质量的文本。</span><span class="sxs-lookup"><span data-stu-id="f4390-104">With the managed GDI+ classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="f4390-105">通常，与较低质量的渲染相比，更高质量的渲染需要更多的处理时间。</span><span class="sxs-lookup"><span data-stu-id="f4390-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="f4390-106">要设置文本质量级别，将<xref:System.Drawing.Graphics.TextRenderingHint%2A>属性<xref:System.Drawing.Graphics>设置为<xref:System.Drawing.Text.TextRenderingHint>枚举的元素之一</span><span class="sxs-lookup"><span data-stu-id="f4390-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4390-107">示例</span><span class="sxs-lookup"><span data-stu-id="f4390-107">Example</span></span>  
 <span data-ttu-id="f4390-108">以下代码示例绘制具有两种不同质量设置的文本。</span><span class="sxs-lookup"><span data-stu-id="f4390-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 <span data-ttu-id="f4390-109">下图显示了示例代码的输出：</span><span class="sxs-lookup"><span data-stu-id="f4390-109">The following illustration shows the output of the example code:</span></span>  
  
 ![显示具有两种不同质量设置的文本的屏幕截图。](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f4390-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="f4390-111">Compiling the Code</span></span>  
 <span data-ttu-id="f4390-112">前面的代码示例设计用于 Windows 窗体，它要求<xref:System.Windows.Forms.PaintEventArgs>`e`. <xref:System.Windows.Forms.PaintEventHandler></span><span class="sxs-lookup"><span data-stu-id="f4390-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4390-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4390-113">See also</span></span>

- [<span data-ttu-id="f4390-114">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="f4390-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
