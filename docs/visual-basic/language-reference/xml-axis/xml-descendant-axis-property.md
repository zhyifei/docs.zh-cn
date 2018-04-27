---
title: XML 后代轴属性 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1dc5fe1addb089f3de9b4d5054f34a578b491fb0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="b44e7-102">XML 后代轴属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b44e7-102">XML Descendant Axis Property (Visual Basic)</span></span>
<span data-ttu-id="b44e7-103">提供的访问权限的后代中的以下：<xref:System.Xml.Linq.XElement>对象，<xref:System.Xml.Linq.XDocument>对象、 一套<xref:System.Xml.Linq.XElement>对象或一套<xref:System.Xml.Linq.XDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="b44e7-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b44e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="b44e7-104">Syntax</span></span>  
  
```  
object...<descendant>  
```  
  
## <a name="parts"></a><span data-ttu-id="b44e7-105">部件</span><span class="sxs-lookup"><span data-stu-id="b44e7-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="b44e7-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="b44e7-106">Required.</span></span> <span data-ttu-id="b44e7-107"><xref:System.Xml.Linq.XElement> 对象、<xref:System.Xml.Linq.XDocument> 对象、<xref:System.Xml.Linq.XElement> 对象的集合或 <xref:System.Xml.Linq.XDocument> 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="b44e7-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
 <span data-ttu-id="b44e7-108">...<</span><span class="sxs-lookup"><span data-stu-id="b44e7-108">...<</span></span>  
 <span data-ttu-id="b44e7-109">必须的。</span><span class="sxs-lookup"><span data-stu-id="b44e7-109">Required.</span></span> <span data-ttu-id="b44e7-110">表示子代轴属性的开头。</span><span class="sxs-lookup"><span data-stu-id="b44e7-110">Denotes the start of a descendant axis property.</span></span>  
  
 `descendant`  
 <span data-ttu-id="b44e7-111">必须的。</span><span class="sxs-lookup"><span data-stu-id="b44e7-111">Required.</span></span> <span data-ttu-id="b44e7-112">若要访问，在窗体的子代节点的名称 [`prefix``:`]`name`。</span><span class="sxs-lookup"><span data-stu-id="b44e7-112">Name of the descendant nodes to access, of the form [`prefix``:`]`name`.</span></span>  
  
|<span data-ttu-id="b44e7-113">部件</span><span class="sxs-lookup"><span data-stu-id="b44e7-113">Part</span></span>|<span data-ttu-id="b44e7-114">描述</span><span class="sxs-lookup"><span data-stu-id="b44e7-114">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="b44e7-115">可选。</span><span class="sxs-lookup"><span data-stu-id="b44e7-115">Optional.</span></span> <span data-ttu-id="b44e7-116">子代节点的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="b44e7-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="b44e7-117">必须使用定义的全局 XML 命名空间`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="b44e7-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="b44e7-118">必须的。</span><span class="sxs-lookup"><span data-stu-id="b44e7-118">Required.</span></span> <span data-ttu-id="b44e7-119">子代节点的本地名称。</span><span class="sxs-lookup"><span data-stu-id="b44e7-119">Local name of the descendant node.</span></span> <span data-ttu-id="b44e7-120">请参阅[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="b44e7-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="b44e7-121">必须的。</span><span class="sxs-lookup"><span data-stu-id="b44e7-121">Required.</span></span> <span data-ttu-id="b44e7-122">表示子代轴属性的结尾。</span><span class="sxs-lookup"><span data-stu-id="b44e7-122">Denotes the end of a descendant axis property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b44e7-123">返回值</span><span class="sxs-lookup"><span data-stu-id="b44e7-123">Return Value</span></span>  
 <span data-ttu-id="b44e7-124"><xref:System.Xml.Linq.XElement> 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="b44e7-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b44e7-125">备注</span><span class="sxs-lookup"><span data-stu-id="b44e7-125">Remarks</span></span>  
 <span data-ttu-id="b44e7-126">你可以使用 XML 子代轴属性按名称从访问子代节点<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>对象，或从集合<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="b44e7-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="b44e7-127">使用 XML`Value`属性来访问返回的集合中的第一个子代节点的值。</span><span class="sxs-lookup"><span data-stu-id="b44e7-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="b44e7-128">有关详细信息，请参阅[XML 值属性](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)。</span><span class="sxs-lookup"><span data-stu-id="b44e7-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="b44e7-129">Visual Basic 编译器将子代轴属性转换为对的调用<xref:System.Xml.Linq.XContainer.Descendants%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="b44e7-129">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="b44e7-130">XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="b44e7-130">XML Namespaces</span></span>  
 <span data-ttu-id="b44e7-131">子代轴属性中的名称可以使用仅 XML 命名空间使用全局声明`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="b44e7-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="b44e7-132">它不能使用在 XML 元素文本中局部声明的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="b44e7-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="b44e7-133">有关详细信息，请参阅[Imports 语句 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="b44e7-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b44e7-134">示例</span><span class="sxs-lookup"><span data-stu-id="b44e7-134">Example</span></span>  
 <span data-ttu-id="b44e7-135">下面的示例演示如何访问名为的第一个子代节点的值`name`和名为的所有子代节点的值`phone`从`contacts`对象。</span><span class="sxs-lookup"><span data-stu-id="b44e7-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 <span data-ttu-id="b44e7-136">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="b44e7-136">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="b44e7-137">示例</span><span class="sxs-lookup"><span data-stu-id="b44e7-137">Example</span></span>  
 <span data-ttu-id="b44e7-138">下面的示例声明 `ns` 作为 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="b44e7-138">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="b44e7-139">然后，它使用的命名空间前缀创建 XML 文本并访问具有限定名的第一个子节点的值`ns:name`。</span><span class="sxs-lookup"><span data-stu-id="b44e7-139">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 <span data-ttu-id="b44e7-140">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="b44e7-140">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="b44e7-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="b44e7-141">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="b44e7-142">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="b44e7-142">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="b44e7-143">XML 文本</span><span class="sxs-lookup"><span data-stu-id="b44e7-143">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="b44e7-144">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="b44e7-144">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="b44e7-145">已声明的 XML 元素和特性的名称</span><span class="sxs-lookup"><span data-stu-id="b44e7-145">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
