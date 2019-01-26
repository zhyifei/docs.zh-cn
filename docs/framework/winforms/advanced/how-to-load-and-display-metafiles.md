---
title: 如何：加载和显示图元文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: d0835d7f2c5ffea44f22661a765ab16b1d0130c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619553"
---
# <a name="how-to-load-and-display-metafiles"></a>如何：加载和显示图元文件
<xref:System.Drawing.Imaging.Metafile>类，该类继承自<xref:System.Drawing.Image>类中，提供用于记录、 显示和检查矢量图像的方法。  
  
## <a name="example"></a>示例  
 若要在屏幕上显示矢量图像 （图元文件），你需要<xref:System.Drawing.Imaging.Metafile>对象和一个<xref:System.Drawing.Graphics>对象。 将文件 （或流） 的名称传递给<xref:System.Drawing.Imaging.Metafile>构造函数。 创建后<xref:System.Drawing.Imaging.Metafile>对象，将其传递<xref:System.Drawing.Imaging.Metafile>对象传递给<xref:System.Drawing.Graphics.DrawImage%2A>方法的<xref:System.Drawing.Graphics>对象。  
  
 此示例将创建<xref:System.Drawing.Imaging.Metafile>EMF （增强型图元文件） 文件中的对象，然后绘制的图像，其左上角位于 （60，10）。  
  
 下图显示了在指定位置绘制图元文件。  
  
 ![图像位置](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>请参阅
- [使用图像、位图、图标和图元文件](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
