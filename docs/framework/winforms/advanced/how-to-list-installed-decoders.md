---
title: 如何：列出已安装的解码器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: 961862d6212b7e76812fc222d3a99f08528d9a16
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626910"
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="aa435-102">如何：列出已安装的解码器</span><span class="sxs-lookup"><span data-stu-id="aa435-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="aa435-103">你可能要列出可用的计算机上的图像解码器，以确定你的应用程序是否可以读取特定图像文件格式。</span><span class="sxs-lookup"><span data-stu-id="aa435-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="aa435-104"><xref:System.Drawing.Imaging.ImageCodecInfo>类提供了<xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>静态方法，以便你可以确定哪个图像解码器可供使用。</span><span class="sxs-lookup"><span data-stu-id="aa435-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="aa435-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 返回一个数组<xref:System.Drawing.Imaging.ImageCodecInfo>对象。</span><span class="sxs-lookup"><span data-stu-id="aa435-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa435-106">示例</span><span class="sxs-lookup"><span data-stu-id="aa435-106">Example</span></span>  
 <span data-ttu-id="aa435-107">下面的代码示例输出已安装的解码器的列表和其属性值。</span><span class="sxs-lookup"><span data-stu-id="aa435-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aa435-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="aa435-108">Compiling the Code</span></span>  
 <span data-ttu-id="aa435-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="aa435-109">This example requires:</span></span>  
  
- <span data-ttu-id="aa435-110">Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="aa435-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="aa435-111">一个<xref:System.Windows.Forms.PaintEventArgs>，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="aa435-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa435-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa435-112">See also</span></span>

- [<span data-ttu-id="aa435-113">如何：列出已安装的编码器</span><span class="sxs-lookup"><span data-stu-id="aa435-113">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="aa435-114">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="aa435-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
