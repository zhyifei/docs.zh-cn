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
ms.openlocfilehash: 91369392f33f2a86a7a4cb5ffb3faa668c113348
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965403"
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="2e417-102">XML 注释文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e417-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="2e417-103">表示<xref:System.Xml.Linq.XComment>对象的文本。</span><span class="sxs-lookup"><span data-stu-id="2e417-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e417-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e417-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="2e417-105">部件</span><span class="sxs-lookup"><span data-stu-id="2e417-105">Parts</span></span>  
  
|<span data-ttu-id="2e417-106">术语</span><span class="sxs-lookup"><span data-stu-id="2e417-106">Term</span></span>|<span data-ttu-id="2e417-107">定义</span><span class="sxs-lookup"><span data-stu-id="2e417-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="2e417-108">必需。</span><span class="sxs-lookup"><span data-stu-id="2e417-108">Required.</span></span> <span data-ttu-id="2e417-109">表示 XML 注释的开头。</span><span class="sxs-lookup"><span data-stu-id="2e417-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="2e417-110">必需。</span><span class="sxs-lookup"><span data-stu-id="2e417-110">Required.</span></span> <span data-ttu-id="2e417-111">要在 XML 注释中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="2e417-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="2e417-112">不能包含一系列两个连字符 (--), 也不能以与结束标记相邻的连字符结尾。</span><span class="sxs-lookup"><span data-stu-id="2e417-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="2e417-113">必需。</span><span class="sxs-lookup"><span data-stu-id="2e417-113">Required.</span></span> <span data-ttu-id="2e417-114">表示 XML 注释的结尾。</span><span class="sxs-lookup"><span data-stu-id="2e417-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="2e417-115">返回值</span><span class="sxs-lookup"><span data-stu-id="2e417-115">Return Value</span></span>  
 <span data-ttu-id="2e417-116">一个 <xref:System.Xml.Linq.XComment> 对象。</span><span class="sxs-lookup"><span data-stu-id="2e417-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e417-117">备注</span><span class="sxs-lookup"><span data-stu-id="2e417-117">Remarks</span></span>  
 <span data-ttu-id="2e417-118">XML 注释文本不包含文档内容;它们包含有关文档的信息。</span><span class="sxs-lookup"><span data-stu-id="2e417-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="2e417-119">XML 注释部分以序列 "-->" 结尾。</span><span class="sxs-lookup"><span data-stu-id="2e417-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="2e417-120">这意味着:</span><span class="sxs-lookup"><span data-stu-id="2e417-120">This implies the following points:</span></span>  
  
- <span data-ttu-id="2e417-121">不能在 XML 注释文本中使用嵌入表达式, 因为嵌入式表达式分隔符是有效的 XML 注释内容。</span><span class="sxs-lookup"><span data-stu-id="2e417-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
- <span data-ttu-id="2e417-122">XML 注释部分不能嵌套, 因为`content`不能包含值 "-->"。</span><span class="sxs-lookup"><span data-stu-id="2e417-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="2e417-123">可以将 XML 注释文本分配给一个变量, 也可以将其包含在 XML 元素文本中。</span><span class="sxs-lookup"><span data-stu-id="2e417-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e417-124">XML 文本可以跨多行, 而无需使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="2e417-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="2e417-125">此功能使你能够从 XML 文档复制内容并将其直接粘贴到 Visual Basic 程序。</span><span class="sxs-lookup"><span data-stu-id="2e417-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="2e417-126">Visual Basic 编译器将 XML 注释文本转换为对<xref:System.Xml.Linq.XComment.%23ctor%2A>构造函数的调用。</span><span class="sxs-lookup"><span data-stu-id="2e417-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e417-127">示例</span><span class="sxs-lookup"><span data-stu-id="2e417-127">Example</span></span>  
 <span data-ttu-id="2e417-128">下面的示例创建一个包含文本 "This is a comment" 的 XML 注释。</span><span class="sxs-lookup"><span data-stu-id="2e417-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="2e417-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e417-129">See also</span></span>

- <xref:System.Xml.Linq.XComment>
- [<span data-ttu-id="2e417-130">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="2e417-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="2e417-131">XML 文本</span><span class="sxs-lookup"><span data-stu-id="2e417-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="2e417-132">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="2e417-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
