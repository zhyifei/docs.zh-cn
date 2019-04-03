---
title: GetXmlNamespace 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 757ca54e5ba370bf2cc48bc70499e7b43ec96ef6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834746"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="e051f-102">GetXmlNamespace 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e051f-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="e051f-103">获取<xref:System.Xml.Linq.XNamespace>对应于指定的 XML 命名空间前缀的对象。</span><span class="sxs-lookup"><span data-stu-id="e051f-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e051f-104">语法</span><span class="sxs-lookup"><span data-stu-id="e051f-104">Syntax</span></span>  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="e051f-105">部件</span><span class="sxs-lookup"><span data-stu-id="e051f-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="e051f-106">可选。</span><span class="sxs-lookup"><span data-stu-id="e051f-106">Optional.</span></span> <span data-ttu-id="e051f-107">用于标识的 XML 命名空间前缀的字符串。</span><span class="sxs-lookup"><span data-stu-id="e051f-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="e051f-108">如果提供，此字符串必须是有效的 XML 标识符。</span><span class="sxs-lookup"><span data-stu-id="e051f-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="e051f-109">有关详细信息，请参阅[名称的声明 XML 元素和属性](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="e051f-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="e051f-110">如果不指定任何前缀，则返回默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="e051f-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="e051f-111">如果指定没有默认命名空间，则返回空命名空间。</span><span class="sxs-lookup"><span data-stu-id="e051f-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e051f-112">返回值</span><span class="sxs-lookup"><span data-stu-id="e051f-112">Return Value</span></span>  
 <span data-ttu-id="e051f-113"><xref:System.Xml.Linq.XNamespace>对应于 XML 命名空间前缀的对象。</span><span class="sxs-lookup"><span data-stu-id="e051f-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e051f-114">备注</span><span class="sxs-lookup"><span data-stu-id="e051f-114">Remarks</span></span>  
 <span data-ttu-id="e051f-115">`GetXmlNamespace`运算符获取<xref:System.Xml.Linq.XNamespace>对象，它对应于 XML 命名空间前缀`xmlNamespacePrefix`。</span><span class="sxs-lookup"><span data-stu-id="e051f-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="e051f-116">可以使用直接在 XML 文本和 XML 轴属性中的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="e051f-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="e051f-117">但是，必须使用`GetXmlNamespace`运算符将转换为的命名空间前缀<xref:System.Xml.Linq.XNamespace>对象，然后可以在代码中使用它。</span><span class="sxs-lookup"><span data-stu-id="e051f-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="e051f-118">您可以将附加到的非限定的元素名称<xref:System.Xml.Linq.XNamespace>对象获取完全限定<xref:System.Xml.Linq.XName>对象的多[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]方法需要。</span><span class="sxs-lookup"><span data-stu-id="e051f-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e051f-119">示例</span><span class="sxs-lookup"><span data-stu-id="e051f-119">Example</span></span>  
 <span data-ttu-id="e051f-120">以下示例将导入`ns`作为 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="e051f-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="e051f-121">然后，它使用的命名空间前缀来创建 XML 文本和访问具有限定的名称的第一个子节点`ns:phone`。</span><span class="sxs-lookup"><span data-stu-id="e051f-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="e051f-122">然后将传递到的子节点`ShowName`子例程，它构造限定的名称，方法是使用`GetXmlNamespace`运算符。</span><span class="sxs-lookup"><span data-stu-id="e051f-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="e051f-123">`ShowName`子例程然后将传递到的限定的名<xref:System.Xml.Linq.XNode.Ancestors%2A>方法以获取父`ns:contact`节点。</span><span class="sxs-lookup"><span data-stu-id="e051f-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="e051f-124">当您调用`TestGetXmlNamespace.RunSample()`，它将显示一个消息框，包含以下文本：</span><span class="sxs-lookup"><span data-stu-id="e051f-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="e051f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="e051f-125">See also</span></span>

- [<span data-ttu-id="e051f-126">Imports 语句（XML 命名空间）</span><span class="sxs-lookup"><span data-stu-id="e051f-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="e051f-127">在 Visual Basic 中访问 XML</span><span class="sxs-lookup"><span data-stu-id="e051f-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
