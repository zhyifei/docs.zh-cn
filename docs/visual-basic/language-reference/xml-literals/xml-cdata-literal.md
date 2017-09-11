---
title: "XML CDATA 文本 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralCdata
dev_langs:
- VB
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: 16
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
ms.openlocfilehash: 6bf12a5dd5b24b0a915cb15f41cb8947c33e94b0
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="10d8d-102">XML CDATA 文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10d8d-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="10d8d-103">一个文字表示<xref:System.Xml.Linq.XCData>对象。</xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="10d8d-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10d8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="10d8d-104">Syntax</span></span>  
  
```  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="10d8d-105">部件</span><span class="sxs-lookup"><span data-stu-id="10d8d-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="10d8d-106">必需。</span><span class="sxs-lookup"><span data-stu-id="10d8d-106">Required.</span></span> <span data-ttu-id="10d8d-107">表示 XML CDATA 节的开头。</span><span class="sxs-lookup"><span data-stu-id="10d8d-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="10d8d-108">必需。</span><span class="sxs-lookup"><span data-stu-id="10d8d-108">Required.</span></span> <span data-ttu-id="10d8d-109">若要显示在 XML CDATA 部分中的文本内容。</span><span class="sxs-lookup"><span data-stu-id="10d8d-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="10d8d-110">必需。</span><span class="sxs-lookup"><span data-stu-id="10d8d-110">Required.</span></span> <span data-ttu-id="10d8d-111">表示部分的结尾。</span><span class="sxs-lookup"><span data-stu-id="10d8d-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10d8d-112">返回值</span><span class="sxs-lookup"><span data-stu-id="10d8d-112">Return Value</span></span>  
 <span data-ttu-id="10d8d-113"><xref:System.Xml.Linq.XCData>对象。</xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="10d8d-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10d8d-114">备注</span><span class="sxs-lookup"><span data-stu-id="10d8d-114">Remarks</span></span>  
 <span data-ttu-id="10d8d-115">XML CDATA 节包含应包含，但不是会分析，含 XML 中包含它的原始文本。</span><span class="sxs-lookup"><span data-stu-id="10d8d-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="10d8d-116">XML CDATA 部分可以包含的任何文本。</span><span class="sxs-lookup"><span data-stu-id="10d8d-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="10d8d-117">这包括 XML 保留的字符。</span><span class="sxs-lookup"><span data-stu-id="10d8d-117">This includes reserved XML characters.</span></span> <span data-ttu-id="10d8d-118">XML CDATA 部分结束与序列"]]&1;>"。</span><span class="sxs-lookup"><span data-stu-id="10d8d-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="10d8d-119">这意味着以下几点︰</span><span class="sxs-lookup"><span data-stu-id="10d8d-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="10d8d-120">您不能在 XML CDATA 文本中使用嵌入式的表达式，因为嵌入式的表达式分隔符是有效的 XML CDATA 内容。</span><span class="sxs-lookup"><span data-stu-id="10d8d-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="10d8d-121">XML CDATA 节无法嵌套，因为`content`不能包含值"]]&1;>"。</span><span class="sxs-lookup"><span data-stu-id="10d8d-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="10d8d-122">您可以将 XML CDATA 文本分配给一个变量，或将其包含在 XML 元素文本。</span><span class="sxs-lookup"><span data-stu-id="10d8d-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10d8d-123">XML 文本可以跨多个行，但不使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="10d8d-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="10d8d-124">这使您可以从 XML 文档中复制内容并将其粘贴直接到[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]程序。</span><span class="sxs-lookup"><span data-stu-id="10d8d-124">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="10d8d-125">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器将 XML CDATA 文本转换为调用<xref:System.Xml.Linq.XCData.%23ctor%2A>构造函数。</xref:System.Xml.Linq.XCData.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="10d8d-125">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10d8d-126">示例</span><span class="sxs-lookup"><span data-stu-id="10d8d-126">Example</span></span>  
 <span data-ttu-id="10d8d-127">下面的示例创建一个包含文本的 CDATA 节"可以包含文字\<XML&1;> 标记"。</span><span class="sxs-lookup"><span data-stu-id="10d8d-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 <span data-ttu-id="10d8d-128">[!code-vb[VbXMLSamples 第&23;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="10d8d-128">[!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10d8d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10d8d-129">See Also</span></span>  
 <span data-ttu-id="10d8d-130"><xref:System.Xml.Linq.XCData></xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="10d8d-130"><xref:System.Xml.Linq.XCData></span></span>   
<span data-ttu-id="10d8d-131"> [XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="10d8d-131"> [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="10d8d-132"> [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="10d8d-132"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="10d8d-133"> [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="10d8d-133"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span></span>
