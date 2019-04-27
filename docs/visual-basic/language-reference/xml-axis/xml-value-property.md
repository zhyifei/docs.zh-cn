---
title: XML 值属性 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 1c7aa1cc32bc1c5ef637f7a606db7e695f1dfaee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799159"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="4a532-102">XML 值属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a532-102">XML Value Property (Visual Basic)</span></span>
<span data-ttu-id="4a532-103">提供对一系列的第一个元素的值的访问<xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="4a532-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a532-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a532-104">Syntax</span></span>  
  
```  
object.Value  
```  
  
## <a name="parts"></a><span data-ttu-id="4a532-105">部件</span><span class="sxs-lookup"><span data-stu-id="4a532-105">Parts</span></span>  
  
|<span data-ttu-id="4a532-106">术语</span><span class="sxs-lookup"><span data-stu-id="4a532-106">Term</span></span>|<span data-ttu-id="4a532-107">定义</span><span class="sxs-lookup"><span data-stu-id="4a532-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="4a532-108">必需。</span><span class="sxs-lookup"><span data-stu-id="4a532-108">Required.</span></span> <span data-ttu-id="4a532-109"><xref:System.Xml.Linq.XElement> 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="4a532-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="4a532-110">返回值</span><span class="sxs-lookup"><span data-stu-id="4a532-110">Return Value</span></span>  
 <span data-ttu-id="4a532-111">一个`String`包含值的集合的第一个元素或`Nothing`集合是否为空。</span><span class="sxs-lookup"><span data-stu-id="4a532-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a532-112">备注</span><span class="sxs-lookup"><span data-stu-id="4a532-112">Remarks</span></span>  
 <span data-ttu-id="4a532-113"><xref:System.Xml.Linq.XElement.Value%2A>属性，则可以轻松访问的集合中的第一个元素的值<xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="4a532-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="4a532-114">此属性首先检查集合是否包含至少一个对象。</span><span class="sxs-lookup"><span data-stu-id="4a532-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="4a532-115">如果集合为空，此属性返回`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="4a532-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="4a532-116">否则，此属性返回的值<xref:System.Xml.Linq.XElement.Value%2A>集合中的第一个元素的属性。</span><span class="sxs-lookup"><span data-stu-id="4a532-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a532-117">当访问的 XML 属性使用值\@的标识符，则返回属性值为`String`并不需要显式指定<xref:System.Xml.Linq.XAttribute.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="4a532-117">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="4a532-118">若要访问集合中的其他元素，可以使用 XML 扩展索引器属性。</span><span class="sxs-lookup"><span data-stu-id="4a532-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="4a532-119">有关详细信息，请参阅[扩展索引器属性](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)。</span><span class="sxs-lookup"><span data-stu-id="4a532-119">For more information, see [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="4a532-120">继承</span><span class="sxs-lookup"><span data-stu-id="4a532-120">Inheritance</span></span>  
 <span data-ttu-id="4a532-121">大多数用户不需要实现<xref:System.Collections.Generic.IEnumerable%601>，因此可以忽略本部分中。</span><span class="sxs-lookup"><span data-stu-id="4a532-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>  
  
 <span data-ttu-id="4a532-122"><xref:System.Xml.Linq.XElement.Value%2A>属性是扩展属性的类型的实现`IEnumerable(Of XElement)`。</span><span class="sxs-lookup"><span data-stu-id="4a532-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="4a532-123">此扩展属性的绑定是类似的扩展方法绑定： 如果某个类型实现一个接口，并且定义了一个具有名称"值"的属性，该属性的优先级高于该扩展属性。</span><span class="sxs-lookup"><span data-stu-id="4a532-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="4a532-124">换而言之，这<xref:System.Xml.Linq.XElement.Value%2A>可以通过定义一个新的属性实现的类中重写属性`IEnumerable(Of XElement)`。</span><span class="sxs-lookup"><span data-stu-id="4a532-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a532-125">示例</span><span class="sxs-lookup"><span data-stu-id="4a532-125">Example</span></span>  
 <span data-ttu-id="4a532-126">下面的示例演示如何使用<xref:System.Xml.Linq.XElement.Value%2A>属性来访问的集合中的第一个节点<xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="4a532-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="4a532-127">该示例使用子轴属性来获取名为的所有子节点的集合`phone`位于`contact`对象。</span><span class="sxs-lookup"><span data-stu-id="4a532-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]  
  
 <span data-ttu-id="4a532-128">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="4a532-128">This code displays the following text:</span></span>  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="4a532-129">示例</span><span class="sxs-lookup"><span data-stu-id="4a532-129">Example</span></span>  
 <span data-ttu-id="4a532-130">下面的示例演示如何获取集合中的 XML 特性的值<xref:System.Xml.Linq.XAttribute>对象。</span><span class="sxs-lookup"><span data-stu-id="4a532-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="4a532-131">该示例使用特性轴属性来显示的值`type`的所有属性`phone`元素。</span><span class="sxs-lookup"><span data-stu-id="4a532-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>  
  
 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]  
  
 <span data-ttu-id="4a532-132">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="4a532-132">This code displays the following text:</span></span>  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a><span data-ttu-id="4a532-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a532-133">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="4a532-134">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="4a532-134">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="4a532-135">XML 文本</span><span class="sxs-lookup"><span data-stu-id="4a532-135">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="4a532-136">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="4a532-136">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="4a532-137">扩展方法</span><span class="sxs-lookup"><span data-stu-id="4a532-137">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="4a532-138">扩展索引器属性</span><span class="sxs-lookup"><span data-stu-id="4a532-138">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)
- [<span data-ttu-id="4a532-139">XML 子轴属性</span><span class="sxs-lookup"><span data-stu-id="4a532-139">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="4a532-140">XML 特性轴属性</span><span class="sxs-lookup"><span data-stu-id="4a532-140">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
