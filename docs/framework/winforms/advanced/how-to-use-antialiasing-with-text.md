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
ms.openlocfilehash: 24d1b1dfbe955bcfa98a16c3be592ab837ec0182
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227608"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="73126-102">如何：对文本使用抗锯齿效果</span><span class="sxs-lookup"><span data-stu-id="73126-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="73126-103">*抗锯齿*指进行绘制的图形和文本，以提高它们的外观或可读性的锯齿状边缘平滑处理。</span><span class="sxs-lookup"><span data-stu-id="73126-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="73126-104">与托管[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]类，您可以呈现高质量消除锯齿的文本，以及较低质量的文本。</span><span class="sxs-lookup"><span data-stu-id="73126-104">With the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="73126-105">通常情况下，更高质量呈现花费的处理时间超过较低质量呈现。</span><span class="sxs-lookup"><span data-stu-id="73126-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="73126-106">若要设置的文本质量级别，设置<xref:System.Drawing.Graphics.TextRenderingHint%2A>的属性<xref:System.Drawing.Graphics>的元素之一<xref:System.Drawing.Text.TextRenderingHint>枚举</span><span class="sxs-lookup"><span data-stu-id="73126-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="73126-107">示例</span><span class="sxs-lookup"><span data-stu-id="73126-107">Example</span></span>  
 <span data-ttu-id="73126-108">下面的代码示例绘制了两种不同的质量设置的文本。</span><span class="sxs-lookup"><span data-stu-id="73126-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 <span data-ttu-id="73126-109">下图显示了示例代码的输出：</span><span class="sxs-lookup"><span data-stu-id="73126-109">The following illustration shows the output of the example code:</span></span>  
  
 ![显示具有两个不同的质量设置文本的屏幕截图。](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73126-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="73126-111">Compiling the Code</span></span>  
 <span data-ttu-id="73126-112">前面的代码示例设计为使用 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="73126-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73126-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="73126-113">See also</span></span>

- [<span data-ttu-id="73126-114">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="73126-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
