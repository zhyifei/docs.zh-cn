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
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504589"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="044b6-102">GDI+ 中的图元文件</span><span class="sxs-lookup"><span data-stu-id="044b6-102">Metafiles in GDI+</span></span>
<span data-ttu-id="044b6-103">GDI + 提供了<xref:System.Drawing.Imaging.Metafile>类，使您可以记录和显示图元文件。</span><span class="sxs-lookup"><span data-stu-id="044b6-103">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="044b6-104">图元文件，也称为矢量图像，是存储为一系列绘图命令和设置的映像。</span><span class="sxs-lookup"><span data-stu-id="044b6-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="044b6-105">在中记录的命令和设置<xref:System.Drawing.Imaging.Metafile>对象可以存储在内存中或保存到文件或流。</span><span class="sxs-lookup"><span data-stu-id="044b6-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="044b6-106">图元文件格式</span><span class="sxs-lookup"><span data-stu-id="044b6-106">Metafile Formats</span></span>  
 <span data-ttu-id="044b6-107">GDI + 可以显示图元文件的已存储在以下格式：</span><span class="sxs-lookup"><span data-stu-id="044b6-107">GDI+ can display metafiles that have been stored in the following formats:</span></span>  
  
- <span data-ttu-id="044b6-108">Windows Metafile (WMF)</span><span class="sxs-lookup"><span data-stu-id="044b6-108">Windows Metafile (WMF)</span></span>  
  
- <span data-ttu-id="044b6-109">增强型图元文件 (EMF)</span><span class="sxs-lookup"><span data-stu-id="044b6-109">Enhanced Metafile (EMF)</span></span>  
  
- <span data-ttu-id="044b6-110">EMF+</span><span class="sxs-lookup"><span data-stu-id="044b6-110">EMF+</span></span>  
  
 <span data-ttu-id="044b6-111">中的 EMF 和 EMF + 格式，但不是在 WMF 格式 GDI + 可以记录图元文件。</span><span class="sxs-lookup"><span data-stu-id="044b6-111">GDI+ can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="044b6-112">EMF + 是允许 GDI + 记录要存储的 EMF 的扩展。</span><span class="sxs-lookup"><span data-stu-id="044b6-112">EMF+ is an extension to EMF that allows GDI+ records to be stored.</span></span> <span data-ttu-id="044b6-113">有两种变体的 EMF + 格式：EMF + 仅和 EMF + 双重。</span><span class="sxs-lookup"><span data-stu-id="044b6-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="044b6-114">EMF + 仅图元文件仅包含 GDI + 记录。</span><span class="sxs-lookup"><span data-stu-id="044b6-114">EMF+ Only metafiles contain only GDI+ records.</span></span> <span data-ttu-id="044b6-115">可以通过 GDI +，但不能通过 GDI 显示此类图元文件。</span><span class="sxs-lookup"><span data-stu-id="044b6-115">Such metafiles can be displayed by GDI+ but not by GDI.</span></span> <span data-ttu-id="044b6-116">EMF + 双重图元文件包含 GDI + 和 GDI 记录。</span><span class="sxs-lookup"><span data-stu-id="044b6-116">EMF+ Dual metafiles contain GDI+ and GDI records.</span></span> <span data-ttu-id="044b6-117">EMF + 双重图元文件中的每个 GDI + 记录都与一个备用的 GDI 记录成对出现。</span><span class="sxs-lookup"><span data-stu-id="044b6-117">Each GDI+ record in an EMF+ Dual metafile is paired with an alternate GDI record.</span></span> <span data-ttu-id="044b6-118">可以通过 GDI + 或通过 GDI 显示此类图元文件。</span><span class="sxs-lookup"><span data-stu-id="044b6-118">Such metafiles can be displayed by GDI+ or by GDI.</span></span>  
  
 <span data-ttu-id="044b6-119">以下示例显示图元文件的以前保存为文件。</span><span class="sxs-lookup"><span data-stu-id="044b6-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="044b6-120">与在其左上角显示图元文件 （100，100）。</span><span class="sxs-lookup"><span data-stu-id="044b6-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="044b6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="044b6-121">See also</span></span>

- [<span data-ttu-id="044b6-122">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="044b6-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
