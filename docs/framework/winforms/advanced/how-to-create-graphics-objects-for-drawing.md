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
ms.openlocfilehash: 79eae4d37c056fc95ac73c78e00dd1a2b68bcd24
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324196"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="c1c63-102">如何：创建用于绘制的 Graphics 对象</span><span class="sxs-lookup"><span data-stu-id="c1c63-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="c1c63-103">您可以绘制线条和形状之前，呈现文本，或显示和操作图像[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，你需要创建<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="c1c63-103">Before you can draw lines and shapes, render text, or display and manipulate images with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="c1c63-104"><xref:System.Drawing.Graphics>对象表示[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]绘图图面，并且是用于创建图形的映像的对象。</span><span class="sxs-lookup"><span data-stu-id="c1c63-104">The <xref:System.Drawing.Graphics> object represents a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="c1c63-105">使用图形中有两个步骤：</span><span class="sxs-lookup"><span data-stu-id="c1c63-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="c1c63-106">创建<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="c1c63-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="c1c63-107">使用<xref:System.Drawing.Graphics>对象来绘制线条和形状、 呈现文本，或显示和操作图像。</span><span class="sxs-lookup"><span data-stu-id="c1c63-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="c1c63-108">创建图形对象</span><span class="sxs-lookup"><span data-stu-id="c1c63-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="c1c63-109">可以在不同的方式创建图形对象。</span><span class="sxs-lookup"><span data-stu-id="c1c63-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="c1c63-110">若要创建图形对象</span><span class="sxs-lookup"><span data-stu-id="c1c63-110">To create a graphics object</span></span>  
  
-   <span data-ttu-id="c1c63-111">接收对图形对象的引用作为的一部分<xref:System.Windows.Forms.PaintEventArgs>在<xref:System.Windows.Forms.Control.Paint>的窗体或控件的事件。</span><span class="sxs-lookup"><span data-stu-id="c1c63-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="c1c63-112">这通常是如何获取对图形对象的引用，创建控件的绘制代码时。</span><span class="sxs-lookup"><span data-stu-id="c1c63-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="c1c63-113">同样，还可以获取图形对象的属性作为<xref:System.Drawing.Printing.PrintPageEventArgs>处理时<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件<xref:System.Drawing.Printing.PrintDocument>。</span><span class="sxs-lookup"><span data-stu-id="c1c63-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="c1c63-114">或</span><span class="sxs-lookup"><span data-stu-id="c1c63-114">-or-</span></span>  
  
-   <span data-ttu-id="c1c63-115">调用<xref:System.Windows.Forms.Control.CreateGraphics%2A>方法的控件或窗体以获取对引用<xref:System.Drawing.Graphics>对象，表示该控件或窗体的绘图图面。</span><span class="sxs-lookup"><span data-stu-id="c1c63-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="c1c63-116">如果你想要在窗体或已存在的控件上绘制，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="c1c63-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="c1c63-117">或</span><span class="sxs-lookup"><span data-stu-id="c1c63-117">-or-</span></span>  
  
-   <span data-ttu-id="c1c63-118">创建<xref:System.Drawing.Graphics>来自任何继承的对象的对象<xref:System.Drawing.Image>。</span><span class="sxs-lookup"><span data-stu-id="c1c63-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="c1c63-119">当你想要更改已存在的图像时，此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="c1c63-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="c1c63-120">以下部分提供有关每个进程的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1c63-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="c1c63-121">Paint 事件处理程序中的 PaintEventArgs</span><span class="sxs-lookup"><span data-stu-id="c1c63-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="c1c63-122">编程时<xref:System.Windows.Forms.PaintEventHandler>控件或<xref:System.Drawing.Printing.PrintDocument.PrintPage>有关<xref:System.Drawing.Printing.PrintDocument>，作为属性之一提供的图形对象<xref:System.Windows.Forms.PaintEventArgs>或<xref:System.Drawing.Printing.PrintPageEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="c1c63-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="c1c63-123">若要获取从中绘制事件 PaintEventArgs 图形对象的引用</span><span class="sxs-lookup"><span data-stu-id="c1c63-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="c1c63-124">声明<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="c1c63-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="c1c63-125">分配变量来指代<xref:System.Drawing.Graphics>对象作为的一部分传递<xref:System.Windows.Forms.PaintEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="c1c63-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="c1c63-126">插入代码以绘制窗体或控件。</span><span class="sxs-lookup"><span data-stu-id="c1c63-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="c1c63-127">下面的示例演示如何引用<xref:System.Drawing.Graphics>对象从<xref:System.Windows.Forms.PaintEventArgs>中<xref:System.Windows.Forms.Control.Paint>事件：</span><span class="sxs-lookup"><span data-stu-id="c1c63-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="c1c63-128">CreateGraphics 方法</span><span class="sxs-lookup"><span data-stu-id="c1c63-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="c1c63-129">此外可以使用<xref:System.Windows.Forms.Control.CreateGraphics%2A>方法的控件或窗体以获取对引用<xref:System.Drawing.Graphics>对象，表示该控件或窗体的绘图图面。</span><span class="sxs-lookup"><span data-stu-id="c1c63-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="c1c63-130">若要创建具有 CreateGraphics 方法的图形对象</span><span class="sxs-lookup"><span data-stu-id="c1c63-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
-   <span data-ttu-id="c1c63-131">调用<xref:System.Windows.Forms.Control.CreateGraphics%2A>依据你想要呈现图形的窗体或控件的方法。</span><span class="sxs-lookup"><span data-stu-id="c1c63-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="c1c63-132">从图像对象创建</span><span class="sxs-lookup"><span data-stu-id="c1c63-132">Create from an Image Object</span></span>  
 <span data-ttu-id="c1c63-133">此外，可以从任何派生的对象创建图形对象<xref:System.Drawing.Image>类。</span><span class="sxs-lookup"><span data-stu-id="c1c63-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="c1c63-134">若要从映像创建图形对象</span><span class="sxs-lookup"><span data-stu-id="c1c63-134">To create a Graphics object from an Image</span></span>  
  
-   <span data-ttu-id="c1c63-135">调用<xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType>方法，并提供你想要创建的映像变量名称<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="c1c63-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="c1c63-136">下面的示例演示如何使用<xref:System.Drawing.Bitmap>对象：</span><span class="sxs-lookup"><span data-stu-id="c1c63-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
>  <span data-ttu-id="c1c63-137">你只能创建<xref:System.Drawing.Graphics>非索引.bmp 文件，如 16 位、 24 位和 32 位.bmp 文件中的对象。</span><span class="sxs-lookup"><span data-stu-id="c1c63-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="c1c63-138">每个像素的非索引.bmp 文件包含一种颜色，与保存到颜色表的索引的索引的.bmp 文件的像素为单位。</span><span class="sxs-lookup"><span data-stu-id="c1c63-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="c1c63-139">绘制和操作形状和图像</span><span class="sxs-lookup"><span data-stu-id="c1c63-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="c1c63-140">创建后，<xref:System.Drawing.Graphics>对象可能会用于绘制线条和形状、 呈现文本，或显示和操作图像。</span><span class="sxs-lookup"><span data-stu-id="c1c63-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="c1c63-141">与一起使用的主体对象<xref:System.Drawing.Graphics>对象：</span><span class="sxs-lookup"><span data-stu-id="c1c63-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
-   <span data-ttu-id="c1c63-142"><xref:System.Drawing.Pen>类，用于绘制线条、 大纲显示形状，或呈现其他几何表示形式。</span><span class="sxs-lookup"><span data-stu-id="c1c63-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
-   <span data-ttu-id="c1c63-143"><xref:System.Drawing.Brush>类，用于填充图形，例如实心的形状、 图像或文本区域。</span><span class="sxs-lookup"><span data-stu-id="c1c63-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
-   <span data-ttu-id="c1c63-144"><xref:System.Drawing.Font>类-提供用于呈现文本时所使用的形状的说明。</span><span class="sxs-lookup"><span data-stu-id="c1c63-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
-   <span data-ttu-id="c1c63-145"><xref:System.Drawing.Color>结构 — 表示不同的颜色显示。</span><span class="sxs-lookup"><span data-stu-id="c1c63-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="c1c63-146">若要使用已创建的图形对象</span><span class="sxs-lookup"><span data-stu-id="c1c63-146">To use the Graphics object you have created</span></span>  
  
-   <span data-ttu-id="c1c63-147">使用上面所列绘制所需的相应对象。</span><span class="sxs-lookup"><span data-stu-id="c1c63-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="c1c63-148">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="c1c63-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="c1c63-149">若要呈现</span><span class="sxs-lookup"><span data-stu-id="c1c63-149">To render</span></span>|<span data-ttu-id="c1c63-150">查看</span><span class="sxs-lookup"><span data-stu-id="c1c63-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="c1c63-151">直线</span><span class="sxs-lookup"><span data-stu-id="c1c63-151">Lines</span></span>|[<span data-ttu-id="c1c63-152">如何：在 Windows 窗体上绘制直线</span><span class="sxs-lookup"><span data-stu-id="c1c63-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="c1c63-153">形状</span><span class="sxs-lookup"><span data-stu-id="c1c63-153">Shapes</span></span>|[<span data-ttu-id="c1c63-154">如何：绘制轮廓形状</span><span class="sxs-lookup"><span data-stu-id="c1c63-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="c1c63-155">Text</span><span class="sxs-lookup"><span data-stu-id="c1c63-155">Text</span></span>|[<span data-ttu-id="c1c63-156">如何：在 Windows 窗体上绘制文本</span><span class="sxs-lookup"><span data-stu-id="c1c63-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="c1c63-157">图像</span><span class="sxs-lookup"><span data-stu-id="c1c63-157">Images</span></span>|[<span data-ttu-id="c1c63-158">如何：使用 GDI+ 呈现图像</span><span class="sxs-lookup"><span data-stu-id="c1c63-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="c1c63-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1c63-159">See also</span></span>

- [<span data-ttu-id="c1c63-160">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="c1c63-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="c1c63-161">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="c1c63-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="c1c63-162">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="c1c63-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="c1c63-163">如何：使用 GDI+ 呈现图像</span><span class="sxs-lookup"><span data-stu-id="c1c63-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
