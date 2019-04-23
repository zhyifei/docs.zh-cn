---
title: 如何：创建空心文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: 237bdc097cd2a3fbfff6dd79bce401c2d091e211
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162223"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="37976-102">如何：创建空心文本</span><span class="sxs-lookup"><span data-stu-id="37976-102">How to: Create Outlined Text</span></span>
<span data-ttu-id="37976-103">在大多数情况下，当要将装饰添加到中的文本字符串时您[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序中，使用的根据一系列离散的字符或字形的文本。</span><span class="sxs-lookup"><span data-stu-id="37976-103">In most cases, when you are adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="37976-104">例如，您可以创建线性渐变画笔，并将其应用于<xref:System.Windows.Controls.Control.Foreground%2A>属性的<xref:System.Windows.Controls.TextBox>对象。</span><span class="sxs-lookup"><span data-stu-id="37976-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="37976-105">当显示或编辑文本框中时，线性渐变画笔是自动应用于当前集的文本字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="37976-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![使用线性渐变画笔显示的文本](./media/how-to-create-outlined-text/text-linear-gradient.jpg)    
  
 <span data-ttu-id="37976-107">但是，您还可以将转换到的文本<xref:System.Windows.Media.Geometry>对象，它允许您创建其他类型的可视化多格式文本。</span><span class="sxs-lookup"><span data-stu-id="37976-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="37976-108">例如，可以创建<xref:System.Windows.Media.Geometry>基于对象的轮廓上的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="37976-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![使用线性渐变画笔的文本轮廓](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="37976-110">当文本转换为<xref:System.Windows.Media.Geometry>对象，它不再是一系列字符，不能修改文本字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="37976-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="37976-111">但是，可修改已转换文本的笔划和填充属性，以此来影响该文本的外观。</span><span class="sxs-lookup"><span data-stu-id="37976-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="37976-112">笔划是指已转换文本的轮廓；填充是指已转换文本的轮廓的内部区域。</span><span class="sxs-lookup"><span data-stu-id="37976-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="37976-113">下面的示例演示了多种方法可以通过修改的笔划和填充的已转换的文本来创建视觉效果。</span><span class="sxs-lookup"><span data-stu-id="37976-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![对填充和笔画使用不同颜色的文本](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![笔画应用了图像画笔的文本](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="37976-116">还有可能要修改的边界框矩形或突出显示，已转换的文本。</span><span class="sxs-lookup"><span data-stu-id="37976-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="37976-117">下面的示例演示通过修改笔划和突出显示的已转换的文本的一种方法来创建视觉效果。</span><span class="sxs-lookup"><span data-stu-id="37976-117">The following example illustrates a way to creating visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![应用绘制笔画，并突出显示了图像画笔的文本](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="37976-119">示例</span><span class="sxs-lookup"><span data-stu-id="37976-119">Example</span></span>  
 <span data-ttu-id="37976-120">将文本转换为密钥<xref:System.Windows.Media.Geometry>对象是使用<xref:System.Windows.Media.FormattedText>对象。</span><span class="sxs-lookup"><span data-stu-id="37976-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="37976-121">创建此对象后，可以使用<xref:System.Windows.Media.FormattedText.BuildGeometry%2A>并<xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A>方法将转换为文本<xref:System.Windows.Media.Geometry>对象。</span><span class="sxs-lookup"><span data-stu-id="37976-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="37976-122">第一种方法将返回带格式的文本; 的几何图形第二种方法返回带格式的文本的几何图形的边界框。</span><span class="sxs-lookup"><span data-stu-id="37976-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="37976-123">下面的代码示例演示如何创建<xref:System.Windows.Media.FormattedText>对象以及如何检索几何图形的带格式的文本和其边界框。</span><span class="sxs-lookup"><span data-stu-id="37976-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="37976-124">要显示检索<xref:System.Windows.Media.Geometry>对象，您需要访问<xref:System.Windows.Media.DrawingContext>显示已转换的文本的对象。</span><span class="sxs-lookup"><span data-stu-id="37976-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that is displaying the converted text.</span></span> <span data-ttu-id="37976-125">在这些代码示例中，这可通过创建从支持用户定义的呈现的类派生的自定义控件对象。</span><span class="sxs-lookup"><span data-stu-id="37976-125">In these code examples, this is done by creating a custom control object that is derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="37976-126">若要显示<xref:System.Windows.Media.Geometry>自定义控件中的对象提供的替代<xref:System.Windows.UIElement.OnRender%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="37976-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="37976-127">重写的方法应使用<xref:System.Windows.Media.DrawingContext.DrawGeometry%2A>方法，以便绘制<xref:System.Windows.Media.Geometry>对象。</span><span class="sxs-lookup"><span data-stu-id="37976-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="37976-128">示例自定义用户控件对象的源，请参阅[OutlineTextControl.cs 为C#](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs)并[OutlineTextControl.vb 适用于 Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb)。</span><span class="sxs-lookup"><span data-stu-id="37976-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="37976-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="37976-129">See also</span></span>

- [<span data-ttu-id="37976-130">绘制格式化文本</span><span class="sxs-lookup"><span data-stu-id="37976-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
