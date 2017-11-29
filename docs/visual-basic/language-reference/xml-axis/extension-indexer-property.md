---
title: "扩展索引器属性 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 99d14b6e54a59ffc904a9e786c22498d23ee8ab6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="f1ef9-102">扩展索引器属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1ef9-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="f1ef9-103">提供对集合中各个元素的访问。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1ef9-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1ef9-104">Syntax</span></span>  
  
```  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="f1ef9-105">部件</span><span class="sxs-lookup"><span data-stu-id="f1ef9-105">Parts</span></span>  
  
|<span data-ttu-id="f1ef9-106">术语</span><span class="sxs-lookup"><span data-stu-id="f1ef9-106">Term</span></span>|<span data-ttu-id="f1ef9-107">定义</span><span class="sxs-lookup"><span data-stu-id="f1ef9-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="f1ef9-108">必需。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-108">Required.</span></span> <span data-ttu-id="f1ef9-109">查询的集合。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-109">A queryable collection.</span></span> <span data-ttu-id="f1ef9-110">也就是说，集合可实现<xref:System.Collections.Generic.IEnumerable%601>或<xref:System.Linq.IQueryable%601>。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="f1ef9-111">(</span><span class="sxs-lookup"><span data-stu-id="f1ef9-111">(</span></span>|<span data-ttu-id="f1ef9-112">必需。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-112">Required.</span></span> <span data-ttu-id="f1ef9-113">表示索引器属性的开头。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="f1ef9-114">必需。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-114">Required.</span></span> <span data-ttu-id="f1ef9-115">一个整数表达式，指定集合的某个元素的从零开始的位置。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="f1ef9-116">)</span><span class="sxs-lookup"><span data-stu-id="f1ef9-116">)</span></span>|<span data-ttu-id="f1ef9-117">必需。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-117">Required.</span></span> <span data-ttu-id="f1ef9-118">表示索引器属性的末尾。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="f1ef9-119">返回值</span><span class="sxs-lookup"><span data-stu-id="f1ef9-119">Return Value</span></span>  
 <span data-ttu-id="f1ef9-120">在集合中，指定的位置中的对象或`Nothing`如果索引超出范围。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1ef9-121">备注</span><span class="sxs-lookup"><span data-stu-id="f1ef9-121">Remarks</span></span>  
 <span data-ttu-id="f1ef9-122">扩展索引器属性可用于访问集合中的各个元素。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="f1ef9-123">XML 轴属性的输出通常用于此索引器属性。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="f1ef9-124">XML 子和 XML 子代轴属性返回的集合<xref:System.Xml.Linq.XElement>对象或属性值。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="f1ef9-125">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器将扩展索引器属性转换为调用`ElementAtOrDefault`方法。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-125">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="f1ef9-126">与数组索引器，不同`ElementAtOrDefault`方法返回`Nothing`如果索引超出范围。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="f1ef9-127">当你将无法轻松确定集合中的元素的数目时，此行为很有用。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="f1ef9-128">此索引器属性是实现的集合的扩展属性相似<xref:System.Collections.Generic.IEnumerable%601>或<xref:System.Linq.IQueryable%601>： 仅当集合不具有一个索引器或默认属性时，才使用它。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="f1ef9-129">若要访问的集合中的第一个元素的值<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XAttribute>对象，你可以使用 XML`Value`属性。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="f1ef9-130">有关详细信息，请参阅[XML 值属性](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1ef9-131">示例</span><span class="sxs-lookup"><span data-stu-id="f1ef9-131">Example</span></span>  
 <span data-ttu-id="f1ef9-132">下面的示例演示如何扩展索引器用于访问集合中的第二个子节点<xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="f1ef9-133">通过使用子轴属性，它将获取名为的所有子元素属性访问集合`phone`中`contact`对象。</span><span class="sxs-lookup"><span data-stu-id="f1ef9-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 <span data-ttu-id="f1ef9-134">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="f1ef9-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="f1ef9-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1ef9-135">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="f1ef9-136">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="f1ef9-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="f1ef9-137">XML 文本</span><span class="sxs-lookup"><span data-stu-id="f1ef9-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="f1ef9-138">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="f1ef9-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="f1ef9-139">XML 值属性</span><span class="sxs-lookup"><span data-stu-id="f1ef9-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
