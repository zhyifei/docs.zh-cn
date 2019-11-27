---
title: XML 元素文本
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6d900ca6868cfffe6b0e5b349321a79c5716c46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347032"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="471ff-102">XML 元素文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="471ff-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="471ff-103">表示 <xref:System.Xml.Linq.XElement> 对象的文本。</span><span class="sxs-lookup"><span data-stu-id="471ff-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="syntax"></a><span data-ttu-id="471ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="471ff-104">Syntax</span></span>

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a><span data-ttu-id="471ff-105">部件</span><span class="sxs-lookup"><span data-stu-id="471ff-105">Parts</span></span>

- `<`

  <span data-ttu-id="471ff-106">必需。</span><span class="sxs-lookup"><span data-stu-id="471ff-106">Required.</span></span> <span data-ttu-id="471ff-107">打开开始元素标记。</span><span class="sxs-lookup"><span data-stu-id="471ff-107">Opens the starting element tag.</span></span>

- `name`

  <span data-ttu-id="471ff-108">必需。</span><span class="sxs-lookup"><span data-stu-id="471ff-108">Required.</span></span> <span data-ttu-id="471ff-109">元素名称。</span><span class="sxs-lookup"><span data-stu-id="471ff-109">Name of the element.</span></span> <span data-ttu-id="471ff-110">格式为以下格式之一：</span><span class="sxs-lookup"><span data-stu-id="471ff-110">The format is one of the following:</span></span>

  - <span data-ttu-id="471ff-111">元素名称的文本文本，格式为 `[ePrefix:]eName`，其中：</span><span class="sxs-lookup"><span data-stu-id="471ff-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>

    |<span data-ttu-id="471ff-112">部件</span><span class="sxs-lookup"><span data-stu-id="471ff-112">Part</span></span>|<span data-ttu-id="471ff-113">说明</span><span class="sxs-lookup"><span data-stu-id="471ff-113">Description</span></span>|
    |---|---|
    |`ePrefix`|<span data-ttu-id="471ff-114">可选。</span><span class="sxs-lookup"><span data-stu-id="471ff-114">Optional.</span></span> <span data-ttu-id="471ff-115">元素的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="471ff-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="471ff-116">必须是一个全局 XML 命名空间，该命名空间是使用文件中的 `Imports` 语句或项目级别定义的，或者是在此元素或父元素中定义的本地 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="471ff-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`eName`|<span data-ttu-id="471ff-117">必需。</span><span class="sxs-lookup"><span data-stu-id="471ff-117">Required.</span></span> <span data-ttu-id="471ff-118">元素名称。</span><span class="sxs-lookup"><span data-stu-id="471ff-118">Name of the element.</span></span> <span data-ttu-id="471ff-119">格式为以下格式之一：</span><span class="sxs-lookup"><span data-stu-id="471ff-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="471ff-120">文本。</span><span class="sxs-lookup"><span data-stu-id="471ff-120">- Literal text.</span></span> <span data-ttu-id="471ff-121">请参阅已[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="471ff-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="471ff-122">-形式 `<%= eNameExp %>`的嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="471ff-122">- Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="471ff-123">`eNameExp` 的类型必须 `String` 或可隐式转换为 <xref:System.Xml.Linq.XName>的类型。</span><span class="sxs-lookup"><span data-stu-id="471ff-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|

  - <span data-ttu-id="471ff-124">格式 `<%= nameExp %>`的嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="471ff-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="471ff-125">`nameExp` 的类型必须 `String` 或可隐式转换为 <xref:System.Xml.Linq.XName>的类型。</span><span class="sxs-lookup"><span data-stu-id="471ff-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="471ff-126">元素的结束标记中不允许使用嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="471ff-126">An embedded expression is not allowed in a closing tag of an element.</span></span>

- `attributeList`

  <span data-ttu-id="471ff-127">可选。</span><span class="sxs-lookup"><span data-stu-id="471ff-127">Optional.</span></span> <span data-ttu-id="471ff-128">在文本中声明的属性的列表。</span><span class="sxs-lookup"><span data-stu-id="471ff-128">List of attributes declared in the literal.</span></span>

  `attribute [ attribute ... ]`

  <span data-ttu-id="471ff-129">每个 `attribute` 都具有以下语法之一：</span><span class="sxs-lookup"><span data-stu-id="471ff-129">Each `attribute` has one of the following syntaxes:</span></span>

  - <span data-ttu-id="471ff-130">属性分配，格式为 `[aPrefix:]aName=aValue`，其中：</span><span class="sxs-lookup"><span data-stu-id="471ff-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>

    |<span data-ttu-id="471ff-131">部件</span><span class="sxs-lookup"><span data-stu-id="471ff-131">Part</span></span>|<span data-ttu-id="471ff-132">说明</span><span class="sxs-lookup"><span data-stu-id="471ff-132">Description</span></span>|
    |---|---|
    |`aPrefix`|<span data-ttu-id="471ff-133">可选。</span><span class="sxs-lookup"><span data-stu-id="471ff-133">Optional.</span></span> <span data-ttu-id="471ff-134">特性的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="471ff-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="471ff-135">必须是使用 `Imports` 语句定义的全局 XML 命名空间，或此元素或父元素中定义的本地 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="471ff-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`aName`|<span data-ttu-id="471ff-136">必需。</span><span class="sxs-lookup"><span data-stu-id="471ff-136">Required.</span></span> <span data-ttu-id="471ff-137">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="471ff-137">Name of the attribute.</span></span> <span data-ttu-id="471ff-138">格式为以下格式之一：</span><span class="sxs-lookup"><span data-stu-id="471ff-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="471ff-139">文本。</span><span class="sxs-lookup"><span data-stu-id="471ff-139">- Literal text.</span></span> <span data-ttu-id="471ff-140">请参阅已[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="471ff-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="471ff-141">-形式 `<%= aNameExp %>`的嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="471ff-141">- Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="471ff-142">`aNameExp` 的类型必须 `String` 或可隐式转换为 <xref:System.Xml.Linq.XName>的类型。</span><span class="sxs-lookup"><span data-stu-id="471ff-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|
    |`aValue`|<span data-ttu-id="471ff-143">可选。</span><span class="sxs-lookup"><span data-stu-id="471ff-143">Optional.</span></span> <span data-ttu-id="471ff-144">特性的值。</span><span class="sxs-lookup"><span data-stu-id="471ff-144">Value of the attribute.</span></span> <span data-ttu-id="471ff-145">格式为以下格式之一：</span><span class="sxs-lookup"><span data-stu-id="471ff-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="471ff-146">文本文本，用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="471ff-146">- Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="471ff-147">-形式 `<%= aValueExp %>`的嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="471ff-147">- Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="471ff-148">允许任何类型。</span><span class="sxs-lookup"><span data-stu-id="471ff-148">Any type is allowed.</span></span>|

  - <span data-ttu-id="471ff-149">格式 `<%= aExp %>`的嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="471ff-149">Embedded expression of the form `<%= aExp %>`.</span></span>

- `/>`

  <span data-ttu-id="471ff-150">可选。</span><span class="sxs-lookup"><span data-stu-id="471ff-150">Optional.</span></span> <span data-ttu-id="471ff-151">指示元素是一个空元素，不包含内容。</span><span class="sxs-lookup"><span data-stu-id="471ff-151">Indicates that the element is an empty element, without content.</span></span>

- `>`

  <span data-ttu-id="471ff-152">必需。</span><span class="sxs-lookup"><span data-stu-id="471ff-152">Required.</span></span> <span data-ttu-id="471ff-153">结束开始或空元素标记。</span><span class="sxs-lookup"><span data-stu-id="471ff-153">Ends the beginning or empty element tag.</span></span>

- `elementContents`

  <span data-ttu-id="471ff-154">可选。</span><span class="sxs-lookup"><span data-stu-id="471ff-154">Optional.</span></span> <span data-ttu-id="471ff-155">元素的内容。</span><span class="sxs-lookup"><span data-stu-id="471ff-155">Content of the element.</span></span>

  `content [ content ... ]`

  <span data-ttu-id="471ff-156">每个 `content` 可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="471ff-156">Each `content` can be one of the following:</span></span>

  - <span data-ttu-id="471ff-157">文本。</span><span class="sxs-lookup"><span data-stu-id="471ff-157">Literal text.</span></span> <span data-ttu-id="471ff-158">如果有任何文本文本，`elementContents` 中的所有空格都非常重要。</span><span class="sxs-lookup"><span data-stu-id="471ff-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>

  - <span data-ttu-id="471ff-159">格式 `<%= contentExp %>`的嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="471ff-159">Embedded expression of the form `<%= contentExp %>`.</span></span>

  - <span data-ttu-id="471ff-160">XML 元素文本。</span><span class="sxs-lookup"><span data-stu-id="471ff-160">XML element literal.</span></span>

  - <span data-ttu-id="471ff-161">XML 注释文本。</span><span class="sxs-lookup"><span data-stu-id="471ff-161">XML comment literal.</span></span> <span data-ttu-id="471ff-162">请参阅[XML 注释文本](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="471ff-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>

  - <span data-ttu-id="471ff-163">XML 处理指令文本。</span><span class="sxs-lookup"><span data-stu-id="471ff-163">XML processing instruction literal.</span></span> <span data-ttu-id="471ff-164">请参阅[XML 处理指令文本](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="471ff-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>

  - <span data-ttu-id="471ff-165">XML CDATA 文本。</span><span class="sxs-lookup"><span data-stu-id="471ff-165">XML CDATA literal.</span></span> <span data-ttu-id="471ff-166">请参阅[XML CDATA 文本](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="471ff-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>

- `</[name]>`

  <span data-ttu-id="471ff-167">可选。</span><span class="sxs-lookup"><span data-stu-id="471ff-167">Optional.</span></span> <span data-ttu-id="471ff-168">表示元素的结束标记。</span><span class="sxs-lookup"><span data-stu-id="471ff-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="471ff-169">当可选 `name` 参数是嵌入式表达式的结果时，不允许使用该参数。</span><span class="sxs-lookup"><span data-stu-id="471ff-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>

## <a name="return-value"></a><span data-ttu-id="471ff-170">返回值</span><span class="sxs-lookup"><span data-stu-id="471ff-170">Return Value</span></span>

<span data-ttu-id="471ff-171">一个 <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="471ff-171">An <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="remarks"></a><span data-ttu-id="471ff-172">备注</span><span class="sxs-lookup"><span data-stu-id="471ff-172">Remarks</span></span>

<span data-ttu-id="471ff-173">可以使用 XML 元素文本语法在代码中创建 <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="471ff-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>

> [!NOTE]
> <span data-ttu-id="471ff-174">XML 文本可以跨多行，而无需使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="471ff-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="471ff-175">此功能使你能够从 XML 文档复制内容并将其直接粘贴到 Visual Basic 程序。</span><span class="sxs-lookup"><span data-stu-id="471ff-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>

<span data-ttu-id="471ff-176">利用形式 `<%= exp %>` 的嵌入式表达式，你可以向 XML 元素文本添加动态信息。</span><span class="sxs-lookup"><span data-stu-id="471ff-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="471ff-177">有关详细信息，请参阅[XML 中的嵌入式表达式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="471ff-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>

<span data-ttu-id="471ff-178">Visual Basic 编译器将 XML 元素文本转换为对 <xref:System.Xml.Linq.XElement.%23ctor%2A> 构造函数的调用，如果需要，则转换为 <xref:System.Xml.Linq.XAttribute.%23ctor%2A> 构造函数。</span><span class="sxs-lookup"><span data-stu-id="471ff-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="471ff-179">XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="471ff-179">XML Namespaces</span></span>

<span data-ttu-id="471ff-180">当你必须在代码中多次使用同一命名空间中的元素创建 XML 文本时，XML 命名空间前缀非常有用。</span><span class="sxs-lookup"><span data-stu-id="471ff-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="471ff-181">你可以使用全局 XML 命名空间前缀，该前缀是使用 `Imports` 语句定义的，或者是通过使用 `xmlns:xmlPrefix="xmlNamespace"` 特性语法定义的本地前缀。</span><span class="sxs-lookup"><span data-stu-id="471ff-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="471ff-182">有关详细信息，请参阅[Imports 语句（XML 命名空间）](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="471ff-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>

<span data-ttu-id="471ff-183">根据 XML 命名空间的作用域规则，本地前缀优先于全局前缀。</span><span class="sxs-lookup"><span data-stu-id="471ff-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="471ff-184">但是，如果 XML 文本定义了 XML 命名空间，则该命名空间不能用于出现在嵌入表达式中的表达式。</span><span class="sxs-lookup"><span data-stu-id="471ff-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="471ff-185">嵌入的表达式只能访问全局 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="471ff-185">The embedded expression can access only the global XML namespace.</span></span>

<span data-ttu-id="471ff-186">Visual Basic 编译器将 XML 文本使用的每个全局 XML 命名空间转换为生成的代码中的一个本地命名空间定义。</span><span class="sxs-lookup"><span data-stu-id="471ff-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="471ff-187">不使用的全局 XML 命名空间不会出现在生成的代码中。</span><span class="sxs-lookup"><span data-stu-id="471ff-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>

## <a name="example"></a><span data-ttu-id="471ff-188">示例</span><span class="sxs-lookup"><span data-stu-id="471ff-188">Example</span></span>

<span data-ttu-id="471ff-189">下面的示例演示如何创建一个具有两个嵌套空元素的简单 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="471ff-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

<span data-ttu-id="471ff-190">该示例显示以下文本。</span><span class="sxs-lookup"><span data-stu-id="471ff-190">The example displays the following text.</span></span> <span data-ttu-id="471ff-191">请注意，文本将保留空元素的结构。</span><span class="sxs-lookup"><span data-stu-id="471ff-191">Notice that the literal preserves the structure of the empty elements.</span></span>

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a><span data-ttu-id="471ff-192">示例</span><span class="sxs-lookup"><span data-stu-id="471ff-192">Example</span></span>

<span data-ttu-id="471ff-193">下面的示例演示如何使用嵌入的表达式来命名元素并创建属性。</span><span class="sxs-lookup"><span data-stu-id="471ff-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

<span data-ttu-id="471ff-194">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="471ff-194">This code displays the following text:</span></span>

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a><span data-ttu-id="471ff-195">示例</span><span class="sxs-lookup"><span data-stu-id="471ff-195">Example</span></span>

<span data-ttu-id="471ff-196">下面的示例声明 `ns` 作为 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="471ff-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="471ff-197">然后，它使用命名空间的前缀创建 XML 文本，并显示该元素的最终形式。</span><span class="sxs-lookup"><span data-stu-id="471ff-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="471ff-198">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="471ff-198">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="471ff-199">请注意，编译器将全局 XML 命名空间的前缀转换为 XML 命名空间的前缀定义。</span><span class="sxs-lookup"><span data-stu-id="471ff-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="471ff-200">\<ns：中间 > 元素将重定义 \<ns： inner1 > 元素的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="471ff-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="471ff-201">但 \<ns： inner2 > 元素使用由 `Imports` 语句定义的命名空间。</span><span class="sxs-lookup"><span data-stu-id="471ff-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="471ff-202">另请参阅</span><span class="sxs-lookup"><span data-stu-id="471ff-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="471ff-203">已声明的 XML 元素和特性的名称</span><span class="sxs-lookup"><span data-stu-id="471ff-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="471ff-204">XML 注释文本</span><span class="sxs-lookup"><span data-stu-id="471ff-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="471ff-205">XML CDATA 文本</span><span class="sxs-lookup"><span data-stu-id="471ff-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [<span data-ttu-id="471ff-206">XML 文本</span><span class="sxs-lookup"><span data-stu-id="471ff-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="471ff-207">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="471ff-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="471ff-208">XML 中的嵌入式表达式</span><span class="sxs-lookup"><span data-stu-id="471ff-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="471ff-209">Imports 语句（XML 命名空间）</span><span class="sxs-lookup"><span data-stu-id="471ff-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
