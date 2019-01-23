---
title: 扩展索引器属性 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 25a868afded83f28f5f56a9f19e050bbd32b24c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490825"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="d8ec0-102">扩展索引器属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8ec0-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="d8ec0-103">提供对集合中各个元素的访问。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8ec0-104">语法</span><span class="sxs-lookup"><span data-stu-id="d8ec0-104">Syntax</span></span>  
  
```  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="d8ec0-105">部件</span><span class="sxs-lookup"><span data-stu-id="d8ec0-105">Parts</span></span>  
  
|<span data-ttu-id="d8ec0-106">术语</span><span class="sxs-lookup"><span data-stu-id="d8ec0-106">Term</span></span>|<span data-ttu-id="d8ec0-107">定义</span><span class="sxs-lookup"><span data-stu-id="d8ec0-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="d8ec0-108">必需。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-108">Required.</span></span> <span data-ttu-id="d8ec0-109">可查询的集合。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-109">A queryable collection.</span></span> <span data-ttu-id="d8ec0-110">也就是说，集合实现<xref:System.Collections.Generic.IEnumerable%601>或<xref:System.Linq.IQueryable%601>。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="d8ec0-111">(</span><span class="sxs-lookup"><span data-stu-id="d8ec0-111">(</span></span>|<span data-ttu-id="d8ec0-112">必需。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-112">Required.</span></span> <span data-ttu-id="d8ec0-113">表示索引器属性的开头。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="d8ec0-114">必需。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-114">Required.</span></span> <span data-ttu-id="d8ec0-115">一个整数表达式，指定集合的元素的从零开始的位置。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="d8ec0-116">)</span><span class="sxs-lookup"><span data-stu-id="d8ec0-116">)</span></span>|<span data-ttu-id="d8ec0-117">必需。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-117">Required.</span></span> <span data-ttu-id="d8ec0-118">表示索引器属性的结尾。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="d8ec0-119">返回值</span><span class="sxs-lookup"><span data-stu-id="d8ec0-119">Return Value</span></span>  
 <span data-ttu-id="d8ec0-120">从集合中指定的位置的对象或`Nothing`如果索引超出范围。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8ec0-121">备注</span><span class="sxs-lookup"><span data-stu-id="d8ec0-121">Remarks</span></span>  
 <span data-ttu-id="d8ec0-122">扩展索引器属性可用于访问集合中的各个元素。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="d8ec0-123">XML 轴属性的输出通常使用此索引器属性。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="d8ec0-124">XML 子和 XML 子代轴属性返回的集合<xref:System.Xml.Linq.XElement>对象或属性值。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="d8ec0-125">Visual Basic 编译器将扩展索引器属性转换为对调用`ElementAtOrDefault`方法。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="d8ec0-126">与数组索引器，不同`ElementAtOrDefault`方法将返回`Nothing`如果索引超出范围。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="d8ec0-127">此行为时，你无法轻松确定集合中的元素数。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="d8ec0-128">此索引器属性是为实现的集合的扩展属性相似<xref:System.Collections.Generic.IEnumerable%601>或<xref:System.Linq.IQueryable%601>： 仅当集合不具有索引器或默认属性使用它。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="d8ec0-129">若要访问的集合中的第一个元素的值<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XAttribute>对象，可以使用 XML`Value`属性。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="d8ec0-130">有关详细信息，请参阅[XML 值属性](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8ec0-131">示例</span><span class="sxs-lookup"><span data-stu-id="d8ec0-131">Example</span></span>  
 <span data-ttu-id="d8ec0-132">下面的示例演示如何使用扩展索引器访问的集合中的第二个子节点<xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="d8ec0-133">通过使用子轴属性，它将获取名为的所有子元素访问集合`phone`在`contact`对象。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 <span data-ttu-id="d8ec0-134">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="d8ec0-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="d8ec0-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8ec0-135">See also</span></span>
- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="d8ec0-136">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="d8ec0-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="d8ec0-137">XML 文本</span><span class="sxs-lookup"><span data-stu-id="d8ec0-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="d8ec0-138">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="d8ec0-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="d8ec0-139">XML 值属性</span><span class="sxs-lookup"><span data-stu-id="d8ec0-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
