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
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="893f1-102">如何：使用 GDI+ 呈现图像</span><span class="sxs-lookup"><span data-stu-id="893f1-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="893f1-103">您可以使用 GDI+ 来渲染应用程序中作为文件存在的图像。</span><span class="sxs-lookup"><span data-stu-id="893f1-103">You can use GDI+ to render images that exist as files in your applications.</span></span> <span data-ttu-id="893f1-104">为此，<xref:System.Drawing.Image>方法是创建类的新对象（如<xref:System.Drawing.Bitmap>），创建引用要使用的绘图表面<xref:System.Drawing.Graphics>的对象，并调用<xref:System.Drawing.Graphics.DrawImage%2A><xref:System.Drawing.Graphics>对象的方法。</span><span class="sxs-lookup"><span data-stu-id="893f1-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="893f1-105">将在图形类所表示的绘图表面上绘制图像。</span><span class="sxs-lookup"><span data-stu-id="893f1-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="893f1-106">您可以使用图像编辑器在设计时创建和编辑图像文件，并在运行时使用 GDI+ 呈现它们。</span><span class="sxs-lookup"><span data-stu-id="893f1-106">You can use the Image Editor to create and edit image files at design time, and render them with GDI+ at run time.</span></span> <span data-ttu-id="893f1-107">有关详细信息，请参阅[图标的图像编辑器](/cpp/windows/image-editor-for-icons)。</span><span class="sxs-lookup"><span data-stu-id="893f1-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="893f1-108">使用 GDI+ 呈现图像</span><span class="sxs-lookup"><span data-stu-id="893f1-108">To render an image with GDI+</span></span>  
  
1. <span data-ttu-id="893f1-109">创建一个对象，该对象表示要显示的图像。</span><span class="sxs-lookup"><span data-stu-id="893f1-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="893f1-110">此对象必须是从 继承的<xref:System.Drawing.Image>类的成员，<xref:System.Drawing.Bitmap>如 。 <xref:System.Drawing.Imaging.Metafile></span><span class="sxs-lookup"><span data-stu-id="893f1-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="893f1-111">下面显示了一个示例：</span><span class="sxs-lookup"><span data-stu-id="893f1-111">An example is shown:</span></span>  
  
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
  
2. <span data-ttu-id="893f1-112">创建<xref:System.Drawing.Graphics>表示要使用的绘图曲面的对象。</span><span class="sxs-lookup"><span data-stu-id="893f1-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="893f1-113">有关详细信息，请参阅[如何：创建用于绘制的 Graphics 对象](how-to-create-graphics-objects-for-drawing.md)。</span><span class="sxs-lookup"><span data-stu-id="893f1-113">For more information, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
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
  
3. <span data-ttu-id="893f1-114"><xref:System.Drawing.Graphics.DrawImage%2A>调用图形对象以渲染图像。</span><span class="sxs-lookup"><span data-stu-id="893f1-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="893f1-115">必须同时指定要绘制的图像以及将绘制它的位置坐标。</span><span class="sxs-lookup"><span data-stu-id="893f1-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="893f1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="893f1-116">See also</span></span>

- [<span data-ttu-id="893f1-117">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="893f1-117">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="893f1-118">如何：创建用于绘制的 Graphics 对象</span><span class="sxs-lookup"><span data-stu-id="893f1-118">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="893f1-119">GDI+ 中的笔、直线和矩形</span><span class="sxs-lookup"><span data-stu-id="893f1-119">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
- [<span data-ttu-id="893f1-120">如何：在 Windows 窗体上绘制文本</span><span class="sxs-lookup"><span data-stu-id="893f1-120">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)
- [<span data-ttu-id="893f1-121">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="893f1-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="893f1-122">绘制线条或闭合图形</span><span class="sxs-lookup"><span data-stu-id="893f1-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [<span data-ttu-id="893f1-123">图标的图像编辑器</span><span class="sxs-lookup"><span data-stu-id="893f1-123">Image Editor for Icons</span></span>](/cpp/windows/image-editor-for-icons)
