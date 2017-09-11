---
title: "XML 注释文本 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralComment
dev_langs:
- VB
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
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
ms.openlocfilehash: ab896399b664c658710c24d9799218ff3d81aecc
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="40899-102">XML 注释文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40899-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="40899-103">一个文字表示<xref:System.Xml.Linq.XComment>对象。</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="40899-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40899-104">语法</span><span class="sxs-lookup"><span data-stu-id="40899-104">Syntax</span></span>  
  
```  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="40899-105">部件</span><span class="sxs-lookup"><span data-stu-id="40899-105">Parts</span></span>  
  
|<span data-ttu-id="40899-106">术语</span><span class="sxs-lookup"><span data-stu-id="40899-106">Term</span></span>|<span data-ttu-id="40899-107">定义</span><span class="sxs-lookup"><span data-stu-id="40899-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="40899-108">必需。</span><span class="sxs-lookup"><span data-stu-id="40899-108">Required.</span></span> <span data-ttu-id="40899-109">表示 XML 注释的开头。</span><span class="sxs-lookup"><span data-stu-id="40899-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="40899-110">必需。</span><span class="sxs-lookup"><span data-stu-id="40899-110">Required.</span></span> <span data-ttu-id="40899-111">将出现在 XML 注释文本。</span><span class="sxs-lookup"><span data-stu-id="40899-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="40899-112">不能包含一系列的两个连字符 （-） 或相邻的结束标记的连字符结尾。</span><span class="sxs-lookup"><span data-stu-id="40899-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="40899-113">必需。</span><span class="sxs-lookup"><span data-stu-id="40899-113">Required.</span></span> <span data-ttu-id="40899-114">表示 XML 注释的结尾。</span><span class="sxs-lookup"><span data-stu-id="40899-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="40899-115">返回值</span><span class="sxs-lookup"><span data-stu-id="40899-115">Return Value</span></span>  
 <span data-ttu-id="40899-116"><xref:System.Xml.Linq.XComment>对象。</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="40899-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40899-117">备注</span><span class="sxs-lookup"><span data-stu-id="40899-117">Remarks</span></span>  
 <span data-ttu-id="40899-118">XML 注释文本不包含文档内容;它们包含有关文档的信息。</span><span class="sxs-lookup"><span data-stu-id="40899-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="40899-119">XML 注释部分结尾"-->"的序列。</span><span class="sxs-lookup"><span data-stu-id="40899-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="40899-120">这意味着以下几点︰</span><span class="sxs-lookup"><span data-stu-id="40899-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="40899-121">您不能在 XML 注释文本中使用嵌入式的表达式，因为嵌入式的表达式分隔符是有效的 XML 注释内容。</span><span class="sxs-lookup"><span data-stu-id="40899-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="40899-122">不能嵌套 XML 注释部分，因为`content`不能包含"-->"的值。</span><span class="sxs-lookup"><span data-stu-id="40899-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="40899-123">可以将 XML 注释文本分配给一个变量，或者可以将其包含在 XML 元素文本。</span><span class="sxs-lookup"><span data-stu-id="40899-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40899-124">XML 文本可以跨多个行，而无需使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="40899-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="40899-125">此功能允许你复制内容的 XML 文档中，将其粘贴直接到[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]程序。</span><span class="sxs-lookup"><span data-stu-id="40899-125">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="40899-126">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器将 XML 注释文本转换为调用<xref:System.Xml.Linq.XComment.%23ctor%2A>构造函数。</xref:System.Xml.Linq.XComment.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="40899-126">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40899-127">示例</span><span class="sxs-lookup"><span data-stu-id="40899-127">Example</span></span>  
 <span data-ttu-id="40899-128">下面的示例创建包含文本的 XML 注释"这是一条注释"。</span><span class="sxs-lookup"><span data-stu-id="40899-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 <span data-ttu-id="40899-129">[!code-vb[VbXMLSamples #&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="40899-129">[!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40899-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40899-130">See Also</span></span>  
 <span data-ttu-id="40899-131"><xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="40899-131"><xref:System.Xml.Linq.XComment></span></span>   
<span data-ttu-id="40899-132"> [XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="40899-132"> [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="40899-133"> [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="40899-133"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="40899-134"> [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="40899-134"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span></span>
