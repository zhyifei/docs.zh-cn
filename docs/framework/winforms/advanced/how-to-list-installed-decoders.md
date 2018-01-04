---
title: "如何：列出已安装的解码器"
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
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7993345a39a24c770fdd717580d428968dae836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="c1021-102">如何：列出已安装的解码器</span><span class="sxs-lookup"><span data-stu-id="c1021-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="c1021-103">你可能想要列出可用的计算机上，图像解码器，以确定你的应用程序是否可以读取特定的图像文件格式。</span><span class="sxs-lookup"><span data-stu-id="c1021-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="c1021-104"><xref:System.Drawing.Imaging.ImageCodecInfo>类提供<xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>静态方法，以便你能够确定哪些图像解码器可供使用。</span><span class="sxs-lookup"><span data-stu-id="c1021-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="c1021-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>返回的数组<xref:System.Drawing.Imaging.ImageCodecInfo>对象。</span><span class="sxs-lookup"><span data-stu-id="c1021-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1021-106">示例</span><span class="sxs-lookup"><span data-stu-id="c1021-106">Example</span></span>  
 <span data-ttu-id="c1021-107">下面的代码示例将输出的已安装的解码器列表和其属性值。</span><span class="sxs-lookup"><span data-stu-id="c1021-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c1021-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="c1021-108">Compiling the Code</span></span>  
 <span data-ttu-id="c1021-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c1021-109">This example requires:</span></span>  
  
-   <span data-ttu-id="c1021-110">Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="c1021-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="c1021-111">A <xref:System.Windows.Forms.PaintEventArgs>，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="c1021-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1021-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1021-112">See Also</span></span>  
 [<span data-ttu-id="c1021-113">如何：列出已安装的编码器</span><span class="sxs-lookup"><span data-stu-id="c1021-113">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [<span data-ttu-id="c1021-114">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="c1021-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
