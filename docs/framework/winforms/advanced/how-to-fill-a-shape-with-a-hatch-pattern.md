---
title: 如何：用阴影图案填充形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: 3fb5b443aac710a5490a238e2a571ed899dec463
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512383"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>如何：用阴影图案填充形状
从两种颜色进行阴影图案： 一个用于在后台，一个用于在后台上形成图案的行。 若要用阴影图案填充闭合的形状，请使用<xref:System.Drawing.Drawing2D.HatchBrush>对象。 下面的示例演示如何用阴影图案填充椭圆，使用：  
  
## <a name="example"></a>示例  
 <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A>构造函数采用三个参数： 的阴影样式、 阴影线条的颜色和背景颜色。 阴影样式参数可以为任何值<xref:System.Drawing.Drawing2D.HatchStyle>枚举。 有超过 50 个元素中的<xref:System.Drawing.Drawing2D.HatchStyle>枚举; 其中几个元素显示在下面的列表：  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 下图显示了实心的椭圆。  
  
 ![阴影图案](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。  
  
## <a name="see-also"></a>请参阅
- [使用画笔填充形状](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
