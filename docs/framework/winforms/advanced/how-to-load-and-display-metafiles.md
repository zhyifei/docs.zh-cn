---
title: 如何：加载和显示图元文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: c2b0a89966100077d5a72edc11822c356d2de1b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="17736-102">如何：加载和显示图元文件</span><span class="sxs-lookup"><span data-stu-id="17736-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="17736-103"><xref:System.Drawing.Imaging.Metafile>类，该类继承自<xref:System.Drawing.Image>类中，提供用于记录、 显示和检查矢量图像的方法。</span><span class="sxs-lookup"><span data-stu-id="17736-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17736-104">示例</span><span class="sxs-lookup"><span data-stu-id="17736-104">Example</span></span>  
 <span data-ttu-id="17736-105">若要在屏幕上显示矢量图像 （图元文件），你需要<xref:System.Drawing.Imaging.Metafile>对象和一个<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="17736-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="17736-106">将文件 （或流） 的名称传递给<xref:System.Drawing.Imaging.Metafile>构造函数。</span><span class="sxs-lookup"><span data-stu-id="17736-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="17736-107">创建后<xref:System.Drawing.Imaging.Metafile>对象，请传递<xref:System.Drawing.Imaging.Metafile>对象传递给<xref:System.Drawing.Graphics.DrawImage%2A>方法<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="17736-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="17736-108">该示例创建<xref:System.Drawing.Imaging.Metafile>EMF （增强型图元文件） 文件中的对象，然后绘制具有在其左上角的映像 （60，10）。</span><span class="sxs-lookup"><span data-stu-id="17736-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="17736-109">下图显示在指定位置绘制图元文件。</span><span class="sxs-lookup"><span data-stu-id="17736-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="17736-110">![图像位置](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="17736-110">![Image Position](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="17736-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="17736-111">Compiling the Code</span></span>  
 <span data-ttu-id="17736-112">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="17736-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17736-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="17736-113">See Also</span></span>  
 [<span data-ttu-id="17736-114">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="17736-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
