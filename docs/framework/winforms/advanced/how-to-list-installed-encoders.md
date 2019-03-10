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
ms.openlocfilehash: 492930b7d8a47db478c8fa0f282cb5f491e144ac
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708452"
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="ca1f4-102">如何：列出已安装的编码器</span><span class="sxs-lookup"><span data-stu-id="ca1f4-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="ca1f4-103">你可能要列出可用的计算机上的图像编码器，以确定是否可以将你的应用程序保存到特定的图像文件格式。</span><span class="sxs-lookup"><span data-stu-id="ca1f4-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="ca1f4-104"><xref:System.Drawing.Imaging.ImageCodecInfo>类提供了<xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>静态方法，以便你可以确定哪个图像编码器可供使用。</span><span class="sxs-lookup"><span data-stu-id="ca1f4-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="ca1f4-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> 返回一个数组<xref:System.Drawing.Imaging.ImageCodecInfo>对象。</span><span class="sxs-lookup"><span data-stu-id="ca1f4-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca1f4-106">示例</span><span class="sxs-lookup"><span data-stu-id="ca1f4-106">Example</span></span>  
 <span data-ttu-id="ca1f4-107">下面的代码示例输出的已安装的编码器列表和其属性值。</span><span class="sxs-lookup"><span data-stu-id="ca1f4-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ca1f4-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="ca1f4-108">Compiling the Code</span></span>  
 <span data-ttu-id="ca1f4-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="ca1f4-109">This example requires:</span></span>  
  
-   <span data-ttu-id="ca1f4-110">Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="ca1f4-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="ca1f4-111">一个<xref:System.Windows.Forms.PaintEventArgs>，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="ca1f4-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca1f4-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca1f4-112">See also</span></span>
- [<span data-ttu-id="ca1f4-113">如何：列出已安装的解码器</span><span class="sxs-lookup"><span data-stu-id="ca1f4-113">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)
- [<span data-ttu-id="ca1f4-114">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="ca1f4-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
