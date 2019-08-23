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
ms.openlocfilehash: 9edf95c7cedced55ab2441baf51b7c2052e4654c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942977"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="6206b-102">XML 值属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6206b-102">XML Value Property (Visual Basic)</span></span>
<span data-ttu-id="6206b-103">提供对<xref:System.Xml.Linq.XElement>对象集合中第一个元素的值的访问。</span><span class="sxs-lookup"><span data-stu-id="6206b-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6206b-104">语法</span><span class="sxs-lookup"><span data-stu-id="6206b-104">Syntax</span></span>  
  
```  
object.Value  
```  
  
## <a name="parts"></a><span data-ttu-id="6206b-105">部件</span><span class="sxs-lookup"><span data-stu-id="6206b-105">Parts</span></span>  
  
|<span data-ttu-id="6206b-106">术语</span><span class="sxs-lookup"><span data-stu-id="6206b-106">Term</span></span>|<span data-ttu-id="6206b-107">定义</span><span class="sxs-lookup"><span data-stu-id="6206b-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="6206b-108">必需。</span><span class="sxs-lookup"><span data-stu-id="6206b-108">Required.</span></span> <span data-ttu-id="6206b-109"><xref:System.Xml.Linq.XElement> 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="6206b-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="6206b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="6206b-110">Return Value</span></span>  
 <span data-ttu-id="6206b-111">一个`String` , 它包含集合`Nothing`中第一个元素的值; 如果集合为空, 则为。</span><span class="sxs-lookup"><span data-stu-id="6206b-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6206b-112">备注</span><span class="sxs-lookup"><span data-stu-id="6206b-112">Remarks</span></span>  
 <span data-ttu-id="6206b-113">使用<xref:System.Xml.Linq.XElement.Value%2A>属性可以轻松访问<xref:System.Xml.Linq.XElement>对象集合中第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="6206b-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="6206b-114">此属性首先检查集合是否包含至少一个对象。</span><span class="sxs-lookup"><span data-stu-id="6206b-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="6206b-115">如果集合为空, 则此属性返回`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="6206b-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="6206b-116">否则, 此属性将返回集合中第<xref:System.Xml.Linq.XElement.Value%2A>一个元素的属性的值。</span><span class="sxs-lookup"><span data-stu-id="6206b-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6206b-117">使用 "\@" 标识符访问 XML 特性的值时, 特性值`String`作为返回, 无<xref:System.Xml.Linq.XAttribute.Value%2A>需显式指定属性。</span><span class="sxs-lookup"><span data-stu-id="6206b-117">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="6206b-118">若要访问集合中的其他元素, 可以使用 XML 扩展索引器属性。</span><span class="sxs-lookup"><span data-stu-id="6206b-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="6206b-119">有关详细信息, 请参阅[扩展索引器属性](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)。</span><span class="sxs-lookup"><span data-stu-id="6206b-119">For more information, see [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="6206b-120">继承</span><span class="sxs-lookup"><span data-stu-id="6206b-120">Inheritance</span></span>  
 <span data-ttu-id="6206b-121">大多数用户将不必实现<xref:System.Collections.Generic.IEnumerable%601>, 因此可以忽略此部分。</span><span class="sxs-lookup"><span data-stu-id="6206b-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>  
  
 <span data-ttu-id="6206b-122">属性是实现`IEnumerable(Of XElement)`的类型的扩展属性。 <xref:System.Xml.Linq.XElement.Value%2A></span><span class="sxs-lookup"><span data-stu-id="6206b-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="6206b-123">此扩展属性的绑定类似于扩展方法的绑定: 如果某个类型实现了一个接口, 并定义了一个名称为 "Value" 的属性, 则该属性的优先级高于扩展属性。</span><span class="sxs-lookup"><span data-stu-id="6206b-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="6206b-124">换言之, 可以通过在<xref:System.Xml.Linq.XElement.Value%2A>实现`IEnumerable(Of XElement)`的类中定义一个新属性来重写此属性。</span><span class="sxs-lookup"><span data-stu-id="6206b-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6206b-125">示例</span><span class="sxs-lookup"><span data-stu-id="6206b-125">Example</span></span>  
 <span data-ttu-id="6206b-126">下面的示例演示如何使用<xref:System.Xml.Linq.XElement.Value%2A>属性访问<xref:System.Xml.Linq.XElement>对象集合中的第一个节点。</span><span class="sxs-lookup"><span data-stu-id="6206b-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="6206b-127">该示例使用子轴属性来获取`phone` `contact`对象中名为的所有子节点的集合。</span><span class="sxs-lookup"><span data-stu-id="6206b-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]  
  
 <span data-ttu-id="6206b-128">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="6206b-128">This code displays the following text:</span></span>  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="6206b-129">示例</span><span class="sxs-lookup"><span data-stu-id="6206b-129">Example</span></span>  
 <span data-ttu-id="6206b-130">下面的示例演示如何从<xref:System.Xml.Linq.XAttribute>对象的集合中获取 XML 特性的值。</span><span class="sxs-lookup"><span data-stu-id="6206b-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="6206b-131">该示例使用 "属性轴" 属性显示所有`type` `phone`元素的属性值。</span><span class="sxs-lookup"><span data-stu-id="6206b-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>  
  
 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]  
  
 <span data-ttu-id="6206b-132">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="6206b-132">This code displays the following text:</span></span>  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a><span data-ttu-id="6206b-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="6206b-133">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="6206b-134">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="6206b-134">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="6206b-135">XML 文本</span><span class="sxs-lookup"><span data-stu-id="6206b-135">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="6206b-136">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="6206b-136">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="6206b-137">扩展方法</span><span class="sxs-lookup"><span data-stu-id="6206b-137">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="6206b-138">扩展索引器属性</span><span class="sxs-lookup"><span data-stu-id="6206b-138">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)
- [<span data-ttu-id="6206b-139">XML 子轴属性</span><span class="sxs-lookup"><span data-stu-id="6206b-139">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="6206b-140">XML 特性轴属性</span><span class="sxs-lookup"><span data-stu-id="6206b-140">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
