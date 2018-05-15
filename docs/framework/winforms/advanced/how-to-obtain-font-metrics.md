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
ms.openlocfilehash: 3cc5ee303efe6c703a61eef6c7448979b487f6bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="5ea2e-102">如何：获取字体规格</span><span class="sxs-lookup"><span data-stu-id="5ea2e-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="5ea2e-103"><xref:System.Drawing.FontFamily>类提供下列方法来检索特定的系列样式组合的各种指标：</span><span class="sxs-lookup"><span data-stu-id="5ea2e-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
-   <span data-ttu-id="5ea2e-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>（要）</span><span class="sxs-lookup"><span data-stu-id="5ea2e-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="5ea2e-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>（要）</span><span class="sxs-lookup"><span data-stu-id="5ea2e-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="5ea2e-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>（要）</span><span class="sxs-lookup"><span data-stu-id="5ea2e-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="5ea2e-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>（要）</span><span class="sxs-lookup"><span data-stu-id="5ea2e-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="5ea2e-108">由这些方法返回的数字是采用字体设计单位，因此它们是独立的大小和单位特定于<xref:System.Drawing.Font>对象。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-108">The numbers returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="5ea2e-109">下图显示的各种度量值。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-109">The following illustration shows the various metrics.</span></span>  
  
 <span data-ttu-id="5ea2e-110">![字体文本](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")</span><span class="sxs-lookup"><span data-stu-id="5ea2e-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ea2e-111">示例</span><span class="sxs-lookup"><span data-stu-id="5ea2e-111">Example</span></span>  
 <span data-ttu-id="5ea2e-112">下面的示例显示 Arial 字体系列的正则样式的度量值。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="5ea2e-113">该代码还创建<xref:System.Drawing.Font>具有大小为 16 像素和显示的度量值 （以像素为单位） 对该特定对象 （基于 Arial 系列）<xref:System.Drawing.Font>对象。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="5ea2e-114">下图显示示例代码的输出。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-114">The following illustration shows the output of the example code.</span></span>  
  
 <span data-ttu-id="5ea2e-115">![字体文本](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")</span><span class="sxs-lookup"><span data-stu-id="5ea2e-115">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")</span></span>  
  
 <span data-ttu-id="5ea2e-116">请注意在上图中的前两个行。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="5ea2e-117"><xref:System.Drawing.Font>对象返回的大小为 16，和<xref:System.Drawing.FontFamily>对象返回的 em 高度为 2048。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="5ea2e-118">这两个数字 （16 和 2048） 是字体设计单位和单位 （在本例中为像素） 之间进行转换的关键<xref:System.Drawing.Font>对象。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="5ea2e-119">例如，你可以将转换上升从设计单位为像素，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ea2e-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 <span data-ttu-id="5ea2e-120">![字体文本](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")</span><span class="sxs-lookup"><span data-stu-id="5ea2e-120">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")</span></span>  
  
 <span data-ttu-id="5ea2e-121">下面的代码放置文本垂直通过设置<xref:System.Drawing.PointF.Y%2A>数据成员的<xref:System.Drawing.PointF>对象。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="5ea2e-122">通过增加 y 坐标`font.Height`每个新行的文本。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="5ea2e-123"><xref:System.Drawing.Font.Height%2A>属性<xref:System.Drawing.Font>对象返回的行间距 （以像素为单位） 对该特定<xref:System.Drawing.Font>对象。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="5ea2e-124">在此示例中，数由<xref:System.Drawing.Font.Height%2A>为 19。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="5ea2e-125">请注意，这是通过将行间距度量值转换为像素得到数字 （向上舍入为整数） 相同。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="5ea2e-126">请注意，全身高度 （也称为大小或 em 大小） 不是上升和下降的总和。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="5ea2e-127">上升和下降的总和称为单元格的高度。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="5ea2e-128">减去内部间隙的单元格高度等于全身高度。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="5ea2e-129">单元格高度加外部间隙等于行间距。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5ea2e-130">编译代码</span><span class="sxs-lookup"><span data-stu-id="5ea2e-130">Compiling the Code</span></span>  
 <span data-ttu-id="5ea2e-131">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。</span><span class="sxs-lookup"><span data-stu-id="5ea2e-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ea2e-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ea2e-132">See Also</span></span>  
 [<span data-ttu-id="5ea2e-133">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="5ea2e-133">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="5ea2e-134">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="5ea2e-134">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
