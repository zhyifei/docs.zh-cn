---
title: "TextElement 内容模型概述"
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
- documents [WPF], flow documents
- TextElement content model [WPF]
- flow content elements [WPF], TextElement content model
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 95d25ff6819ba913b7e9270bc2d87dd77032c5c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="textelement-content-model-overview"></a><span data-ttu-id="e7608-102">TextElement 内容模型概述</span><span class="sxs-lookup"><span data-stu-id="e7608-102">TextElement Content Model Overview</span></span>
<span data-ttu-id="e7608-103">此内容模型概述介绍支持的内容<xref:System.Windows.Documents.TextElement>。</span><span class="sxs-lookup"><span data-stu-id="e7608-103">This content model overview describes the supported content for a <xref:System.Windows.Documents.TextElement>.</span></span> <span data-ttu-id="e7608-104"><xref:System.Windows.Documents.Paragraph>类是一种<xref:System.Windows.Documents.TextElement>。</span><span class="sxs-lookup"><span data-stu-id="e7608-104">The <xref:System.Windows.Documents.Paragraph> class is a type of <xref:System.Windows.Documents.TextElement>.</span></span> <span data-ttu-id="e7608-105">内容模型描述哪些对象/元素可包含在其他对象/元素中。</span><span class="sxs-lookup"><span data-stu-id="e7608-105">A content model describes what objects/elements can be contained in others.</span></span> <span data-ttu-id="e7608-106">本概述汇总了用于派生自的对象的内容模型<xref:System.Windows.Documents.TextElement>。</span><span class="sxs-lookup"><span data-stu-id="e7608-106">This overview summarizes the content model used for objects derived from <xref:System.Windows.Documents.TextElement>.</span></span> <span data-ttu-id="e7608-107">有关详细信息，请参阅[流文档概述](../../../../docs/framework/wpf/advanced/flow-document-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e7608-107">For more information, see [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md).</span></span>  
  
  
<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a><span data-ttu-id="e7608-108">内容模型图</span><span class="sxs-lookup"><span data-stu-id="e7608-108">Content Model Diagram</span></span>  
 <span data-ttu-id="e7608-109">下图总结了内容模型，类派生自<xref:System.Windows.Documents.TextElement>以及如何其他非`TextElement`适应此模型的类。</span><span class="sxs-lookup"><span data-stu-id="e7608-109">The following diagram summarizes the content model for classes derived from <xref:System.Windows.Documents.TextElement> as well as how other non- `TextElement` classes fit into this model.</span></span>  
  
 <span data-ttu-id="e7608-110">![关系图：流内容包含架构](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow_Content_Schema")</span><span class="sxs-lookup"><span data-stu-id="e7608-110">![Diagram: Flow content containment schema](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow_Content_Schema")</span></span>  
  
 <span data-ttu-id="e7608-111">如下所示从之前的图，允许的元素的子级不一定由是否派生自该类<xref:System.Windows.Documents.Block>类或<xref:System.Windows.Documents.Inline>类。</span><span class="sxs-lookup"><span data-stu-id="e7608-111">As can be seen from the preceding diagram, the children allowed for an element are not necessarily determined by whether a class is derived from the <xref:System.Windows.Documents.Block> class or an <xref:System.Windows.Documents.Inline> class.</span></span> <span data-ttu-id="e7608-112">例如， <xref:System.Windows.Documents.Span> ( <xref:System.Windows.Documents.Inline>-派生类) 只能有<xref:System.Windows.Documents.Inline>子元素，但<xref:System.Windows.Documents.Figure>(还<xref:System.Windows.Documents.Inline>-派生类) 只能有<xref:System.Windows.Documents.Block>子元素。</span><span class="sxs-lookup"><span data-stu-id="e7608-112">For example, a <xref:System.Windows.Documents.Span> (an <xref:System.Windows.Documents.Inline>-derived class) can only have <xref:System.Windows.Documents.Inline> child elements, but a <xref:System.Windows.Documents.Figure> (also an <xref:System.Windows.Documents.Inline>-derived class) can only have <xref:System.Windows.Documents.Block> child elements.</span></span> <span data-ttu-id="e7608-113">因此，关系图可用于快速确定哪些元素可以包含在其他元素中。</span><span class="sxs-lookup"><span data-stu-id="e7608-113">Therefore, a diagram is useful for quickly determining what element can be contained in another.</span></span> <span data-ttu-id="e7608-114">例如，让我们使用关系图来确定如何构造的流内容<xref:System.Windows.Controls.RichTextBox>。</span><span class="sxs-lookup"><span data-stu-id="e7608-114">As an example, let's use the diagram to determine how to construct the flow content of a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
1.  <span data-ttu-id="e7608-115">A<xref:System.Windows.Controls.RichTextBox>必须包含<xref:System.Windows.Documents.FlowDocument>其中反过来必须包含<xref:System.Windows.Documents.Block>-派生对象。</span><span class="sxs-lookup"><span data-stu-id="e7608-115">A <xref:System.Windows.Controls.RichTextBox> must contain a <xref:System.Windows.Documents.FlowDocument> which in turn must contain a <xref:System.Windows.Documents.Block>-derived object.</span></span> <span data-ttu-id="e7608-116">以下是上述关系图中的相应部分。</span><span class="sxs-lookup"><span data-stu-id="e7608-116">The following is the corresponding segment from the preceding diagram.</span></span>  
  
     <span data-ttu-id="e7608-117">![关系图：RichTextBox 包含规则](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")</span><span class="sxs-lookup"><span data-stu-id="e7608-117">![Diagram: RichTextBox containment rules](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")</span></span>  
  
     <span data-ttu-id="e7608-118">到此为止，标记可能类似于所示内容。</span><span class="sxs-lookup"><span data-stu-id="e7608-118">Thus far, this is what the markup might look like.</span></span>  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2.  <span data-ttu-id="e7608-119">根据关系图中，有几个<xref:System.Windows.Documents.Block>元素可供选择包括<xref:System.Windows.Documents.Paragraph>， <xref:System.Windows.Documents.Section>， <xref:System.Windows.Documents.Table>， <xref:System.Windows.Documents.List>，和<xref:System.Windows.Documents.BlockUIContainer>（请参阅之前的图块派生的类）。</span><span class="sxs-lookup"><span data-stu-id="e7608-119">According to the diagram, there are several <xref:System.Windows.Documents.Block> elements to choose from including <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, and <xref:System.Windows.Documents.BlockUIContainer> (see Block-derived classes in the preceding diagram).</span></span> <span data-ttu-id="e7608-120">假设我们想<xref:System.Windows.Documents.Table>。</span><span class="sxs-lookup"><span data-stu-id="e7608-120">Let's say we want a <xref:System.Windows.Documents.Table>.</span></span> <span data-ttu-id="e7608-121">上图中，根据<xref:System.Windows.Documents.Table>包含<xref:System.Windows.Documents.TableRowGroup>包含<xref:System.Windows.Documents.TableRow>元素，其中包含<xref:System.Windows.Documents.TableCell>元素包含<xref:System.Windows.Documents.Block>-派生对象。</span><span class="sxs-lookup"><span data-stu-id="e7608-121">According to the preceding diagram, a <xref:System.Windows.Documents.Table> contains a <xref:System.Windows.Documents.TableRowGroup> containing <xref:System.Windows.Documents.TableRow> elements, which contain <xref:System.Windows.Documents.TableCell> elements which contain a <xref:System.Windows.Documents.Block>-derived object.</span></span> <span data-ttu-id="e7608-122">以下是为相应的分段<xref:System.Windows.Documents.Table>来自之前的图。</span><span class="sxs-lookup"><span data-stu-id="e7608-122">The following is the corresponding segment for <xref:System.Windows.Documents.Table> taken from the preceding diagram.</span></span>  
  
     <span data-ttu-id="e7608-123">![关系图：Table 的父/子架构](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")</span><span class="sxs-lookup"><span data-stu-id="e7608-123">![Diagram: Parent&#47;child schema for Table](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")</span></span>  
  
     <span data-ttu-id="e7608-124">下面是相应的标记。</span><span class="sxs-lookup"><span data-stu-id="e7608-124">The following is the corresponding markup.</span></span>  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3.  <span data-ttu-id="e7608-125">同样，一个或多个<xref:System.Windows.Documents.Block>下都需要所元素<xref:System.Windows.Documents.TableCell>。</span><span class="sxs-lookup"><span data-stu-id="e7608-125">Again, one or more <xref:System.Windows.Documents.Block> elements are required underneath a <xref:System.Windows.Documents.TableCell>.</span></span> <span data-ttu-id="e7608-126">为简单起见，在单元格内部放置一些文本。</span><span class="sxs-lookup"><span data-stu-id="e7608-126">To make it simple, let's place some text inside the cell.</span></span> <span data-ttu-id="e7608-127">可以执行此操作使用<xref:System.Windows.Documents.Paragraph>与<xref:System.Windows.Documents.Run>元素。</span><span class="sxs-lookup"><span data-stu-id="e7608-127">We can do this using a <xref:System.Windows.Documents.Paragraph> with a <xref:System.Windows.Documents.Run> element.</span></span> <span data-ttu-id="e7608-128">下面是从显示的关系图中的相应段<xref:System.Windows.Documents.Paragraph>可以<xref:System.Windows.Documents.Inline>元素，而<xref:System.Windows.Documents.Run>(<xref:System.Windows.Documents.Inline>元素) 只能采用纯文本。</span><span class="sxs-lookup"><span data-stu-id="e7608-128">The following is the corresponding segments from the diagram showing that a <xref:System.Windows.Documents.Paragraph> can take an <xref:System.Windows.Documents.Inline> element and that a <xref:System.Windows.Documents.Run> (an <xref:System.Windows.Documents.Inline> element) can only take plain text.</span></span>  
  
     <span data-ttu-id="e7608-129">![关系图：Paragraph 的父/子架构](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")</span><span class="sxs-lookup"><span data-stu-id="e7608-129">![Diagram: Parent&#47;child schema for Paragraph](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")</span></span>  
  
     <span data-ttu-id="e7608-130">![关系图：Run 的父/子架构](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")</span><span class="sxs-lookup"><span data-stu-id="e7608-130">![Diagram: Parent&#47;Child schema for Run](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")</span></span>  
  
 <span data-ttu-id="e7608-131">下面是标记中的完整示例。</span><span class="sxs-lookup"><span data-stu-id="e7608-131">The following is the entire example in markup.</span></span>  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a><span data-ttu-id="e7608-132">以编程方式处理 TextElement 内容</span><span class="sxs-lookup"><span data-stu-id="e7608-132">Working with TextElement Content Programmatically</span></span>  
 <span data-ttu-id="e7608-133">内容<xref:System.Windows.Documents.TextElement>组成的集合，因此以编程方式操作的内容<xref:System.Windows.Documents.TextElement>对象可通过使用这些集合。</span><span class="sxs-lookup"><span data-stu-id="e7608-133">The contents of a <xref:System.Windows.Documents.TextElement> is made up by collections and so programmatically manipulating the contents of <xref:System.Windows.Documents.TextElement> objects is done by working with these collections.</span></span> <span data-ttu-id="e7608-134">有三个不同的集合使用<xref:System.Windows.Documents.TextElement>-派生类：</span><span class="sxs-lookup"><span data-stu-id="e7608-134">There are three different collections used by <xref:System.Windows.Documents.TextElement> -derived classes:</span></span>  
  
-   <span data-ttu-id="e7608-135"><xref:System.Windows.Documents.InlineCollection>： 表示的集合<xref:System.Windows.Documents.Inline>元素。</span><span class="sxs-lookup"><span data-stu-id="e7608-135"><xref:System.Windows.Documents.InlineCollection>: Represents a collection of <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="e7608-136"><xref:System.Windows.Documents.InlineCollection>定义的允许的子内容的<xref:System.Windows.Documents.Paragraph>， <xref:System.Windows.Documents.Span>，和<xref:System.Windows.Controls.TextBlock>元素。</span><span class="sxs-lookup"><span data-stu-id="e7608-136"><xref:System.Windows.Documents.InlineCollection> defines the allowable child content of the <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span>, and <xref:System.Windows.Controls.TextBlock> elements.</span></span>  
  
-   <span data-ttu-id="e7608-137"><xref:System.Windows.Documents.BlockCollection>： 表示的集合<xref:System.Windows.Documents.Block>元素。</span><span class="sxs-lookup"><span data-stu-id="e7608-137"><xref:System.Windows.Documents.BlockCollection>: Represents a collection of <xref:System.Windows.Documents.Block> elements.</span></span> <span data-ttu-id="e7608-138"><xref:System.Windows.Documents.BlockCollection> 定义 <xref:System.Windows.Documents.FlowDocument>、<xref:System.Windows.Documents.Section>、<xref:System.Windows.Documents.ListItem>、<xref:System.Windows.Documents.TableCell>、<xref:System.Windows.Documents.Floater> 和 <xref:System.Windows.Documents.Figure> 元素允许的子内容。</span><span class="sxs-lookup"><span data-stu-id="e7608-138"><xref:System.Windows.Documents.BlockCollection> defines the allowable child content of the <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater>, and <xref:System.Windows.Documents.Figure> elements.</span></span>  
  
-   <span data-ttu-id="e7608-139"><xref:System.Windows.Documents.ListItemCollection>： 表示排序中的特定内容项的流内容元素或无序<xref:System.Windows.Documents.List>。</span><span class="sxs-lookup"><span data-stu-id="e7608-139"><xref:System.Windows.Documents.ListItemCollection>: A flow content element that represents a particular content item in an ordered or unordered <xref:System.Windows.Documents.List>.</span></span>  
  
 <span data-ttu-id="e7608-140">你可以操作 （添加或删除项） 从这些集合使用的相应属性**内联**，**块**，和**ListItems**。</span><span class="sxs-lookup"><span data-stu-id="e7608-140">You can manipulate (add or remove items) from these collections using the respective properties of **Inlines**, **Blocks**, and **ListItems**.</span></span> <span data-ttu-id="e7608-141">下面的示例演示如何操作的范围使用的内容**内联**属性。</span><span class="sxs-lookup"><span data-stu-id="e7608-141">The following examples show how to manipulate the contents of a Span using the **Inlines** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7608-142">表格使用多个集合来操作其内容，但这里不对其进行说明。</span><span class="sxs-lookup"><span data-stu-id="e7608-142">Table uses several collections to manipulate its contents, but they are not covered here.</span></span> <span data-ttu-id="e7608-143">有关详细信息，请参阅[表概述](../../../../docs/framework/wpf/advanced/table-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e7608-143">For more information, see [Table Overview](../../../../docs/framework/wpf/advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="e7608-144">下面的示例创建一个新<xref:System.Windows.Documents.Span>对象，然后使用`Add`方法添加两个文本运行，作为内容的子级<xref:System.Windows.Documents.Span>。</span><span class="sxs-lookup"><span data-stu-id="e7608-144">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the `Add` method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 <span data-ttu-id="e7608-145">下面的示例创建一个新<xref:System.Windows.Documents.Run>元素并将其插入的开始处<xref:System.Windows.Documents.Span>。</span><span class="sxs-lookup"><span data-stu-id="e7608-145">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 <span data-ttu-id="e7608-146">以下示例将删除最后一个<xref:System.Windows.Documents.Inline>中的元素<xref:System.Windows.Documents.Span>。</span><span class="sxs-lookup"><span data-stu-id="e7608-146">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 <span data-ttu-id="e7608-147">下面的示例清除的所有内容 (<xref:System.Windows.Documents.Inline>元素) 从<xref:System.Windows.Documents.Span>。</span><span class="sxs-lookup"><span data-stu-id="e7608-147">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a><span data-ttu-id="e7608-148">共享此内容模型的类型</span><span class="sxs-lookup"><span data-stu-id="e7608-148">Types That Share This Content Model</span></span>  
 <span data-ttu-id="e7608-149">以下类型都继承自<xref:System.Windows.Documents.TextElement>类，并可能用来显示此概述中所述的内容。</span><span class="sxs-lookup"><span data-stu-id="e7608-149">The following types inherit from the <xref:System.Windows.Documents.TextElement> class and may be used to display the content described in this overview.</span></span>  
  
 <span data-ttu-id="e7608-150"><xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.</span><span class="sxs-lookup"><span data-stu-id="e7608-150"><xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.</span></span>  
  
 <span data-ttu-id="e7608-151">请注意，此列表仅包含与一起发行的非抽象类型[!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e7608-151">Note that this list only includes nonabstract types distributed with the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="e7608-152">你可能使用继承自其他类型<xref:System.Windows.Documents.TextElement>。</span><span class="sxs-lookup"><span data-stu-id="e7608-152">You may use other types that inherit from <xref:System.Windows.Documents.TextElement>.</span></span>  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a><span data-ttu-id="e7608-153">可包含 TextElement 对象的类型</span><span class="sxs-lookup"><span data-stu-id="e7608-153">Types That Can Contain TextElement Objects</span></span>  
 <span data-ttu-id="e7608-154">请参阅[WPF 内容模型](../../../../docs/framework/wpf/controls/wpf-content-model.md)。</span><span class="sxs-lookup"><span data-stu-id="e7608-154">See [WPF Content Model](../../../../docs/framework/wpf/controls/wpf-content-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7608-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7608-155">See Also</span></span>  
 [<span data-ttu-id="e7608-156">通过 Blocks 属性控制 FlowDocument</span><span class="sxs-lookup"><span data-stu-id="e7608-156">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="e7608-157">通过 Blocks 属性控制流内容元素</span><span class="sxs-lookup"><span data-stu-id="e7608-157">Manipulate Flow Content Elements through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-flow-content-elements-through-the-blocks-property.md)  
 [<span data-ttu-id="e7608-158">通过 Blocks 属性控制 FlowDocument</span><span class="sxs-lookup"><span data-stu-id="e7608-158">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="e7608-159">通过 Columns 属性控制表列</span><span class="sxs-lookup"><span data-stu-id="e7608-159">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="e7608-160">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="e7608-160">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
