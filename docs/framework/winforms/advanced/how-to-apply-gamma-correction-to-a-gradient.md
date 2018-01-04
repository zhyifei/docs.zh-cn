---
title: "如何：对渐变应用灰度校正"
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
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6321894c86f340154bd37f50e81ea8a58a2e0896
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="2b111-102">如何：对渐变应用灰度校正</span><span class="sxs-lookup"><span data-stu-id="2b111-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="2b111-103">你可以通过设置画笔的启用线性渐变画笔的灰度校正<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="2b111-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="2b111-104">你可以通过设置禁用灰度校正<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>属性`false`。</span><span class="sxs-lookup"><span data-stu-id="2b111-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="2b111-105">默认情况下，禁用灰度校正。</span><span class="sxs-lookup"><span data-stu-id="2b111-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b111-106">示例</span><span class="sxs-lookup"><span data-stu-id="2b111-106">Example</span></span>  
 <span data-ttu-id="2b111-107">该示例创建线性渐变画笔，并使用该画笔填充两个矩形。</span><span class="sxs-lookup"><span data-stu-id="2b111-107">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="2b111-108">第一个矩形在填充时未灰度校正和第二个矩形填入灰度校正。</span><span class="sxs-lookup"><span data-stu-id="2b111-108">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="2b111-109">下图显示两个填充的矩形。</span><span class="sxs-lookup"><span data-stu-id="2b111-109">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="2b111-110">顶部矩形，没有灰度校正，显示深色在中部。</span><span class="sxs-lookup"><span data-stu-id="2b111-110">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="2b111-111">底部矩形，具有灰度校正，显示为具有多个统一的强度。</span><span class="sxs-lookup"><span data-stu-id="2b111-111">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="2b111-112">![渐变](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="2b111-112">![Gradient](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2b111-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="2b111-113">Compiling the Code</span></span>  
 <span data-ttu-id="2b111-114">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="2b111-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b111-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b111-115">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>  
 [<span data-ttu-id="2b111-116">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="2b111-116">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
