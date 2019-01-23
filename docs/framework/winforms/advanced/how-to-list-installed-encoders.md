---
title: 如何：列出已安装的编码器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: c5019a349b4f3c881190241042cecc6c4c571950
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605651"
---
# <a name="how-to-list-installed-encoders"></a>如何：列出已安装的编码器
你可能要列出可用的计算机上的图像编码器，以确定是否可以将你的应用程序保存到特定的图像文件格式。 <xref:System.Drawing.Imaging.ImageCodecInfo>类提供了<xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>静态方法，以便你可以确定哪个图像编码器可供使用。 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> 返回一个数组<xref:System.Drawing.Imaging.ImageCodecInfo>对象。  
  
## <a name="example"></a>示例  
 下面的代码示例输出的已安装的编码器列表和其属性值。  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   Windows 窗体应用程序。  
  
-   一个<xref:System.Windows.Forms.PaintEventArgs>，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>请参阅
- [如何：列出已安装的解码器](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)
- [在托管 GDI+ 中使用图像编码器和解码器](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
