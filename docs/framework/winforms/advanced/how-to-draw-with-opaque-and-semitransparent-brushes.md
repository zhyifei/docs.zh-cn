---
title: "如何：用不透明和半透明的画笔绘制"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- semi-transparent shapes [Windows Forms], drawing
- transparency [Windows Forms], semi-transparent shapes
- alpha blending [Windows Forms], brush
- brushes [Windows Forms], using semi-transparent
ms.assetid: a4f6f6b8-3bc8-440a-84af-d62ef0f8ff40
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4af2664851ed0903a362a4b88edf1db9bb042dfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-with-opaque-and-semitransparent-brushes"></a><span data-ttu-id="c5528-102">如何：用不透明和半透明的画笔绘制</span><span class="sxs-lookup"><span data-stu-id="c5528-102">How to: Draw with Opaque and Semitransparent Brushes</span></span>
<span data-ttu-id="c5528-103">当填充形状时，必须将 <xref:System.Drawing.Brush> 对象传递到 <xref:System.Drawing.Graphics> 类的填充方法之一。</span><span class="sxs-lookup"><span data-stu-id="c5528-103">When you fill a shape, you must pass a <xref:System.Drawing.Brush> object to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="c5528-104"><xref:System.Drawing.SolidBrush.%23ctor%2A> 构造函数的参数是 <xref:System.Drawing.Color> 对象。</span><span class="sxs-lookup"><span data-stu-id="c5528-104">The one parameter of the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="c5528-105">若要填充不透明的形状，将颜色的 alpha 分量设置为 255。</span><span class="sxs-lookup"><span data-stu-id="c5528-105">To fill an opaque shape, set the alpha component of the color to 255.</span></span> <span data-ttu-id="c5528-106">若要填充半透明的形状，将 alpha 分量设置为从 1 到 254 之间的任何值。</span><span class="sxs-lookup"><span data-stu-id="c5528-106">To fill a semitransparent shape, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="c5528-107">当填充半透明形状时，形状的颜色与背景的颜色混合。</span><span class="sxs-lookup"><span data-stu-id="c5528-107">When you fill a semitransparent shape, the color of the shape is blended with the colors of the background.</span></span> <span data-ttu-id="c5528-108">alpha 分量指定形状颜色和背景色混合的方式；alpha 值越接近 0，背景颜色的比重越大，alpha 值越接近 255，形状颜色的比重越大。</span><span class="sxs-lookup"><span data-stu-id="c5528-108">The alpha component specifies how the shape and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the shape color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5528-109">示例</span><span class="sxs-lookup"><span data-stu-id="c5528-109">Example</span></span>  
 <span data-ttu-id="c5528-110">以下示例绘制位图，然后填充重叠位图的三个椭圆。</span><span class="sxs-lookup"><span data-stu-id="c5528-110">The following example draws a bitmap and then fills three ellipses that overlap the bitmap.</span></span> <span data-ttu-id="c5528-111">第一个椭圆使用值为 255 的 alpha 分量，因此它是不透明的。</span><span class="sxs-lookup"><span data-stu-id="c5528-111">The first ellipse uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="c5528-112">第二个和第三个椭圆使用值为 128 的 alpha 分量，因此它们是半透明的；还可透过椭圆看到背景图像。</span><span class="sxs-lookup"><span data-stu-id="c5528-112">The second and third ellipses use an alpha component of 128, so they are semitransparent; you can see the background image through the ellipses.</span></span> <span data-ttu-id="c5528-113">设置 <xref:System.Drawing.Graphics.CompositingQuality%2A> 属性的调用会导致第三个椭圆的混合与灰度校正联合完成。</span><span class="sxs-lookup"><span data-stu-id="c5528-113">The call that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third ellipse to be done in conjunction with gamma correction.</span></span>  
  
 <span data-ttu-id="c5528-114">下图显示以下代码的输出。</span><span class="sxs-lookup"><span data-stu-id="c5528-114">The following illustration shows the output of the following code.</span></span>  
  
 <span data-ttu-id="c5528-115">![不透明和半透明](../../../../docs/framework/winforms/advanced/media/compqualellipse.png "compqualellipse")</span><span class="sxs-lookup"><span data-stu-id="c5528-115">![Opaque and Semitransparent](../../../../docs/framework/winforms/advanced/media/compqualellipse.png "compqualellipse")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.AlphaBlending#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c5528-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="c5528-116">Compiling the Code</span></span>  
 <span data-ttu-id="c5528-117">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。</span><span class="sxs-lookup"><span data-stu-id="c5528-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5528-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5528-118">See Also</span></span>  
 [<span data-ttu-id="c5528-119">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="c5528-119">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="c5528-120">alpha 值混合处理直线和填充</span><span class="sxs-lookup"><span data-stu-id="c5528-120">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [<span data-ttu-id="c5528-121">如何：为控件设置透明背景</span><span class="sxs-lookup"><span data-stu-id="c5528-121">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 [<span data-ttu-id="c5528-122">如何：绘制不透明和半透明的直线</span><span class="sxs-lookup"><span data-stu-id="c5528-122">How to: Draw Opaque and Semitransparent Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)
