---
title: 如何：列出已安装的解码器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 1882ce9a140fb325c29411173ba7bde717bd3f98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524750"
---
# <a name="how-to-list-installed-encoders"></a>如何：列出已安装的解码器
你可能想要列出可用的计算机上的图像编码器，以确定是否可以将你的应用程序保存到特定的图像文件格式。 <xref:System.Drawing.Imaging.ImageCodecInfo>类提供<xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>静态方法，以便你能够确定哪些图像编码器可供使用。 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> 返回的数组<xref:System.Drawing.Imaging.ImageCodecInfo>对象。  
  
## <a name="example"></a>示例  
 下面的代码示例将输出的已安装的编码器列表和其属性值。  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   Windows 窗体应用程序。  
  
-   A <xref:System.Windows.Forms.PaintEventArgs>，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>请参阅  
 [如何：列出已安装的解码器](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 [在托管 GDI+ 中使用图像编码器和解码器](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
