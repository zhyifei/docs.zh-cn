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
# <a name="how-to-crop-and-scale-images"></a>如何：裁切和缩放图像
<xref:System.Drawing.Graphics>类提供了若干个<xref:System.Drawing.Graphics.DrawImage%2A>方法，其中一些具有可用于裁剪和缩放图像的源和目标矩形参数。  
  
## <a name="example"></a>示例  
 下面的示例构造<xref:System.Drawing.Image>从磁盘文件 Apple.gif 的对象。 代码中的原始大小绘制整个 apple 映像。 然后，代码调用<xref:System.Drawing.Graphics.DrawImage%2A>方法<xref:System.Drawing.Graphics>对象大于原始 apple 映像的目标矩形中绘制 apple 映像的一部分。  
  
 <xref:System.Drawing.Graphics.DrawImage%2A>方法确定 apple 绘制通过查看源矩形，通过第三个、 第四步： 指定第五个，和第六个自变量的哪个部分。 在这种情况下，apple 裁剪为 75%的其宽度和高度的 75%。  
  
 <xref:System.Drawing.Graphics.DrawImage%2A>方法确定绘制裁剪后的 apple 的位置和大小以使通过查看目标矩形的裁剪的 apple，即第二个自变量所指定。 在这种情况下，目标矩形是 30%宽度和高度大于原始图像的 30%。  
  
 下图显示原始 apple 和缩放、 裁剪 apple。  
  
 ![裁剪和缩放](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 请确保将`Apple.gif`用的图像文件名称和你系统有效的路径。  
  
## <a name="see-also"></a>另请参阅  
 [图像、位图和图元文件](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [使用图像、位图、图标和图元文件](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
