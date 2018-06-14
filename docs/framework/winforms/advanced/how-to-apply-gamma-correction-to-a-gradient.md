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
ms.openlocfilehash: 9c3c9c5c63194b1dee8314a1ef96497a8b78b5ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520729"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>如何：对渐变应用灰度校正
你可以通过设置画笔的启用线性渐变画笔的灰度校正<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>属性`true`。 你可以通过设置禁用灰度校正<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>属性`false`。 默认情况下，禁用灰度校正。  
  
## <a name="example"></a>示例  
 该示例创建线性渐变画笔，并使用该画笔填充两个矩形。 第一个矩形在填充时未灰度校正和第二个矩形填入灰度校正。  
  
 下图显示两个填充的矩形。 顶部矩形，没有灰度校正，显示深色在中部。 底部矩形，具有灰度校正，显示为具有多个统一的强度。  
  
 ![渐变](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>  
 [使用渐变画笔填充形状](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
