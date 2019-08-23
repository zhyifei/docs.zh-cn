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
ms.openlocfilehash: 3d3ab62896f6b799cd38a8180b90f33125a9929b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964345"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="f0a85-102">如何：创建用于绘制的 Graphics 对象</span><span class="sxs-lookup"><span data-stu-id="f0a85-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="f0a85-103">你需要创建一个<xref:System.Drawing.Graphics>对象, 然后才能使用 gdi + 绘制线条和形状、呈现文本或显示和操作图像。</span><span class="sxs-lookup"><span data-stu-id="f0a85-103">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="f0a85-104"><xref:System.Drawing.Graphics>对象表示 gdi + 绘图图面, 是用于创建图形图像的对象。</span><span class="sxs-lookup"><span data-stu-id="f0a85-104">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="f0a85-105">使用图形需要执行两个步骤:</span><span class="sxs-lookup"><span data-stu-id="f0a85-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="f0a85-106"><xref:System.Drawing.Graphics>创建对象。</span><span class="sxs-lookup"><span data-stu-id="f0a85-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="f0a85-107"><xref:System.Drawing.Graphics>使用对象绘制线条和形状、呈现文本或显示和操作图像。</span><span class="sxs-lookup"><span data-stu-id="f0a85-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="f0a85-108">创建图形对象</span><span class="sxs-lookup"><span data-stu-id="f0a85-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="f0a85-109">可以通过多种方式创建图形对象。</span><span class="sxs-lookup"><span data-stu-id="f0a85-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="f0a85-110">创建图形对象</span><span class="sxs-lookup"><span data-stu-id="f0a85-110">To create a graphics object</span></span>  
  
- <span data-ttu-id="f0a85-111">在窗体或控件的事件中,接收对图形对象的引用作为的一部分。<xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.PaintEventArgs></span><span class="sxs-lookup"><span data-stu-id="f0a85-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="f0a85-112">这通常是在创建控件的绘制代码时获取对图形对象的引用的方式。</span><span class="sxs-lookup"><span data-stu-id="f0a85-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="f0a85-113">同样, 在为<xref:System.Drawing.Printing.PrintPageEventArgs> <xref:System.Drawing.Printing.PrintDocument.PrintPage>处理事件<xref:System.Drawing.Printing.PrintDocument>时, 还可以获取图形对象作为的属性。</span><span class="sxs-lookup"><span data-stu-id="f0a85-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="f0a85-114">或</span><span class="sxs-lookup"><span data-stu-id="f0a85-114">-or-</span></span>  
  
- <span data-ttu-id="f0a85-115">调用控件<xref:System.Windows.Forms.Control.CreateGraphics%2A>或窗体的方法来获取<xref:System.Drawing.Graphics>对对象的引用, 该对象表示该控件或窗体的绘图图面。</span><span class="sxs-lookup"><span data-stu-id="f0a85-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="f0a85-116">如果要在已存在的窗体或控件上进行绘制, 请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="f0a85-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="f0a85-117">或</span><span class="sxs-lookup"><span data-stu-id="f0a85-117">-or-</span></span>  
  
- <span data-ttu-id="f0a85-118">从继承自<xref:System.Drawing.Image>的任何对象创建对象。<xref:System.Drawing.Graphics></span><span class="sxs-lookup"><span data-stu-id="f0a85-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="f0a85-119">当您想要更改现有的映像时, 此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="f0a85-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="f0a85-120">以下各节将详细介绍其中每个过程。</span><span class="sxs-lookup"><span data-stu-id="f0a85-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="f0a85-121">Paint 事件处理程序中的 PaintEventArgs</span><span class="sxs-lookup"><span data-stu-id="f0a85-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="f0a85-122">在<xref:System.Windows.Forms.PaintEventHandler>对控件<xref:System.Drawing.Printing.PrintDocument.PrintPage>或的进行<xref:System.Drawing.Printing.PrintDocument>编程时, 图形对象作为<xref:System.Windows.Forms.PaintEventArgs>或<xref:System.Drawing.Printing.PrintPageEventArgs>的属性之一提供。</span><span class="sxs-lookup"><span data-stu-id="f0a85-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="f0a85-123">从画图事件的 PaintEventArgs 中获取对图形对象的引用</span><span class="sxs-lookup"><span data-stu-id="f0a85-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="f0a85-124"><xref:System.Drawing.Graphics>声明对象。</span><span class="sxs-lookup"><span data-stu-id="f0a85-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="f0a85-125">分配变量以引用<xref:System.Drawing.Graphics>作为的<xref:System.Windows.Forms.PaintEventArgs>一部分传递的对象。</span><span class="sxs-lookup"><span data-stu-id="f0a85-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="f0a85-126">插入用于绘制窗体或控件的代码。</span><span class="sxs-lookup"><span data-stu-id="f0a85-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="f0a85-127">下面的示例演示如何<xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs>在<xref:System.Windows.Forms.Control.Paint>事件中引用对象:</span><span class="sxs-lookup"><span data-stu-id="f0a85-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="f0a85-128">CreateGraphics 方法</span><span class="sxs-lookup"><span data-stu-id="f0a85-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="f0a85-129">你还可以使用控件<xref:System.Windows.Forms.Control.CreateGraphics%2A>或窗体的方法来获取<xref:System.Drawing.Graphics>对对象的引用, 该对象表示该控件或窗体的绘图图面。</span><span class="sxs-lookup"><span data-stu-id="f0a85-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="f0a85-130">使用 CreateGraphics 方法创建图形对象</span><span class="sxs-lookup"><span data-stu-id="f0a85-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="f0a85-131">调用要在其上呈现图形的窗体或控件的方法。<xref:System.Windows.Forms.Control.CreateGraphics%2A></span><span class="sxs-lookup"><span data-stu-id="f0a85-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="f0a85-132">从 Image 对象创建</span><span class="sxs-lookup"><span data-stu-id="f0a85-132">Create from an Image Object</span></span>  
 <span data-ttu-id="f0a85-133">此外, 还可以从派生自<xref:System.Drawing.Image>类的任何对象创建图形对象。</span><span class="sxs-lookup"><span data-stu-id="f0a85-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="f0a85-134">从图像创建图形对象</span><span class="sxs-lookup"><span data-stu-id="f0a85-134">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="f0a85-135">调用方法, 并提供要从中<xref:System.Drawing.Graphics>创建对象的图像变量的名称。 <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f0a85-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="f0a85-136">下面的示例演示如何使用<xref:System.Drawing.Bitmap>对象:</span><span class="sxs-lookup"><span data-stu-id="f0a85-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
> <span data-ttu-id="f0a85-137">只能从非索引<xref:System.Drawing.Graphics>的 .bmp 文件创建对象, 例如16位、24位和32位 .bmp 文件。</span><span class="sxs-lookup"><span data-stu-id="f0a85-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="f0a85-138">非索引 .bmp 文件的每个像素都包含一种颜色, 这与用于保存颜色表的索引的索引 .bmp 文件的像素不同。</span><span class="sxs-lookup"><span data-stu-id="f0a85-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="f0a85-139">绘制和操作形状和图像</span><span class="sxs-lookup"><span data-stu-id="f0a85-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="f0a85-140">创建<xref:System.Drawing.Graphics>对象后, 可以使用对象来绘制线条和形状、呈现文本或显示和操作图像。</span><span class="sxs-lookup"><span data-stu-id="f0a85-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="f0a85-141">与<xref:System.Drawing.Graphics>对象一起使用的主体对象包括:</span><span class="sxs-lookup"><span data-stu-id="f0a85-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="f0a85-142"><xref:System.Drawing.Pen>类-用于绘制线条、显示形状或呈现其他几何表示形式。</span><span class="sxs-lookup"><span data-stu-id="f0a85-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="f0a85-143"><xref:System.Drawing.Brush>类-用于填充图形区域, 如填充的形状、图像或文本。</span><span class="sxs-lookup"><span data-stu-id="f0a85-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="f0a85-144"><xref:System.Drawing.Font>类-提供要在呈现文本时使用的形状的说明。</span><span class="sxs-lookup"><span data-stu-id="f0a85-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="f0a85-145"><xref:System.Drawing.Color>结构-表示要显示的不同颜色。</span><span class="sxs-lookup"><span data-stu-id="f0a85-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="f0a85-146">使用已创建的图形对象</span><span class="sxs-lookup"><span data-stu-id="f0a85-146">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="f0a85-147">使用上面列出的相应对象来绘制您需要的内容。</span><span class="sxs-lookup"><span data-stu-id="f0a85-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="f0a85-148">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="f0a85-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="f0a85-149">呈现</span><span class="sxs-lookup"><span data-stu-id="f0a85-149">To render</span></span>|<span data-ttu-id="f0a85-150">查看</span><span class="sxs-lookup"><span data-stu-id="f0a85-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="f0a85-151">直线</span><span class="sxs-lookup"><span data-stu-id="f0a85-151">Lines</span></span>|[<span data-ttu-id="f0a85-152">如何：在 Windows 窗体上绘制线条</span><span class="sxs-lookup"><span data-stu-id="f0a85-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="f0a85-153">形状</span><span class="sxs-lookup"><span data-stu-id="f0a85-153">Shapes</span></span>|[<span data-ttu-id="f0a85-154">如何：绘制空心形状</span><span class="sxs-lookup"><span data-stu-id="f0a85-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="f0a85-155">文本</span><span class="sxs-lookup"><span data-stu-id="f0a85-155">Text</span></span>|[<span data-ttu-id="f0a85-156">如何：在 Windows 窗体上绘制文本</span><span class="sxs-lookup"><span data-stu-id="f0a85-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="f0a85-157">映像</span><span class="sxs-lookup"><span data-stu-id="f0a85-157">Images</span></span>|[<span data-ttu-id="f0a85-158">如何：用 GDI + 呈现图像</span><span class="sxs-lookup"><span data-stu-id="f0a85-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="f0a85-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0a85-159">See also</span></span>

- [<span data-ttu-id="f0a85-160">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="f0a85-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="f0a85-161">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="f0a85-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f0a85-162">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="f0a85-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="f0a85-163">如何：用 GDI + 呈现图像</span><span class="sxs-lookup"><span data-stu-id="f0a85-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
