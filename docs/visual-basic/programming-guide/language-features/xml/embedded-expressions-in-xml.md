---
title: "在 XML (Visual Basic 中) 中嵌入表达式 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XmlEmbeddedExpression
dev_langs:
- VB
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d24a49f2fa6fd66fe6e4c7724bd4298d65fb7a59
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="c6fe1-102">XML 中的嵌入式表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6fe1-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="c6fe1-103">嵌入的表达式，可以创建包含在运行时计算的表达式的 XML 文本。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="c6fe1-104">嵌入式表达式的语法是`<%=` `expression` `%>`，这是相同的中使用的语法[!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].</span></span>  
  
 <span data-ttu-id="c6fe1-105">例如，您可以创建一个 XML 元素文本，组合与文字文本内容的嵌入式的表达式。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 <span data-ttu-id="c6fe1-106">[!code-vb[VbXMLSamples #&27;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c6fe1-106">[!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]</span></span>  
  
 <span data-ttu-id="c6fe1-107">如果`isbnNumber`包含整数 12345 和`modifiedDate`包含的日期 3/5/2006，当此代码执行时，值`book`是︰</span><span class="sxs-lookup"><span data-stu-id="c6fe1-107">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="c6fe1-108">嵌入式的表达式定位和验证</span><span class="sxs-lookup"><span data-stu-id="c6fe1-108">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="c6fe1-109">嵌入的表达式只能出现在 XML 文本表达式中的某些位置。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-109">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="c6fe1-110">可以返回类型的表达式的表达式位置控件以及如何`Nothing`进行处理。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-110">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="c6fe1-111">下表描述允许的位置和嵌入式表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-111">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="c6fe1-112">在文本中的位置</span><span class="sxs-lookup"><span data-stu-id="c6fe1-112">Location in literal</span></span>|<span data-ttu-id="c6fe1-113">表达式的类型</span><span class="sxs-lookup"><span data-stu-id="c6fe1-113">Type of expression</span></span>|<span data-ttu-id="c6fe1-114">处理`Nothing`</span><span class="sxs-lookup"><span data-stu-id="c6fe1-114">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="c6fe1-115">XML 元素名称</span><span class="sxs-lookup"><span data-stu-id="c6fe1-115">XML element name</span></span>|<span data-ttu-id="c6fe1-116"><xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="c6fe1-116"><xref:System.Xml.Linq.XName></span></span>|<span data-ttu-id="c6fe1-117">错误</span><span class="sxs-lookup"><span data-stu-id="c6fe1-117">Error</span></span>|  
|<span data-ttu-id="c6fe1-118">XML 元素内容</span><span class="sxs-lookup"><span data-stu-id="c6fe1-118">XML element content</span></span>|<span data-ttu-id="c6fe1-119">`Object`或数组`Object`</span><span class="sxs-lookup"><span data-stu-id="c6fe1-119">`Object` or array of `Object`</span></span>|<span data-ttu-id="c6fe1-120">忽略</span><span class="sxs-lookup"><span data-stu-id="c6fe1-120">Ignored</span></span>|  
|<span data-ttu-id="c6fe1-121">XML 元素特性名</span><span class="sxs-lookup"><span data-stu-id="c6fe1-121">XML element attribute name</span></span>|<span data-ttu-id="c6fe1-122"><xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="c6fe1-122"><xref:System.Xml.Linq.XName></span></span>|<span data-ttu-id="c6fe1-123">错误，除非也是属性值`Nothing`</span><span class="sxs-lookup"><span data-stu-id="c6fe1-123">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="c6fe1-124">XML 元素特性值</span><span class="sxs-lookup"><span data-stu-id="c6fe1-124">XML element attribute value</span></span>|`Object`|<span data-ttu-id="c6fe1-125">忽略的属性声明</span><span class="sxs-lookup"><span data-stu-id="c6fe1-125">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="c6fe1-126">XML 元素特性</span><span class="sxs-lookup"><span data-stu-id="c6fe1-126">XML element attribute</span></span>|<span data-ttu-id="c6fe1-127"><xref:System.Xml.Linq.XAttribute>或集合<xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="c6fe1-127"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="c6fe1-128">忽略</span><span class="sxs-lookup"><span data-stu-id="c6fe1-128">Ignored</span></span>|  
|<span data-ttu-id="c6fe1-129">XML 文档根元素</span><span class="sxs-lookup"><span data-stu-id="c6fe1-129">XML document root element</span></span>|<span data-ttu-id="c6fe1-130"><xref:System.Xml.Linq.XElement>或者一个<xref:System.Xml.Linq.XElement>对象和任意数目的<xref:System.Xml.Linq.XProcessingInstruction>和<xref:System.Xml.Linq.XComment>对象</xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XElement>的集合</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c6fe1-130"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="c6fe1-131">忽略</span><span class="sxs-lookup"><span data-stu-id="c6fe1-131">Ignored</span></span>|  
  
-   <span data-ttu-id="c6fe1-132">XML 元素名称中的嵌入式表达式的示例︰</span><span class="sxs-lookup"><span data-stu-id="c6fe1-132">Example of an embedded expression in an XML element name:</span></span>  
  
     <span data-ttu-id="c6fe1-133">[!code-vb[VbXMLSamples #&32;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c6fe1-133">[!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]</span></span>  
  
-   <span data-ttu-id="c6fe1-134">XML 元素内容中的嵌入式表达式的示例︰</span><span class="sxs-lookup"><span data-stu-id="c6fe1-134">Example of an embedded expression in the content of an XML element:</span></span>  
  
     <span data-ttu-id="c6fe1-135">[!code-vb[VbXMLSamples 第&33;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c6fe1-135">[!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]</span></span>  
  
-   <span data-ttu-id="c6fe1-136">XML 元素特性名称中的嵌入式表达式的示例︰</span><span class="sxs-lookup"><span data-stu-id="c6fe1-136">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     <span data-ttu-id="c6fe1-137">[!code-vb[VbXMLSamples #&34;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="c6fe1-137">[!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]</span></span>  
  
-   <span data-ttu-id="c6fe1-138">XML 元素特性值中的嵌入式表达式的示例︰</span><span class="sxs-lookup"><span data-stu-id="c6fe1-138">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     <span data-ttu-id="c6fe1-139">[!code-vb[VbXMLSamples #&35;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="c6fe1-139">[!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]</span></span>  
  
-   <span data-ttu-id="c6fe1-140">在 XML 元素特性中的嵌入式表达式的示例︰</span><span class="sxs-lookup"><span data-stu-id="c6fe1-140">Example of an embedded expression in an XML element attribute:</span></span>  
  
     <span data-ttu-id="c6fe1-141">[!code-vb[VbXMLSamples #&36;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="c6fe1-141">[!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]</span></span>  
  
-   <span data-ttu-id="c6fe1-142">XML 文档根元素中的嵌入式表达式的示例︰</span><span class="sxs-lookup"><span data-stu-id="c6fe1-142">Example of an embedded expression in an XML document root element:</span></span>  
  
     <span data-ttu-id="c6fe1-143">[!code-vb[VbXMLSamples #&37;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="c6fe1-143">[!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]</span></span>  
  
 <span data-ttu-id="c6fe1-144">如果您启用`Option Strict`，编译器会检查每个嵌入的表达式的类型加宽到所需的类型。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-144">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="c6fe1-145">唯一的例外是，代码将运行时，会验证 XML 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-145">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="c6fe1-146">如果您的情况下编译`Option Strict`，可以嵌入类型的表达式`Object`并在运行时验证它们的类型。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-146">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="c6fe1-147">可选的内容的位置中嵌入表达式包含`Nothing`将被忽略。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-147">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="c6fe1-148">这意味着无需检查元素内容、 属性值，并且数组元素不是`Nothing`使用 XML 文本之前。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-148">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="c6fe1-149">所需值，例如，元素和属性名称不能为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-149">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="c6fe1-150">有关在特定类型的文本中使用嵌入式的表达式的详细信息，请参阅[XML 文档文本](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)， [XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-150">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="c6fe1-151">作用域规则</span><span class="sxs-lookup"><span data-stu-id="c6fe1-151">Scoping Rules</span></span>  
 <span data-ttu-id="c6fe1-152">编译器将每个 XML 文本转换为相应的文本类型的构造函数调用。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-152">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="c6fe1-153">文本内容和 XML 文本中嵌入的表达式作为参数传递给构造函数。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-153">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="c6fe1-154">这意味着所有[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]可用于 XML 文本的编程元素也都可在其嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-154">This means that all [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="c6fe1-155">在 XML 文本中，可以用声明的前缀的 XML 命名空间来访问`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-155">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="c6fe1-156">您可以声明新的 XML 命名空间前缀，或现有的 XML 命名空间前缀，使用元素中的卷影`xmlns`属性。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-156">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="c6fe1-157">新的命名空间位于该元素的子节点但不是属于 XML 文本中嵌入的表达式。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-157">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6fe1-158">当使用声明 XML 命名空间前缀`xmlns`命名空间属性，属性值必须是常量字符串。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-158">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="c6fe1-159">在这方面，使用`xmlns`属性是类似于使用`Imports`语句声明 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-159">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="c6fe1-160">不能使用嵌入式的表达式来指定 XML 命名空间值。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-160">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6fe1-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6fe1-161">See Also</span></span>  
 <span data-ttu-id="c6fe1-162">[在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="c6fe1-162">[Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="c6fe1-163"> [XML 文档文本](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span><span class="sxs-lookup"><span data-stu-id="c6fe1-163"> [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span></span>  
<span data-ttu-id="c6fe1-164"> [XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="c6fe1-164"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="c6fe1-165"> [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c6fe1-165"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="c6fe1-166"> [Imports 语句（.NET 命名空间和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="c6fe1-166"> [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="c6fe1-167"> [XML 文本概述](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c6fe1-167"> [XML Literals Overview](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)</span></span>
