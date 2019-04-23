---
title: 如何：获取字体规格
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 24cada3962339cae0608bbe01e070a0b8e256e73
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119049"
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="e8999-102">如何：获取字体规格</span><span class="sxs-lookup"><span data-stu-id="e8999-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="e8999-103"><xref:System.Drawing.FontFamily>类提供了检索特定系列/样式组合的各种度量值的以下方法：</span><span class="sxs-lookup"><span data-stu-id="e8999-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
-   <span data-ttu-id="e8999-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="e8999-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="e8999-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="e8999-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="e8999-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="e8999-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="e8999-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="e8999-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="e8999-108">这些方法返回的数字都是采用字体设计单位，因此它们将独立的大小和单位的特定于<xref:System.Drawing.Font>对象。</span><span class="sxs-lookup"><span data-stu-id="e8999-108">The numbers returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="e8999-109">下图显示了各种指标。</span><span class="sxs-lookup"><span data-stu-id="e8999-109">The following illustration shows the various metrics.</span></span>  
  
 <span data-ttu-id="e8999-110">![字体文本](./media/fontstext7a.png "fontstext7A")</span><span class="sxs-lookup"><span data-stu-id="e8999-110">![Fonts Text](./media/fontstext7a.png "fontstext7A")</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8999-111">示例</span><span class="sxs-lookup"><span data-stu-id="e8999-111">Example</span></span>  
 <span data-ttu-id="e8999-112">以下示例显示 Arial 字体系列的正则样式的度量值。</span><span class="sxs-lookup"><span data-stu-id="e8999-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="e8999-113">该代码还创建<xref:System.Drawing.Font>具有大小为 16 像素和显示的度量值 （以像素为单位） 对该特定对象 （基于 Arial 系列）<xref:System.Drawing.Font>对象。</span><span class="sxs-lookup"><span data-stu-id="e8999-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="e8999-114">下图显示了示例代码的输出。</span><span class="sxs-lookup"><span data-stu-id="e8999-114">The following illustration shows the output of the example code.</span></span>  
  
 <span data-ttu-id="e8999-115">![字体文本](./media/csfontstext8.png "csFontsText8")</span><span class="sxs-lookup"><span data-stu-id="e8999-115">![Fonts Text](./media/csfontstext8.png "csFontsText8")</span></span>  
  
 <span data-ttu-id="e8999-116">请注意上图中的输出的前两行。</span><span class="sxs-lookup"><span data-stu-id="e8999-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="e8999-117"><xref:System.Drawing.Font>对象返回的大小为 16，和<xref:System.Drawing.FontFamily>对象返回 2,048 全身高度。</span><span class="sxs-lookup"><span data-stu-id="e8999-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="e8999-118">这两个数字 （16 和 2,048） 是字体设计单位和的单位 （在本例中为像素） 之间进行转换的关键<xref:System.Drawing.Font>对象。</span><span class="sxs-lookup"><span data-stu-id="e8999-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="e8999-119">例如，您可以将转换上移量从设计单位为像素，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8999-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 <span data-ttu-id="e8999-120">![字体文本](./media/fontstext9.png "FontsText9")</span><span class="sxs-lookup"><span data-stu-id="e8999-120">![Fonts Text](./media/fontstext9.png "FontsText9")</span></span>  
  
 <span data-ttu-id="e8999-121">下面的代码定位文本垂直通过设置<xref:System.Drawing.PointF.Y%2A>的数据成员<xref:System.Drawing.PointF>对象。</span><span class="sxs-lookup"><span data-stu-id="e8999-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="e8999-122">Y 坐标为增量进行递增`font.Height`的每一行新文本。</span><span class="sxs-lookup"><span data-stu-id="e8999-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="e8999-123"><xref:System.Drawing.Font.Height%2A>的属性<xref:System.Drawing.Font>对象返回的行间距 （以像素为单位） 对该特定<xref:System.Drawing.Font>对象。</span><span class="sxs-lookup"><span data-stu-id="e8999-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="e8999-124">在此示例中，返回的号<xref:System.Drawing.Font.Height%2A>为 19。</span><span class="sxs-lookup"><span data-stu-id="e8999-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="e8999-125">请注意，这是通过将行间距度量值转换为像素中获取的编号 （向上舍入为整数） 相同。</span><span class="sxs-lookup"><span data-stu-id="e8999-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="e8999-126">请注意，全身高度 （也称为大小或 em 大小） 不是上升和下降的总和。</span><span class="sxs-lookup"><span data-stu-id="e8999-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="e8999-127">上升和下降的总和被调用单元格的高度。</span><span class="sxs-lookup"><span data-stu-id="e8999-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="e8999-128">单元格的高度减去内部间隙等于全身高度。</span><span class="sxs-lookup"><span data-stu-id="e8999-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="e8999-129">单元格高度加外部间隙等于行间距。</span><span class="sxs-lookup"><span data-stu-id="e8999-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e8999-130">编译代码</span><span class="sxs-lookup"><span data-stu-id="e8999-130">Compiling the Code</span></span>  
 <span data-ttu-id="e8999-131">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="e8999-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8999-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8999-132">See also</span></span>

- [<span data-ttu-id="e8999-133">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="e8999-133">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="e8999-134">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="e8999-134">Using Fonts and Text</span></span>](using-fonts-and-text.md)
