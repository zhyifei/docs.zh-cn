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
ms.openlocfilehash: da637152737510847830e885fdcd065ab92f16b3
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505756"
---
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="8a41d-102">如何：使用 GDI+ 呈现图像</span><span class="sxs-lookup"><span data-stu-id="8a41d-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="8a41d-103">您可以使用 GDI + 呈现图像作为您的应用程序中的文件存在。</span><span class="sxs-lookup"><span data-stu-id="8a41d-103">You can use GDI+ to render images that exist as files in your applications.</span></span> <span data-ttu-id="8a41d-104">为此，可创建新的对象的<xref:System.Drawing.Image>类 (如<xref:System.Drawing.Bitmap>)，则创建<xref:System.Drawing.Graphics>对象，是指你想要使用，请在绘图图面，并调用<xref:System.Drawing.Graphics.DrawImage%2A>方法<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="8a41d-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="8a41d-105">将在图形类所表示的绘图表面上绘制图像。</span><span class="sxs-lookup"><span data-stu-id="8a41d-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="8a41d-106">可以使用图像编辑器创建和编辑在设计时，图像文件，并在运行时使用 GDI + 呈现它们。</span><span class="sxs-lookup"><span data-stu-id="8a41d-106">You can use the Image Editor to create and edit image files at design time, and render them with GDI+ at run time.</span></span> <span data-ttu-id="8a41d-107">有关详细信息，请参阅[图标的图像编辑器](/cpp/windows/image-editor-for-icons)。</span><span class="sxs-lookup"><span data-stu-id="8a41d-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="8a41d-108">使用 GDI+ 呈现图像</span><span class="sxs-lookup"><span data-stu-id="8a41d-108">To render an image with GDI+</span></span>  
  
1. <span data-ttu-id="8a41d-109">创建一个对象，该对象表示要显示的图像。</span><span class="sxs-lookup"><span data-stu-id="8a41d-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="8a41d-110">此对象必须是继承的类成员<xref:System.Drawing.Image>，如<xref:System.Drawing.Bitmap>或<xref:System.Drawing.Imaging.Metafile>。</span><span class="sxs-lookup"><span data-stu-id="8a41d-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="8a41d-111">下面显示了一个示例：</span><span class="sxs-lookup"><span data-stu-id="8a41d-111">An example is shown:</span></span>  
  
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
  
2. <span data-ttu-id="8a41d-112">创建<xref:System.Drawing.Graphics>对象，表示你想要使用的绘图图面。</span><span class="sxs-lookup"><span data-stu-id="8a41d-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="8a41d-113">有关详细信息，请参阅[如何：创建用于绘制图形对象](how-to-create-graphics-objects-for-drawing.md)。</span><span class="sxs-lookup"><span data-stu-id="8a41d-113">For more information, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
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
  
3. <span data-ttu-id="8a41d-114">调用<xref:System.Drawing.Graphics.DrawImage%2A>的 graphics 对象，以呈现图像。</span><span class="sxs-lookup"><span data-stu-id="8a41d-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="8a41d-115">必须同时指定要绘制的图像以及将绘制它的位置坐标。</span><span class="sxs-lookup"><span data-stu-id="8a41d-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8a41d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a41d-116">See also</span></span>

- [<span data-ttu-id="8a41d-117">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="8a41d-117">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="8a41d-118">如何：创建用于绘制图形对象</span><span class="sxs-lookup"><span data-stu-id="8a41d-118">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="8a41d-119">GDI+ 中的笔、直线和矩形</span><span class="sxs-lookup"><span data-stu-id="8a41d-119">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
- [<span data-ttu-id="8a41d-120">如何：在 Windows 窗体上绘制文本</span><span class="sxs-lookup"><span data-stu-id="8a41d-120">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)
- [<span data-ttu-id="8a41d-121">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="8a41d-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="8a41d-122">绘制线条或闭合的图形</span><span class="sxs-lookup"><span data-stu-id="8a41d-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [<span data-ttu-id="8a41d-123">图标的图像编辑器</span><span class="sxs-lookup"><span data-stu-id="8a41d-123">Image Editor for Icons</span></span>](/cpp/windows/image-editor-for-icons)
