---
title: XML 特性轴属性 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: cfc18df4487488bd90d7b0250a9053f55305d8a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631487"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="4e6ca-102">XML 特性轴属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e6ca-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="4e6ca-103">提供访问的属性的值<xref:System.Xml.Linq.XElement>对象或集合中的第一个元素<xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e6ca-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e6ca-104">Syntax</span></span>  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="4e6ca-105">部件</span><span class="sxs-lookup"><span data-stu-id="4e6ca-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="4e6ca-106">必需。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-106">Required.</span></span> <span data-ttu-id="4e6ca-107"><xref:System.Xml.Linq.XElement>对象或一系列<xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="4e6ca-108">.@</span><span class="sxs-lookup"><span data-stu-id="4e6ca-108">.@</span></span>  
 <span data-ttu-id="4e6ca-109">必需。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-109">Required.</span></span> <span data-ttu-id="4e6ca-110">表示特性轴属性的开头。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="4e6ca-111">可选。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-111">Optional.</span></span> <span data-ttu-id="4e6ca-112">表示的属性的名称的开头时`attribute`不是在 Visual Basic 中是有效的标识符。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="4e6ca-113">必需。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-113">Required.</span></span> <span data-ttu-id="4e6ca-114">若要访问的窗体的属性的名称 [`prefix`:]`name`。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="4e6ca-115">部件</span><span class="sxs-lookup"><span data-stu-id="4e6ca-115">Part</span></span>|<span data-ttu-id="4e6ca-116">描述</span><span class="sxs-lookup"><span data-stu-id="4e6ca-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="4e6ca-117">可选。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-117">Optional.</span></span> <span data-ttu-id="4e6ca-118">该属性的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="4e6ca-119">必须是使用 `Imports` 语句定义的全局 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="4e6ca-120">必需。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-120">Required.</span></span> <span data-ttu-id="4e6ca-121">本地属性名称。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-121">Local attribute name.</span></span> <span data-ttu-id="4e6ca-122">请参阅[声明的 XML 元素和特性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="4e6ca-123">可选。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-123">Optional.</span></span> <span data-ttu-id="4e6ca-124">表示属性的名称的末尾时`attribute`不是在 Visual Basic 中是有效的标识符。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e6ca-125">返回值</span><span class="sxs-lookup"><span data-stu-id="4e6ca-125">Return Value</span></span>  
 <span data-ttu-id="4e6ca-126">包含的值的字符串`attribute`。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="4e6ca-127">如果属性名称不存在，`Nothing`返回。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e6ca-128">备注</span><span class="sxs-lookup"><span data-stu-id="4e6ca-128">Remarks</span></span>  
 <span data-ttu-id="4e6ca-129">可以使用 XML 特性轴属性从按名称访问的属性值<xref:System.Xml.Linq.XElement>对象或从集合中的第一个元素<xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="4e6ca-130">可以按名称，检索的属性值，也可以将新属性添加到元素中，通过指定新名称前面有 @ 标识符。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="4e6ca-131">如果是指 XML 属性使用 @ 标识符，返回的属性值为一个字符串，并且不需要显式指定<xref:System.Xml.Linq.XAttribute.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="4e6ca-132">XML 特性的命名规则不同于 Visual Basic 标识符的命名规则。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="4e6ca-133">若要访问 XML 特性都不是有效的 Visual Basic 标识符的名称，请将名称括在尖括号 (\<和 >)。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="4e6ca-134">XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="4e6ca-134">XML Namespaces</span></span>  
 <span data-ttu-id="4e6ca-135">中特性轴属性的名称可以使用通过使用全局声明的只有 XML 命名空间前缀`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="4e6ca-136">它不能使用在 XML 元素文本中局部声明的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="4e6ca-137">有关详细信息，请参阅[Imports 语句 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e6ca-138">示例</span><span class="sxs-lookup"><span data-stu-id="4e6ca-138">Example</span></span>  
 <span data-ttu-id="4e6ca-139">下面的示例演示如何获取名为 XML 属性的值`type`集合中的 XML 元素名为`phone`。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 <span data-ttu-id="4e6ca-140">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="4e6ca-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="4e6ca-141">示例</span><span class="sxs-lookup"><span data-stu-id="4e6ca-141">Example</span></span>  
 <span data-ttu-id="4e6ca-142">下面的示例演示如何创建这两个 XML 元素的属性作为一部分的 XML，并动态通过将属性添加到的实例，以声明方式<xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="4e6ca-143">`type`属性以声明方式创建和`owner`动态创建属性。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 <span data-ttu-id="4e6ca-144">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="4e6ca-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="4e6ca-145">示例</span><span class="sxs-lookup"><span data-stu-id="4e6ca-145">Example</span></span>  
 <span data-ttu-id="4e6ca-146">下面的示例使用尖括号语法来获取名为 XML 特性的值`number-type`，这不是在 Visual Basic 中是有效的标识符。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 <span data-ttu-id="4e6ca-147">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="4e6ca-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="4e6ca-148">示例</span><span class="sxs-lookup"><span data-stu-id="4e6ca-148">Example</span></span>  
 <span data-ttu-id="4e6ca-149">下面的示例声明 `ns` 作为 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="4e6ca-150">然后，它使用的命名空间前缀来创建 XML 文本和访问具有限定名称的第一个子节点"`ns:name`"。</span><span class="sxs-lookup"><span data-stu-id="4e6ca-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 <span data-ttu-id="4e6ca-151">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="4e6ca-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="4e6ca-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e6ca-152">See also</span></span>
- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="4e6ca-153">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="4e6ca-153">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="4e6ca-154">XML 文本</span><span class="sxs-lookup"><span data-stu-id="4e6ca-154">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="4e6ca-155">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="4e6ca-155">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="4e6ca-156">已声明的 XML 元素和特性的名称</span><span class="sxs-lookup"><span data-stu-id="4e6ca-156">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
