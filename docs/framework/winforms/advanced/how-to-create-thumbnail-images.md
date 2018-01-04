---
title: "如何：创建缩略图像"
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
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b8eeb856fabd895e171c0ad8739ae6a63b5c7065
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="0b333-102">如何：创建缩略图像</span><span class="sxs-lookup"><span data-stu-id="0b333-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="0b333-103">缩略图是映像的缩小版本。</span><span class="sxs-lookup"><span data-stu-id="0b333-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="0b333-104">你可以通过调用创建缩略图<xref:System.Drawing.Image.GetThumbnailImage%2A>方法<xref:System.Drawing.Image>对象。</span><span class="sxs-lookup"><span data-stu-id="0b333-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b333-105">示例</span><span class="sxs-lookup"><span data-stu-id="0b333-105">Example</span></span>  
 <span data-ttu-id="0b333-106">下面的示例构造<xref:System.Drawing.Image>从 JPG 文件的对象。</span><span class="sxs-lookup"><span data-stu-id="0b333-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="0b333-107">原始的图像的宽度为 640 像素，479 像素的高度。</span><span class="sxs-lookup"><span data-stu-id="0b333-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="0b333-108">该代码创建缩略图具有 100 个像素宽度和 100 像素的高度。</span><span class="sxs-lookup"><span data-stu-id="0b333-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="0b333-109">下图显示的缩略图。</span><span class="sxs-lookup"><span data-stu-id="0b333-109">The following illustration shows the thumbnail image.</span></span>  
  
 <span data-ttu-id="0b333-110">![缩略图](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")</span><span class="sxs-lookup"><span data-stu-id="0b333-110">![Thumbnail Image](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b333-111">在此示例中，回调方法是声明，但是从不使用。</span><span class="sxs-lookup"><span data-stu-id="0b333-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="0b333-112">这样可支持所有版本的 GDI +。</span><span class="sxs-lookup"><span data-stu-id="0b333-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0b333-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="0b333-113">Compiling the Code</span></span>  
 <span data-ttu-id="0b333-114">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="0b333-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="0b333-115">若要运行该示例，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="0b333-115">To run the example, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0b333-116">创建新的 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b333-116">Create a new Windows Forms application.</span></span>  
  
2.  <span data-ttu-id="0b333-117">添加到窗体代码示例。</span><span class="sxs-lookup"><span data-stu-id="0b333-117">Add the example code to the form.</span></span>  
  
3.  <span data-ttu-id="0b333-118">创建的处理程序窗体的<xref:System.Windows.Forms.Control.Paint>事件</span><span class="sxs-lookup"><span data-stu-id="0b333-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4.  <span data-ttu-id="0b333-119">在<xref:System.Windows.Forms.Control.Paint>处理程序中，调用`GetThumbnail`方法并传入`e`为<xref:System.Windows.Forms.PaintEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="0b333-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5.  <span data-ttu-id="0b333-120">找到你想要的缩略图图像文件。</span><span class="sxs-lookup"><span data-stu-id="0b333-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6.  <span data-ttu-id="0b333-121">在`GetThumbnail`方法，指定的路径和文件到你的映像的名称。</span><span class="sxs-lookup"><span data-stu-id="0b333-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7.  <span data-ttu-id="0b333-122">按 F5 运行该示例。</span><span class="sxs-lookup"><span data-stu-id="0b333-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="0b333-123">窗体上显示 100 通过 100 缩略图。</span><span class="sxs-lookup"><span data-stu-id="0b333-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b333-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b333-124">See Also</span></span>  
 [<span data-ttu-id="0b333-125">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="0b333-125">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="0b333-126">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="0b333-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
