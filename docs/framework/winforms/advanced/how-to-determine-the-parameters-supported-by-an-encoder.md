---
title: 如何：确定编码器支持的参数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 7f7c270c4ae590c070103d51f116158869b678c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521974"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a>如何：确定编码器支持的参数
你可以调整图像参数，如质量和压缩级别，但你必须知道给定的图像编码器支持的参数。 <xref:System.Drawing.Image>类提供<xref:System.Drawing.Image.GetEncoderParameterList%2A>方法，以便你能够确定为特定编码器支持哪些映像参数。 你指定编码器使用的 GUID。 <xref:System.Drawing.Image.GetEncoderParameterList%2A>方法返回的数组<xref:System.Drawing.Imaging.EncoderParameter>对象。  
  
## <a name="example"></a>示例  
 下面的代码示例输出 JPEG 编码器支持的参数。 使用的参数类别和中的关联的 Guid 列表<xref:System.Drawing.Imaging.Encoder>类的概述来确定每个参数的类别。  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   Windows 窗体应用程序。  
  
-   A <xref:System.Windows.Forms.PaintEventArgs>，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>请参阅  
 [如何：列出已安装的编码器](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [位图类型](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 [在托管 GDI+ 中使用图像编码器和解码器](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
