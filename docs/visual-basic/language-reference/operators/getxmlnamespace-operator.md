---
title: GetXmlNamespace 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 4d6e738f4e3a47d73e37c395dd74fe19e99d81bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353195"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="161df-102">GetXmlNamespace 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="161df-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="161df-103">获取与指定的 XML 命名空间前缀相对应的 <xref:System.Xml.Linq.XNamespace> 对象。</span><span class="sxs-lookup"><span data-stu-id="161df-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="161df-104">语法</span><span class="sxs-lookup"><span data-stu-id="161df-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="161df-105">部件</span><span class="sxs-lookup"><span data-stu-id="161df-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="161df-106">可选。</span><span class="sxs-lookup"><span data-stu-id="161df-106">Optional.</span></span> <span data-ttu-id="161df-107">标识 XML 命名空间前缀的字符串。</span><span class="sxs-lookup"><span data-stu-id="161df-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="161df-108">如果提供，则此字符串必须是有效的 XML 标识符。</span><span class="sxs-lookup"><span data-stu-id="161df-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="161df-109">有关详细信息，请参阅已[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="161df-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="161df-110">如果未指定前缀，则返回默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="161df-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="161df-111">如果未指定默认命名空间，则返回空命名空间。</span><span class="sxs-lookup"><span data-stu-id="161df-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="161df-112">返回值</span><span class="sxs-lookup"><span data-stu-id="161df-112">Return Value</span></span>  
 <span data-ttu-id="161df-113">对应于 XML 命名空间前缀的 <xref:System.Xml.Linq.XNamespace> 对象。</span><span class="sxs-lookup"><span data-stu-id="161df-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="161df-114">备注</span><span class="sxs-lookup"><span data-stu-id="161df-114">Remarks</span></span>  
 <span data-ttu-id="161df-115">`GetXmlNamespace` 运算符获取对应于 XML 命名空间前缀 `xmlNamespacePrefix`的 <xref:System.Xml.Linq.XNamespace> 对象。</span><span class="sxs-lookup"><span data-stu-id="161df-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="161df-116">您可以直接在 XML 文本和 XML 轴属性中使用 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="161df-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="161df-117">但是，必须使用 `GetXmlNamespace` 运算符将命名空间前缀转换为 <xref:System.Xml.Linq.XNamespace> 对象，然后才能在代码中使用它。</span><span class="sxs-lookup"><span data-stu-id="161df-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="161df-118">可以将未限定的元素名称追加到 <xref:System.Xml.Linq.XNamespace> 对象，以获取完全限定的 <xref:System.Xml.Linq.XName> 对象，这很多 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 方法都需要。</span><span class="sxs-lookup"><span data-stu-id="161df-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="161df-119">示例</span><span class="sxs-lookup"><span data-stu-id="161df-119">Example</span></span>  
 <span data-ttu-id="161df-120">下面的示例将 `ns` 导入为 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="161df-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="161df-121">然后，它使用命名空间的前缀创建 XML 文本，并访问具有限定名 `ns:phone`的第一个子节点。</span><span class="sxs-lookup"><span data-stu-id="161df-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="161df-122">然后，它将该子节点传递到 `ShowName` 子例程，该子例程使用 `GetXmlNamespace` 运算符构造限定名称。</span><span class="sxs-lookup"><span data-stu-id="161df-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="161df-123">然后 `ShowName` 子例程将限定名传递给 <xref:System.Xml.Linq.XNode.Ancestors%2A> 方法以获取父 `ns:contact` 节点。</span><span class="sxs-lookup"><span data-stu-id="161df-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="161df-124">调用 `TestGetXmlNamespace.RunSample()`时，它将显示一个消息框，其中包含以下文本：</span><span class="sxs-lookup"><span data-stu-id="161df-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="161df-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="161df-125">See also</span></span>

- [<span data-ttu-id="161df-126">Imports 语句（XML 命名空间）</span><span class="sxs-lookup"><span data-stu-id="161df-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="161df-127">在 Visual Basic 中访问 XML</span><span class="sxs-lookup"><span data-stu-id="161df-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
