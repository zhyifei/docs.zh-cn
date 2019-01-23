---
title: 如何：对渐变应用灰度校正
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: b3b45c312542a3f8410bd93fcbe4e4cb70aa8516
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527154"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="64d65-102">如何：对渐变应用灰度校正</span><span class="sxs-lookup"><span data-stu-id="64d65-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="64d65-103">可以通过设置画笔的启用线性渐变画笔的灰度校正<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="64d65-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="64d65-104">可以通过设置禁用灰度校正<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="64d65-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="64d65-105">默认情况下禁用灰度校正。</span><span class="sxs-lookup"><span data-stu-id="64d65-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64d65-106">示例</span><span class="sxs-lookup"><span data-stu-id="64d65-106">Example</span></span>  
 <span data-ttu-id="64d65-107">该示例创建线性渐变画笔，并使用该画笔来填充两个矩形。</span><span class="sxs-lookup"><span data-stu-id="64d65-107">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="64d65-108">第一个矩形填充而无需灰度校正和第二个矩形填充与灰度校正。</span><span class="sxs-lookup"><span data-stu-id="64d65-108">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="64d65-109">下图显示了两个实心的矩形。</span><span class="sxs-lookup"><span data-stu-id="64d65-109">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="64d65-110">不具有灰度校正的顶部矩形显示为灰色中间。</span><span class="sxs-lookup"><span data-stu-id="64d65-110">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="64d65-111">下面的矩形采用具有灰度校正，似乎亮度更均匀。</span><span class="sxs-lookup"><span data-stu-id="64d65-111">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="64d65-112">![渐变](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="64d65-112">![Gradient](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="64d65-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="64d65-113">Compiling the Code</span></span>  
 <span data-ttu-id="64d65-114">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="64d65-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d65-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="64d65-115">See also</span></span>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush>
- [<span data-ttu-id="64d65-116">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="64d65-116">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
