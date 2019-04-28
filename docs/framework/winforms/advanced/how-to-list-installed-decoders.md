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
ms.openlocfilehash: c92b8010def2f77f859ee0bd9cdb1ed51dd15f27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723038"
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="c55d6-102">如何：列出已安装的解码器</span><span class="sxs-lookup"><span data-stu-id="c55d6-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="c55d6-103">你可能要列出可用的计算机上的图像解码器，以确定你的应用程序是否可以读取特定图像文件格式。</span><span class="sxs-lookup"><span data-stu-id="c55d6-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="c55d6-104"><xref:System.Drawing.Imaging.ImageCodecInfo>类提供了<xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>静态方法，以便你可以确定哪个图像解码器可供使用。</span><span class="sxs-lookup"><span data-stu-id="c55d6-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="c55d6-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 返回一个数组<xref:System.Drawing.Imaging.ImageCodecInfo>对象。</span><span class="sxs-lookup"><span data-stu-id="c55d6-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c55d6-106">示例</span><span class="sxs-lookup"><span data-stu-id="c55d6-106">Example</span></span>  
 <span data-ttu-id="c55d6-107">下面的代码示例输出已安装的解码器的列表和其属性值。</span><span class="sxs-lookup"><span data-stu-id="c55d6-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c55d6-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="c55d6-108">Compiling the Code</span></span>  
 <span data-ttu-id="c55d6-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c55d6-109">This example requires:</span></span>  
  
- <span data-ttu-id="c55d6-110">Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="c55d6-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="c55d6-111">一个<xref:System.Windows.Forms.PaintEventArgs>，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="c55d6-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c55d6-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c55d6-112">See also</span></span>

- [<span data-ttu-id="c55d6-113">如何：列出已安装的编码器</span><span class="sxs-lookup"><span data-stu-id="c55d6-113">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="c55d6-114">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="c55d6-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
