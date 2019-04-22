---
title: XML 注释文本 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 149bbac6d301a9c2f166d05698e3780171126cb3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827271"
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="adfb3-102">XML 注释文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adfb3-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="adfb3-103">一个文本表示<xref:System.Xml.Linq.XComment>对象。</span><span class="sxs-lookup"><span data-stu-id="adfb3-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adfb3-104">语法</span><span class="sxs-lookup"><span data-stu-id="adfb3-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="adfb3-105">部件</span><span class="sxs-lookup"><span data-stu-id="adfb3-105">Parts</span></span>  
  
|<span data-ttu-id="adfb3-106">术语</span><span class="sxs-lookup"><span data-stu-id="adfb3-106">Term</span></span>|<span data-ttu-id="adfb3-107">定义</span><span class="sxs-lookup"><span data-stu-id="adfb3-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="adfb3-108">必需。</span><span class="sxs-lookup"><span data-stu-id="adfb3-108">Required.</span></span> <span data-ttu-id="adfb3-109">表示 XML 注释的开始。</span><span class="sxs-lookup"><span data-stu-id="adfb3-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="adfb3-110">必需。</span><span class="sxs-lookup"><span data-stu-id="adfb3-110">Required.</span></span> <span data-ttu-id="adfb3-111">XML 注释中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="adfb3-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="adfb3-112">不能包含一系列的两个连字符 （-） 或与结束标记相邻的连字符结尾。</span><span class="sxs-lookup"><span data-stu-id="adfb3-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="adfb3-113">必需。</span><span class="sxs-lookup"><span data-stu-id="adfb3-113">Required.</span></span> <span data-ttu-id="adfb3-114">表示 XML 注释的结尾。</span><span class="sxs-lookup"><span data-stu-id="adfb3-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="adfb3-115">返回值</span><span class="sxs-lookup"><span data-stu-id="adfb3-115">Return Value</span></span>  
 <span data-ttu-id="adfb3-116">一个 <xref:System.Xml.Linq.XComment> 对象。</span><span class="sxs-lookup"><span data-stu-id="adfb3-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adfb3-117">备注</span><span class="sxs-lookup"><span data-stu-id="adfb3-117">Remarks</span></span>  
 <span data-ttu-id="adfb3-118">XML 注释文本不包含文档内容;它们包含有关文档的信息。</span><span class="sxs-lookup"><span data-stu-id="adfb3-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="adfb3-119">序列"-->"结尾的 XML 注释部分。</span><span class="sxs-lookup"><span data-stu-id="adfb3-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="adfb3-120">这意味着以下几点：</span><span class="sxs-lookup"><span data-stu-id="adfb3-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="adfb3-121">因为嵌入的分隔符是有效的 XML 注释内容，不能在 XML 注释文本中使用嵌入式的表达式。</span><span class="sxs-lookup"><span data-stu-id="adfb3-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="adfb3-122">XML 注释节无法嵌套，因为`content`不能包含值"-->"。</span><span class="sxs-lookup"><span data-stu-id="adfb3-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="adfb3-123">可以将 XML 注释文本分配给一个变量，或将其包含在 XML 元素文本中。</span><span class="sxs-lookup"><span data-stu-id="adfb3-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adfb3-124">XML 文本可以跨多个行，而无需使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="adfb3-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="adfb3-125">此功能，可将内容从 XML 文档复制并粘贴直接到 Visual Basic 程序。</span><span class="sxs-lookup"><span data-stu-id="adfb3-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="adfb3-126">Visual Basic 编译器将 XML 注释文本转换为调用<xref:System.Xml.Linq.XComment.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="adfb3-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adfb3-127">示例</span><span class="sxs-lookup"><span data-stu-id="adfb3-127">Example</span></span>  
 <span data-ttu-id="adfb3-128">以下示例创建 XML 注释包含文本"这是一条注释"。</span><span class="sxs-lookup"><span data-stu-id="adfb3-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="adfb3-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="adfb3-129">See also</span></span>

- <xref:System.Xml.Linq.XComment>
- [<span data-ttu-id="adfb3-130">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="adfb3-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="adfb3-131">XML 文本</span><span class="sxs-lookup"><span data-stu-id="adfb3-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="adfb3-132">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="adfb3-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
