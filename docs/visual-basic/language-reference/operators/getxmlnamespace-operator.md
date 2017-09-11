---
title: "GetXmlNamespace 运算符 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
dev_langs:
- VB
helpviewer_keywords:
- GetXmlNamespace operator
- GetXmlNamespace keyword
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
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
ms.openlocfilehash: d6f977ab8c0b7dfb2dee936436ef4ec8530ba8f6
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="a67a8-102">GetXmlNamespace 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a67a8-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="a67a8-103">获取<xref:System.Xml.Linq.XNamespace>对应于指定的 XML 命名空间前缀的对象。</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="a67a8-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a67a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="a67a8-104">Syntax</span></span>  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="a67a8-105">部件</span><span class="sxs-lookup"><span data-stu-id="a67a8-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="a67a8-106">可选。</span><span class="sxs-lookup"><span data-stu-id="a67a8-106">Optional.</span></span> <span data-ttu-id="a67a8-107">标识 XML 命名空间前缀的字符串。</span><span class="sxs-lookup"><span data-stu-id="a67a8-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="a67a8-108">如果提供，此字符串必须是有效的 XML 标识符。</span><span class="sxs-lookup"><span data-stu-id="a67a8-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="a67a8-109">有关详细信息，请参阅[名称的声明 XML 元素和属性](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="a67a8-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="a67a8-110">如果未指定前缀，则返回默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="a67a8-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="a67a8-111">如果指定没有默认命名空间，则返回空命名空间。</span><span class="sxs-lookup"><span data-stu-id="a67a8-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a67a8-112">返回值</span><span class="sxs-lookup"><span data-stu-id="a67a8-112">Return Value</span></span>  
 <span data-ttu-id="a67a8-113"><xref:System.Xml.Linq.XNamespace>对应于 XML 命名空间前缀的对象。</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="a67a8-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a67a8-114">备注</span><span class="sxs-lookup"><span data-stu-id="a67a8-114">Remarks</span></span>  
 <span data-ttu-id="a67a8-115">`GetXmlNamespace`运算符获取<xref:System.Xml.Linq.XNamespace>对应于 XML 命名空间前缀的对象`xmlNamespacePrefix`。</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="a67a8-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="a67a8-116">您可以使用直接在 XML 文本和 XML 轴属性中的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="a67a8-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="a67a8-117">但是，必须使用`GetXmlNamespace`运算符以转换到的命名空间前缀<xref:System.Xml.Linq.XNamespace>对象，然后可以在代码中使用它。</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="a67a8-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="a67a8-118">您可以将附加到非限定的元素名称<xref:System.Xml.Linq.XNamespace>要获取完全限定对象<xref:System.Xml.Linq.XName>对象时，哪些多[!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]方法都要求。</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="a67a8-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a67a8-119">示例</span><span class="sxs-lookup"><span data-stu-id="a67a8-119">Example</span></span>  
 <span data-ttu-id="a67a8-120">下面的示例导入`ns`作为 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="a67a8-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="a67a8-121">它然后使用该命名空间前缀创建 XML 文本和访问具有限定的名的第一个子节点`ns:phone`。</span><span class="sxs-lookup"><span data-stu-id="a67a8-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="a67a8-122">然后将其传递到，该子节点`ShowName`子例程，它通过构造一个限定的名`GetXmlNamespace`运算符。</span><span class="sxs-lookup"><span data-stu-id="a67a8-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="a67a8-123">`ShowName`子例程然后将传递到的限定的名<xref:System.Xml.Linq.XNode.Ancestors%2A>方法要获取其父类`ns:contact`节点。</xref:System.Xml.Linq.XNode.Ancestors%2A></span><span class="sxs-lookup"><span data-stu-id="a67a8-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 <span data-ttu-id="a67a8-124">[!code-vb[VbXMLSamples #&38;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a67a8-124">[!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="a67a8-125">当您调用`TestGetXmlNamespace.RunSample()`，它将显示一个消息框，包含以下文本︰</span><span class="sxs-lookup"><span data-stu-id="a67a8-125">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="a67a8-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a67a8-126">See Also</span></span>  
 <span data-ttu-id="a67a8-127">[Imports 语句 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="a67a8-127">[Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="a67a8-128"> [在 Visual Basic 中访问 XML](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)</span><span class="sxs-lookup"><span data-stu-id="a67a8-128"> [Accessing XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)</span></span>
