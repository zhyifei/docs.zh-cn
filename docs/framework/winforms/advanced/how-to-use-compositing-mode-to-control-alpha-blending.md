---
title: 如何：使用复合模式控制 alpha 值混合处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 6863e59efa25323f80933bf8ab595316b430ef53
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590140"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="19858-102">如何：使用复合模式控制 alpha 值混合处理</span><span class="sxs-lookup"><span data-stu-id="19858-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="19858-103">可能您想要创建屏幕外位图，具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="19858-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
- <span data-ttu-id="19858-104">颜色的 alpha 值都小于 255 个。</span><span class="sxs-lookup"><span data-stu-id="19858-104">Colors have alpha values that are less than 255.</span></span>  
  
- <span data-ttu-id="19858-105">颜色不是 alpha 混合与每个其他的创建位图。</span><span class="sxs-lookup"><span data-stu-id="19858-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
- <span data-ttu-id="19858-106">显示完成的位图，位图中的颜色时，alpha 值混合处理与背景色显示设备上。</span><span class="sxs-lookup"><span data-stu-id="19858-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="19858-107">若要创建这种位图，请构造一个空白<xref:System.Drawing.Bitmap>对象，然后再构造<xref:System.Drawing.Graphics>对象基于该位图。</span><span class="sxs-lookup"><span data-stu-id="19858-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="19858-108">设置的复合模式<xref:System.Drawing.Graphics>对象传递给<xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="19858-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19858-109">示例</span><span class="sxs-lookup"><span data-stu-id="19858-109">Example</span></span>  
 <span data-ttu-id="19858-110">下面的示例创建<xref:System.Drawing.Graphics>对象，基于<xref:System.Drawing.Bitmap>对象。</span><span class="sxs-lookup"><span data-stu-id="19858-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="19858-111">该代码使用<xref:System.Drawing.Graphics>对象以及两个半透明的画笔 (alpha = 160) 绘制位图上。</span><span class="sxs-lookup"><span data-stu-id="19858-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="19858-112">该代码填充红色椭圆和绿色椭圆使用半透明的画笔。</span><span class="sxs-lookup"><span data-stu-id="19858-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="19858-113">绿色椭圆重叠红色椭圆，但由于未与红色混合绿色的复合模式<xref:System.Drawing.Graphics>对象设置为<xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>。</span><span class="sxs-lookup"><span data-stu-id="19858-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="19858-114">该代码在屏幕上绘制位图两次： 一次在白色背景上，一次在彩色背景上。</span><span class="sxs-lookup"><span data-stu-id="19858-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="19858-115">属于两个椭圆组成的位图中像素有 160 的 alpha 分量，因此与屏幕的背景颜色混合的省略号。</span><span class="sxs-lookup"><span data-stu-id="19858-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="19858-116">下图显示的代码示例的输出。</span><span class="sxs-lookup"><span data-stu-id="19858-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="19858-117">请注意，省略号混合和背景，但它们之间不相互进行混合。</span><span class="sxs-lookup"><span data-stu-id="19858-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 ![与在后台，不相互混合的关系图显示省略号。](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 <span data-ttu-id="19858-119">此代码示例包含此语句：</span><span class="sxs-lookup"><span data-stu-id="19858-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="19858-120">如果你希望省略号以以及在后台使用混合，更改该语句所示：</span><span class="sxs-lookup"><span data-stu-id="19858-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="19858-121">下图显示修改后的代码的输出。</span><span class="sxs-lookup"><span data-stu-id="19858-121">The following illustration shows the output of the revised code.</span></span>  
  
 ![图示显示省略号混合在一起并具有背景。](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="19858-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="19858-123">Compiling the Code</span></span>  
 <span data-ttu-id="19858-124">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="19858-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19858-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="19858-125">See also</span></span>

- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="19858-126">alpha 值混合处理直线和填充</span><span class="sxs-lookup"><span data-stu-id="19858-126">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
