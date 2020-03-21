---
title: 如何：使用 GDI+ 呈现图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: fffe1f1052d7323d234985b7e752866f2e89657d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182504"
---
# <a name="how-to-render-images-with-gdi"></a>如何：使用 GDI+ 呈现图像
您可以使用 GDI+ 来渲染应用程序中作为文件存在的图像。 为此，<xref:System.Drawing.Image>方法是创建类的新对象（如<xref:System.Drawing.Bitmap>），创建引用要使用的绘图表面<xref:System.Drawing.Graphics>的对象，并调用<xref:System.Drawing.Graphics.DrawImage%2A><xref:System.Drawing.Graphics>对象的方法。 将在图形类所表示的绘图表面上绘制图像。 您可以使用图像编辑器在设计时创建和编辑图像文件，并在运行时使用 GDI+ 呈现它们。 有关详细信息，请参阅[图标的图像编辑器](/cpp/windows/image-editor-for-icons)。  
  
### <a name="to-render-an-image-with-gdi"></a>使用 GDI+ 呈现图像  
  
1. 创建一个对象，该对象表示要显示的图像。 此对象必须是从 继承的<xref:System.Drawing.Image>类的成员，<xref:System.Drawing.Bitmap>如 。 <xref:System.Drawing.Imaging.Metafile> 下面显示了一个示例：  
  
    ```vb  
    ' Uses the System.Environment.GetFolderPath to get the path to the
    ' current user's MyPictures folder.  
    Dim myBitmap as New Bitmap _  
       (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.MyPictures))  
    ```  
  
    ```csharp  
    // Uses the System.Environment.GetFolderPath to get the path to the
    // current user's MyPictures folder.  
    Bitmap myBitmap = new Bitmap  
       (System.Environment.GetFolderPath  
          (System.Environment.SpecialFolder.MyPictures));  
    ```  
  
    ```cpp  
    // Uses the System.Environment.GetFolderPath to get the path to the
    // current user's MyPictures folder.  
    Bitmap^ myBitmap = gcnew Bitmap  
       (System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::MyPictures));  
    ```  
  
2. 创建<xref:System.Drawing.Graphics>表示要使用的绘图曲面的对象。 有关详细信息，请参阅[如何：创建用于绘制的 Graphics 对象](how-to-create-graphics-objects-for-drawing.md)。  
  
    ```vb  
    ' Creates a Graphics object that represents the drawing surface of
    ' Button1.  
    Dim g as Graphics = Button1.CreateGraphics  
    ```  
  
    ```csharp  
    // Creates a Graphics object that represents the drawing surface of
    // Button1.  
    Graphics g = Button1.CreateGraphics();  
    ```  
  
    ```cpp  
    // Creates a Graphics object that represents the drawing surface of
    // Button1.  
    Graphics^ g = button1->CreateGraphics();  
    ```  
  
3. <xref:System.Drawing.Graphics.DrawImage%2A>调用图形对象以渲染图像。 必须同时指定要绘制的图像以及将绘制它的位置坐标。  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a>另请参阅

- [图形编程入门](getting-started-with-graphics-programming.md)
- [如何：创建用于绘制的 Graphics 对象](how-to-create-graphics-objects-for-drawing.md)
- [GDI+ 中的笔、直线和矩形](pens-lines-and-rectangles-in-gdi.md)
- [如何：在 Windows 窗体上绘制文本](how-to-draw-text-on-a-windows-form.md)
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [绘制线条或闭合图形](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [图标的图像编辑器](/cpp/windows/image-editor-for-icons)
