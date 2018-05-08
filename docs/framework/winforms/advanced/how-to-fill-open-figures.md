---
title: 如何：填充开放图形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: b7422ae2a4dc4d59fd337ab2294caa0d65057bae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-fill-open-figures"></a>如何：填充开放图形
你可以通过传递填写路径<xref:System.Drawing.Drawing2D.GraphicsPath>对象传递给<xref:System.Drawing.Graphics.FillPath%2A>方法。 <xref:System.Drawing.Graphics.FillPath%2A>方法填充的填充模式 （备用或绕） 根据当前设置的路径的路径。 如果路径具有任何开放图形，路径已填充，就像这些图形闭合。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 通过从其结束的点到起始点绘制一条直线闭合图形。  
  
## <a name="example"></a>示例  
 下面的示例创建具有一个开放图形 （一段弧线） 和一个闭合的图形 （椭圆） 的路径。 <xref:System.Drawing.Graphics.FillPath%2A>方法填充根据默认的填充模式，即路径<xref:System.Drawing.Drawing2D.FillMode.Alternate>。  
  
 下图显示示例代码的输出。 请注意路径已填充 (根据<xref:System.Drawing.Drawing2D.FillMode.Alternate>) 就像打开图关闭的一条直线从其结束的点到起始点。  
  
 ![填充开放路径](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [GDI+ 中的图形路径](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
