---
title: 如何：对渐变应用 gamma 矫正
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e812e441233c1d29a67dac639048e20a659549f0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753566"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="58213-102">如何：对渐变应用 gamma 矫正</span><span class="sxs-lookup"><span data-stu-id="58213-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="58213-103">可以通过设置画笔的启用线性渐变画笔的灰度校正<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="58213-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="58213-104">可以通过设置禁用灰度校正<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="58213-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="58213-105">默认情况下禁用灰度校正。</span><span class="sxs-lookup"><span data-stu-id="58213-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58213-106">示例</span><span class="sxs-lookup"><span data-stu-id="58213-106">Example</span></span>  

<span data-ttu-id="58213-107">下面的示例是从控件的调用的方法<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="58213-107">The following example is a method that is called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="58213-108">该示例创建线性渐变画笔，并使用该画笔来填充两个矩形。</span><span class="sxs-lookup"><span data-stu-id="58213-108">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="58213-109">第一个矩形填充而无需灰度校正和第二个矩形填充与灰度校正。</span><span class="sxs-lookup"><span data-stu-id="58213-109">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="58213-110">下图显示了两个实心的矩形。</span><span class="sxs-lookup"><span data-stu-id="58213-110">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="58213-111">不具有灰度校正的顶部矩形显示为灰色中间。</span><span class="sxs-lookup"><span data-stu-id="58213-111">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="58213-112">下面的矩形采用具有灰度校正，似乎亮度更均匀。</span><span class="sxs-lookup"><span data-stu-id="58213-112">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 ![两个渐变填充矩形，使用和不使用灰度校正。](./media/how-to-apply-gamma-correction-to-a-gradient/two-rectangles-gamma-gradient.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="58213-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="58213-114">Compiling the Code</span></span>  
 <span data-ttu-id="58213-115">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="58213-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58213-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="58213-116">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="58213-117">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="58213-117">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
