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
ms.openlocfilehash: 896081c3dc7ca9e50b4dc4bd87675e957c34b649
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582164"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="e1794-102">XML 特性轴属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1794-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="e1794-103">提供对 <xref:System.Xml.Linq.XElement> 对象的特性值或 <xref:System.Xml.Linq.XElement> 对象集合中第一个元素的访问。</span><span class="sxs-lookup"><span data-stu-id="e1794-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1794-104">语法</span><span class="sxs-lookup"><span data-stu-id="e1794-104">Syntax</span></span>  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="e1794-105">部件</span><span class="sxs-lookup"><span data-stu-id="e1794-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="e1794-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="e1794-106">Required.</span></span> <span data-ttu-id="e1794-107">一个 <xref:System.Xml.Linq.XElement> 对象或 <xref:System.Xml.Linq.XElement> 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="e1794-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="e1794-108">.@</span><span class="sxs-lookup"><span data-stu-id="e1794-108">.@</span></span>  
 <span data-ttu-id="e1794-109">必须的。</span><span class="sxs-lookup"><span data-stu-id="e1794-109">Required.</span></span> <span data-ttu-id="e1794-110">表示属性轴属性的开头。</span><span class="sxs-lookup"><span data-stu-id="e1794-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="e1794-111">可选。</span><span class="sxs-lookup"><span data-stu-id="e1794-111">Optional.</span></span> <span data-ttu-id="e1794-112">如果 `attribute` 在 Visual Basic 中不是有效的标识符，则表示属性名称的开头。</span><span class="sxs-lookup"><span data-stu-id="e1794-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="e1794-113">必须的。</span><span class="sxs-lookup"><span data-stu-id="e1794-113">Required.</span></span> <span data-ttu-id="e1794-114">要访问的属性的名称，格式为 [`prefix`：] `name`。</span><span class="sxs-lookup"><span data-stu-id="e1794-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="e1794-115">部件</span><span class="sxs-lookup"><span data-stu-id="e1794-115">Part</span></span>|<span data-ttu-id="e1794-116">描述</span><span class="sxs-lookup"><span data-stu-id="e1794-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="e1794-117">可选。</span><span class="sxs-lookup"><span data-stu-id="e1794-117">Optional.</span></span> <span data-ttu-id="e1794-118">特性的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="e1794-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="e1794-119">必须是使用 `Imports` 语句定义的全局 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="e1794-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="e1794-120">必须的。</span><span class="sxs-lookup"><span data-stu-id="e1794-120">Required.</span></span> <span data-ttu-id="e1794-121">本地属性名称。</span><span class="sxs-lookup"><span data-stu-id="e1794-121">Local attribute name.</span></span> <span data-ttu-id="e1794-122">请参阅已[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="e1794-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="e1794-123">可选。</span><span class="sxs-lookup"><span data-stu-id="e1794-123">Optional.</span></span> <span data-ttu-id="e1794-124">如果 `attribute` 在 Visual Basic 中不是有效的标识符，则表示属性名称的末尾。</span><span class="sxs-lookup"><span data-stu-id="e1794-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1794-125">返回值</span><span class="sxs-lookup"><span data-stu-id="e1794-125">Return Value</span></span>  
 <span data-ttu-id="e1794-126">一个字符串，其中包含 `attribute` 的值。</span><span class="sxs-lookup"><span data-stu-id="e1794-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="e1794-127">如果属性名不存在，则返回 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="e1794-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1794-128">备注</span><span class="sxs-lookup"><span data-stu-id="e1794-128">Remarks</span></span>  
 <span data-ttu-id="e1794-129">您可以使用 XML 特性轴属性，按名称从 <xref:System.Xml.Linq.XElement> 对象或从 <xref:System.Xml.Linq.XElement> 对象集合中的第一个元素访问属性值。</span><span class="sxs-lookup"><span data-stu-id="e1794-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="e1794-130">可以按名称检索属性值，也可以通过指定一个新名称（前面带有 @ 标识符）来向元素添加一个新的属性。</span><span class="sxs-lookup"><span data-stu-id="e1794-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="e1794-131">当使用 @ 标识符引用 XML 特性时，属性值将以字符串的形式返回，无需显式指定 <xref:System.Xml.Linq.XAttribute.Value%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="e1794-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="e1794-132">XML 特性的命名规则不同于 Visual Basic 标识符的命名规则。</span><span class="sxs-lookup"><span data-stu-id="e1794-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="e1794-133">若要访问名称不是有效 Visual Basic 标识符的 XML 特性，请将该名称括在尖括号（\< 和 >）中。</span><span class="sxs-lookup"><span data-stu-id="e1794-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="e1794-134">XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="e1794-134">XML Namespaces</span></span>  
 <span data-ttu-id="e1794-135">特性轴属性中的名称只能使用 `Imports` 语句全局声明的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="e1794-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="e1794-136">它不能使用在 XML 元素文本中局部声明的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="e1794-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="e1794-137">有关详细信息，请参阅[Imports 语句（XML 命名空间）](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="e1794-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1794-138">示例</span><span class="sxs-lookup"><span data-stu-id="e1794-138">Example</span></span>  
 <span data-ttu-id="e1794-139">下面的示例演示如何从名为 `phone` 的 XML 元素集合中获取名为 `type` 的 XML 特性的值。</span><span class="sxs-lookup"><span data-stu-id="e1794-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 <span data-ttu-id="e1794-140">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="e1794-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="e1794-141">示例</span><span class="sxs-lookup"><span data-stu-id="e1794-141">Example</span></span>  
 <span data-ttu-id="e1794-142">下面的示例演示如何在 XML 中以声明方式同时创建 XML 元素的特性，并通过将特性添加到 <xref:System.Xml.Linq.XElement> 对象的实例来动态创建属性。</span><span class="sxs-lookup"><span data-stu-id="e1794-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="e1794-143">@No__t_0 属性以声明方式创建，并动态创建 `owner` 属性。</span><span class="sxs-lookup"><span data-stu-id="e1794-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 <span data-ttu-id="e1794-144">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="e1794-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="e1794-145">示例</span><span class="sxs-lookup"><span data-stu-id="e1794-145">Example</span></span>  
 <span data-ttu-id="e1794-146">下面的示例使用尖括号语法来获取名为 `number-type` 的 XML 属性的值，该属性不是 Visual Basic 中的有效标识符。</span><span class="sxs-lookup"><span data-stu-id="e1794-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 <span data-ttu-id="e1794-147">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="e1794-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="e1794-148">示例</span><span class="sxs-lookup"><span data-stu-id="e1794-148">Example</span></span>  
 <span data-ttu-id="e1794-149">下面的示例声明 `ns` 作为 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="e1794-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="e1794-150">然后，它使用命名空间的前缀创建 XML 文本，并访问具有限定名 "`ns:name`" 的第一个子节点。</span><span class="sxs-lookup"><span data-stu-id="e1794-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 <span data-ttu-id="e1794-151">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="e1794-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="e1794-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1794-152">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="e1794-153">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="e1794-153">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="e1794-154">XML 文本</span><span class="sxs-lookup"><span data-stu-id="e1794-154">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="e1794-155">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="e1794-155">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="e1794-156">已声明的 XML 元素和特性的名称</span><span class="sxs-lookup"><span data-stu-id="e1794-156">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
