---
title: XML 注释文本 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d5bb8c10c28a4ab864220c1b4ce4702622e55c92
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="d5599-102">XML 注释文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5599-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="d5599-103">一个文本表示<xref:System.Xml.Linq.XComment>对象。</span><span class="sxs-lookup"><span data-stu-id="d5599-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5599-104">语法</span><span class="sxs-lookup"><span data-stu-id="d5599-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="d5599-105">部件</span><span class="sxs-lookup"><span data-stu-id="d5599-105">Parts</span></span>  
  
|<span data-ttu-id="d5599-106">术语</span><span class="sxs-lookup"><span data-stu-id="d5599-106">Term</span></span>|<span data-ttu-id="d5599-107">定义</span><span class="sxs-lookup"><span data-stu-id="d5599-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="d5599-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="d5599-108">Required.</span></span> <span data-ttu-id="d5599-109">表示 XML 注释的开头。</span><span class="sxs-lookup"><span data-stu-id="d5599-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="d5599-110">必须的。</span><span class="sxs-lookup"><span data-stu-id="d5599-110">Required.</span></span> <span data-ttu-id="d5599-111">若要显示的 XML 注释中的文本。</span><span class="sxs-lookup"><span data-stu-id="d5599-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="d5599-112">不能包含一系列的两个连字符 （-） 或靠近结束标记的连字符结尾。</span><span class="sxs-lookup"><span data-stu-id="d5599-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="d5599-113">必须的。</span><span class="sxs-lookup"><span data-stu-id="d5599-113">Required.</span></span> <span data-ttu-id="d5599-114">表示 XML 注释的结尾。</span><span class="sxs-lookup"><span data-stu-id="d5599-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="d5599-115">返回值</span><span class="sxs-lookup"><span data-stu-id="d5599-115">Return Value</span></span>  
 <span data-ttu-id="d5599-116">一个 <xref:System.Xml.Linq.XComment> 对象。</span><span class="sxs-lookup"><span data-stu-id="d5599-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5599-117">备注</span><span class="sxs-lookup"><span data-stu-id="d5599-117">Remarks</span></span>  
 <span data-ttu-id="d5599-118">XML 注释文本不包含文档内容;它们包含有关文档的信息。</span><span class="sxs-lookup"><span data-stu-id="d5599-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="d5599-119">序列"-->"结尾的 XML 注释部分。</span><span class="sxs-lookup"><span data-stu-id="d5599-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="d5599-120">这意味着以下几点：</span><span class="sxs-lookup"><span data-stu-id="d5599-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="d5599-121">你无法使用嵌入式的表达式 XML 注释文本中，因为嵌入式的表达式分隔符是有效的 XML 注释内容。</span><span class="sxs-lookup"><span data-stu-id="d5599-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="d5599-122">XML 注释部分不能嵌套，因为`content`不能包含值"-->"。</span><span class="sxs-lookup"><span data-stu-id="d5599-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="d5599-123">可以将 XML 注释文本分配给一个变量，或者可以将其包含在 XML 元素文本。</span><span class="sxs-lookup"><span data-stu-id="d5599-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5599-124">XML 文本可以跨多行，而无需使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="d5599-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="d5599-125">此功能，可从 XML 文档中复制内容，然后将其粘贴到 Visual Basic 程序直接。</span><span class="sxs-lookup"><span data-stu-id="d5599-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="d5599-126">Visual Basic 编译器将 XML 注释文本转换为调用<xref:System.Xml.Linq.XComment.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="d5599-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5599-127">示例</span><span class="sxs-lookup"><span data-stu-id="d5599-127">Example</span></span>  
 <span data-ttu-id="d5599-128">下面的示例创建包含文本的 XML 注释"这是一个注释"。</span><span class="sxs-lookup"><span data-stu-id="d5599-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d5599-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5599-129">See Also</span></span>  
 <xref:System.Xml.Linq.XComment>  
 [<span data-ttu-id="d5599-130">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="d5599-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="d5599-131">XML 文本</span><span class="sxs-lookup"><span data-stu-id="d5599-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="d5599-132">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="d5599-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
