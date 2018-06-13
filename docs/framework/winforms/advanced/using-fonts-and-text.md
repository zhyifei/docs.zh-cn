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
ms.openlocfilehash: d157b51e24009d847dede9ea6a9f81c8898c5b06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526258"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="c38d5-102">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="c38d5-102">Using Fonts and Text</span></span>
<span data-ttu-id="c38d5-103">有几个类提供[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]和[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]为 Windows 窗体上绘制文本。</span><span class="sxs-lookup"><span data-stu-id="c38d5-103">There are several classes offered by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text on Windows Forms.</span></span> <span data-ttu-id="c38d5-104">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics>类具有多个<xref:System.Drawing.Graphics.DrawString%2A>允许你指定的文本，例如位置，边界矩形、 字体和格式的各种功能的方法。</span><span class="sxs-lookup"><span data-stu-id="c38d5-104">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="c38d5-105">此外，你可以绘制和度量值具有文本[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]使用静态<xref:System.Windows.Forms.TextRenderer.DrawText%2A>和<xref:System.Windows.Forms.TextRenderer.MeasureText%2A>方法提供的`TextRenderer`类。</span><span class="sxs-lookup"><span data-stu-id="c38d5-105">In addition, you can draw and measure text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="c38d5-106">[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]方法还允许你指定位置、 字体和格式。</span><span class="sxs-lookup"><span data-stu-id="c38d5-106">The [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="c38d5-107">你可以任选一个[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]或[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]文本呈现; 但是，[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]通常提供更好的性能和更准确的文本测量。</span><span class="sxs-lookup"><span data-stu-id="c38d5-107">You can choose either [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] or [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] for text rendering; however, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="c38d5-108">导致文本呈现的其他类包括`FontFamily`， `Font`， <xref:System.Drawing.StringFormat>，和`TextFormatFlags`。</span><span class="sxs-lookup"><span data-stu-id="c38d5-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c38d5-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="c38d5-109">In This Section</span></span>  
 [<span data-ttu-id="c38d5-110">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="c38d5-110">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="c38d5-111">演示如何创建`Font`和`FontFamily`对象。</span><span class="sxs-lookup"><span data-stu-id="c38d5-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="c38d5-112">如何：在指定位置绘制文本</span><span class="sxs-lookup"><span data-stu-id="c38d5-112">How to: Draw Text at a Specified Location</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="c38d5-113">描述如何绘制中某些位置使用文本[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]和[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c38d5-113">Describes how to draw text in a certain location using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="c38d5-114">如何：在矩形中绘制换行文本</span><span class="sxs-lookup"><span data-stu-id="c38d5-114">How to: Draw Wrapped Text in a Rectangle</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="c38d5-115">说明如何绘制在矩形中使用的文本[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]和[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c38d5-115">Explains how to draw text in a rectangle using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="c38d5-116">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="c38d5-116">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="c38d5-117">演示如何使用[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]中绘制文本。</span><span class="sxs-lookup"><span data-stu-id="c38d5-117">Demonstrates how to use [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text.</span></span>  
  
 [<span data-ttu-id="c38d5-118">如何：对齐绘制的文本</span><span class="sxs-lookup"><span data-stu-id="c38d5-118">How to: Align Drawn Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 <span data-ttu-id="c38d5-119">演示如何设置格式[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]和[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]文本。</span><span class="sxs-lookup"><span data-stu-id="c38d5-119">Shows how to format [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] text.</span></span>  
  
 [<span data-ttu-id="c38d5-120">如何：创建竖排文本</span><span class="sxs-lookup"><span data-stu-id="c38d5-120">How to: Create Vertical Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 <span data-ttu-id="c38d5-121">描述如何绘制垂直对齐的文本[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c38d5-121">Describes how to draw vertically aligned text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="c38d5-122">如何：在绘制的文本中设置制表位</span><span class="sxs-lookup"><span data-stu-id="c38d5-122">How to: Set Tab Stops in Drawn Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="c38d5-123">演示如何绘制文本使用制表位与[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c38d5-123">Shows how draw text with tab stops with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="c38d5-124">如何：枚举已安装的字体</span><span class="sxs-lookup"><span data-stu-id="c38d5-124">How to: Enumerate Installed Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="c38d5-125">说明如何列出已安装的字体的名称。</span><span class="sxs-lookup"><span data-stu-id="c38d5-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="c38d5-126">如何：创建专用的字体集合</span><span class="sxs-lookup"><span data-stu-id="c38d5-126">How to: Create a Private Font Collection</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="c38d5-127">描述如何创建<xref:System.Drawing.Text.PrivateFontCollection>对象。</span><span class="sxs-lookup"><span data-stu-id="c38d5-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="c38d5-128">如何：获取字体规格</span><span class="sxs-lookup"><span data-stu-id="c38d5-128">How to: Obtain Font Metrics</span></span>](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 <span data-ttu-id="c38d5-129">演示如何获取单元格上升等下降的字体指标。</span><span class="sxs-lookup"><span data-stu-id="c38d5-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="c38d5-130">如何：对文本使用抗锯齿效果</span><span class="sxs-lookup"><span data-stu-id="c38d5-130">How to: Use Antialiasing with Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="c38d5-131">说明如何时绘制文本使用抗锯齿效果。</span><span class="sxs-lookup"><span data-stu-id="c38d5-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c38d5-132">参考</span><span class="sxs-lookup"><span data-stu-id="c38d5-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="c38d5-133">对此类进行描述，并包含其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="c38d5-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="c38d5-134">对此类进行描述，并包含其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="c38d5-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="c38d5-135">对此类进行描述，并包含其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="c38d5-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="c38d5-136">对此类进行描述，并包含其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="c38d5-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="c38d5-137">对此类进行描述，并包含其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="c38d5-137">Describes this class and contains links to all of its members.</span></span>
