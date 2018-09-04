---
title: 转换中的结果树片断
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: df363480-ba02-4233-9ddf-8434e421c4f1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca6871886a64c864451eb3e2f6f4843e0150123b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43553015"
---
# <a name="result-tree-fragment-in-transformations"></a><span data-ttu-id="68a45-102">转换中的结果树片断</span><span class="sxs-lookup"><span data-stu-id="68a45-102">Result Tree Fragment in Transformations</span></span>

> [!NOTE]
> <span data-ttu-id="68a45-103"><xref:System.Xml.Xsl.XslTransform> 类在 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 中已过期。</span><span class="sxs-lookup"><span data-stu-id="68a45-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="68a45-104">可以使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类执行可扩展样式表语言转换 (XSLT) 转换。</span><span class="sxs-lookup"><span data-stu-id="68a45-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="68a45-105">请参阅[使用 XslCompiledTransform 类](using-the-xslcompiledtransform-class.md)和[从 XslTransform 类迁移](migrating-from-the-xsltransform-class.md)，以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="68a45-105">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>

 <span data-ttu-id="68a45-106">结果树片段只是一个特殊类型的节点集。</span><span class="sxs-lookup"><span data-stu-id="68a45-106">Result tree fragments, also known as result tree fragments, are nothing more than a special type of node set.</span></span> <span data-ttu-id="68a45-107">您可以对它们执行可对节点集执行的任何函数。</span><span class="sxs-lookup"><span data-stu-id="68a45-107">You can perform any function on them that can be performed on a node set.</span></span> <span data-ttu-id="68a45-108">您也可以用 `node-set()` 函数将结果树片段转换成一个节点集，然后就可以在任何可使用节点集的位置使用了。</span><span class="sxs-lookup"><span data-stu-id="68a45-108">Or, you can also convert a result tree fragment to a node set using the `node-set()` function and subsequently use it any place that a node set can be used.</span></span>

 <span data-ttu-id="68a45-109">结果树片段是通过在样式表中以一种特定方式使用 `<xsl:variable>` 或 `<xsl:param>` 元素而创建的。</span><span class="sxs-lookup"><span data-stu-id="68a45-109">A result tree fragment is created as a result of using an `<xsl:variable>` or `<xsl:param>` element in a specific manner in a style sheet.</span></span> <span data-ttu-id="68a45-110">`variable` 和 `parameter` 元素的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="68a45-110">The syntax for the `variable` and `parameter` elements is as follows:</span></span>

```xml
<xsl:param name=Qname select= XPath Expression >
    template body
</xsl:param>

<xsl:variable name=Qname select=XPath Expression >
    template body
</xsl:variable>
```

<span data-ttu-id="68a45-111">对于 `parameter` 元素，可以用几种方式给限定名 (`Qname`) 赋值。</span><span class="sxs-lookup"><span data-stu-id="68a45-111">For the `parameter` element, the value is assigned to the qualified name (`Qname`) in several ways.</span></span> <span data-ttu-id="68a45-112">您可以通过如下方式为该参数分配默认值：从 `select` 属性中的 XML 路径语言 (XPath) 表达式返回内容，或者将模板正文的内容分配给该参数。</span><span class="sxs-lookup"><span data-stu-id="68a45-112">You can assign a default value to the parameter by returning content from the XML Path Language (XPath) expression in the `select` attribute, or by assigning it the contents of the template body.</span></span>

<span data-ttu-id="68a45-113">对于 `variable` 元素，赋值方法也有多种。</span><span class="sxs-lookup"><span data-stu-id="68a45-113">For the `variable` element, the value is also assigned in several ways.</span></span> <span data-ttu-id="68a45-114">您可以通过从 `select` 属性中的 XPath 表达式返回内容或通过将模板正文的内容分配给该参数来进行赋值。</span><span class="sxs-lookup"><span data-stu-id="68a45-114">You can assign it by returning content from the XPath expression in the `select` attribute, or by assigning it the contents of the template body.</span></span>

<span data-ttu-id="68a45-115">对于 `parameter` 和 `variable` 这两个元素，如果通过 XPath 表达式赋值，则将返回四种基本 XPath 类型之一：布尔值、字符串、数字或节点集。</span><span class="sxs-lookup"><span data-stu-id="68a45-115">For both the `parameter` and `variable` elements, if a value is assigned by the XPath expression, then one of the four basic XPath types will be returned: Boolean, string, number, or node set.</span></span> <span data-ttu-id="68a45-116">如果是通过非空模板正文赋值，则会返回非 XPath 数据类型，而且将是一个结果树片段。</span><span class="sxs-lookup"><span data-stu-id="68a45-116">When the value is given by using a non-empty template body, then a non-XPath data type is returned, and that will be a result tree fragment.</span></span>

<span data-ttu-id="68a45-117">只有当变量绑定到结果树片段而非这四种基本 XPath 数据类型之一时，XPath 查询才会返回这四种 XPath 对象类型以外的类型。</span><span class="sxs-lookup"><span data-stu-id="68a45-117">When a variable is bound to a result tree fragment instead of one of the four basic XPath data types, this is the only time that an XPath query returns a type that is not one of the four XPath object types.</span></span> <span data-ttu-id="68a45-118">结果树片段及其行为在[万维网联合会 (W3C) 规范](https://www.w3.org/TR/xslt-10/) [第 11.1 节“Result Tree Fragments”](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments)至[第 11.6 节“Passing Parameters to Templates”](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates)中讲述。</span><span class="sxs-lookup"><span data-stu-id="68a45-118">Result tree fragments and their behavior are discussed in the [World Wide Web Consortium (W3C) specification](https://www.w3.org/TR/xslt-10/), [section 11.1 Result Tree Fragments](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments) through [section 11.6 Passing Parameters to Templates](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates).</span></span> <span data-ttu-id="68a45-119">另外，[第 1 节“Introduction”](https://www.w3.org/TR/xslt-10/#section-Introduction)讲述了模板如何包含 XSLT 命名空间中返回或创建结果树片段的元素。</span><span class="sxs-lookup"><span data-stu-id="68a45-119">Also, [section 1 Introduction](https://www.w3.org/TR/xslt-10/#section-Introduction) discusses how templates can contain elements from the XSLT namespace that return or create result tree fragments.</span></span>

<span data-ttu-id="68a45-120">从概念上说，结果树片段的行为就像一个只有单个根节点的节点集。</span><span class="sxs-lookup"><span data-stu-id="68a45-120">A result tree fragment, in concept, behaves like a node set with nothing more than a single root node.</span></span> <span data-ttu-id="68a45-121">不过，返回的其余节点都是子节点。</span><span class="sxs-lookup"><span data-stu-id="68a45-121">However, the rest of the nodes returned are child nodes.</span></span> <span data-ttu-id="68a45-122">若要以编程方式查看子节点，请使用 `<xsl:copy-of>` 元素将结果树片段复制到结果树中。</span><span class="sxs-lookup"><span data-stu-id="68a45-122">To programmatically see the child nodes, copy the result tree fragment to the result tree using the `<xsl:copy-of>` element.</span></span> <span data-ttu-id="68a45-123">在执行 copy-of 时，所有子节点也都按顺序复制到结果树中。</span><span class="sxs-lookup"><span data-stu-id="68a45-123">When the copy-of is performed, all the child nodes are also copied to the result tree in sequence.</span></span> <span data-ttu-id="68a45-124">在使用 `copy` 或 `copy-of` 之前，结果树片段不是结果树或转换输出的一部分。</span><span class="sxs-lookup"><span data-stu-id="68a45-124">Until a `copy` or `copy-of` is used, a result tree fragment is not part of the result tree or the output from the transformation.</span></span>

<span data-ttu-id="68a45-125">若要循环访问结果树片段的返回节点，请使用 <xref:System.Xml.XPath.XPathNavigator>。</span><span class="sxs-lookup"><span data-stu-id="68a45-125">To iterate over the returned nodes of a result tree fragment, an <xref:System.Xml.XPath.XPathNavigator> is used.</span></span> <span data-ttu-id="68a45-126">下面的代码示例显示了如何通过调用具有参数 `fragment`（包含 XML）的函数在样式表内创建一个结果树片段。</span><span class="sxs-lookup"><span data-stu-id="68a45-126">The following code sample shows how to create a result tree fragment within a style sheet by calling the function with a parameter `fragment`, which contains XML.</span></span>

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"
                xmlns:user="http://www.adventure-works.com"
                version="1.0">
    <xsl:var name="fragment">
        <node1>
            <node2/>
        </node1>
    <xsl:var>

  <msxsl:script language="C#" implements-prefix="user">
    function NodeFragment(XPathNavigator nav)
    {
      if (nav.HasSelection == false)
        XPathNavigator.MoveToNext();
      return;
    }
  </msxsl:script>

    <xsl:template match="/">
            <xsl:value-of select="user:NodeFragment(msxml:node-set($fragment))"/>
    </xsl:template>
</xsl:stylesheet>
```

<span data-ttu-id="68a45-127">下面是另一个显示变量的示例，此变量的格式为 RTF（丰富文本格式），因而一种结果树片段类型，未转换为节点集，</span><span class="sxs-lookup"><span data-stu-id="68a45-127">Here is another sample showing a variable, which is in Rich Text Format (RTF), and hence, a type of result tree fragment, that is not converted to a node set.</span></span> <span data-ttu-id="68a45-128">而是传递给一个脚本函数，<xref:System.Xml.XPath.XPathNavigator> 用来在这些节点上浏览。</span><span class="sxs-lookup"><span data-stu-id="68a45-128">Instead, it is passed to a script function, and the <xref:System.Xml.XPath.XPathNavigator> is used to navigate over the nodes.</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"
        xmlns:user="urn:books"
        exclude-result-prefixes="msxsl">

<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>

<xsl:variable name="node-fragment">
    <book>Book1</book>
    <book>Book2</book>
    <book>Book3</book>
    <book>Book4</book>
</xsl:variable>

<msxsl:script implements-prefix="user" language="c#">

<![CDATA[
    string func(XPathNavigator nav)
    {
        bool b = nav.MoveToFirstChild();
        if (b)
            return nav.Value;
        else
            return "Does not exist";
    }

]]>

</msxsl:script>

<xsl:template match="/">
    <first_book>
        <xsl:value-of select="user:func($node-fragment)"/>
    </first_book>
</xsl:template>

</xsl:stylesheet>
```

<span data-ttu-id="68a45-129">用此样式表转换任何 XML 的结果显示在下面的输出中。</span><span class="sxs-lookup"><span data-stu-id="68a45-129">The result of transforming any XML with this style sheet is shown in the following output.</span></span>

## <a name="output"></a><span data-ttu-id="68a45-130">输出</span><span class="sxs-lookup"><span data-stu-id="68a45-130">Output</span></span>

```xml
<first_book xmlns:user="urn:books">Book1</first_book>
```

<span data-ttu-id="68a45-131">如前所述，`node-set` 函数可以将结果树片段转换成节点集。</span><span class="sxs-lookup"><span data-stu-id="68a45-131">As stated above, the `node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="68a45-132">生成的节点集总是包含单个节点并且是树的根节点。</span><span class="sxs-lookup"><span data-stu-id="68a45-132">The resulting node always contains a single node that is the root node of the tree.</span></span> <span data-ttu-id="68a45-133">如果将结果树片段转换成节点集，就可以在任何使用常规节点集的位置使用，如在 for-each 语句或在 `select` 属性的值中。</span><span class="sxs-lookup"><span data-stu-id="68a45-133">If you convert a result tree fragment to a node set, then you can use it anywhere a regular node set is used, such as in a for-each statement or in the value of a `select` attribute.</span></span> <span data-ttu-id="68a45-134">下面的代码行显示了被转换为节点集并作为节点集使用的片段：</span><span class="sxs-lookup"><span data-stu-id="68a45-134">The following lines of code show the fragment being converted to a node set and used as a node set:</span></span>

`<xsl:for-each select="msxsl:node-set($node-fragment)">`

`<xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>`

<span data-ttu-id="68a45-135">当片段转换成节点集后，就再也不用 <xref:System.Xml.XPath.XPathNavigator> 进行浏览。</span><span class="sxs-lookup"><span data-stu-id="68a45-135">When a fragment is converted to a node set, you no longer use the <xref:System.Xml.XPath.XPathNavigator> to navigate over it.</span></span> <span data-ttu-id="68a45-136">对于节点集，应改用 <xref:System.Xml.XPath.XPathNodeIterator>。</span><span class="sxs-lookup"><span data-stu-id="68a45-136">For a node set, you use the <xref:System.Xml.XPath.XPathNodeIterator> instead.</span></span>

<span data-ttu-id="68a45-137">在下面的示例中，`$var` 是一个变量，是样式表中的一个节点树。</span><span class="sxs-lookup"><span data-stu-id="68a45-137">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="68a45-138">for-each 语句与 `node-set` 函数组合使用，允许用户将此树作为节点集循环访问。</span><span class="sxs-lookup"><span data-stu-id="68a45-138">The for-each statement, combined with the `node-set` function, allows the user to iterate over this tree as a node set.</span></span>

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"
                xmlns:user="http://www.adventure-works.com"
                version="1.0">
    <xsl:variable name="states">
        <node1>AL</node1>
        <node1>CA</node1>
        <node1>CO</node1>
        <node1>WA</node1>
    </xsl:variable>

    <xsl:template match="/">
            <xsl:for-each select="msxsl:node-set($states)"/> 
    </xsl:template>
</xsl:stylesheet>
```

<span data-ttu-id="68a45-139">下面是另一个变量示例，该变量格式为 RTF，因而是节点树片段类型，在作为 XPathNodeIterator 传递给一个脚本函数前转换成了节点集。</span><span class="sxs-lookup"><span data-stu-id="68a45-139">Here is another example of a variable that is in RTF, and hence of type result tree fragment, that is converted to a node set before being passed to a script function as XPathNodeIterator.</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"
        xmlns:user="urn:books"
        exclude-result-prefixes="msxsl">

<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>

<xsl:variable name="node-fragment">
    <book>Book1</book>
    <book>Book2</book>
    <book>Book3</book>
    <book>Book4</book>
</xsl:variable>

<msxsl:script implements-prefix="user" language="c#">

<![CDATA[
    string func(XPathNodeIterator it)
    {
        it.MoveNext(); 
        return it.Current.Value; 
        //it.Current returns XPathNavigator positioned on the current node
    }

]]>

</msxsl:script>
<xsl:template match="/">
    <books>
        <xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>
    </books>
</xsl:template>

</xsl:stylesheet>
```

<span data-ttu-id="68a45-140">用此样式表转换 XML 的结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="68a45-140">The following is the result of transforming XML with this style sheet:</span></span>

```xml
<books xmlns:user="urn:books">Book1Book2Book3Book4</books>
```

## <a name="see-also"></a><span data-ttu-id="68a45-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="68a45-141">See Also</span></span>

<xref:System.Xml.XPath.XPathNodeIterator>  
<xref:System.Xml.XPath.XPathNodeIterator>  
[<span data-ttu-id="68a45-142">XslTransform 类的 XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="68a45-142">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)  
[<span data-ttu-id="68a45-143">XslTransform 类实现 XSLT 处理器</span><span class="sxs-lookup"><span data-stu-id="68a45-143">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)  
