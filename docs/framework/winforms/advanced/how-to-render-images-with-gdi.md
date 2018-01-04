---
title: "如何：使用 GDI+ 呈现图像"
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
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a6edc48c93f83611bdc2be5b7398ab0abe843407
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="8bfce-102">如何：使用 GDI+ 呈现图像</span><span class="sxs-lookup"><span data-stu-id="8bfce-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="8bfce-103">可在应用程序中使用 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 呈现以文件形式存在的图像。</span><span class="sxs-lookup"><span data-stu-id="8bfce-103">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render images that exist as files in your applications.</span></span> <span data-ttu-id="8bfce-104">执行此操作通过创建的新对象<xref:System.Drawing.Image>类 (如<xref:System.Drawing.Bitmap>)，则创建<xref:System.Drawing.Graphics>对象来引用所需的绘图图面的和调用<xref:System.Drawing.Graphics.DrawImage%2A>方法<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="8bfce-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="8bfce-105">将在图形类所表示的绘图表面上绘制图像。</span><span class="sxs-lookup"><span data-stu-id="8bfce-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="8bfce-106">可在设计时使用图像编辑器创建和编辑图像文件，而在运行时使用 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 呈现图像。</span><span class="sxs-lookup"><span data-stu-id="8bfce-106">You can use the Image Editor to create and edit image files at design time, and render them with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] at run time.</span></span> <span data-ttu-id="8bfce-107">有关详细信息，请参阅[图标的图像编辑器](/cpp/windows/image-editor-for-icons)。</span><span class="sxs-lookup"><span data-stu-id="8bfce-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="8bfce-108">使用 GDI+ 呈现图像</span><span class="sxs-lookup"><span data-stu-id="8bfce-108">To render an image with GDI+</span></span>  
  
1.  <span data-ttu-id="8bfce-109">创建一个对象，该对象表示要显示的图像。</span><span class="sxs-lookup"><span data-stu-id="8bfce-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="8bfce-110">此对象必须是继承自的类成员<xref:System.Drawing.Image>，如<xref:System.Drawing.Bitmap>或<xref:System.Drawing.Imaging.Metafile>。</span><span class="sxs-lookup"><span data-stu-id="8bfce-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="8bfce-111">下面显示了一个示例：</span><span class="sxs-lookup"><span data-stu-id="8bfce-111">An example is shown:</span></span>  
  
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
  
2.  <span data-ttu-id="8bfce-112">创建<xref:System.Drawing.Graphics>对象，表示你想要使用的绘图图面。</span><span class="sxs-lookup"><span data-stu-id="8bfce-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="8bfce-113">有关详细信息，请参阅[如何：创建用于绘制的 Graphics 对象](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)。</span><span class="sxs-lookup"><span data-stu-id="8bfce-113">For more information, see [How to: Create Graphics Objects for Drawing](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
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
  
3.  <span data-ttu-id="8bfce-114">调用<xref:System.Drawing.Graphics.DrawImage%2A>的图形对象呈现图像。</span><span class="sxs-lookup"><span data-stu-id="8bfce-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="8bfce-115">必须同时指定要绘制的图像以及将绘制它的位置坐标。</span><span class="sxs-lookup"><span data-stu-id="8bfce-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8bfce-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bfce-116">See Also</span></span>  
 [<span data-ttu-id="8bfce-117">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="8bfce-117">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="8bfce-118">如何：创建用于绘制的图形对象</span><span class="sxs-lookup"><span data-stu-id="8bfce-118">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="8bfce-119">GDI+ 中的笔、直线和矩形</span><span class="sxs-lookup"><span data-stu-id="8bfce-119">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)  
 [<span data-ttu-id="8bfce-120">如何：在 Windows 窗体上绘制文本</span><span class="sxs-lookup"><span data-stu-id="8bfce-120">How to: Draw Text on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)  
 [<span data-ttu-id="8bfce-121">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="8bfce-121">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="8bfce-122">绘制线条或闭合的图形</span><span class="sxs-lookup"><span data-stu-id="8bfce-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)  
 [<span data-ttu-id="8bfce-123">图标的图像编辑器</span><span class="sxs-lookup"><span data-stu-id="8bfce-123">Image Editor for Icons</span></span>](/cpp/windows/image-editor-for-icons)
