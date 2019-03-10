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
ms.openlocfilehash: 121f285a95d0169db79bdc302d80dba03b3b40c2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720038"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="13c53-102">如何：加载和显示图元文件</span><span class="sxs-lookup"><span data-stu-id="13c53-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="13c53-103"><xref:System.Drawing.Imaging.Metafile>类，该类继承自<xref:System.Drawing.Image>类中，提供用于记录、 显示和检查矢量图像的方法。</span><span class="sxs-lookup"><span data-stu-id="13c53-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13c53-104">示例</span><span class="sxs-lookup"><span data-stu-id="13c53-104">Example</span></span>  
 <span data-ttu-id="13c53-105">若要在屏幕上显示矢量图像 （图元文件），你需要<xref:System.Drawing.Imaging.Metafile>对象和一个<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="13c53-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="13c53-106">将文件 （或流） 的名称传递给<xref:System.Drawing.Imaging.Metafile>构造函数。</span><span class="sxs-lookup"><span data-stu-id="13c53-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="13c53-107">创建后<xref:System.Drawing.Imaging.Metafile>对象，将其传递<xref:System.Drawing.Imaging.Metafile>对象传递给<xref:System.Drawing.Graphics.DrawImage%2A>方法的<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="13c53-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="13c53-108">此示例将创建<xref:System.Drawing.Imaging.Metafile>EMF （增强型图元文件） 文件中的对象，然后绘制的图像，其左上角位于 （60，10）。</span><span class="sxs-lookup"><span data-stu-id="13c53-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="13c53-109">下图显示了在指定位置绘制图元文件。</span><span class="sxs-lookup"><span data-stu-id="13c53-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="13c53-110">![图像位置](./media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="13c53-110">![Image Position](./media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="13c53-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="13c53-111">Compiling the Code</span></span>  
 <span data-ttu-id="13c53-112">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="13c53-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c53-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="13c53-113">See also</span></span>
- [<span data-ttu-id="13c53-114">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="13c53-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
