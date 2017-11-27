---
title: "如何：创建用于绘制的 Graphics 对象"
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
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 72f1af49a5c64395e018707d1f71cc0feaa2d22c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>如何：创建用于绘制的 Graphics 对象
您可以绘制线条和形状之前，呈现文本，或显示和操作与图像[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，你需要创建<xref:System.Drawing.Graphics>对象。 <xref:System.Drawing.Graphics>对象所表示[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]绘图图面，并且是用于创建图形映像的对象。  
  
 在使用图形中有两个步骤：  
  
1.  创建<xref:System.Drawing.Graphics>对象。  
  
2.  使用<xref:System.Drawing.Graphics>要绘制线条和形状、 呈现文本，或显示和操作图像对象。  
  
## <a name="creating-a-graphics-object"></a>创建图形对象  
 图形对象可以创建各种不同的方式。  
  
#### <a name="to-create-a-graphics-object"></a>若要创建的图形对象  
  
-   作为的一部分接收到的图形对象的引用<xref:System.Windows.Forms.PaintEventArgs>中<xref:System.Windows.Forms.Control.Paint>的窗体或控件的事件。 这通常是如何获取对图形对象的引用，创建控件的绘制代码时。 同样，你还可以作为的属性获取的图形对象<xref:System.Drawing.Printing.PrintPageEventArgs>时处理<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件<xref:System.Drawing.Printing.PrintDocument>。  
  
     - 或 -  
  
-   调用<xref:System.Windows.Forms.Control.CreateGraphics%2A>控件或窗体，以获得对引用方法<xref:System.Drawing.Graphics>对象，表示该控件或窗体的绘图图面。 如果你想要在窗体或已存在的控件上绘制，请使用此方法。  
  
     - 或 -  
  
-   创建<xref:System.Drawing.Graphics>从继承自任何对象的对象<xref:System.Drawing.Image>。 当你想要更改现有的映像时，此方法非常有用。  
  
     以下部分提供有关每个这些进程的详细信息。  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>在绘制事件处理程序的 PaintEventArgs  
 编程时<xref:System.Windows.Forms.PaintEventHandler>控件或<xref:System.Drawing.Printing.PrintDocument.PrintPage>为<xref:System.Drawing.Printing.PrintDocument>，作为属性之一提供的图形对象<xref:System.Windows.Forms.PaintEventArgs>或<xref:System.Drawing.Printing.PrintPageEventArgs>。  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>若要获取在绘制事件 Paint 中的图形对象的引用  
  
1.  声明<xref:System.Drawing.Graphics>对象。  
  
2.  分配变量来引用<xref:System.Drawing.Graphics>对象作为的一部分传递<xref:System.Windows.Forms.PaintEventArgs>。  
  
3.  插入代码以绘制窗体或控件。  
  
     下面的示例演示如何引用<xref:System.Drawing.Graphics>对象<xref:System.Windows.Forms.PaintEventArgs>中<xref:System.Windows.Forms.Control.Paint>事件：  
  
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
  
## <a name="creategraphics-method"></a>CreateGraphics 方法  
 你还可以使用<xref:System.Windows.Forms.Control.CreateGraphics%2A>控件或窗体，以获得对引用方法<xref:System.Drawing.Graphics>对象，表示该控件或窗体的绘图图面。  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>若要创建具有 CreateGraphics 方法的图形对象  
  
-   调用<xref:System.Windows.Forms.Control.CreateGraphics%2A>的要在其呈现图形的窗体或控件的方法。  
  
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
  
## <a name="create-from-an-image-object"></a>从映像对象创建  
 此外，你可以从任何派生自的对象创建图形对象<xref:System.Drawing.Image>类。  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>若要从映像创建的图形对象  
  
-   调用<xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType>方法，并提供你想要创建的映像变量名称<xref:System.Drawing.Graphics>对象。  
  
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
>  你只能创建<xref:System.Drawing.Graphics>非索引.bmp 文件，如 16 位、 24 位和 32 位.bmp 文件中的对象。 每个像素的非索引.bmp 文件包含一种颜色，与的索引的.bmp 文件保存到颜色表的索引的像素为单位。  
  
-  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>绘制和操作形状和图像  
 它创建后，<xref:System.Drawing.Graphics>对象可能用于绘制线条和形状、 呈现文本，或显示和操作图像。 与使用的主体对象<xref:System.Drawing.Graphics>对象：  
  
-   <xref:System.Drawing.Pen>类-用于绘制线条、 大纲显示形状，还是呈现其他几何表示形式之间。  
  
-   <xref:System.Drawing.Brush>类-用于填充图形，例如已填充的形状、 图像或文本区域。  
  
-   <xref:System.Drawing.Font>类-提供用于呈现文本时可用的形状的说明。  
  
-   <xref:System.Drawing.Color>结构-表示不同的颜色显示。  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>若要使用你创建的图形对象  
  
-   使用上面列出的、 要绘制所需的相应对象。  
  
     有关详细信息，请参阅下列主题：  
  
    |呈现|请参阅|  
    |---------------|---------|  
    |直线|[如何：在 Windows 窗体上绘制直线](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |形状|[如何：绘制显示边框的形状](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |Text|[如何：在 Windows 窗体上绘制文本](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |图像|[如何：使用 GDI+ 呈现图像](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>另请参阅  
 [图形编程入门](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [如何：使用 GDI+ 呈现图像](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
