---
title: 如何：确定编码器支持的参数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 2626eee239d9876125340dd133c5a9b3e45c3d7e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004323"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a>如何：确定编码器支持的参数
可以调整图像的参数，例如质量和压缩级别，但你必须知道给定的图像编码器支持哪些参数。 <xref:System.Drawing.Image>类提供了<xref:System.Drawing.Image.GetEncoderParameterList%2A>方法，以便你可以确定特定编码器支持的图像参数。 使用 GUID 指定编码器。 <xref:System.Drawing.Image.GetEncoderParameterList%2A>方法返回的数组<xref:System.Drawing.Imaging.EncoderParameter>对象。  
  
## <a name="example"></a>示例  
 下面的代码示例输出 JPEG 编码器支持的参数。 使用参数类别和相关联的 Guid 中的列表<xref:System.Drawing.Imaging.Encoder>类概述来确定每个参数的类别。  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- Windows 窗体应用程序。  
  
- 一个<xref:System.Windows.Forms.PaintEventArgs>，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>请参阅

- [如何：列出已安装的编码器](how-to-list-installed-encoders.md)
- [位图类型](types-of-bitmaps.md)
- [在托管 GDI+ 中使用图像编码器和解码器](using-image-encoders-and-decoders-in-managed-gdi.md)
