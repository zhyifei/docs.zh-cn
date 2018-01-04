---
title: "如何：创建空心文字"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41254d8f93174c896923b1c070e6bf9b5b7c863c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="3e4a8-102">如何：创建空心文字</span><span class="sxs-lookup"><span data-stu-id="3e4a8-102">How to: Create Outlined Text</span></span>
<span data-ttu-id="3e4a8-103">在大多数情况下，在对中的文本字符串添加装饰时你[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序中，使用离散字符或标志符号的集合形式的文本。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-103">In most cases, when you are adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="3e4a8-104">例如，你可以创建线性渐变画笔，并将其应用于<xref:System.Windows.Controls.Control.Foreground%2A>属性<xref:System.Windows.Controls.TextBox>对象。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="3e4a8-105">当你显示或编辑文本框中时，线性渐变画笔自动应用于当前集文本字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 <span data-ttu-id="3e4a8-106">![使用线性渐变画笔显示的文本](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")</span><span class="sxs-lookup"><span data-stu-id="3e4a8-106">![Text displayed with a linear gradient brush](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")</span></span>  
<span data-ttu-id="3e4a8-107">线性渐变画笔应用到的文本框中的示例</span><span class="sxs-lookup"><span data-stu-id="3e4a8-107">Example of a linear gradient brush applied to a text box</span></span>  
  
 <span data-ttu-id="3e4a8-108">但是，你还可以将转换到的文本<xref:System.Windows.Media.Geometry>对象，使你可以创建其他类型的可视化多格式文本。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-108">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="3e4a8-109">例如，你可以创建<xref:System.Windows.Media.Geometry>对象基于轮廓的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-109">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 <span data-ttu-id="3e4a8-110">![使用线性渐变画笔的文本轮廓](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")</span><span class="sxs-lookup"><span data-stu-id="3e4a8-110">![Text outline using a linear gradient brush](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")</span></span>  
<span data-ttu-id="3e4a8-111">线性渐变画笔应用于文本的大纲几何图形的示例</span><span class="sxs-lookup"><span data-stu-id="3e4a8-111">Example of a linear gradient brush applied to the outline geometry of text</span></span>  
  
 <span data-ttu-id="3e4a8-112">当文本转换为<xref:System.Windows.Media.Geometry>对象，它不再是字符的集合，无法修改的文本字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-112">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="3e4a8-113">但是，可修改已转换文本的笔划和填充属性，以此来影响该文本的外观。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-113">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="3e4a8-114">笔划是指已转换文本的轮廓；填充是指已转换文本的轮廓的内部区域。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-114">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="3e4a8-115">下面的示例说明了多种方法可以通过修改的笔画和填充的已转换的文本来创建视觉效果。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-115">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 <span data-ttu-id="3e4a8-116">![对填充和笔画使用不同颜色的文本](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")</span><span class="sxs-lookup"><span data-stu-id="3e4a8-116">![Text with different colors for fill and stroke](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")</span></span>  
<span data-ttu-id="3e4a8-117">将笔划和填充设置为不同颜色的示例</span><span class="sxs-lookup"><span data-stu-id="3e4a8-117">Example of setting stroke and fill to different colors</span></span>  
  
 <span data-ttu-id="3e4a8-118">![笔画应用了图像画笔的文本](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")</span><span class="sxs-lookup"><span data-stu-id="3e4a8-118">![Text with image brush applied to stroke](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")</span></span>  
<span data-ttu-id="3e4a8-119">笔划应用了图像画笔的示例</span><span class="sxs-lookup"><span data-stu-id="3e4a8-119">Example of an image brush applied to the stroke</span></span>  
  
 <span data-ttu-id="3e4a8-120">还有可能要修改的边界框矩形或突出显示，已转换的文本。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-120">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="3e4a8-121">下面的示例演示通过修改笔划和突出显示的已转换的文本来创建视觉效果的方法。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-121">The following example illustrates a way to creating visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 <span data-ttu-id="3e4a8-122">![笔画应用了图像画笔的文本](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")</span><span class="sxs-lookup"><span data-stu-id="3e4a8-122">![Text with image brush applied to stroke](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")</span></span>  
<span data-ttu-id="3e4a8-123">笔划和突出显示应用了图像画笔的示例</span><span class="sxs-lookup"><span data-stu-id="3e4a8-123">Example of an image brush applied to the stroke and highlight</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e4a8-124">示例</span><span class="sxs-lookup"><span data-stu-id="3e4a8-124">Example</span></span>  
 <span data-ttu-id="3e4a8-125">将文本转换为密钥<xref:System.Windows.Media.Geometry>对象是使用<xref:System.Windows.Media.FormattedText>对象。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-125">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="3e4a8-126">一旦你已创建此对象，就可以使用<xref:System.Windows.Media.FormattedText.BuildGeometry%2A>和<xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A>方法来将文本转换为<xref:System.Windows.Media.Geometry>对象。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-126">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="3e4a8-127">第一种方法返回的几何图形的带格式的文本;第二种方法返回的几何图形的带格式的文本的边界框。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-127">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="3e4a8-128">下面的代码示例演示如何创建<xref:System.Windows.Media.FormattedText>对象并检索带格式的文本和其边界框的几何图形。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-128">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="3e4a8-129">为了显示检索<xref:System.Windows.Media.Geometry>你需要访问的对象<xref:System.Windows.Media.DrawingContext>显示转换后的文本的对象。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-129">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that is displaying the converted text.</span></span> <span data-ttu-id="3e4a8-130">在这些代码示例，这可通过创建从支持用户定义的呈现的类派生的自定义控件对象。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-130">In these code examples, this is done by creating a custom control object that is derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="3e4a8-131">若要显示<xref:System.Windows.Media.Geometry>在自定义控件中，对象提供的替代<xref:System.Windows.UIElement.OnRender%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-131">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="3e4a8-132">重写的方法应使用<xref:System.Windows.Media.DrawingContext.DrawGeometry%2A>方法，以便绘制<xref:System.Windows.Media.Geometry>对象。</span><span class="sxs-lookup"><span data-stu-id="3e4a8-132">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## <a name="see-also"></a><span data-ttu-id="3e4a8-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e4a8-133">See Also</span></span>  
 [<span data-ttu-id="3e4a8-134">绘制格式化文本</span><span class="sxs-lookup"><span data-stu-id="3e4a8-134">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
