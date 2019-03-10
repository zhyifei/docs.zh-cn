---
title: 如何：在屏幕上绘制现有位图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: a23026e0ac377294e3e4356d341c45d31b4ecd79
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724435"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a><span data-ttu-id="a7ba1-102">如何：在屏幕上绘制现有位图</span><span class="sxs-lookup"><span data-stu-id="a7ba1-102">How to: Draw an Existing Bitmap to the Screen</span></span>
<span data-ttu-id="a7ba1-103">在屏幕上，可以轻松地绘制现有映像。</span><span class="sxs-lookup"><span data-stu-id="a7ba1-103">You can easily draw an existing image on the screen.</span></span> <span data-ttu-id="a7ba1-104">首先需要创建<xref:System.Drawing.Bitmap>对象使用的位图构造函数采用一个文件名， <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>。</span><span class="sxs-lookup"><span data-stu-id="a7ba1-104">First you need to create a <xref:System.Drawing.Bitmap> object by using the bitmap constructor that takes a file name, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span></span> <span data-ttu-id="a7ba1-105">此构造函数接受使用几个不同的文件格式，包括 BMP、 GIF、 JPEG、 PNG 和 TIFF 图像。</span><span class="sxs-lookup"><span data-stu-id="a7ba1-105">This constructor accepts images with several different file formats, including BMP, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="a7ba1-106">创建后<xref:System.Drawing.Bitmap>对象，将其传递<xref:System.Drawing.Bitmap>对象传递给<xref:System.Drawing.Graphics.DrawImage%2A>方法的<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="a7ba1-106">After you have created the <xref:System.Drawing.Bitmap> object, pass that <xref:System.Drawing.Bitmap> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7ba1-107">示例</span><span class="sxs-lookup"><span data-stu-id="a7ba1-107">Example</span></span>  
 <span data-ttu-id="a7ba1-108">此示例将创建<xref:System.Drawing.Bitmap>JPEG 文件中的对象，然后绘制在其左上角的位图 （60，10）。</span><span class="sxs-lookup"><span data-stu-id="a7ba1-108">This example creates a <xref:System.Drawing.Bitmap> object from a JPEG file and then draws the bitmap with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="a7ba1-109">下图显示了在指定位置绘制位图。</span><span class="sxs-lookup"><span data-stu-id="a7ba1-109">The following illustration shows the bitmap drawn at the specified location.</span></span>  
  
 <span data-ttu-id="a7ba1-110">![图像位置](./media/csimageposition1.png "csimageposition1")</span><span class="sxs-lookup"><span data-stu-id="a7ba1-110">![Image Position](./media/csimageposition1.png "csimageposition1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a7ba1-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="a7ba1-111">Compiling the Code</span></span>  
 <span data-ttu-id="a7ba1-112">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="a7ba1-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ba1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7ba1-113">See also</span></span>
- [<span data-ttu-id="a7ba1-114">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="a7ba1-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="a7ba1-115">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="a7ba1-115">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
