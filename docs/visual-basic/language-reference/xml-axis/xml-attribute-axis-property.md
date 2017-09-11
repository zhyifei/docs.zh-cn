---
title: "XML 特性轴属性 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyAttributeAxis
dev_langs:
- VB
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 23
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
ms.openlocfilehash: a3c327f4448287bcf6c45b9b6e26a1ef9ba13c16
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="71692-102">XML 特性轴属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71692-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="71692-103">提供对有关属性的值的访问<xref:System.Xml.Linq.XElement>对象或集合中的第一个元素<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="71692-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71692-104">语法</span><span class="sxs-lookup"><span data-stu-id="71692-104">Syntax</span></span>  
  
```  
  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="71692-105">部件</span><span class="sxs-lookup"><span data-stu-id="71692-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="71692-106">必需。</span><span class="sxs-lookup"><span data-stu-id="71692-106">Required.</span></span> <span data-ttu-id="71692-107"><xref:System.Xml.Linq.XElement>对象或集合的<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="71692-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="71692-108">.@</span><span class="sxs-lookup"><span data-stu-id="71692-108">.@</span></span>  
 <span data-ttu-id="71692-109">必需。</span><span class="sxs-lookup"><span data-stu-id="71692-109">Required.</span></span> <span data-ttu-id="71692-110">表示特性轴属性的开头。</span><span class="sxs-lookup"><span data-stu-id="71692-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="71692-111">可选。</span><span class="sxs-lookup"><span data-stu-id="71692-111">Optional.</span></span> <span data-ttu-id="71692-112">表示属性的名称开头时`attribute`不是有效的标识符中[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="71692-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 `attribute`  
 <span data-ttu-id="71692-113">必需。</span><span class="sxs-lookup"><span data-stu-id="71692-113">Required.</span></span> <span data-ttu-id="71692-114">若要访问，窗体的属性名称 [`prefix`:]`name`。</span><span class="sxs-lookup"><span data-stu-id="71692-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="71692-115">部件</span><span class="sxs-lookup"><span data-stu-id="71692-115">Part</span></span>|<span data-ttu-id="71692-116">描述</span><span class="sxs-lookup"><span data-stu-id="71692-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="71692-117">可选。</span><span class="sxs-lookup"><span data-stu-id="71692-117">Optional.</span></span> <span data-ttu-id="71692-118">该属性的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="71692-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="71692-119">必须是使用 `Imports` 语句定义的全局 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="71692-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="71692-120">必需。</span><span class="sxs-lookup"><span data-stu-id="71692-120">Required.</span></span> <span data-ttu-id="71692-121">本地属性名称。</span><span class="sxs-lookup"><span data-stu-id="71692-121">Local attribute name.</span></span> <span data-ttu-id="71692-122">请参阅[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="71692-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="71692-123">可选。</span><span class="sxs-lookup"><span data-stu-id="71692-123">Optional.</span></span> <span data-ttu-id="71692-124">表示属性的名称的结尾时`attribute`不是有效的标识符中[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="71692-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71692-125">返回值</span><span class="sxs-lookup"><span data-stu-id="71692-125">Return Value</span></span>  
 <span data-ttu-id="71692-126">一个字符串，包含的值`attribute`。</span><span class="sxs-lookup"><span data-stu-id="71692-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="71692-127">如果属性名称不存在，`Nothing`返回。</span><span class="sxs-lookup"><span data-stu-id="71692-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71692-128">备注</span><span class="sxs-lookup"><span data-stu-id="71692-128">Remarks</span></span>  
 <span data-ttu-id="71692-129">可以使用 XML 特性轴属性来访问属性的值按名称从<xref:System.Xml.Linq.XElement>对象或从集合中的第一个元素<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="71692-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="71692-130">可以按名称检索属性值，也可以将新属性添加到元素，通过指定新名称前面有 @ 标识符。</span><span class="sxs-lookup"><span data-stu-id="71692-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="71692-131">引用时使用 XML 属性使用 @ 标识符，该属性值返回作为字符串，并且不需要显式指定<xref:System.Xml.Linq.XAttribute.Value%2A>属性。</xref:System.Xml.Linq.XAttribute.Value%2A></span><span class="sxs-lookup"><span data-stu-id="71692-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="71692-132">用于 XML 特性的命名规则与不同的命名规则[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]标识符。</span><span class="sxs-lookup"><span data-stu-id="71692-132">The naming rules for XML attributes differ from the naming rules for [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] identifiers.</span></span> <span data-ttu-id="71692-133">若要访问 XML 特性都不是有效的 Visual Basic 标识符的名称，请将名称括在尖括号 (\<和&1;>)。</span><span class="sxs-lookup"><span data-stu-id="71692-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="71692-134">XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="71692-134">XML Namespaces</span></span>  
 <span data-ttu-id="71692-135">特性轴属性中的名称可以使用通过使用全局声明的只有 XML 命名空间前缀`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="71692-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="71692-136">它不能使用在 XML 元素文本中局部声明的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="71692-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="71692-137">有关详细信息，请参阅[Imports 语句 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="71692-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71692-138">示例</span><span class="sxs-lookup"><span data-stu-id="71692-138">Example</span></span>  
 <span data-ttu-id="71692-139">下面的示例演示如何获取名为的 XML 特性的值`type`从 XML 元素的命名集合`phone`。</span><span class="sxs-lookup"><span data-stu-id="71692-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 <span data-ttu-id="71692-140">[!code-vb[VbXMLSamples #&12;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="71692-140">[!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]</span></span>  
  
 <span data-ttu-id="71692-141">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="71692-141">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="71692-142">示例</span><span class="sxs-lookup"><span data-stu-id="71692-142">Example</span></span>  
 <span data-ttu-id="71692-143">下面的示例演示如何以声明方式的一部分，该 XML，并动态地通过将属性添加到的实例创建这两个 XML 元素的属性<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="71692-143">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="71692-144">`type`属性以声明方式创建和`owne`r 特性动态创建。</span><span class="sxs-lookup"><span data-stu-id="71692-144">The `type` attribute is created declaratively and the `owne`r attribute is created dynamically.</span></span>  
  
 <span data-ttu-id="71692-145">[!code-vb[VbXMLSamples #&44;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="71692-145">[!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]</span></span>  
  
 <span data-ttu-id="71692-146">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="71692-146">This code displays the following text:</span></span>  
  
```  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="71692-147">示例</span><span class="sxs-lookup"><span data-stu-id="71692-147">Example</span></span>  
 <span data-ttu-id="71692-148">下面的示例使用尖括号语法来获取名为 XML 属性的值`number-type`，它不在有效标识符[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="71692-148">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="71692-149">[!code-vb[VbXMLSamples #&13;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="71692-149">[!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]</span></span>  
  
 <span data-ttu-id="71692-150">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="71692-150">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="71692-151">示例</span><span class="sxs-lookup"><span data-stu-id="71692-151">Example</span></span>  
 <span data-ttu-id="71692-152">下面的示例声明 `ns` 作为 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="71692-152">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="71692-153">它然后使用该命名空间前缀创建 XML 文本和访问的第一个子节点的限定名"`ns:name`"。</span><span class="sxs-lookup"><span data-stu-id="71692-153">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 <span data-ttu-id="71692-154">[!code-vb[VbXMLSamples #&14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="71692-154">[!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]</span></span>  
  
 <span data-ttu-id="71692-155">此代码显示以下文本：</span><span class="sxs-lookup"><span data-stu-id="71692-155">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="71692-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71692-156">See Also</span></span>  
 <span data-ttu-id="71692-157"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="71692-157"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="71692-158"> [XML 轴属性](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="71692-158"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="71692-159"> [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="71692-159"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="71692-160"> [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="71692-160"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="71692-161"> [已声明的 XML 元素和特性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="71692-161"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span></span>
