---
title: 如何：创建用于绘制的 Graphics 对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
ms.openlocfilehash: d591d65904484e33285e5db7aa99760f3e1909d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142428"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>如何：创建用于绘制的 Graphics 对象
在使用 GDI+ 绘制线条和形状、渲染文本或显示和操作图像之前，需要创建一个<xref:System.Drawing.Graphics>对象。 该<xref:System.Drawing.Graphics>对象表示 GDI+ 绘图表面，是用于创建图形图像的对象。  
  
 使用图形有两个步骤：  
  
1. 创建<xref:System.Drawing.Graphics>对象。  
  
2. 使用<xref:System.Drawing.Graphics>对象绘制线条和形状、渲染文本或显示和操作图像。  
  
## <a name="creating-a-graphics-object"></a>创建图形对象  
 图形对象可以通过多种方式创建。  
  
#### <a name="to-create-a-graphics-object"></a>创建图形对象  
  
- 在窗体或控件<xref:System.Windows.Forms.PaintEventArgs><xref:System.Windows.Forms.Control.Paint>的情况下，接收对图形对象的引用，作为 的一部分。 这通常是在为控件创建绘制代码时获取图形对象的引用的方式。 同样，在处理 的事件<xref:System.Drawing.Printing.PrintPageEventArgs>时<xref:System.Drawing.Printing.PrintDocument.PrintPage>，还可以获取图形对象作为<xref:System.Drawing.Printing.PrintDocument>属性。  
  
     -或-  
  
- 调用控件<xref:System.Windows.Forms.Control.CreateGraphics%2A>或窗体的方法以获取对表示该控件或窗体的绘图<xref:System.Drawing.Graphics>表面的对象的引用。 如果要在已存在的窗体或控件上绘制，请使用此方法。  
  
     -或-  
  
- 从<xref:System.Drawing.Graphics>继承的任何<xref:System.Drawing.Image>对象创建对象。 当您要更改已有的映像时，此方法非常有用。  
  
     以下各节详细介绍了每个过程。  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>绘制事件处理程序中的绘制事件  
 在编程<xref:System.Windows.Forms.PaintEventHandler>控件 或<xref:System.Drawing.Printing.PrintDocument.PrintPage>的 时<xref:System.Drawing.Printing.PrintDocument>，图形对象作为 或<xref:System.Windows.Forms.PaintEventArgs><xref:System.Drawing.Printing.PrintPageEventArgs>的属性之一提供。  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>从"绘制"事件中的"绘制事件"中获取对图形对象的引用  
  
1. 声明对象<xref:System.Drawing.Graphics>。  
  
2. 分配变量以引用作为 的<xref:System.Drawing.Graphics><xref:System.Windows.Forms.PaintEventArgs>一部分传递的对象。  
  
3. 插入代码以绘制窗体或控件。  
  
     下面的示例演示如何引用<xref:System.Drawing.Graphics><xref:System.Windows.Forms.PaintEventArgs>事件中<xref:System.Windows.Forms.Control.Paint>的对象：  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,
       System.Windows.Forms.PaintEventArgs pe)
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## <a name="creategraphics-method"></a>创建图形方法  
 您还可以使用控件或窗体<xref:System.Windows.Forms.Control.CreateGraphics%2A>的方法来获取对表示该控件或窗体的绘图表面<xref:System.Drawing.Graphics>的对象的引用。  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>使用"创建图形"方法创建图形对象  
  
- 调用要<xref:System.Windows.Forms.Control.CreateGraphics%2A>呈现图形的窗体或控件的方法。  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## <a name="create-from-an-image-object"></a>从图像对象创建  
 此外，还可以从从<xref:System.Drawing.Image>类派生的任何对象创建图形对象。  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>从图像创建图形对象  
  
- 调用<xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType>方法，提供要从中创建<xref:System.Drawing.Graphics>对象的 Image 变量的名称。  
  
     下面的示例演示如何使用<xref:System.Drawing.Bitmap>对象：  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
> 只能从非索引<xref:System.Drawing.Graphics>的 .bmp 文件创建对象，例如 16 位、24 位和 32 位 .bmp 文件。 非索引 .bmp 文件的每个像素都包含一种颜色，而索引 .bmp 文件的像素将索引保留到颜色表。  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>绘制和操作形状和图像  
 创建对象后，可以使用对象<xref:System.Drawing.Graphics>绘制线条和形状、渲染文本或显示和操作图像。 与<xref:System.Drawing.Graphics>对象一起使用的主体对象是：  
  
- 类<xref:System.Drawing.Pen>— 用于绘制线条、勾画形状或渲染其他几何表示。  
  
- 类<xref:System.Drawing.Brush>— 用于填充图形区域，如填充形状、图像或文本。  
  
- 类<xref:System.Drawing.Font>— 提供渲染文本时要使用的形状的说明。  
  
- 结构<xref:System.Drawing.Color>— 表示要显示的不同颜色。  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>使用已创建的图形对象  
  
- 使用上面列出的相应对象绘制所需的内容。  
  
     有关详情，请参阅以下主题：  
  
    |渲染|请参阅|  
    |---------------|---------|  
    |线条|[如何：在 Windows 窗体上绘制线条](how-to-draw-a-line-on-a-windows-form.md)|  
    |形状|[如何：绘制空心形状](how-to-draw-an-outlined-shape.md)|  
    |文本|[如何：在 Windows 窗体上绘制文本](how-to-draw-text-on-a-windows-form.md)|  
    |映像|[如何：使用 GDI+ 呈现图像](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>另请参阅

- [图形编程入门](getting-started-with-graphics-programming.md)
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [直线、曲线和图形](lines-curves-and-shapes.md)
- [如何：使用 GDI+ 呈现图像](how-to-render-images-with-gdi.md)
