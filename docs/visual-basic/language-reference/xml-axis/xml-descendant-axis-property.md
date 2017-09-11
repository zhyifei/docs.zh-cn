---
title: "XML 子代轴属性 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyDescendantsAxis
dev_langs:
- VB
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
ms.openlocfilehash: e84a8bb989ebbed57595ebf93cef620027a04328
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="2a8c2-102">XML 后代轴属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a8c2-102">XML Descendant Axis Property (Visual Basic)</span></span>
<span data-ttu-id="2a8c2-103">提供对以下的后代的访问︰<xref:System.Xml.Linq.XElement>对象，<xref:System.Xml.Linq.XDocument>对象、 一套<xref:System.Xml.Linq.XElement>对象或一套<xref:System.Xml.Linq.XDocument>对象。</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2a8c2-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a8c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a8c2-104">Syntax</span></span>  
  
```  
  
object...<descendant>  
```  
  
## <a name="parts"></a><span data-ttu-id="2a8c2-105">部件</span><span class="sxs-lookup"><span data-stu-id="2a8c2-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="2a8c2-106">必需。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-106">Required.</span></span> <span data-ttu-id="2a8c2-107"><xref:System.Xml.Linq.XElement>对象，<xref:System.Xml.Linq.XDocument>对象、 一套<xref:System.Xml.Linq.XElement>对象或一套<xref:System.Xml.Linq.XDocument>对象。</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2a8c2-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
 <span data-ttu-id="2a8c2-108">...<</span><span class="sxs-lookup"><span data-stu-id="2a8c2-108">...<</span></span>  
 <span data-ttu-id="2a8c2-109">必需。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-109">Required.</span></span> <span data-ttu-id="2a8c2-110">表示子代轴属性的开头。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-110">Denotes the start of a descendant axis property.</span></span>  
  
 `descendant`  
 <span data-ttu-id="2a8c2-111">必需。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-111">Required.</span></span> <span data-ttu-id="2a8c2-112">若要访问，窗体的子代节点的名称 [`prefix``:`]`name`。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-112">Name of the descendant nodes to access, of the form [`prefix``:`]`name`.</span></span>  
  
|<span data-ttu-id="2a8c2-113">部件</span><span class="sxs-lookup"><span data-stu-id="2a8c2-113">Part</span></span>|<span data-ttu-id="2a8c2-114">说明</span><span class="sxs-lookup"><span data-stu-id="2a8c2-114">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="2a8c2-115">可选。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-115">Optional.</span></span> <span data-ttu-id="2a8c2-116">子代节点的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="2a8c2-117">必须通过定义一个全局 XML 命名空间`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="2a8c2-118">必需。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-118">Required.</span></span> <span data-ttu-id="2a8c2-119">子代节点的本地名称。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-119">Local name of the descendant node.</span></span> <span data-ttu-id="2a8c2-120">请参阅[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="2a8c2-121">必需。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-121">Required.</span></span> <span data-ttu-id="2a8c2-122">表示子代轴属性的结尾。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-122">Denotes the end of a descendant axis property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a8c2-123">返回值</span><span class="sxs-lookup"><span data-stu-id="2a8c2-123">Return Value</span></span>  
 <span data-ttu-id="2a8c2-124">一套<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2a8c2-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a8c2-125">备注</span><span class="sxs-lookup"><span data-stu-id="2a8c2-125">Remarks</span></span>  
 <span data-ttu-id="2a8c2-126">可以使用 XML 后代轴属性按名称从访问子代节点<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>对象，或从大量的<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>对象。</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2a8c2-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="2a8c2-127">使用 XML`Value`属性来访问返回的集合中的第一个后代节点的值。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="2a8c2-128">有关详细信息，请参阅[XML 值属性](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="2a8c2-129">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器将子代轴属性转换为对调用<xref:System.Xml.Linq.XContainer.Descendants%2A>方法。</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="2a8c2-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="2a8c2-130">XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="2a8c2-130">XML Namespaces</span></span>  
 <span data-ttu-id="2a8c2-131">子代轴属性中的名称可以使用只有 XML 命名空间使用全局声明`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="2a8c2-132">它不能使用在 XML 元素文本中局部声明的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="2a8c2-133">有关详细信息，请参阅[Imports 语句 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a8c2-134">示例</span><span class="sxs-lookup"><span data-stu-id="2a8c2-134">Example</span></span>  
 <span data-ttu-id="2a8c2-135">下面的示例演示如何访问名为的第一个后代节点的值`name`和名为的所有子代节点的值`phone`从`contacts`对象。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>  
  
 <span data-ttu-id="2a8c2-136">[!code-vb[VbXMLSamples #&25;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a8c2-136">[!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]</span></span>  
  
 <span data-ttu-id="2a8c2-137">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="2a8c2-137">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="2a8c2-138">示例</span><span class="sxs-lookup"><span data-stu-id="2a8c2-138">Example</span></span>  
 <span data-ttu-id="2a8c2-139">下面的示例声明 `ns` 作为 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-139">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="2a8c2-140">它然后使用该命名空间前缀创建 XML 文本和访问具有限定名的第一个子节点的值`ns:name`。</span><span class="sxs-lookup"><span data-stu-id="2a8c2-140">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>  
  
 <span data-ttu-id="2a8c2-141">[!code-vb[VbXMLSamples #&26;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a8c2-141">[!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]</span></span>  
  
 <span data-ttu-id="2a8c2-142">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="2a8c2-142">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="2a8c2-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a8c2-143">See Also</span></span>  
 <span data-ttu-id="2a8c2-144"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2a8c2-144"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="2a8c2-145"> [XML 轴属性](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="2a8c2-145"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="2a8c2-146"> [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="2a8c2-146"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="2a8c2-147"> [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="2a8c2-147"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="2a8c2-148"> [已声明的 XML 元素和特性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="2a8c2-148"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span></span>
