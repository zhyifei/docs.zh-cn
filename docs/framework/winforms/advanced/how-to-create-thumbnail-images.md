---
title: 如何：创建缩略图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 870ea223698e48438bd4dd08597d0a6ab79cec27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-thumbnail-images"></a>如何：创建缩略图像
缩略图是映像的缩小版本。 你可以通过调用创建缩略图<xref:System.Drawing.Image.GetThumbnailImage%2A>方法<xref:System.Drawing.Image>对象。  
  
## <a name="example"></a>示例  
 下面的示例构造<xref:System.Drawing.Image>从 JPG 文件的对象。 原始的图像的宽度为 640 像素，479 像素的高度。 该代码创建缩略图具有 100 个像素宽度和 100 像素的高度。  
  
 下图显示的缩略图。  
  
 ![缩略图](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  在此示例中，回调方法是声明，但是从不使用。 这样可支持所有版本的 GDI +。  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 若要运行该示例，请按照下列步骤：  
  
1.  创建新的 Windows 窗体应用程序。  
  
2.  添加到窗体代码示例。  
  
3.  创建的处理程序窗体的<xref:System.Windows.Forms.Control.Paint>事件  
  
4.  在<xref:System.Windows.Forms.Control.Paint>处理程序中，调用`GetThumbnail`方法并传入`e`为<xref:System.Windows.Forms.PaintEventArgs>。  
  
5.  找到你想要的缩略图图像文件。  
  
6.  在`GetThumbnail`方法，指定的路径和文件到你的映像的名称。  
  
7.  按 F5 运行该示例。  
  
     窗体上显示 100 通过 100 缩略图。  
  
## <a name="see-also"></a>请参阅  
 [图像、位图和图元文件](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [使用图像、位图、图标和图元文件](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
