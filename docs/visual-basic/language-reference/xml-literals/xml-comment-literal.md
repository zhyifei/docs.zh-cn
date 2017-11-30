---
title: "XML 注释文本 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36be34ac22cfe926a2eea946f5e4c4eb534de696
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="47d22-102">XML 注释文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47d22-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="47d22-103">一个文本表示<xref:System.Xml.Linq.XComment>对象。</span><span class="sxs-lookup"><span data-stu-id="47d22-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47d22-104">语法</span><span class="sxs-lookup"><span data-stu-id="47d22-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="47d22-105">部件</span><span class="sxs-lookup"><span data-stu-id="47d22-105">Parts</span></span>  
  
|<span data-ttu-id="47d22-106">术语</span><span class="sxs-lookup"><span data-stu-id="47d22-106">Term</span></span>|<span data-ttu-id="47d22-107">定义</span><span class="sxs-lookup"><span data-stu-id="47d22-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="47d22-108">必需。</span><span class="sxs-lookup"><span data-stu-id="47d22-108">Required.</span></span> <span data-ttu-id="47d22-109">表示 XML 注释的开头。</span><span class="sxs-lookup"><span data-stu-id="47d22-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="47d22-110">必需。</span><span class="sxs-lookup"><span data-stu-id="47d22-110">Required.</span></span> <span data-ttu-id="47d22-111">若要显示的 XML 注释中的文本。</span><span class="sxs-lookup"><span data-stu-id="47d22-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="47d22-112">不能包含一系列的两个连字符 （-） 或靠近结束标记的连字符结尾。</span><span class="sxs-lookup"><span data-stu-id="47d22-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="47d22-113">必需。</span><span class="sxs-lookup"><span data-stu-id="47d22-113">Required.</span></span> <span data-ttu-id="47d22-114">表示 XML 注释的结尾。</span><span class="sxs-lookup"><span data-stu-id="47d22-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="47d22-115">返回值</span><span class="sxs-lookup"><span data-stu-id="47d22-115">Return Value</span></span>  
 <span data-ttu-id="47d22-116">一个 <xref:System.Xml.Linq.XComment> 对象。</span><span class="sxs-lookup"><span data-stu-id="47d22-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47d22-117">备注</span><span class="sxs-lookup"><span data-stu-id="47d22-117">Remarks</span></span>  
 <span data-ttu-id="47d22-118">XML 注释文本不包含文档内容;它们包含有关文档的信息。</span><span class="sxs-lookup"><span data-stu-id="47d22-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="47d22-119">序列"-->"结尾的 XML 注释部分。</span><span class="sxs-lookup"><span data-stu-id="47d22-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="47d22-120">这意味着以下几点：</span><span class="sxs-lookup"><span data-stu-id="47d22-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="47d22-121">你无法使用嵌入式的表达式 XML 注释文本中，因为嵌入式的表达式分隔符是有效的 XML 注释内容。</span><span class="sxs-lookup"><span data-stu-id="47d22-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="47d22-122">XML 注释部分不能嵌套，因为`content`不能包含值"-->"。</span><span class="sxs-lookup"><span data-stu-id="47d22-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="47d22-123">可以将 XML 注释文本分配给一个变量，或者可以将其包含在 XML 元素文本。</span><span class="sxs-lookup"><span data-stu-id="47d22-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47d22-124">XML 文本可以跨多行，而无需使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="47d22-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="47d22-125">此功能，可将内容复制从 XML 文档并将其粘贴直接到[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]程序。</span><span class="sxs-lookup"><span data-stu-id="47d22-125">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="47d22-126">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器将 XML 注释文本转换为调用<xref:System.Xml.Linq.XComment.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="47d22-126">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47d22-127">示例</span><span class="sxs-lookup"><span data-stu-id="47d22-127">Example</span></span>  
 <span data-ttu-id="47d22-128">下面的示例创建包含文本的 XML 注释"这是一个注释"。</span><span class="sxs-lookup"><span data-stu-id="47d22-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="47d22-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47d22-129">See Also</span></span>  
 <xref:System.Xml.Linq.XComment>  
 [<span data-ttu-id="47d22-130">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="47d22-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="47d22-131">XML 文本</span><span class="sxs-lookup"><span data-stu-id="47d22-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="47d22-132">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="47d22-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
