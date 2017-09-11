---
title: "XML 元素文本 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralElement
dev_langs:
- VB
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: 32
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
ms.openlocfilehash: d5cf769a1e3f668652d1eb4551058deba38a8acf
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="25535-102">XML 元素文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25535-102">XML Element Literal (Visual Basic)</span></span>
<span data-ttu-id="25535-103">表示的文字值<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="25535-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25535-104">语法</span><span class="sxs-lookup"><span data-stu-id="25535-104">Syntax</span></span>  
  
```  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="25535-105">部件</span><span class="sxs-lookup"><span data-stu-id="25535-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="25535-106">必需。</span><span class="sxs-lookup"><span data-stu-id="25535-106">Required.</span></span> <span data-ttu-id="25535-107">打开元素开始标记。</span><span class="sxs-lookup"><span data-stu-id="25535-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="25535-108">必需。</span><span class="sxs-lookup"><span data-stu-id="25535-108">Required.</span></span> <span data-ttu-id="25535-109">元素名称。</span><span class="sxs-lookup"><span data-stu-id="25535-109">Name of the element.</span></span> <span data-ttu-id="25535-110">格式为以下项之一︰</span><span class="sxs-lookup"><span data-stu-id="25535-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="25535-111">元素名称、 窗体的文字文本 [`ePrefix``:`]`eName`，其中︰</span><span class="sxs-lookup"><span data-stu-id="25535-111">Literal text for the element name, of the form [`ePrefix``:`]`eName`, where:</span></span>  
  
        |<span data-ttu-id="25535-112">部件</span><span class="sxs-lookup"><span data-stu-id="25535-112">Part</span></span>|<span data-ttu-id="25535-113">说明</span><span class="sxs-lookup"><span data-stu-id="25535-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="25535-114">可选。</span><span class="sxs-lookup"><span data-stu-id="25535-114">Optional.</span></span> <span data-ttu-id="25535-115">该元素的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="25535-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="25535-116">必须是全局的 XML 命名空间定义与`Imports`语句在文件中或在项目级别或在此元素或其父元素中定义一个本地 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="25535-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="25535-117">必需。</span><span class="sxs-lookup"><span data-stu-id="25535-117">Required.</span></span> <span data-ttu-id="25535-118">元素名称。</span><span class="sxs-lookup"><span data-stu-id="25535-118">Name of the element.</span></span> <span data-ttu-id="25535-119">格式为以下项之一︰</span><span class="sxs-lookup"><span data-stu-id="25535-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="25535-120">文本。</span><span class="sxs-lookup"><span data-stu-id="25535-120">-   Literal text.</span></span> <span data-ttu-id="25535-121">请参阅[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="25535-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="25535-122">嵌入形式的表达式`<%=`e`NameExp` `%>`。</span><span class="sxs-lookup"><span data-stu-id="25535-122">-   Embedded expression of the form `<%=` e`NameExp` `%>`.</span></span> <span data-ttu-id="25535-123">一种`eNameExp`必须`String`类型或类型的隐式转换为<xref:System.Xml.Linq.XName>。</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="25535-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="25535-124">窗体的嵌入式表达式`<%=` `nameExp` `%>`。</span><span class="sxs-lookup"><span data-stu-id="25535-124">Embedded expression of the form `<%=` `nameExp` `%>`.</span></span> <span data-ttu-id="25535-125">一种`nameExp`必须`String`或隐式转换为<xref:System.Xml.Linq.XName>。</xref:System.Xml.Linq.XName>类型</span><span class="sxs-lookup"><span data-stu-id="25535-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="25535-126">元素的结束标记中不允许的嵌入式的表达式。</span><span class="sxs-lookup"><span data-stu-id="25535-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="25535-127">可选。</span><span class="sxs-lookup"><span data-stu-id="25535-127">Optional.</span></span> <span data-ttu-id="25535-128">在文本中声明的属性列表。</span><span class="sxs-lookup"><span data-stu-id="25535-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="25535-129">每个`attribute`具有以下语法之一︰</span><span class="sxs-lookup"><span data-stu-id="25535-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="25535-130">属性指定窗体 [`aPrefix``:`]`aName``=``aValue`，其中︰</span><span class="sxs-lookup"><span data-stu-id="25535-130">Attribute assignment, of the form [`aPrefix``:`]`aName``=``aValue`, where:</span></span>  
  
        |<span data-ttu-id="25535-131">部件</span><span class="sxs-lookup"><span data-stu-id="25535-131">Part</span></span>|<span data-ttu-id="25535-132">描述</span><span class="sxs-lookup"><span data-stu-id="25535-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="25535-133">可选。</span><span class="sxs-lookup"><span data-stu-id="25535-133">Optional.</span></span> <span data-ttu-id="25535-134">该属性的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="25535-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="25535-135">必须是全局的 XML 命名空间定义与`Imports`语句或在此元素或其父元素中定义一个本地 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="25535-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="25535-136">必需。</span><span class="sxs-lookup"><span data-stu-id="25535-136">Required.</span></span> <span data-ttu-id="25535-137">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="25535-137">Name of the attribute.</span></span> <span data-ttu-id="25535-138">格式为以下项之一︰</span><span class="sxs-lookup"><span data-stu-id="25535-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="25535-139">文本。</span><span class="sxs-lookup"><span data-stu-id="25535-139">-   Literal text.</span></span> <span data-ttu-id="25535-140">请参阅[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="25535-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="25535-141">嵌入形式的表达式`<%=` `aNameExp` `%>`。</span><span class="sxs-lookup"><span data-stu-id="25535-141">-   Embedded expression of the form `<%=` `aNameExp` `%>`.</span></span> <span data-ttu-id="25535-142">一种`aNameExp`必须`String`类型或类型的隐式转换为<xref:System.Xml.Linq.XName>。</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="25535-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="25535-143">可选。</span><span class="sxs-lookup"><span data-stu-id="25535-143">Optional.</span></span> <span data-ttu-id="25535-144">该属性的值。</span><span class="sxs-lookup"><span data-stu-id="25535-144">Value of the attribute.</span></span> <span data-ttu-id="25535-145">格式为以下项之一︰</span><span class="sxs-lookup"><span data-stu-id="25535-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="25535-146">的文字文本，用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="25535-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="25535-147">嵌入形式的表达式`<%=` `aValueExp` `%>`。</span><span class="sxs-lookup"><span data-stu-id="25535-147">-   Embedded expression of the form `<%=` `aValueExp` `%>`.</span></span> <span data-ttu-id="25535-148">可以是任何类型。</span><span class="sxs-lookup"><span data-stu-id="25535-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="25535-149">窗体的嵌入式表达式`<%=` `aExp` `%>`。</span><span class="sxs-lookup"><span data-stu-id="25535-149">Embedded expression of the form `<%=` `aExp` `%>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="25535-150">可选。</span><span class="sxs-lookup"><span data-stu-id="25535-150">Optional.</span></span> <span data-ttu-id="25535-151">指示元素是空的元素，而不包含内容。</span><span class="sxs-lookup"><span data-stu-id="25535-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="25535-152">必需。</span><span class="sxs-lookup"><span data-stu-id="25535-152">Required.</span></span> <span data-ttu-id="25535-153">结束开始标记或空元素标记。</span><span class="sxs-lookup"><span data-stu-id="25535-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="25535-154">可选。</span><span class="sxs-lookup"><span data-stu-id="25535-154">Optional.</span></span> <span data-ttu-id="25535-155">元素的内容。</span><span class="sxs-lookup"><span data-stu-id="25535-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="25535-156">每个`content`可以是以下之一︰</span><span class="sxs-lookup"><span data-stu-id="25535-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="25535-157">文字文本。</span><span class="sxs-lookup"><span data-stu-id="25535-157">Literal text.</span></span> <span data-ttu-id="25535-158">中的所有空白`elementContents`变得很大，如果没有任何文字文本。</span><span class="sxs-lookup"><span data-stu-id="25535-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="25535-159">窗体的嵌入式表达式`<%=` `contentExp` `%>`。</span><span class="sxs-lookup"><span data-stu-id="25535-159">Embedded expression of the form `<%=` `contentExp` `%>`.</span></span>  
  
    -   <span data-ttu-id="25535-160">XML 元素文本。</span><span class="sxs-lookup"><span data-stu-id="25535-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="25535-161">XML 注释文本。</span><span class="sxs-lookup"><span data-stu-id="25535-161">XML comment literal.</span></span> <span data-ttu-id="25535-162">请参阅[XML 注释文本](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="25535-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="25535-163">XML 处理指令文本。</span><span class="sxs-lookup"><span data-stu-id="25535-163">XML processing instruction literal.</span></span> <span data-ttu-id="25535-164">请参阅[XML 处理指令文本](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="25535-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="25535-165">XML CDATA 文本。</span><span class="sxs-lookup"><span data-stu-id="25535-165">XML CDATA literal.</span></span> <span data-ttu-id="25535-166">请参阅[XML CDATA 文本](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="25535-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   <span data-ttu-id="25535-167">`</`[`name`]`>`</span><span class="sxs-lookup"><span data-stu-id="25535-167">`</`[`name`]`>`</span></span>  
  
     <span data-ttu-id="25535-168">可选。</span><span class="sxs-lookup"><span data-stu-id="25535-168">Optional.</span></span> <span data-ttu-id="25535-169">表示该元素的结束标记。</span><span class="sxs-lookup"><span data-stu-id="25535-169">Represents the closing tag for the element.</span></span> <span data-ttu-id="25535-170">可选`name`的嵌入式表达式的结果时，不允许使用参数。</span><span class="sxs-lookup"><span data-stu-id="25535-170">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25535-171">返回值</span><span class="sxs-lookup"><span data-stu-id="25535-171">Return Value</span></span>  
 <span data-ttu-id="25535-172"><xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="25535-172">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25535-173">备注</span><span class="sxs-lookup"><span data-stu-id="25535-173">Remarks</span></span>  
 <span data-ttu-id="25535-174">可以使用 XML 元素文本语法创建<xref:System.Xml.Linq.XElement>您代码中的对象。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="25535-174">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25535-175">XML 文本可以跨多个行，而无需使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="25535-175">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="25535-176">此功能允许你复制内容的 XML 文档中，将其粘贴直接到[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]程序。</span><span class="sxs-lookup"><span data-stu-id="25535-176">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="25535-177">嵌入形式的表达式中`<%=` `exp` `%>`使您能够将动态信息添加到 XML 元素文本。</span><span class="sxs-lookup"><span data-stu-id="25535-177">Embedded expressions of the form `<%=` `exp` `%>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="25535-178">有关详细信息，请参阅[XML 中的嵌入式表达式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="25535-178">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="25535-179">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器将 XML 元素文本转换为对调用<xref:System.Xml.Linq.XElement.%23ctor%2A>构造函数，如有必要，<xref:System.Xml.Linq.XAttribute.%23ctor%2A>构造函数。</xref:System.Xml.Linq.XAttribute.%23ctor%2A> </xref:System.Xml.Linq.XElement.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="25535-179">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="25535-180">XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="25535-180">XML Namespaces</span></span>  
 <span data-ttu-id="25535-181">当您必须创建具有很多时候在代码中的同一个命名空间元素的 XML 文本时，XML 命名空间前缀非常有用。</span><span class="sxs-lookup"><span data-stu-id="25535-181">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="25535-182">可以使用全局 XML 命名空间前缀，您通过使用定义`Imports`语句或通过使用定义的本地前缀`xmlns:``xmlPrefix`="`xmlNamespace`"特性语法。</span><span class="sxs-lookup"><span data-stu-id="25535-182">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:``xmlPrefix`="`xmlNamespace`" attribute syntax.</span></span> <span data-ttu-id="25535-183">有关详细信息，请参阅[Imports 语句 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="25535-183">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="25535-184">XML 命名空间的范围规则，根据局部前缀优先于全局前缀。</span><span class="sxs-lookup"><span data-stu-id="25535-184">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="25535-185">但是，如果 XML 文本定义的 XML 命名空间，该命名空间不可用来显示在嵌入式表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="25535-185">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="25535-186">嵌入式的表达式可以访问仅全局 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="25535-186">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="25535-187">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器将转换为生成的代码中的一个本地命名空间定义的 XML 文本使用每个全局 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="25535-187">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="25535-188">未使用的全局 XML 命名空间不会出现在生成的代码。</span><span class="sxs-lookup"><span data-stu-id="25535-188">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25535-189">示例</span><span class="sxs-lookup"><span data-stu-id="25535-189">Example</span></span>  
 <span data-ttu-id="25535-190">下面的示例演示如何创建一个具有两个嵌套的空元素的简单 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="25535-190">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 <span data-ttu-id="25535-191">[!code-vb[VbXMLSamples #&20;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="25535-191">[!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]</span></span>  
  
 <span data-ttu-id="25535-192">此示例显示以下文本。</span><span class="sxs-lookup"><span data-stu-id="25535-192">The example displays the following text.</span></span> <span data-ttu-id="25535-193">请注意，文本将保留为空的元素的结构。</span><span class="sxs-lookup"><span data-stu-id="25535-193">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="25535-194">示例</span><span class="sxs-lookup"><span data-stu-id="25535-194">Example</span></span>  
 <span data-ttu-id="25535-195">下面的示例演示如何使用嵌入式的表达式来命名某个元素和创建属性。</span><span class="sxs-lookup"><span data-stu-id="25535-195">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 <span data-ttu-id="25535-196">[!code-vb[VbXMLSamples #&21;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="25535-196">[!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]</span></span>  
  
 <span data-ttu-id="25535-197">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="25535-197">This code displays the following text:</span></span>  
  
```  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="25535-198">示例</span><span class="sxs-lookup"><span data-stu-id="25535-198">Example</span></span>  
 <span data-ttu-id="25535-199">下面的示例声明 `ns` 作为 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="25535-199">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="25535-200">然后使用该命名空间前缀创建 XML 文本，并显示该元素的最终形式。</span><span class="sxs-lookup"><span data-stu-id="25535-200">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 <span data-ttu-id="25535-201">[!code-vb[VbXMLSamples #&22;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="25535-201">[!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]</span></span>  
  
 <span data-ttu-id="25535-202">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="25535-202">This code displays the following text:</span></span>  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="25535-203">请注意，编译器转换为全局的 XML 命名空间的前缀的 XML 命名空间的前缀定义。</span><span class="sxs-lookup"><span data-stu-id="25535-203">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="25535-204">\<Ns:middle&1;> 元素重新定义的 XML 命名空间前缀\<ns:inner1&1;> 元素。</span><span class="sxs-lookup"><span data-stu-id="25535-204">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="25535-205">但是， \<ns:inner2&1;> 元素使用定义的命名空间`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="25535-205">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25535-206">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25535-206">See Also</span></span>  
 <span data-ttu-id="25535-207"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="25535-207"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="25535-208"> [声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="25535-208"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span></span>  
<span data-ttu-id="25535-209"> [XML 注释文本](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span><span class="sxs-lookup"><span data-stu-id="25535-209"> [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span></span>  
<span data-ttu-id="25535-210"> [XML CDATA 文本](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md) </span><span class="sxs-lookup"><span data-stu-id="25535-210"> [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md) </span></span>  
<span data-ttu-id="25535-211"> [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="25535-211"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="25535-212"> [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="25535-212"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="25535-213"> [XML 中的嵌入式的表达式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span><span class="sxs-lookup"><span data-stu-id="25535-213"> [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span></span>  
<span data-ttu-id="25535-214"> [Imports 语句（XML 命名空间）](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)</span><span class="sxs-lookup"><span data-stu-id="25535-214"> [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)</span></span>
