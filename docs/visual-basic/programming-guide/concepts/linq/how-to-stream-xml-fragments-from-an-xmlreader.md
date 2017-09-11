---
title: "如何︰ 从 XmlReader (Visual Basic 中) 的 XML 片段进行流式处理 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c9c60bb4730ef6569390f76f63c40a2cbd1c9524
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a><span data-ttu-id="a1f0e-102">如何︰ 从 XmlReader (Visual Basic 中) 的 XML 片段进行流式处理</span><span class="sxs-lookup"><span data-stu-id="a1f0e-102">How to: Stream XML Fragments from an XmlReader (Visual Basic)</span></span>
<span data-ttu-id="a1f0e-103">如果必须处理很大的 XML 文件，将整个 XML 树加载到内存可能不可行。</span><span class="sxs-lookup"><span data-stu-id="a1f0e-103">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="a1f0e-104">本主题演示如何使用<xref:System.Xml.XmlReader>。</xref:System.Xml.XmlReader>片段进行流式处理</span><span class="sxs-lookup"><span data-stu-id="a1f0e-104">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="a1f0e-105">若要使用的最有效方法之一<xref:System.Xml.XmlReader>读取<xref:System.Xml.Linq.XElement>对象是编写您自己的自定义轴方法。</xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="a1f0e-105">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="a1f0e-106">轴方法通常返回一个集合比如<xref:System.Collections.Generic.IEnumerable%601>的<xref:System.Xml.Linq.XElement>，本主题中的示例中所示。</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="a1f0e-106">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="a1f0e-107">在自定义轴方法中，通过调用创建的 XML 片段后<xref:System.Xml.Linq.XNode.ReadFrom%2A>方法，返回集合使用`yield return`。</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="a1f0e-107">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="a1f0e-108">这可为您的自定义轴方法提供延迟执行语义。</span><span class="sxs-lookup"><span data-stu-id="a1f0e-108">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="a1f0e-109">当创建 XML 树从<xref:System.Xml.XmlReader>对象，<xref:System.Xml.XmlReader>必须定位在元素上。</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="a1f0e-109">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="a1f0e-110"><xref:System.Xml.Linq.XNode.ReadFrom%2A>方法不返回读取的元素结束标记之前。</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="a1f0e-110">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="a1f0e-111">如果您想要创建一个部分树，您可以实例化<xref:System.Xml.XmlReader>，将读取器定位在想要转换为节点<xref:System.Xml.Linq.XElement>树，然后再创建<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="a1f0e-111">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="a1f0e-112">主题[如何︰ 流处理可访问标头信息 (Visual Basic 中) 的 XML 片段](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md)包含信息以及有关如何流式处理更复杂文档的示例。</span><span class="sxs-lookup"><span data-stu-id="a1f0e-112">The topic [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>  
  
 <span data-ttu-id="a1f0e-113">主题[如何︰ 执行流式处理转换的大型 XML 文档 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md)包含举例说明如何使用 LINQ to XML 在保持很小的内存需求量的同时转换极大的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="a1f0e-113">The topic [How to: Perform Streaming Transform of Large XML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1f0e-114">示例</span><span class="sxs-lookup"><span data-stu-id="a1f0e-114">Example</span></span>  
 <span data-ttu-id="a1f0e-115">本示例创建一个自定义轴方法。</span><span class="sxs-lookup"><span data-stu-id="a1f0e-115">This example creates a custom axis method.</span></span> <span data-ttu-id="a1f0e-116">可以通过使用 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 查询来查询该方法。</span><span class="sxs-lookup"><span data-stu-id="a1f0e-116">You can query it by using a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query.</span></span> <span data-ttu-id="a1f0e-117">自定义轴方法 `StreamRootChildDoc` 是一个专门设计的方法，用于读取具有重复 `Child` 元素的文档。</span><span class="sxs-lookup"><span data-stu-id="a1f0e-117">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
<span data-ttu-id="a1f0e-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a1f0e-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="a1f0e-119">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="a1f0e-119">This example produces the following output:</span></span>  
  
<span data-ttu-id="a1f0e-120"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a1f0e-120"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="a1f0e-121">在本示例中，源文档非常小。</span><span class="sxs-lookup"><span data-stu-id="a1f0e-121">In this example, the source document is very small.</span></span> <span data-ttu-id="a1f0e-122">但是即使有数百万个 `Child` 元素，本示例也仍具有很小的内存需求量。</span><span class="sxs-lookup"><span data-stu-id="a1f0e-122">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f0e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1f0e-123">See Also</span></span>  
 <span data-ttu-id="a1f0e-124">[演练︰ 在 Visual Basic 中实现 IEnumerable(Of T)](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md) </span><span class="sxs-lookup"><span data-stu-id="a1f0e-124">[Walkthrough: Implementing IEnumerable(Of T) in Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md) </span></span>  
<span data-ttu-id="a1f0e-125"> [分析 XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)</span><span class="sxs-lookup"><span data-stu-id="a1f0e-125"> [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)</span></span>
