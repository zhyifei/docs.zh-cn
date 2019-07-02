---
title: 使用字体和文本
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505117"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="8a082-102">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="8a082-102">Using Fonts and Text</span></span>
<span data-ttu-id="8a082-103">还有几个类为在 Windows 窗体上绘制文本提供通过 GDI + 和 GDI。</span><span class="sxs-lookup"><span data-stu-id="8a082-103">There are several classes offered by GDI+ and GDI for drawing text on Windows Forms.</span></span> <span data-ttu-id="8a082-104">GDI +<xref:System.Drawing.Graphics>类具有多个<xref:System.Drawing.Graphics.DrawString%2A>，可以指定的文本，例如位置、 边框矩形、 字体和格式的各种功能的方法。</span><span class="sxs-lookup"><span data-stu-id="8a082-104">The GDI+ <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="8a082-105">此外，可以绘制和度量的文本值与使用静态的 GDI<xref:System.Windows.Forms.TextRenderer.DrawText%2A>并<xref:System.Windows.Forms.TextRenderer.MeasureText%2A>方法提供的`TextRenderer`类。</span><span class="sxs-lookup"><span data-stu-id="8a082-105">In addition, you can draw and measure text with GDI using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="8a082-106">GDI 方法还允许您指定位置、 字体和格式。</span><span class="sxs-lookup"><span data-stu-id="8a082-106">The GDI methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="8a082-107">你可为文本呈现; 选择 GDI 或 GDI +但是，GDI 通常提供更好的性能，并且正在测量更准确的文本。</span><span class="sxs-lookup"><span data-stu-id="8a082-107">You can choose either GDI or GDI+ for text rendering; however, GDI generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="8a082-108">涉及文本呈现其他类包括`FontFamily`， `Font`， <xref:System.Drawing.StringFormat>，和`TextFormatFlags`。</span><span class="sxs-lookup"><span data-stu-id="8a082-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a082-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="8a082-109">In This Section</span></span>  
 [<span data-ttu-id="8a082-110">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="8a082-110">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="8a082-111">演示如何创建`Font`和`FontFamily`对象。</span><span class="sxs-lookup"><span data-stu-id="8a082-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="8a082-112">如何：在指定位置绘制文本</span><span class="sxs-lookup"><span data-stu-id="8a082-112">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="8a082-113">介绍如何在某个位置使用 GDI + 和 GDI 绘制文本。</span><span class="sxs-lookup"><span data-stu-id="8a082-113">Describes how to draw text in a certain location using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="8a082-114">如何：在矩形中绘制换行文本</span><span class="sxs-lookup"><span data-stu-id="8a082-114">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="8a082-115">介绍如何在使用 GDI + 和 GDI 的矩形中绘制文本。</span><span class="sxs-lookup"><span data-stu-id="8a082-115">Explains how to draw text in a rectangle using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="8a082-116">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="8a082-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="8a082-117">演示如何使用 GDI 绘制文本。</span><span class="sxs-lookup"><span data-stu-id="8a082-117">Demonstrates how to use GDI for drawing text.</span></span>  
  
 [<span data-ttu-id="8a082-118">如何：对齐绘制的文本</span><span class="sxs-lookup"><span data-stu-id="8a082-118">How to: Align Drawn Text</span></span>](how-to-align-drawn-text.md)  
 <span data-ttu-id="8a082-119">演示如何设置 GDI + 和 GDI 文本的格式。</span><span class="sxs-lookup"><span data-stu-id="8a082-119">Shows how to format GDI+ and GDI text.</span></span>  
  
 [<span data-ttu-id="8a082-120">如何：创建垂直文本</span><span class="sxs-lookup"><span data-stu-id="8a082-120">How to: Create Vertical Text</span></span>](how-to-create-vertical-text.md)  
 <span data-ttu-id="8a082-121">描述如何绘制使用 GDI + 的垂直对齐的文本。</span><span class="sxs-lookup"><span data-stu-id="8a082-121">Describes how to draw vertically aligned text with GDI+.</span></span>  
  
 [<span data-ttu-id="8a082-122">如何：在绘制的文本中设置制表位</span><span class="sxs-lookup"><span data-stu-id="8a082-122">How to: Set Tab Stops in Drawn Text</span></span>](how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="8a082-123">显示了如何绘制使用 GDI + 选项卡停止使用的文本。</span><span class="sxs-lookup"><span data-stu-id="8a082-123">Shows how draw text with tab stops with GDI+.</span></span>  
  
 [<span data-ttu-id="8a082-124">如何：枚举已安装的字体</span><span class="sxs-lookup"><span data-stu-id="8a082-124">How to: Enumerate Installed Fonts</span></span>](how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="8a082-125">说明如何列出已安装的字体的名称。</span><span class="sxs-lookup"><span data-stu-id="8a082-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="8a082-126">如何：创建专用的字体集合</span><span class="sxs-lookup"><span data-stu-id="8a082-126">How to: Create a Private Font Collection</span></span>](how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="8a082-127">介绍如何创建<xref:System.Drawing.Text.PrivateFontCollection>对象。</span><span class="sxs-lookup"><span data-stu-id="8a082-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="8a082-128">如何：获取字体规格</span><span class="sxs-lookup"><span data-stu-id="8a082-128">How to: Obtain Font Metrics</span></span>](how-to-obtain-font-metrics.md)  
 <span data-ttu-id="8a082-129">演示如何获取字体规格如单元格上升和下降。</span><span class="sxs-lookup"><span data-stu-id="8a082-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="8a082-130">如何：对文本使用抗锯齿效果</span><span class="sxs-lookup"><span data-stu-id="8a082-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="8a082-131">说明如何绘制文本时使用抗锯齿效果。</span><span class="sxs-lookup"><span data-stu-id="8a082-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8a082-132">参考</span><span class="sxs-lookup"><span data-stu-id="8a082-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="8a082-133">介绍此类并包含指向其所有成员。</span><span class="sxs-lookup"><span data-stu-id="8a082-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="8a082-134">介绍此类并包含指向其所有成员。</span><span class="sxs-lookup"><span data-stu-id="8a082-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="8a082-135">介绍此类并包含指向其所有成员。</span><span class="sxs-lookup"><span data-stu-id="8a082-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="8a082-136">介绍此类并包含指向其所有成员。</span><span class="sxs-lookup"><span data-stu-id="8a082-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="8a082-137">介绍此类并包含指向其所有成员。</span><span class="sxs-lookup"><span data-stu-id="8a082-137">Describes this class and contains links to all of its members.</span></span>
