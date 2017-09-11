---
title: "XML 文档文本 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralDocument
dev_langs:
- VB
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
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
ms.openlocfilehash: 5e173c8bc89f61925c3e6127fb3cac61379aeffa
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="32034-102">XML 文档文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32034-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="32034-103">一个文字表示<xref:System.Xml.Linq.XDocument>对象。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="32034-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32034-104">语法</span><span class="sxs-lookup"><span data-stu-id="32034-104">Syntax</span></span>  
  
```  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="32034-105">部件</span><span class="sxs-lookup"><span data-stu-id="32034-105">Parts</span></span>  
  
|<span data-ttu-id="32034-106">术语</span><span class="sxs-lookup"><span data-stu-id="32034-106">Term</span></span>|<span data-ttu-id="32034-107">定义</span><span class="sxs-lookup"><span data-stu-id="32034-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="32034-108">可选。</span><span class="sxs-lookup"><span data-stu-id="32034-108">Optional.</span></span> <span data-ttu-id="32034-109">声明的编码的文档使用的文字文本。</span><span class="sxs-lookup"><span data-stu-id="32034-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="32034-110">可选。</span><span class="sxs-lookup"><span data-stu-id="32034-110">Optional.</span></span> <span data-ttu-id="32034-111">文字文本。</span><span class="sxs-lookup"><span data-stu-id="32034-111">Literal text.</span></span> <span data-ttu-id="32034-112">必须是"yes"或"no"。</span><span class="sxs-lookup"><span data-stu-id="32034-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="32034-113">可选。</span><span class="sxs-lookup"><span data-stu-id="32034-113">Optional.</span></span> <span data-ttu-id="32034-114">XML 处理指令和 XML 注释的列表。</span><span class="sxs-lookup"><span data-stu-id="32034-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="32034-115">采用以下格式︰</span><span class="sxs-lookup"><span data-stu-id="32034-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="32034-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="32034-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="32034-117">每个`piComment`可以是以下之一︰</span><span class="sxs-lookup"><span data-stu-id="32034-117">Each `piComment`can be one of the following:</span></span><br /><br /><span data-ttu-id="32034-118"> -   [XML 处理指令文本](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="32034-118"> -   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="32034-119">-   [XML 注释文本](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="32034-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="32034-120">必需。</span><span class="sxs-lookup"><span data-stu-id="32034-120">Required.</span></span> <span data-ttu-id="32034-121">文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="32034-121">Root element of the document.</span></span> <span data-ttu-id="32034-122">格式为以下项之一︰</span><span class="sxs-lookup"><span data-stu-id="32034-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="32034-123">[XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="32034-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="32034-124">窗体的嵌入式表达式`<%=` `elementExp` `%>`。</span><span class="sxs-lookup"><span data-stu-id="32034-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="32034-125">`elementExp`返回以下类型之一︰</span><span class="sxs-lookup"><span data-stu-id="32034-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="32034-126"><xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="32034-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="32034-127">一个集合，包含一个<xref:System.Xml.Linq.XElement>对象以及任意数量的<xref:System.Xml.Linq.XProcessingInstruction>和<xref:System.Xml.Linq.XComment>对象。</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="32034-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="32034-128">有关详细信息，请参阅[XML 中的嵌入式表达式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="32034-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="32034-129">返回值</span><span class="sxs-lookup"><span data-stu-id="32034-129">Return Value</span></span>  
 <span data-ttu-id="32034-130"><xref:System.Xml.Linq.XDocument>对象。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="32034-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32034-131">备注</span><span class="sxs-lookup"><span data-stu-id="32034-131">Remarks</span></span>  
 <span data-ttu-id="32034-132">通过文本开头的 XML 声明进行标识的 XML 文档文本。</span><span class="sxs-lookup"><span data-stu-id="32034-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="32034-133">尽管每个 XML 文档文本必须恰好一个根 XML 元素，它可以有任意数量的 XML 处理指令和 XML 注释。</span><span class="sxs-lookup"><span data-stu-id="32034-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="32034-134">XML 文档文本不能出现在一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="32034-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32034-135">XML 文本可以跨多个行，而无需使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="32034-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="32034-136">这使您可以从 XML 文档中复制内容并将其粘贴直接到[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]程序。</span><span class="sxs-lookup"><span data-stu-id="32034-136">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="32034-137">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器将 XML 文档文本转换为对调用<xref:System.Xml.Linq.XDocument.%23ctor%2A>和<xref:System.Xml.Linq.XDeclaration.%23ctor%2A>构造函数。</xref:System.Xml.Linq.XDeclaration.%23ctor%2A> </xref:System.Xml.Linq.XDocument.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="32034-137">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32034-138">示例</span><span class="sxs-lookup"><span data-stu-id="32034-138">Example</span></span>  
 <span data-ttu-id="32034-139">下面的示例创建具有 XML 声明、 处理指令、 注释和一个包含另一个元素的元素的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="32034-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 <span data-ttu-id="32034-140">[!code-vb[VbXMLSamples #&30;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="32034-140">[!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32034-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32034-141">See Also</span></span>  
 <span data-ttu-id="32034-142"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="32034-142"><xref:System.Xml.Linq.XElement></span></span>   
 <span data-ttu-id="32034-143"><xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="32034-143"><xref:System.Xml.Linq.XProcessingInstruction></span></span>   
 <span data-ttu-id="32034-144"><xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="32034-144"><xref:System.Xml.Linq.XComment></span></span>   
 <span data-ttu-id="32034-145"><xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="32034-145"><xref:System.Xml.Linq.XDocument></span></span>   
<span data-ttu-id="32034-146"> [XML 处理指令文本](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md) </span><span class="sxs-lookup"><span data-stu-id="32034-146"> [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md) </span></span>  
<span data-ttu-id="32034-147"> [XML 注释文本](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span><span class="sxs-lookup"><span data-stu-id="32034-147"> [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span></span>  
<span data-ttu-id="32034-148"> [XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="32034-148"> [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="32034-149"> [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="32034-149"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="32034-150"> [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="32034-150"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="32034-151"> [XML 中的嵌入式表达式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)</span><span class="sxs-lookup"><span data-stu-id="32034-151"> [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)</span></span>
