---
title: 如何：绘制不透明和半透明的线条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
ms.openlocfilehash: 7408722dc13e83828cfca3f0615a2730e3c53461
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004024"
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a><span data-ttu-id="26ead-102">如何：绘制不透明和半透明的线条</span><span class="sxs-lookup"><span data-stu-id="26ead-102">How to: Draw Opaque and Semitransparent Lines</span></span>
<span data-ttu-id="26ead-103">绘制线条时，必须将 <xref:System.Drawing.Pen> 对象传递给 <xref:System.Drawing.Graphics> 类的 <xref:System.Drawing.Graphics.DrawLine%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="26ead-103">When you draw a line, you must pass a <xref:System.Drawing.Pen> object to the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="26ead-104"><xref:System.Drawing.Pen.%23ctor%2A> 构造函数的参数之一是 <xref:System.Drawing.Color> 对象。</span><span class="sxs-lookup"><span data-stu-id="26ead-104">One of the parameters of the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="26ead-105">若要绘制不透明的线条，请将颜色的 alpha 分量设置为 255。</span><span class="sxs-lookup"><span data-stu-id="26ead-105">To draw an opaque line, set the alpha component of the color to 255.</span></span> <span data-ttu-id="26ead-106">若要绘制半透明的线条，请将 alpha 分量设置为从 1 到 254 的任何值。</span><span class="sxs-lookup"><span data-stu-id="26ead-106">To draw a semitransparent line, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="26ead-107">在背景上绘制半透明的线条时，线条的颜色与背景的颜色混合。</span><span class="sxs-lookup"><span data-stu-id="26ead-107">When you draw a semitransparent line over a background, the color of the line is blended with the colors of the background.</span></span> <span data-ttu-id="26ead-108">alpha 分量指定线条和背景色混合的方式；alpha 值越接近 0，背景颜色的权重越大，alpha 值越接近 255，线条颜色的权重越大。</span><span class="sxs-lookup"><span data-stu-id="26ead-108">The alpha component specifies how the line and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the line color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26ead-109">示例</span><span class="sxs-lookup"><span data-stu-id="26ead-109">Example</span></span>  
 <span data-ttu-id="26ead-110">下面的示例绘制一个位图，然后制使用该位图作为背景绘三条线。</span><span class="sxs-lookup"><span data-stu-id="26ead-110">The following example draws a bitmap and then draws three lines that use the bitmap as a background.</span></span> <span data-ttu-id="26ead-111">第一条线使用值为 255 的 alpha 分量，因此它是不透明的。</span><span class="sxs-lookup"><span data-stu-id="26ead-111">The first line uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="26ead-112">第二条和第三条线使用值为 128 的 alpha 分量，因此它们是半透明的；你可透过线条看到背景图像。</span><span class="sxs-lookup"><span data-stu-id="26ead-112">The second and third lines use an alpha component of 128, so they are semitransparent; you can see the background image through the lines.</span></span> <span data-ttu-id="26ead-113">设置 <xref:System.Drawing.Graphics.CompositingQuality%2A> 属性的语句会导致第三条线的混合与 gamma 矫正一起完成。</span><span class="sxs-lookup"><span data-stu-id="26ead-113">The statement that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third line to be done in conjunction with gamma correction.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
 <span data-ttu-id="26ead-114">下图显示了以下代码的输出：</span><span class="sxs-lookup"><span data-stu-id="26ead-114">The following illustration shows the output of the following code:</span></span>  
  
 ![图显示了不透明和半透明的输出](./media/how-to-draw-opaque-and-semitransparent-lines/opaque-semitransparent-lines.png)  

## <a name="compiling-the-code"></a><span data-ttu-id="26ead-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="26ead-116">Compiling the Code</span></span>  
 <span data-ttu-id="26ead-117">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="26ead-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ead-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="26ead-118">See also</span></span>

- [<span data-ttu-id="26ead-119">alpha 值混合处理直线和填充</span><span class="sxs-lookup"><span data-stu-id="26ead-119">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="26ead-120">如何：使控件拥有透明背景</span><span class="sxs-lookup"><span data-stu-id="26ead-120">How to: Give Your Control a Transparent Background</span></span>](../controls/how-to-give-your-control-a-transparent-background.md)
- [<span data-ttu-id="26ead-121">如何：用不透明和半透明的画笔绘制</span><span class="sxs-lookup"><span data-stu-id="26ead-121">How to: Draw with Opaque and Semitransparent Brushes</span></span>](how-to-draw-with-opaque-and-semitransparent-brushes.md)
