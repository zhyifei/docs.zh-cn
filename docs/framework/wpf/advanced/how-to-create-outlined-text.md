---
title: 如何：创建空心文字
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
ms.openlocfilehash: 86bfa396a2aa44eb511c014687501d60e170a396
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278920"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="431a8-102">如何：创建大纲文本</span><span class="sxs-lookup"><span data-stu-id="431a8-102">How to: Create outlined text</span></span>

<span data-ttu-id="431a8-103">在大多数情况下，当您在[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序中向文本字符串添加修饰时，您将使用文本作为离散字符或字形的集合。</span><span class="sxs-lookup"><span data-stu-id="431a8-103">In most cases, when you're adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="431a8-104">例如，您可以创建线性渐变画笔并将其应用于<xref:System.Windows.Controls.Control.Foreground%2A><xref:System.Windows.Controls.TextBox>对象的属性。</span><span class="sxs-lookup"><span data-stu-id="431a8-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="431a8-105">显示或编辑文本框时，线性渐变画笔将自动应用于文本字符串中的当前字符集。</span><span class="sxs-lookup"><span data-stu-id="431a8-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![使用线性渐变画笔显示的文本](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 <span data-ttu-id="431a8-107">但是，您还可以将文本转换为<xref:System.Windows.Media.Geometry>对象，从而创建其他类型的视觉丰富的文本。</span><span class="sxs-lookup"><span data-stu-id="431a8-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="431a8-108">例如，可以基于文本字符串的<xref:System.Windows.Media.Geometry>轮廓创建对象。</span><span class="sxs-lookup"><span data-stu-id="431a8-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![使用线性渐变画笔的文本轮廓](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="431a8-110">将文本转换为对象时<xref:System.Windows.Media.Geometry>，它不再是字符的集合，无法修改文本字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="431a8-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="431a8-111">但是，可修改已转换文本的笔划和填充属性，以此来影响该文本的外观。</span><span class="sxs-lookup"><span data-stu-id="431a8-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="431a8-112">笔划是指已转换文本的轮廓；填充是指已转换文本的轮廓的内部区域。</span><span class="sxs-lookup"><span data-stu-id="431a8-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="431a8-113">以下示例说明了通过修改描边和填充转换文本来创建视觉效果的几种方法。</span><span class="sxs-lookup"><span data-stu-id="431a8-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![对填充和笔画使用不同颜色的文本](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![笔画应用了图像画笔的文本](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="431a8-116">还可以修改转换文本的边界框矩形或高光。</span><span class="sxs-lookup"><span data-stu-id="431a8-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="431a8-117">下面的示例说明了通过修改转换文本的描边和高光来创建视觉效果的方法。</span><span class="sxs-lookup"><span data-stu-id="431a8-117">The following example illustrates a way to create visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![应用图像画笔进行描边和高光的文本](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="431a8-119">示例</span><span class="sxs-lookup"><span data-stu-id="431a8-119">Example</span></span>  
 <span data-ttu-id="431a8-120">将文本转换为<xref:System.Windows.Media.Geometry>对象的键是使用该<xref:System.Windows.Media.FormattedText>对象。</span><span class="sxs-lookup"><span data-stu-id="431a8-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="431a8-121">创建此对象后，可以使用<xref:System.Windows.Media.FormattedText.BuildGeometry%2A>和<xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A>方法将文本转换为<xref:System.Windows.Media.Geometry>对象。</span><span class="sxs-lookup"><span data-stu-id="431a8-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="431a8-122">第一种方法返回格式化文本的几何体;第二种方法返回格式化文本的边界框的几何体。</span><span class="sxs-lookup"><span data-stu-id="431a8-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="431a8-123">以下代码示例演示如何创建<xref:System.Windows.Media.FormattedText>对象并检索格式化文本及其边界框的几何体。</span><span class="sxs-lookup"><span data-stu-id="431a8-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="431a8-124">为了显示检索到<xref:System.Windows.Media.Geometry>的对象，您需要访问<xref:System.Windows.Media.DrawingContext>显示转换文本的对象。</span><span class="sxs-lookup"><span data-stu-id="431a8-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that's displaying the converted text.</span></span> <span data-ttu-id="431a8-125">在这些代码示例中，通过创建从支持用户定义的呈现的类派生的自定义控件对象来实现此访问。</span><span class="sxs-lookup"><span data-stu-id="431a8-125">In these code examples, this access is achieved by creating a custom control object that's derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="431a8-126">要在<xref:System.Windows.Media.Geometry>自定义控件中显示对象，请为<xref:System.Windows.UIElement.OnRender%2A>方法提供重写。</span><span class="sxs-lookup"><span data-stu-id="431a8-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="431a8-127">重写的方法应使用 方法<xref:System.Windows.Media.DrawingContext.DrawGeometry%2A>绘制<xref:System.Windows.Media.Geometry>对象。</span><span class="sxs-lookup"><span data-stu-id="431a8-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="431a8-128">有关示例自定义用户控件对象的源，请参阅[C# 和](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs)[大纲文本控制.vb 的 OutlineTextControl.cs。](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb)</span><span class="sxs-lookup"><span data-stu-id="431a8-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="431a8-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="431a8-129">See also</span></span>

- [<span data-ttu-id="431a8-130">绘制格式化文本</span><span class="sxs-lookup"><span data-stu-id="431a8-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
