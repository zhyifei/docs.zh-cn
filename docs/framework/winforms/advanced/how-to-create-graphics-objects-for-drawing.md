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
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="9ef69-102">如何：创建用于绘制的 Graphics 对象</span><span class="sxs-lookup"><span data-stu-id="9ef69-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="9ef69-103">在使用 GDI+ 绘制线条和形状、渲染文本或显示和操作图像之前，需要创建一个<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="9ef69-103">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9ef69-104">该<xref:System.Drawing.Graphics>对象表示 GDI+ 绘图表面，是用于创建图形图像的对象。</span><span class="sxs-lookup"><span data-stu-id="9ef69-104">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="9ef69-105">使用图形有两个步骤：</span><span class="sxs-lookup"><span data-stu-id="9ef69-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="9ef69-106">创建<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="9ef69-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="9ef69-107">使用<xref:System.Drawing.Graphics>对象绘制线条和形状、渲染文本或显示和操作图像。</span><span class="sxs-lookup"><span data-stu-id="9ef69-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="9ef69-108">创建图形对象</span><span class="sxs-lookup"><span data-stu-id="9ef69-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="9ef69-109">图形对象可以通过多种方式创建。</span><span class="sxs-lookup"><span data-stu-id="9ef69-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="9ef69-110">创建图形对象</span><span class="sxs-lookup"><span data-stu-id="9ef69-110">To create a graphics object</span></span>  
  
- <span data-ttu-id="9ef69-111">在窗体或控件<xref:System.Windows.Forms.PaintEventArgs><xref:System.Windows.Forms.Control.Paint>的情况下，接收对图形对象的引用，作为 的一部分。</span><span class="sxs-lookup"><span data-stu-id="9ef69-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="9ef69-112">这通常是在为控件创建绘制代码时获取图形对象的引用的方式。</span><span class="sxs-lookup"><span data-stu-id="9ef69-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="9ef69-113">同样，在处理 的事件<xref:System.Drawing.Printing.PrintPageEventArgs>时<xref:System.Drawing.Printing.PrintDocument.PrintPage>，还可以获取图形对象作为<xref:System.Drawing.Printing.PrintDocument>属性。</span><span class="sxs-lookup"><span data-stu-id="9ef69-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="9ef69-114">-或-</span><span class="sxs-lookup"><span data-stu-id="9ef69-114">-or-</span></span>  
  
- <span data-ttu-id="9ef69-115">调用控件<xref:System.Windows.Forms.Control.CreateGraphics%2A>或窗体的方法以获取对表示该控件或窗体的绘图<xref:System.Drawing.Graphics>表面的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="9ef69-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="9ef69-116">如果要在已存在的窗体或控件上绘制，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="9ef69-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="9ef69-117">-或-</span><span class="sxs-lookup"><span data-stu-id="9ef69-117">-or-</span></span>  
  
- <span data-ttu-id="9ef69-118">从<xref:System.Drawing.Graphics>继承的任何<xref:System.Drawing.Image>对象创建对象。</span><span class="sxs-lookup"><span data-stu-id="9ef69-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="9ef69-119">当您要更改已有的映像时，此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="9ef69-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="9ef69-120">以下各节详细介绍了每个过程。</span><span class="sxs-lookup"><span data-stu-id="9ef69-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="9ef69-121">绘制事件处理程序中的绘制事件</span><span class="sxs-lookup"><span data-stu-id="9ef69-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="9ef69-122">在编程<xref:System.Windows.Forms.PaintEventHandler>控件 或<xref:System.Drawing.Printing.PrintDocument.PrintPage>的 时<xref:System.Drawing.Printing.PrintDocument>，图形对象作为 或<xref:System.Windows.Forms.PaintEventArgs><xref:System.Drawing.Printing.PrintPageEventArgs>的属性之一提供。</span><span class="sxs-lookup"><span data-stu-id="9ef69-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="9ef69-123">从"绘制"事件中的"绘制事件"中获取对图形对象的引用</span><span class="sxs-lookup"><span data-stu-id="9ef69-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="9ef69-124">声明对象<xref:System.Drawing.Graphics>。</span><span class="sxs-lookup"><span data-stu-id="9ef69-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="9ef69-125">分配变量以引用作为 的<xref:System.Drawing.Graphics><xref:System.Windows.Forms.PaintEventArgs>一部分传递的对象。</span><span class="sxs-lookup"><span data-stu-id="9ef69-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="9ef69-126">插入代码以绘制窗体或控件。</span><span class="sxs-lookup"><span data-stu-id="9ef69-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="9ef69-127">下面的示例演示如何引用<xref:System.Drawing.Graphics><xref:System.Windows.Forms.PaintEventArgs>事件中<xref:System.Windows.Forms.Control.Paint>的对象：</span><span class="sxs-lookup"><span data-stu-id="9ef69-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="9ef69-128">创建图形方法</span><span class="sxs-lookup"><span data-stu-id="9ef69-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="9ef69-129">您还可以使用控件或窗体<xref:System.Windows.Forms.Control.CreateGraphics%2A>的方法来获取对表示该控件或窗体的绘图表面<xref:System.Drawing.Graphics>的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="9ef69-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="9ef69-130">使用"创建图形"方法创建图形对象</span><span class="sxs-lookup"><span data-stu-id="9ef69-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="9ef69-131">调用要<xref:System.Windows.Forms.Control.CreateGraphics%2A>呈现图形的窗体或控件的方法。</span><span class="sxs-lookup"><span data-stu-id="9ef69-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="9ef69-132">从图像对象创建</span><span class="sxs-lookup"><span data-stu-id="9ef69-132">Create from an Image Object</span></span>  
 <span data-ttu-id="9ef69-133">此外，还可以从从<xref:System.Drawing.Image>类派生的任何对象创建图形对象。</span><span class="sxs-lookup"><span data-stu-id="9ef69-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="9ef69-134">从图像创建图形对象</span><span class="sxs-lookup"><span data-stu-id="9ef69-134">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="9ef69-135">调用<xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType>方法，提供要从中创建<xref:System.Drawing.Graphics>对象的 Image 变量的名称。</span><span class="sxs-lookup"><span data-stu-id="9ef69-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="9ef69-136">下面的示例演示如何使用<xref:System.Drawing.Bitmap>对象：</span><span class="sxs-lookup"><span data-stu-id="9ef69-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
> <span data-ttu-id="9ef69-137">只能从非索引<xref:System.Drawing.Graphics>的 .bmp 文件创建对象，例如 16 位、24 位和 32 位 .bmp 文件。</span><span class="sxs-lookup"><span data-stu-id="9ef69-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="9ef69-138">非索引 .bmp 文件的每个像素都包含一种颜色，而索引 .bmp 文件的像素将索引保留到颜色表。</span><span class="sxs-lookup"><span data-stu-id="9ef69-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="9ef69-139">绘制和操作形状和图像</span><span class="sxs-lookup"><span data-stu-id="9ef69-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="9ef69-140">创建对象后，可以使用对象<xref:System.Drawing.Graphics>绘制线条和形状、渲染文本或显示和操作图像。</span><span class="sxs-lookup"><span data-stu-id="9ef69-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="9ef69-141">与<xref:System.Drawing.Graphics>对象一起使用的主体对象是：</span><span class="sxs-lookup"><span data-stu-id="9ef69-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="9ef69-142">类<xref:System.Drawing.Pen>— 用于绘制线条、勾画形状或渲染其他几何表示。</span><span class="sxs-lookup"><span data-stu-id="9ef69-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="9ef69-143">类<xref:System.Drawing.Brush>— 用于填充图形区域，如填充形状、图像或文本。</span><span class="sxs-lookup"><span data-stu-id="9ef69-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="9ef69-144">类<xref:System.Drawing.Font>— 提供渲染文本时要使用的形状的说明。</span><span class="sxs-lookup"><span data-stu-id="9ef69-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="9ef69-145">结构<xref:System.Drawing.Color>— 表示要显示的不同颜色。</span><span class="sxs-lookup"><span data-stu-id="9ef69-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="9ef69-146">使用已创建的图形对象</span><span class="sxs-lookup"><span data-stu-id="9ef69-146">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="9ef69-147">使用上面列出的相应对象绘制所需的内容。</span><span class="sxs-lookup"><span data-stu-id="9ef69-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="9ef69-148">有关详情，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="9ef69-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="9ef69-149">渲染</span><span class="sxs-lookup"><span data-stu-id="9ef69-149">To render</span></span>|<span data-ttu-id="9ef69-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ef69-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="9ef69-151">线条</span><span class="sxs-lookup"><span data-stu-id="9ef69-151">Lines</span></span>|[<span data-ttu-id="9ef69-152">如何：在 Windows 窗体上绘制线条</span><span class="sxs-lookup"><span data-stu-id="9ef69-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="9ef69-153">形状</span><span class="sxs-lookup"><span data-stu-id="9ef69-153">Shapes</span></span>|[<span data-ttu-id="9ef69-154">如何：绘制空心形状</span><span class="sxs-lookup"><span data-stu-id="9ef69-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="9ef69-155">文本</span><span class="sxs-lookup"><span data-stu-id="9ef69-155">Text</span></span>|[<span data-ttu-id="9ef69-156">如何：在 Windows 窗体上绘制文本</span><span class="sxs-lookup"><span data-stu-id="9ef69-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="9ef69-157">映像</span><span class="sxs-lookup"><span data-stu-id="9ef69-157">Images</span></span>|[<span data-ttu-id="9ef69-158">如何：使用 GDI+ 呈现图像</span><span class="sxs-lookup"><span data-stu-id="9ef69-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="9ef69-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ef69-159">See also</span></span>

- [<span data-ttu-id="9ef69-160">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="9ef69-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="9ef69-161">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="9ef69-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="9ef69-162">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="9ef69-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="9ef69-163">如何：使用 GDI+ 呈现图像</span><span class="sxs-lookup"><span data-stu-id="9ef69-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
