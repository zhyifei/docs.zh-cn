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
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="e352c-102">如何：确定编码器支持的参数</span><span class="sxs-lookup"><span data-stu-id="e352c-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="e352c-103">可以调整图像的参数，例如质量和压缩级别，但你必须知道给定的图像编码器支持哪些参数。</span><span class="sxs-lookup"><span data-stu-id="e352c-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="e352c-104"><xref:System.Drawing.Image>类提供了<xref:System.Drawing.Image.GetEncoderParameterList%2A>方法，以便你可以确定特定编码器支持的图像参数。</span><span class="sxs-lookup"><span data-stu-id="e352c-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="e352c-105">使用 GUID 指定编码器。</span><span class="sxs-lookup"><span data-stu-id="e352c-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="e352c-106"><xref:System.Drawing.Image.GetEncoderParameterList%2A>方法返回的数组<xref:System.Drawing.Imaging.EncoderParameter>对象。</span><span class="sxs-lookup"><span data-stu-id="e352c-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e352c-107">示例</span><span class="sxs-lookup"><span data-stu-id="e352c-107">Example</span></span>  
 <span data-ttu-id="e352c-108">下面的代码示例输出 JPEG 编码器支持的参数。</span><span class="sxs-lookup"><span data-stu-id="e352c-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="e352c-109">使用参数类别和相关联的 Guid 中的列表<xref:System.Drawing.Imaging.Encoder>类概述来确定每个参数的类别。</span><span class="sxs-lookup"><span data-stu-id="e352c-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e352c-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="e352c-110">Compiling the Code</span></span>  
 <span data-ttu-id="e352c-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="e352c-111">This example requires:</span></span>  
  
- <span data-ttu-id="e352c-112">Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="e352c-112">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="e352c-113">一个<xref:System.Windows.Forms.PaintEventArgs>，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="e352c-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e352c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e352c-114">See also</span></span>

- [<span data-ttu-id="e352c-115">如何：列出已安装的编码器</span><span class="sxs-lookup"><span data-stu-id="e352c-115">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="e352c-116">位图类型</span><span class="sxs-lookup"><span data-stu-id="e352c-116">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="e352c-117">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="e352c-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
