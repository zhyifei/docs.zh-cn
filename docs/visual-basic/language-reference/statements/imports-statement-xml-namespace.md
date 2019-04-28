---
title: Imports 语句-XML Namespace (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 97d08113a37477add9d770b0a680c303fe7e3040
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638952"
---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="73d0b-102">Imports 语句（XML 命名空间）</span><span class="sxs-lookup"><span data-stu-id="73d0b-102">Imports Statement (XML Namespace)</span></span>
<span data-ttu-id="73d0b-103">导入在 XML 文本和 XML 轴属性中使用的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="73d0b-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73d0b-104">语法</span><span class="sxs-lookup"><span data-stu-id="73d0b-104">Syntax</span></span>  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a><span data-ttu-id="73d0b-105">部件</span><span class="sxs-lookup"><span data-stu-id="73d0b-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="73d0b-106">可选。</span><span class="sxs-lookup"><span data-stu-id="73d0b-106">Optional.</span></span> <span data-ttu-id="73d0b-107">由哪些 XML 元素和属性可以引用的字符串`xmlNamespaceName`。</span><span class="sxs-lookup"><span data-stu-id="73d0b-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="73d0b-108">如果没有`xmlNamespacePrefix`是提供，导入的 XML 命名空间是默认 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="73d0b-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="73d0b-109">必须是有效的 XML 标识符。</span><span class="sxs-lookup"><span data-stu-id="73d0b-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="73d0b-110">有关详细信息，请参阅[名称的声明 XML 元素和属性](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="73d0b-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>  
  
 `xmlNamespaceName`  
 <span data-ttu-id="73d0b-111">必需。</span><span class="sxs-lookup"><span data-stu-id="73d0b-111">Required.</span></span> <span data-ttu-id="73d0b-112">标识要导入的 XML 命名空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="73d0b-112">The string identifying the XML namespace being imported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73d0b-113">备注</span><span class="sxs-lookup"><span data-stu-id="73d0b-113">Remarks</span></span>  
 <span data-ttu-id="73d0b-114">可以使用`Imports`语句来定义与 XML 文本和 XML 轴属性，或作为参数传递到可以使用的全局 XML 命名空间`GetXmlNamespace`运算符。</span><span class="sxs-lookup"><span data-stu-id="73d0b-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="73d0b-115">(有关使用信息`Imports`语句导入别名，可在代码中，使用类型名称，请参阅[Imports 语句 （.NET Namespace 和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。)通过使用声明 XML 命名空间的语法`Imports`语句等同于在 XML 中使用的语法。</span><span class="sxs-lookup"><span data-stu-id="73d0b-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="73d0b-116">因此，您可以从 XML 文件中复制的命名空间声明，并使用它在`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="73d0b-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>  
  
 <span data-ttu-id="73d0b-117">你想要反复创建相同的命名空间中的 XML 元素时，XML 命名空间前缀非常有用。</span><span class="sxs-lookup"><span data-stu-id="73d0b-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="73d0b-118">使用 XML 命名空间前缀声明`Imports`语句是全局的意义上说，它是适用于所有代码文件中。</span><span class="sxs-lookup"><span data-stu-id="73d0b-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="73d0b-119">在创建 XML 元素文本和 XML 轴属性的访问时，可以使用它。</span><span class="sxs-lookup"><span data-stu-id="73d0b-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="73d0b-120">有关详细信息，请参阅[XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)并[XML 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)。</span><span class="sxs-lookup"><span data-stu-id="73d0b-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>  
  
 <span data-ttu-id="73d0b-121">如果定义一个不带命名空间前缀的全局 XML 命名空间 (例如， `Imports <xmlns="http://SomeNameSpace>"`)，该命名空间被视为默认 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="73d0b-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="73d0b-122">默认 XML 命名空间用于任何 XML 元素文本或 XML 特性轴属性的未显式指定命名空间。</span><span class="sxs-lookup"><span data-stu-id="73d0b-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="73d0b-123">如果指定的命名空间是空的命名空间还使用默认命名空间 (即， `xmlns=""`)。</span><span class="sxs-lookup"><span data-stu-id="73d0b-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="73d0b-124">默认 XML 命名空间不适用于 XML 文本中的 XML 特性或不具有命名空间的 XML 特性轴属性。</span><span class="sxs-lookup"><span data-stu-id="73d0b-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>  
  
 <span data-ttu-id="73d0b-125">XML 定义的命名空间中 XML 文本，也称为*本地 XML 命名空间*，通过定义的 XML 命名空间的优先级高于`Imports`语句作为全局。</span><span class="sxs-lookup"><span data-stu-id="73d0b-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="73d0b-126">由定义的 XML 命名空间`Imports`语句优先于为 Visual Basic 项目导入的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="73d0b-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="73d0b-127">如果 XML 文本定义的 XML 命名空间，该本地命名空间不适用于嵌入的表达式。</span><span class="sxs-lookup"><span data-stu-id="73d0b-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>  
  
 <span data-ttu-id="73d0b-128">全局 XML 命名空间按照与.NET Framework 命名空间相同的作用域和定义规则。</span><span class="sxs-lookup"><span data-stu-id="73d0b-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="73d0b-129">因此，可以包括`Imports`语句来定义一个全局的 XML 命名空间可以在任意位置导入.NET Framework 命名空间。</span><span class="sxs-lookup"><span data-stu-id="73d0b-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="73d0b-130">这包括代码文件和项目级别导入命名空间。</span><span class="sxs-lookup"><span data-stu-id="73d0b-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="73d0b-131">有关项目级别导入命名空间的信息，请参阅[引用页上，项目设计器 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="73d0b-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="73d0b-132">每个源文件可以包含任意数量的`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="73d0b-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="73d0b-133">这些必须遵循选项声明，如`Option Strict`语句，并且它们必须位于之前编程元素声明，如`Module`或`Class`语句。</span><span class="sxs-lookup"><span data-stu-id="73d0b-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73d0b-134">示例</span><span class="sxs-lookup"><span data-stu-id="73d0b-134">Example</span></span>  
 <span data-ttu-id="73d0b-135">下面的示例将默认 XML 命名空间和 XML 命名空间前缀标识导入`ns`。</span><span class="sxs-lookup"><span data-stu-id="73d0b-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="73d0b-136">然后，创建使用这两个命名空间的 XML 文本。</span><span class="sxs-lookup"><span data-stu-id="73d0b-136">It then creates XML literals that use both namespaces.</span></span>  
  
 [!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]  
  
 <span data-ttu-id="73d0b-137">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="73d0b-137">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a><span data-ttu-id="73d0b-138">示例</span><span class="sxs-lookup"><span data-stu-id="73d0b-138">Example</span></span>  
 <span data-ttu-id="73d0b-139">以下示例将导入的 XML 命名空间前缀`ns`。</span><span class="sxs-lookup"><span data-stu-id="73d0b-139">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="73d0b-140">然后，创建 XML 文本的使用的命名空间前缀，并显示元素的最终形式。</span><span class="sxs-lookup"><span data-stu-id="73d0b-140">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]  
  
 <span data-ttu-id="73d0b-141">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="73d0b-141">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="73d0b-142">请注意，编译器为本地前缀定义从全局前缀转换的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="73d0b-142">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73d0b-143">示例</span><span class="sxs-lookup"><span data-stu-id="73d0b-143">Example</span></span>  
 <span data-ttu-id="73d0b-144">以下示例将导入的 XML 命名空间前缀`ns`。</span><span class="sxs-lookup"><span data-stu-id="73d0b-144">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="73d0b-145">然后它使用该命名空间前缀来创建 XML 文本并访问具有限定名称 `ns:name` 的第一个子节点。</span><span class="sxs-lookup"><span data-stu-id="73d0b-145">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="73d0b-146">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="73d0b-146">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="73d0b-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="73d0b-147">See also</span></span>

- [<span data-ttu-id="73d0b-148">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="73d0b-148">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="73d0b-149">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="73d0b-149">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="73d0b-150">已声明的 XML 元素和特性的名称</span><span class="sxs-lookup"><span data-stu-id="73d0b-150">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="73d0b-151">GetXmlNamespace 运算符</span><span class="sxs-lookup"><span data-stu-id="73d0b-151">GetXmlNamespace Operator</span></span>](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
