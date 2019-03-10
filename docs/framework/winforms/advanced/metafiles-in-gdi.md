---
title: GDI+ 中的图元文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: 25ce3fdd98560aba0918431bb77d6f3f23a04784
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722459"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="6e7c5-102">GDI+ 中的图元文件</span><span class="sxs-lookup"><span data-stu-id="6e7c5-102">Metafiles in GDI+</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="6e7c5-103">提供了<xref:System.Drawing.Imaging.Metafile>类，使您可以记录和显示图元文件。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-103">provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="6e7c5-104">图元文件，也称为矢量图像，是存储为一系列绘图命令和设置的映像。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="6e7c5-105">在中记录的命令和设置<xref:System.Drawing.Imaging.Metafile>对象可以存储在内存中或保存到文件或流。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="6e7c5-106">图元文件格式</span><span class="sxs-lookup"><span data-stu-id="6e7c5-106">Metafile Formats</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="6e7c5-107">可以显示图元文件的已存储在以下格式：</span><span class="sxs-lookup"><span data-stu-id="6e7c5-107">can display metafiles that have been stored in the following formats:</span></span>  
  
-   <span data-ttu-id="6e7c5-108">Windows Metafile (WMF)</span><span class="sxs-lookup"><span data-stu-id="6e7c5-108">Windows Metafile (WMF)</span></span>  
  
-   <span data-ttu-id="6e7c5-109">增强型图元文件 (EMF)</span><span class="sxs-lookup"><span data-stu-id="6e7c5-109">Enhanced Metafile (EMF)</span></span>  
  
-   <span data-ttu-id="6e7c5-110">EMF+</span><span class="sxs-lookup"><span data-stu-id="6e7c5-110">EMF+</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="6e7c5-111">可以记录图元文件中的 EMF 和 EMF + 格式，但不是在 WMF 格式。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-111">can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="6e7c5-112">EMF + 是允许的 EMF 扩展[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]要存储的记录。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-112">EMF+ is an extension to EMF that allows [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records to be stored.</span></span> <span data-ttu-id="6e7c5-113">有两种变体的 EMF + 格式：EMF + 仅和 EMF + 双重。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="6e7c5-114">EMF + 仅图元文件仅包含[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]记录。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-114">EMF+ Only metafiles contain only [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records.</span></span> <span data-ttu-id="6e7c5-115">此类图元文件可由显示[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]而不是按[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-115">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] but not by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span> <span data-ttu-id="6e7c5-116">EMF + 双重图元文件包含[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]和[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]记录。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-116">EMF+ Dual metafiles contain [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] records.</span></span> <span data-ttu-id="6e7c5-117">每个[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]记录 EMF + 双重中图元文件与配对备用[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]记录。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-117">Each [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record in an EMF+ Dual metafile is paired with an alternate [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record.</span></span> <span data-ttu-id="6e7c5-118">此类图元文件可由显示[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]或通过[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-118">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] or by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 <span data-ttu-id="6e7c5-119">以下示例显示图元文件的以前保存为文件。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="6e7c5-120">与在其左上角显示图元文件 （100，100）。</span><span class="sxs-lookup"><span data-stu-id="6e7c5-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="6e7c5-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e7c5-121">See also</span></span>
- [<span data-ttu-id="6e7c5-122">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="6e7c5-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
