---
title: "如何：裁切和缩放图像"
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
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8fb5d527cd1047197f370c4a9a9b1f8f33461653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="561a5-102">如何：裁切和缩放图像</span><span class="sxs-lookup"><span data-stu-id="561a5-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="561a5-103"><xref:System.Drawing.Graphics>类提供了若干个<xref:System.Drawing.Graphics.DrawImage%2A>方法，其中一些具有可用于裁剪和缩放图像的源和目标矩形参数。</span><span class="sxs-lookup"><span data-stu-id="561a5-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="561a5-104">示例</span><span class="sxs-lookup"><span data-stu-id="561a5-104">Example</span></span>  
 <span data-ttu-id="561a5-105">下面的示例构造<xref:System.Drawing.Image>从磁盘文件 Apple.gif 的对象。</span><span class="sxs-lookup"><span data-stu-id="561a5-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="561a5-106">代码中的原始大小绘制整个 apple 映像。</span><span class="sxs-lookup"><span data-stu-id="561a5-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="561a5-107">然后，代码调用<xref:System.Drawing.Graphics.DrawImage%2A>方法<xref:System.Drawing.Graphics>对象大于原始 apple 映像的目标矩形中绘制 apple 映像的一部分。</span><span class="sxs-lookup"><span data-stu-id="561a5-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="561a5-108"><xref:System.Drawing.Graphics.DrawImage%2A>方法确定 apple 绘制通过查看源矩形，通过第三个、 第四步： 指定第五个，和第六个自变量的哪个部分。</span><span class="sxs-lookup"><span data-stu-id="561a5-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="561a5-109">在这种情况下，apple 裁剪为 75%的其宽度和高度的 75%。</span><span class="sxs-lookup"><span data-stu-id="561a5-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="561a5-110"><xref:System.Drawing.Graphics.DrawImage%2A>方法确定绘制裁剪后的 apple 的位置和大小以使通过查看目标矩形的裁剪的 apple，即第二个自变量所指定。</span><span class="sxs-lookup"><span data-stu-id="561a5-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="561a5-111">在这种情况下，目标矩形是 30%宽度和高度大于原始图像的 30%。</span><span class="sxs-lookup"><span data-stu-id="561a5-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="561a5-112">下图显示原始 apple 和缩放、 裁剪 apple。</span><span class="sxs-lookup"><span data-stu-id="561a5-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 <span data-ttu-id="561a5-113">![裁剪和缩放](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")</span><span class="sxs-lookup"><span data-stu-id="561a5-113">![Crop & Scale](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="561a5-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="561a5-114">Compiling the Code</span></span>  
 <span data-ttu-id="561a5-115">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="561a5-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="561a5-116">请确保将`Apple.gif`用的图像文件名称和你系统有效的路径。</span><span class="sxs-lookup"><span data-stu-id="561a5-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="561a5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="561a5-117">See Also</span></span>  
 [<span data-ttu-id="561a5-118">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="561a5-118">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="561a5-119">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="561a5-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
