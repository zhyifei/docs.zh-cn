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
ms.openlocfilehash: de5825a6af1dd1b93c3c85651125cf817dc564f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="4b461-102">XML 元素文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b461-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="4b461-103">表示的文字值<xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="4b461-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b461-104">语法</span><span class="sxs-lookup"><span data-stu-id="4b461-104">Syntax</span></span>  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="4b461-105">部件</span><span class="sxs-lookup"><span data-stu-id="4b461-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="4b461-106">必需。</span><span class="sxs-lookup"><span data-stu-id="4b461-106">Required.</span></span> <span data-ttu-id="4b461-107">将打开起始元素标记。</span><span class="sxs-lookup"><span data-stu-id="4b461-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="4b461-108">必需。</span><span class="sxs-lookup"><span data-stu-id="4b461-108">Required.</span></span> <span data-ttu-id="4b461-109">元素名称。</span><span class="sxs-lookup"><span data-stu-id="4b461-109">Name of the element.</span></span> <span data-ttu-id="4b461-110">格式为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="4b461-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="4b461-111">对于元素名称，在窗体的文字文本`[ePrefix:]eName`，其中：</span><span class="sxs-lookup"><span data-stu-id="4b461-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>  
  
        |<span data-ttu-id="4b461-112">部件</span><span class="sxs-lookup"><span data-stu-id="4b461-112">Part</span></span>|<span data-ttu-id="4b461-113">描述</span><span class="sxs-lookup"><span data-stu-id="4b461-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="4b461-114">可选。</span><span class="sxs-lookup"><span data-stu-id="4b461-114">Optional.</span></span> <span data-ttu-id="4b461-115">元素的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="4b461-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="4b461-116">必须使用定义的全局 XML 命名空间`Imports`语句文件中或在项目级别或在此元素或父元素中定义的本地 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="4b461-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="4b461-117">必需。</span><span class="sxs-lookup"><span data-stu-id="4b461-117">Required.</span></span> <span data-ttu-id="4b461-118">元素名称。</span><span class="sxs-lookup"><span data-stu-id="4b461-118">Name of the element.</span></span> <span data-ttu-id="4b461-119">格式为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="4b461-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="4b461-120">-文字文本。</span><span class="sxs-lookup"><span data-stu-id="4b461-120">-   Literal text.</span></span> <span data-ttu-id="4b461-121">请参阅[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="4b461-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="4b461-122">嵌入形式的表达式`<%= eNameExp %>`。</span><span class="sxs-lookup"><span data-stu-id="4b461-122">-   Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="4b461-123">一种`eNameExp`必须`String`或隐式转换为类型<xref:System.Xml.Linq.XName>。</span><span class="sxs-lookup"><span data-stu-id="4b461-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="4b461-124">嵌入形式的表达式`<%= nameExp %>`。</span><span class="sxs-lookup"><span data-stu-id="4b461-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="4b461-125">一种`nameExp`必须`String`或隐式转换为类型<xref:System.Xml.Linq.XName>。</span><span class="sxs-lookup"><span data-stu-id="4b461-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="4b461-126">中的元素结束标记不允许嵌入式的表达式。</span><span class="sxs-lookup"><span data-stu-id="4b461-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="4b461-127">可选。</span><span class="sxs-lookup"><span data-stu-id="4b461-127">Optional.</span></span> <span data-ttu-id="4b461-128">在文本中声明的属性列表。</span><span class="sxs-lookup"><span data-stu-id="4b461-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="4b461-129">每个`attribute`具有以下语法之一：</span><span class="sxs-lookup"><span data-stu-id="4b461-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="4b461-130">属性的窗体分配`[aPrefix:]aName=aValue`，其中：</span><span class="sxs-lookup"><span data-stu-id="4b461-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>  
  
        |<span data-ttu-id="4b461-131">部件</span><span class="sxs-lookup"><span data-stu-id="4b461-131">Part</span></span>|<span data-ttu-id="4b461-132">描述</span><span class="sxs-lookup"><span data-stu-id="4b461-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="4b461-133">可选。</span><span class="sxs-lookup"><span data-stu-id="4b461-133">Optional.</span></span> <span data-ttu-id="4b461-134">该属性的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="4b461-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="4b461-135">必须使用定义的全局 XML 命名空间`Imports`语句或在此元素或父元素中定义的本地 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="4b461-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="4b461-136">必需。</span><span class="sxs-lookup"><span data-stu-id="4b461-136">Required.</span></span> <span data-ttu-id="4b461-137">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="4b461-137">Name of the attribute.</span></span> <span data-ttu-id="4b461-138">格式为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="4b461-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="4b461-139">-文字文本。</span><span class="sxs-lookup"><span data-stu-id="4b461-139">-   Literal text.</span></span> <span data-ttu-id="4b461-140">请参阅[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="4b461-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="4b461-141">嵌入形式的表达式`<%= aNameExp %>`。</span><span class="sxs-lookup"><span data-stu-id="4b461-141">-   Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="4b461-142">一种`aNameExp`必须`String`或隐式转换为类型<xref:System.Xml.Linq.XName>。</span><span class="sxs-lookup"><span data-stu-id="4b461-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="4b461-143">可选。</span><span class="sxs-lookup"><span data-stu-id="4b461-143">Optional.</span></span> <span data-ttu-id="4b461-144">属性值。</span><span class="sxs-lookup"><span data-stu-id="4b461-144">Value of the attribute.</span></span> <span data-ttu-id="4b461-145">格式为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="4b461-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="4b461-146">-文字文本，用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="4b461-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="4b461-147">嵌入形式的表达式`<%= aValueExp %>`。</span><span class="sxs-lookup"><span data-stu-id="4b461-147">-   Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="4b461-148">可以是任何类型。</span><span class="sxs-lookup"><span data-stu-id="4b461-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="4b461-149">嵌入形式的表达式`<%= aExp %>`。</span><span class="sxs-lookup"><span data-stu-id="4b461-149">Embedded expression of the form `<%= aExp %>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="4b461-150">可选。</span><span class="sxs-lookup"><span data-stu-id="4b461-150">Optional.</span></span> <span data-ttu-id="4b461-151">指示元素是空元素，但不包括内容。</span><span class="sxs-lookup"><span data-stu-id="4b461-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="4b461-152">必需。</span><span class="sxs-lookup"><span data-stu-id="4b461-152">Required.</span></span> <span data-ttu-id="4b461-153">结束开始标记或空元素标记。</span><span class="sxs-lookup"><span data-stu-id="4b461-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="4b461-154">可选。</span><span class="sxs-lookup"><span data-stu-id="4b461-154">Optional.</span></span> <span data-ttu-id="4b461-155">元素的内容。</span><span class="sxs-lookup"><span data-stu-id="4b461-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="4b461-156">每个`content`可以是以下之一：</span><span class="sxs-lookup"><span data-stu-id="4b461-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="4b461-157">文字文本。</span><span class="sxs-lookup"><span data-stu-id="4b461-157">Literal text.</span></span> <span data-ttu-id="4b461-158">中的所有空白`elementContents`变得很大，如果没有任何文字文本。</span><span class="sxs-lookup"><span data-stu-id="4b461-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="4b461-159">嵌入形式的表达式`<%= contentExp %>`。</span><span class="sxs-lookup"><span data-stu-id="4b461-159">Embedded expression of the form `<%= contentExp %>`.</span></span>  
  
    -   <span data-ttu-id="4b461-160">XML 元素文本。</span><span class="sxs-lookup"><span data-stu-id="4b461-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="4b461-161">XML 注释文本。</span><span class="sxs-lookup"><span data-stu-id="4b461-161">XML comment literal.</span></span> <span data-ttu-id="4b461-162">请参阅[XML 注释文本](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="4b461-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="4b461-163">XML 处理指令文本。</span><span class="sxs-lookup"><span data-stu-id="4b461-163">XML processing instruction literal.</span></span> <span data-ttu-id="4b461-164">请参阅[XML 处理指令文本](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="4b461-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="4b461-165">XML CDATA 文本。</span><span class="sxs-lookup"><span data-stu-id="4b461-165">XML CDATA literal.</span></span> <span data-ttu-id="4b461-166">请参阅[XML CDATA 文本](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="4b461-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   `</[name]>`  
  
     <span data-ttu-id="4b461-167">可选。</span><span class="sxs-lookup"><span data-stu-id="4b461-167">Optional.</span></span> <span data-ttu-id="4b461-168">表示元素的结束标记。</span><span class="sxs-lookup"><span data-stu-id="4b461-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="4b461-169">可选`name`嵌入表达式的结果时，不允许使用参数。</span><span class="sxs-lookup"><span data-stu-id="4b461-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b461-170">返回值</span><span class="sxs-lookup"><span data-stu-id="4b461-170">Return Value</span></span>  
 <span data-ttu-id="4b461-171">一个 <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="4b461-171">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b461-172">备注</span><span class="sxs-lookup"><span data-stu-id="4b461-172">Remarks</span></span>  
 <span data-ttu-id="4b461-173">你可以使用 XML 元素文本语法创建<xref:System.Xml.Linq.XElement>在代码中的对象。</span><span class="sxs-lookup"><span data-stu-id="4b461-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b461-174">XML 文本可以跨多行，而无需使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="4b461-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="4b461-175">此功能，可将内容复制从 XML 文档并将其粘贴直接到[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]程序。</span><span class="sxs-lookup"><span data-stu-id="4b461-175">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="4b461-176">嵌入表达式的窗体`<%= exp %>`使您能够将动态信息添加到 XML 元素文本。</span><span class="sxs-lookup"><span data-stu-id="4b461-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="4b461-177">有关详细信息，请参阅[XML 中的嵌入式表达式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="4b461-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="4b461-178">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器将调用转换为 XML 元素文本<xref:System.Xml.Linq.XElement.%23ctor%2A>构造函数，如果它是必需的<xref:System.Xml.Linq.XAttribute.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="4b461-178">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="4b461-179">XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="4b461-179">XML Namespaces</span></span>  
 <span data-ttu-id="4b461-180">当你需要创建包含从代码中多次相同的命名空间的元素的 XML 文本，XML 命名空间前缀非常有用。</span><span class="sxs-lookup"><span data-stu-id="4b461-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="4b461-181">你可以使用全局 XML 命名空间前缀，使用定义`Imports`语句或使用定义的本地前缀`xmlns:xmlPrefix="xmlNamespace"`属性语法。</span><span class="sxs-lookup"><span data-stu-id="4b461-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="4b461-182">有关详细信息，请参阅[Imports 语句 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="4b461-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="4b461-183">XML 命名空间的范围规则，根据本地前缀优先于全局前缀。</span><span class="sxs-lookup"><span data-stu-id="4b461-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="4b461-184">但是，如果 XML 文本定义的 XML 命名空间，该命名空间不可用来显示在嵌入式表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="4b461-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="4b461-185">嵌入的表达式可以访问仅全局 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="4b461-185">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="4b461-186">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器将转换为生成的代码中的一个本地命名空间定义 XML 文本使用每个全局 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="4b461-186">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="4b461-187">未使用的全局 XML 命名空间不会出现在生成的代码。</span><span class="sxs-lookup"><span data-stu-id="4b461-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b461-188">示例</span><span class="sxs-lookup"><span data-stu-id="4b461-188">Example</span></span>  
 <span data-ttu-id="4b461-189">下面的示例演示如何创建具有两个嵌套的空元素的简单 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="4b461-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 <span data-ttu-id="4b461-190">此示例显示以下文本。</span><span class="sxs-lookup"><span data-stu-id="4b461-190">The example displays the following text.</span></span> <span data-ttu-id="4b461-191">请注意，文本将保留为空的元素的结构。</span><span class="sxs-lookup"><span data-stu-id="4b461-191">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="4b461-192">示例</span><span class="sxs-lookup"><span data-stu-id="4b461-192">Example</span></span>  
 <span data-ttu-id="4b461-193">下面的示例演示如何使用嵌入式的表达式命名元素和创建属性。</span><span class="sxs-lookup"><span data-stu-id="4b461-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 <span data-ttu-id="4b461-194">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="4b461-194">This code displays the following text:</span></span>  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="4b461-195">示例</span><span class="sxs-lookup"><span data-stu-id="4b461-195">Example</span></span>  
 <span data-ttu-id="4b461-196">下面的示例声明 `ns` 作为 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="4b461-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="4b461-197">然后，它将使用的命名空间前缀来创建 XML 文本，并显示元素的最终形式。</span><span class="sxs-lookup"><span data-stu-id="4b461-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]  
  
 <span data-ttu-id="4b461-198">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="4b461-198">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="4b461-199">请注意编译器为 XML 命名空间的前缀定义转换的全局 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="4b461-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="4b461-200">\<Ns:middle > 元素重新定义的 XML 命名空间前缀\<ns:inner1 > 元素。</span><span class="sxs-lookup"><span data-stu-id="4b461-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="4b461-201">但是， \<ns:inner2 > 元素使用定义的命名空间`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="4b461-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b461-202">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b461-202">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="4b461-203">已声明的 XML 元素和特性的名称</span><span class="sxs-lookup"><span data-stu-id="4b461-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [<span data-ttu-id="4b461-204">XML 注释文本</span><span class="sxs-lookup"><span data-stu-id="4b461-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [<span data-ttu-id="4b461-205">XML CDATA 文本</span><span class="sxs-lookup"><span data-stu-id="4b461-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)  
 [<span data-ttu-id="4b461-206">XML 文本</span><span class="sxs-lookup"><span data-stu-id="4b461-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="4b461-207">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="4b461-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="4b461-208">XML 中的嵌入式表达式</span><span class="sxs-lookup"><span data-stu-id="4b461-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="4b461-209">Imports 语句（XML 命名空间）</span><span class="sxs-lookup"><span data-stu-id="4b461-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
