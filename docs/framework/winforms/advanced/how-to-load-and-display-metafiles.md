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
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424824"
---
# <a name="how-to-load-and-display-metafiles"></a>如何：加载和显示图元文件
<xref:System.Drawing.Imaging.Metafile> 类，该类继承自 <xref:System.Drawing.Image> 类，提供用于记录、显示和检查矢量图像的方法。  
  
## <a name="example"></a>示例  
 若要在屏幕上显示矢量图像（图元文件），需要 <xref:System.Drawing.Imaging.Metafile> 对象和 <xref:System.Drawing.Graphics> 对象。 将文件的名称（或流）传递到 <xref:System.Drawing.Imaging.Metafile> 构造函数。 创建 <xref:System.Drawing.Imaging.Metafile> 对象后，将该 <xref:System.Drawing.Imaging.Metafile> 对象传递到 <xref:System.Drawing.Graphics> 对象的 <xref:System.Drawing.Graphics.DrawImage%2A> 方法。  
  
 该示例从 EMF （增强型图元文件）文件创建一个 <xref:System.Drawing.Imaging.Metafile> 对象，然后将该图像的左上角绘制（60，10）。  
  
 下图显示了在指定位置绘制的图元文件。  
  
 ![显示图像位置的屏幕截图。](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，它是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>请参阅

- [使用图像、位图、图标和图元文件](working-with-images-bitmaps-icons-and-metafiles.md)
