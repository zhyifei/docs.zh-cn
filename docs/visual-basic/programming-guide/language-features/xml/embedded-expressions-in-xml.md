---
title: XML 中的嵌入式表达式 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: ef8ac62d9d969ce4463931d69b0302376ca0ccc4
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881554"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="c96d6-102">XML 中的嵌入式表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c96d6-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="c96d6-103">嵌入的表达式，可以创建包含在运行时计算的表达式的 XML 文本。</span><span class="sxs-lookup"><span data-stu-id="c96d6-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="c96d6-104">嵌入式表达式的语法是`<%=` `expression` `%>`，即在 ASP.NET 中使用的语法相同。</span><span class="sxs-lookup"><span data-stu-id="c96d6-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in ASP.NET.</span></span>  
  
 <span data-ttu-id="c96d6-105">例如，您可以创建一个 XML 元素文本，组合嵌入式的表达式包含文字文本内容。</span><span class="sxs-lookup"><span data-stu-id="c96d6-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 <span data-ttu-id="c96d6-106">如果`isbnNumber`包含整数 12345 并`modifiedDate`包含的日期 3/5/2006，当此代码执行时，值`book`是：</span><span class="sxs-lookup"><span data-stu-id="c96d6-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="c96d6-107">嵌入的表达式的位置和验证</span><span class="sxs-lookup"><span data-stu-id="c96d6-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="c96d6-108">嵌入的表达式只能出现在 XML 文本表达式中的某些位置。</span><span class="sxs-lookup"><span data-stu-id="c96d6-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="c96d6-109">可以返回该类型的表达式的表达式位置控件以及如何`Nothing`进行处理。</span><span class="sxs-lookup"><span data-stu-id="c96d6-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="c96d6-110">下表介绍了允许的位置和嵌入表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="c96d6-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="c96d6-111">在文本中的位置</span><span class="sxs-lookup"><span data-stu-id="c96d6-111">Location in literal</span></span>|<span data-ttu-id="c96d6-112">表达式的类型</span><span class="sxs-lookup"><span data-stu-id="c96d6-112">Type of expression</span></span>|<span data-ttu-id="c96d6-113">处理 `Nothing`</span><span class="sxs-lookup"><span data-stu-id="c96d6-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="c96d6-114">XML 元素名称</span><span class="sxs-lookup"><span data-stu-id="c96d6-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="c96d6-115">Error</span><span class="sxs-lookup"><span data-stu-id="c96d6-115">Error</span></span>|  
|<span data-ttu-id="c96d6-116">XML 元素内容</span><span class="sxs-lookup"><span data-stu-id="c96d6-116">XML element content</span></span>|<span data-ttu-id="c96d6-117">`Object` 或数组 `Object`</span><span class="sxs-lookup"><span data-stu-id="c96d6-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="c96d6-118">忽略</span><span class="sxs-lookup"><span data-stu-id="c96d6-118">Ignored</span></span>|  
|<span data-ttu-id="c96d6-119">XML 元素属性名称</span><span class="sxs-lookup"><span data-stu-id="c96d6-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="c96d6-120">错误，除非也是属性值 `Nothing`</span><span class="sxs-lookup"><span data-stu-id="c96d6-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="c96d6-121">XML 元素特性值</span><span class="sxs-lookup"><span data-stu-id="c96d6-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="c96d6-122">忽略的属性声明</span><span class="sxs-lookup"><span data-stu-id="c96d6-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="c96d6-123">XML 元素特性</span><span class="sxs-lookup"><span data-stu-id="c96d6-123">XML element attribute</span></span>|<span data-ttu-id="c96d6-124"><xref:System.Xml.Linq.XAttribute> 或一系列 <xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="c96d6-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="c96d6-125">忽略</span><span class="sxs-lookup"><span data-stu-id="c96d6-125">Ignored</span></span>|  
|<span data-ttu-id="c96d6-126">XML 文档根元素</span><span class="sxs-lookup"><span data-stu-id="c96d6-126">XML document root element</span></span>|<span data-ttu-id="c96d6-127"><xref:System.Xml.Linq.XElement> 或其中一个集合<xref:System.Xml.Linq.XElement>对象和任意数量<xref:System.Xml.Linq.XProcessingInstruction>和<xref:System.Xml.Linq.XComment>对象</span><span class="sxs-lookup"><span data-stu-id="c96d6-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="c96d6-128">忽略</span><span class="sxs-lookup"><span data-stu-id="c96d6-128">Ignored</span></span>|  
  
- <span data-ttu-id="c96d6-129">XML 元素名称中嵌入表达式的示例：</span><span class="sxs-lookup"><span data-stu-id="c96d6-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- <span data-ttu-id="c96d6-130">XML 元素的内容中嵌入表达式的示例：</span><span class="sxs-lookup"><span data-stu-id="c96d6-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- <span data-ttu-id="c96d6-131">XML 元素属性名称中嵌入表达式的示例：</span><span class="sxs-lookup"><span data-stu-id="c96d6-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- <span data-ttu-id="c96d6-132">嵌入表达式的 XML 元素特性值中的示例：</span><span class="sxs-lookup"><span data-stu-id="c96d6-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- <span data-ttu-id="c96d6-133">XML 元素特性中嵌入表达式的示例：</span><span class="sxs-lookup"><span data-stu-id="c96d6-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- <span data-ttu-id="c96d6-134">XML 文档的根元素中的嵌入式表达式的示例：</span><span class="sxs-lookup"><span data-stu-id="c96d6-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 <span data-ttu-id="c96d6-135">如果启用`Option Strict`，编译器会检查每个嵌入表达式的类型加宽到所需的类型。</span><span class="sxs-lookup"><span data-stu-id="c96d6-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="c96d6-136">唯一的例外是在代码运行时验证 XML 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="c96d6-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="c96d6-137">如果编译而无需`Option Strict`，可以将嵌入类型的表达式`Object`和在运行时验证它们的类型。</span><span class="sxs-lookup"><span data-stu-id="c96d6-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="c96d6-138">可选的内容的位置中嵌入表达式包含`Nothing`将被忽略。</span><span class="sxs-lookup"><span data-stu-id="c96d6-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="c96d6-139">这意味着不需要检查该元素内容中，属性值，并且数组元素不是`Nothing`使用 XML 文本之前。</span><span class="sxs-lookup"><span data-stu-id="c96d6-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="c96d6-140">所需的值，例如元素和属性名称不能为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="c96d6-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="c96d6-141">有关在特定类型的文本中使用嵌入式的表达式的详细信息，请参阅[XML 文档文本](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)， [XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="c96d6-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="c96d6-142">作用域规则</span><span class="sxs-lookup"><span data-stu-id="c96d6-142">Scoping Rules</span></span>  
 <span data-ttu-id="c96d6-143">编译器将每个 XML 文本转换为相应的文本类型的构造函数调用。</span><span class="sxs-lookup"><span data-stu-id="c96d6-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="c96d6-144">文本内容和 XML 文本中的嵌入式的表达式作为参数传递给构造函数。</span><span class="sxs-lookup"><span data-stu-id="c96d6-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="c96d6-145">这意味着所有 Visual Basic 编程元素可用于 XML 文本也都都可在其嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="c96d6-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="c96d6-146">在 XML 文本中，可以访问的 XML 命名空间前缀声明与`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="c96d6-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="c96d6-147">您可以声明新的 XML 命名空间前缀，或现有的 XML 命名空间前缀，使用的元素中的卷影`xmlns`属性。</span><span class="sxs-lookup"><span data-stu-id="c96d6-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="c96d6-148">新的命名空间是可用的子节点的该元素，而不是属于 XML 文本中嵌入的表达式。</span><span class="sxs-lookup"><span data-stu-id="c96d6-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c96d6-149">当使用声明 XML 命名空间前缀`xmlns`命名空间属性的属性值必须是常量字符串。</span><span class="sxs-lookup"><span data-stu-id="c96d6-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="c96d6-150">在这方面，使用`xmlns`属性就像使用`Imports`语句声明 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="c96d6-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="c96d6-151">不能使用嵌入式的表达式来指定 XML 命名空间值。</span><span class="sxs-lookup"><span data-stu-id="c96d6-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c96d6-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="c96d6-152">See also</span></span>

- [<span data-ttu-id="c96d6-153">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="c96d6-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="c96d6-154">XML 文档文本</span><span class="sxs-lookup"><span data-stu-id="c96d6-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="c96d6-155">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="c96d6-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="c96d6-156">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="c96d6-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="c96d6-157">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="c96d6-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="c96d6-158">XML 文本概述</span><span class="sxs-lookup"><span data-stu-id="c96d6-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
