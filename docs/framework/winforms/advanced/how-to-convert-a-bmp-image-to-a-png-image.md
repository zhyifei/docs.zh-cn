---
title: "如何：将 BMP 图像转换为 PNG 图像"
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
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ee2669c41f4ee558d9457cee7df0ae8425cf065
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a><span data-ttu-id="5bd00-102">如何：将 BMP 图像转换为 PNG 图像</span><span class="sxs-lookup"><span data-stu-id="5bd00-102">How to: Convert a BMP image to a PNG image</span></span>
<span data-ttu-id="5bd00-103">通常，需要转换图像文件格式。</span><span class="sxs-lookup"><span data-stu-id="5bd00-103">Oftentimes, you will want to convert from one image file format to another.</span></span> <span data-ttu-id="5bd00-104">可以通过调用 <xref:System.Drawing.Image> 类的 <xref:System.Drawing.Image.Save%2A> 方法，并将 <xref:System.Drawing.Imaging.ImageFormat> 指定为所需的图像文件格式来轻松完成转换。</span><span class="sxs-lookup"><span data-stu-id="5bd00-104">You can do this conversion easily by calling the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class and specifying the <xref:System.Drawing.Imaging.ImageFormat> for the desired image file format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bd00-105">示例</span><span class="sxs-lookup"><span data-stu-id="5bd00-105">Example</span></span>  
 <span data-ttu-id="5bd00-106">以下示例从一个类型加载 BMP 图像，并以 PNG 格式保存该图像。</span><span class="sxs-lookup"><span data-stu-id="5bd00-106">The following example loads a BMP image from a type, and saves the image in the PNG format.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5bd00-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="5bd00-107">Compiling the Code</span></span>  
 <span data-ttu-id="5bd00-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="5bd00-108">This example requires:</span></span>  
  
-   <span data-ttu-id="5bd00-109">Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="5bd00-109">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="5bd00-110">对 `System.Drawing.Imaging` 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="5bd00-110">A reference to the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd00-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bd00-111">See Also</span></span>  
 [<span data-ttu-id="5bd00-112">如何：列出已安装的编码器</span><span class="sxs-lookup"><span data-stu-id="5bd00-112">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [<span data-ttu-id="5bd00-113">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="5bd00-113">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)  
 [<span data-ttu-id="5bd00-114">位图类型</span><span class="sxs-lookup"><span data-stu-id="5bd00-114">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)
