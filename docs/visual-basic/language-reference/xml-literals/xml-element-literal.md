---
title: XML 元素文本 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: 32
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 58b11c61253b199bdeeb2f373eed5f6a358b9e0e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="bb5cf-102">XML 元素文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb5cf-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="bb5cf-103">表示的文字值<xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb5cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb5cf-104">Syntax</span></span>  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="bb5cf-105">部件</span><span class="sxs-lookup"><span data-stu-id="bb5cf-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="bb5cf-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-106">Required.</span></span> <span data-ttu-id="bb5cf-107">将打开起始元素标记。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="bb5cf-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-108">Required.</span></span> <span data-ttu-id="bb5cf-109">元素名称。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-109">Name of the element.</span></span> <span data-ttu-id="bb5cf-110">格式为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="bb5cf-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="bb5cf-111">对于元素名称，在窗体的文字文本`[ePrefix:]eName`，其中：</span><span class="sxs-lookup"><span data-stu-id="bb5cf-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>  
  
        |<span data-ttu-id="bb5cf-112">部件</span><span class="sxs-lookup"><span data-stu-id="bb5cf-112">Part</span></span>|<span data-ttu-id="bb5cf-113">描述</span><span class="sxs-lookup"><span data-stu-id="bb5cf-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="bb5cf-114">可选。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-114">Optional.</span></span> <span data-ttu-id="bb5cf-115">元素的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="bb5cf-116">必须使用定义的全局 XML 命名空间`Imports`语句文件中或在项目级别或在此元素或父元素中定义的本地 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="bb5cf-117">必须的。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-117">Required.</span></span> <span data-ttu-id="bb5cf-118">元素名称。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-118">Name of the element.</span></span> <span data-ttu-id="bb5cf-119">格式为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="bb5cf-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="bb5cf-120">-文字文本。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-120">-   Literal text.</span></span> <span data-ttu-id="bb5cf-121">请参阅[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="bb5cf-122">嵌入形式的表达式`<%= eNameExp %>`。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-122">-   Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="bb5cf-123">一种`eNameExp`必须`String`或隐式转换为类型<xref:System.Xml.Linq.XName>。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="bb5cf-124">嵌入形式的表达式`<%= nameExp %>`。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="bb5cf-125">一种`nameExp`必须`String`或隐式转换为类型<xref:System.Xml.Linq.XName>。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="bb5cf-126">中的元素结束标记不允许嵌入式的表达式。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="bb5cf-127">可选。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-127">Optional.</span></span> <span data-ttu-id="bb5cf-128">在文本中声明的属性列表。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="bb5cf-129">每个`attribute`具有以下语法之一：</span><span class="sxs-lookup"><span data-stu-id="bb5cf-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="bb5cf-130">属性的窗体分配`[aPrefix:]aName=aValue`，其中：</span><span class="sxs-lookup"><span data-stu-id="bb5cf-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>  
  
        |<span data-ttu-id="bb5cf-131">部件</span><span class="sxs-lookup"><span data-stu-id="bb5cf-131">Part</span></span>|<span data-ttu-id="bb5cf-132">描述</span><span class="sxs-lookup"><span data-stu-id="bb5cf-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="bb5cf-133">可选。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-133">Optional.</span></span> <span data-ttu-id="bb5cf-134">该属性的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="bb5cf-135">必须使用定义的全局 XML 命名空间`Imports`语句或在此元素或父元素中定义的本地 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="bb5cf-136">必须的。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-136">Required.</span></span> <span data-ttu-id="bb5cf-137">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-137">Name of the attribute.</span></span> <span data-ttu-id="bb5cf-138">格式为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="bb5cf-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="bb5cf-139">-文字文本。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-139">-   Literal text.</span></span> <span data-ttu-id="bb5cf-140">请参阅[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="bb5cf-141">嵌入形式的表达式`<%= aNameExp %>`。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-141">-   Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="bb5cf-142">一种`aNameExp`必须`String`或隐式转换为类型<xref:System.Xml.Linq.XName>。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="bb5cf-143">可选。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-143">Optional.</span></span> <span data-ttu-id="bb5cf-144">属性值。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-144">Value of the attribute.</span></span> <span data-ttu-id="bb5cf-145">格式为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="bb5cf-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="bb5cf-146">-文字文本，用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="bb5cf-147">嵌入形式的表达式`<%= aValueExp %>`。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-147">-   Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="bb5cf-148">可以是任何类型。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="bb5cf-149">嵌入形式的表达式`<%= aExp %>`。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-149">Embedded expression of the form `<%= aExp %>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="bb5cf-150">可选。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-150">Optional.</span></span> <span data-ttu-id="bb5cf-151">指示元素是空元素，但不包括内容。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="bb5cf-152">必须的。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-152">Required.</span></span> <span data-ttu-id="bb5cf-153">结束开始标记或空元素标记。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="bb5cf-154">可选。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-154">Optional.</span></span> <span data-ttu-id="bb5cf-155">元素的内容。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="bb5cf-156">每个`content`可以是以下之一：</span><span class="sxs-lookup"><span data-stu-id="bb5cf-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="bb5cf-157">文字文本。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-157">Literal text.</span></span> <span data-ttu-id="bb5cf-158">中的所有空白`elementContents`变得很大，如果没有任何文字文本。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="bb5cf-159">嵌入形式的表达式`<%= contentExp %>`。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-159">Embedded expression of the form `<%= contentExp %>`.</span></span>  
  
    -   <span data-ttu-id="bb5cf-160">XML 元素文本。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="bb5cf-161">XML 注释文本。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-161">XML comment literal.</span></span> <span data-ttu-id="bb5cf-162">请参阅[XML 注释文本](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="bb5cf-163">XML 处理指令文本。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-163">XML processing instruction literal.</span></span> <span data-ttu-id="bb5cf-164">请参阅[XML 处理指令文本](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="bb5cf-165">XML CDATA 文本。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-165">XML CDATA literal.</span></span> <span data-ttu-id="bb5cf-166">请参阅[XML CDATA 文本](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   `</[name]>`  
  
     <span data-ttu-id="bb5cf-167">可选。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-167">Optional.</span></span> <span data-ttu-id="bb5cf-168">表示元素的结束标记。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="bb5cf-169">可选`name`嵌入表达式的结果时，不允许使用参数。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb5cf-170">返回值</span><span class="sxs-lookup"><span data-stu-id="bb5cf-170">Return Value</span></span>  
 <span data-ttu-id="bb5cf-171">一个 <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-171">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb5cf-172">备注</span><span class="sxs-lookup"><span data-stu-id="bb5cf-172">Remarks</span></span>  
 <span data-ttu-id="bb5cf-173">你可以使用 XML 元素文本语法创建<xref:System.Xml.Linq.XElement>在代码中的对象。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb5cf-174">XML 文本可以跨多行，而无需使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="bb5cf-175">此功能，可从 XML 文档中复制内容，然后将其粘贴到 Visual Basic 程序直接。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="bb5cf-176">嵌入表达式的窗体`<%= exp %>`使您能够将动态信息添加到 XML 元素文本。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="bb5cf-177">有关详细信息，请参阅[XML 中的嵌入式表达式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="bb5cf-178">Visual Basic 编译器将调用转换为 XML 元素文本<xref:System.Xml.Linq.XElement.%23ctor%2A>构造函数，如果它是必需的<xref:System.Xml.Linq.XAttribute.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="bb5cf-179">XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="bb5cf-179">XML Namespaces</span></span>  
 <span data-ttu-id="bb5cf-180">当你需要创建包含从代码中多次相同的命名空间的元素的 XML 文本，XML 命名空间前缀非常有用。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="bb5cf-181">你可以使用全局 XML 命名空间前缀，使用定义`Imports`语句或使用定义的本地前缀`xmlns:xmlPrefix="xmlNamespace"`属性语法。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="bb5cf-182">有关详细信息，请参阅[Imports 语句 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="bb5cf-183">XML 命名空间的范围规则，根据本地前缀优先于全局前缀。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="bb5cf-184">但是，如果 XML 文本定义的 XML 命名空间，该命名空间不可用来显示在嵌入式表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="bb5cf-185">嵌入的表达式可以访问仅全局 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-185">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="bb5cf-186">Visual Basic 编译器将转换为生成的代码中的一个本地命名空间定义 XML 文本使用每个全局 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="bb5cf-187">未使用的全局 XML 命名空间不会出现在生成的代码。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb5cf-188">示例</span><span class="sxs-lookup"><span data-stu-id="bb5cf-188">Example</span></span>  
 <span data-ttu-id="bb5cf-189">下面的示例演示如何创建具有两个嵌套的空元素的简单 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 <span data-ttu-id="bb5cf-190">此示例显示以下文本。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-190">The example displays the following text.</span></span> <span data-ttu-id="bb5cf-191">请注意，文本将保留为空的元素的结构。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-191">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="bb5cf-192">示例</span><span class="sxs-lookup"><span data-stu-id="bb5cf-192">Example</span></span>  
 <span data-ttu-id="bb5cf-193">下面的示例演示如何使用嵌入式的表达式命名元素和创建属性。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 <span data-ttu-id="bb5cf-194">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="bb5cf-194">This code displays the following text:</span></span>  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="bb5cf-195">示例</span><span class="sxs-lookup"><span data-stu-id="bb5cf-195">Example</span></span>  
 <span data-ttu-id="bb5cf-196">下面的示例声明 `ns` 作为 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="bb5cf-197">然后，它将使用的命名空间前缀来创建 XML 文本，并显示元素的最终形式。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]  
  
 <span data-ttu-id="bb5cf-198">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="bb5cf-198">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="bb5cf-199">请注意编译器为 XML 命名空间的前缀定义转换的全局 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="bb5cf-200">\<Ns:middle > 元素重新定义的 XML 命名空间前缀\<ns:inner1 > 元素。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="bb5cf-201">但是， \<ns:inner2 > 元素使用定义的命名空间`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="bb5cf-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5cf-202">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb5cf-202">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="bb5cf-203">已声明的 XML 元素和特性的名称</span><span class="sxs-lookup"><span data-stu-id="bb5cf-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [<span data-ttu-id="bb5cf-204">XML 注释文本</span><span class="sxs-lookup"><span data-stu-id="bb5cf-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [<span data-ttu-id="bb5cf-205">XML CDATA 文本</span><span class="sxs-lookup"><span data-stu-id="bb5cf-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)  
 [<span data-ttu-id="bb5cf-206">XML 文本</span><span class="sxs-lookup"><span data-stu-id="bb5cf-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="bb5cf-207">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="bb5cf-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="bb5cf-208">XML 中的嵌入式表达式</span><span class="sxs-lookup"><span data-stu-id="bb5cf-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="bb5cf-209">Imports 语句（XML 命名空间）</span><span class="sxs-lookup"><span data-stu-id="bb5cf-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
