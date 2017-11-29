---
title: "如何：用纯色填充形状"
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
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eb3e160392a903083386d9942f8e2cfe31ee89a4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a><span data-ttu-id="a6c2b-102">如何：用纯色填充形状</span><span class="sxs-lookup"><span data-stu-id="a6c2b-102">How to: Fill a Shape with a Solid Color</span></span>
<span data-ttu-id="a6c2b-103">若要使用纯色填充形状，创建<xref:System.Drawing.SolidBrush>对象，以及然后将其传递<xref:System.Drawing.SolidBrush>对象的填充方法之一的自变量作为<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="a6c2b-103">To fill a shape with a solid color, create a <xref:System.Drawing.SolidBrush> object, and then pass that <xref:System.Drawing.SolidBrush> object as an argument to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="a6c2b-104">下面的示例演示如何用红色的颜色填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="a6c2b-104">The following example shows how to fill an ellipse with the color red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6c2b-105">示例</span><span class="sxs-lookup"><span data-stu-id="a6c2b-105">Example</span></span>  
 <span data-ttu-id="a6c2b-106">在下面的代码中，<xref:System.Drawing.SolidBrush.%23ctor%2A>构造函数采用<xref:System.Drawing.Color>对象作为其唯一的参数。</span><span class="sxs-lookup"><span data-stu-id="a6c2b-106">In the following code, the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor takes a <xref:System.Drawing.Color> object as its only argument.</span></span> <span data-ttu-id="a6c2b-107">使用的值<xref:System.Drawing.Color.FromArgb%2A>方法表示颜色的 alpha、 红色、 绿色和蓝色组件。</span><span class="sxs-lookup"><span data-stu-id="a6c2b-107">The values used by the <xref:System.Drawing.Color.FromArgb%2A> method represent the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="a6c2b-108">其中每个值必须在范围 0 到 255 之间。</span><span class="sxs-lookup"><span data-stu-id="a6c2b-108">Each of these values must be in the range 0 through 255.</span></span> <span data-ttu-id="a6c2b-109">第一个 255 指示的颜色是完全不透明，而第二个 255 指示达到最大亮度是红色的组件。</span><span class="sxs-lookup"><span data-stu-id="a6c2b-109">The first 255 indicates that the color is fully opaque, and the second 255 indicates that the red component is at full intensity.</span></span> <span data-ttu-id="a6c2b-110">将两个 0 指示绿色和蓝色分量这两个具有强度为 0。</span><span class="sxs-lookup"><span data-stu-id="a6c2b-110">The two zeros indicate that the green and blue components both have an intensity of 0.</span></span>  
  
 <span data-ttu-id="a6c2b-111">四个数字 （0，0，100，60） 传递给<xref:System.Drawing.Graphics.FillEllipse%2A>方法指定的位置和大小的椭圆的边框。</span><span class="sxs-lookup"><span data-stu-id="a6c2b-111">The four numbers (0, 0, 100, 60) passed to the <xref:System.Drawing.Graphics.FillEllipse%2A> method specify the location and size of the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="a6c2b-112">矩形具有的左上角 （0，0），为 100，宽度和高度为 60。</span><span class="sxs-lookup"><span data-stu-id="a6c2b-112">The rectangle has an upper-left corner of (0, 0), a width of 100, and a height of 60.</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a6c2b-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="a6c2b-113">Compiling the Code</span></span>  
 <span data-ttu-id="a6c2b-114">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="a6c2b-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c2b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6c2b-115">See Also</span></span>  
 [<span data-ttu-id="a6c2b-116">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="a6c2b-116">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
