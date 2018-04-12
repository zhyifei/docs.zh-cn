---
title: XML 文档文本 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 008b5857418a572046797bf061a05f265669d427
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="a8339-102">XML 文档文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8339-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="a8339-103">一个文本表示<xref:System.Xml.Linq.XDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="a8339-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8339-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8339-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="a8339-105">部件</span><span class="sxs-lookup"><span data-stu-id="a8339-105">Parts</span></span>  
  
|<span data-ttu-id="a8339-106">术语</span><span class="sxs-lookup"><span data-stu-id="a8339-106">Term</span></span>|<span data-ttu-id="a8339-107">定义</span><span class="sxs-lookup"><span data-stu-id="a8339-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="a8339-108">可选。</span><span class="sxs-lookup"><span data-stu-id="a8339-108">Optional.</span></span> <span data-ttu-id="a8339-109">声明的编码的文档使用的文字文本。</span><span class="sxs-lookup"><span data-stu-id="a8339-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="a8339-110">可选。</span><span class="sxs-lookup"><span data-stu-id="a8339-110">Optional.</span></span> <span data-ttu-id="a8339-111">文字文本。</span><span class="sxs-lookup"><span data-stu-id="a8339-111">Literal text.</span></span> <span data-ttu-id="a8339-112">必须为"是"或"否"。</span><span class="sxs-lookup"><span data-stu-id="a8339-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="a8339-113">可选。</span><span class="sxs-lookup"><span data-stu-id="a8339-113">Optional.</span></span> <span data-ttu-id="a8339-114">XML 处理指令和 XML 注释的列表。</span><span class="sxs-lookup"><span data-stu-id="a8339-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="a8339-115">采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="a8339-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="a8339-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="a8339-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="a8339-117">每个`piComment`可以是以下之一：</span><span class="sxs-lookup"><span data-stu-id="a8339-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="a8339-118">-   [XML 处理指令文本](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="a8339-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="a8339-119">-   [XML 注释文本](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="a8339-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="a8339-120">必需。</span><span class="sxs-lookup"><span data-stu-id="a8339-120">Required.</span></span> <span data-ttu-id="a8339-121">文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="a8339-121">Root element of the document.</span></span> <span data-ttu-id="a8339-122">格式为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="a8339-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="a8339-123">[XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="a8339-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="a8339-124">嵌入形式的表达式`<%=` `elementExp` `%>`。</span><span class="sxs-lookup"><span data-stu-id="a8339-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="a8339-125">`elementExp`返回以下项之一：</span><span class="sxs-lookup"><span data-stu-id="a8339-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="a8339-126">一个 <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="a8339-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="a8339-127">一个集合包含一个<xref:System.Xml.Linq.XElement>对象以及任意数量的<xref:System.Xml.Linq.XProcessingInstruction>和<xref:System.Xml.Linq.XComment>对象。</span><span class="sxs-lookup"><span data-stu-id="a8339-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="a8339-128">有关详细信息，请参阅[XML 中的嵌入式表达式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="a8339-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="a8339-129">返回值</span><span class="sxs-lookup"><span data-stu-id="a8339-129">Return Value</span></span>  
 <span data-ttu-id="a8339-130">一个 <xref:System.Xml.Linq.XDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="a8339-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8339-131">备注</span><span class="sxs-lookup"><span data-stu-id="a8339-131">Remarks</span></span>  
 <span data-ttu-id="a8339-132">XML 文档文本由开头的文本的 XML 声明标识。</span><span class="sxs-lookup"><span data-stu-id="a8339-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="a8339-133">尽管每个 XML 文档文本必须具有恰好一个根 XML 元素，但它可具有任意数量的 XML 处理指令和 XML 注释。</span><span class="sxs-lookup"><span data-stu-id="a8339-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="a8339-134">XML 文档文本不能出现在一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="a8339-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8339-135">XML 文本可以跨多行，而无需使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="a8339-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="a8339-136">这使您可以从 XML 文档中复制内容，然后将其粘贴直接到[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]程序。</span><span class="sxs-lookup"><span data-stu-id="a8339-136">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="a8339-137">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器将 XML 文档文本转换为对的调用<xref:System.Xml.Linq.XDocument.%23ctor%2A>和<xref:System.Xml.Linq.XDeclaration.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="a8339-137">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8339-138">示例</span><span class="sxs-lookup"><span data-stu-id="a8339-138">Example</span></span>  
 <span data-ttu-id="a8339-139">下面的示例创建具有 XML 声明、 处理指令、 注释和一个包含另一个元素的元素的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="a8339-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a8339-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8339-140">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 <xref:System.Xml.Linq.XComment>  
 <xref:System.Xml.Linq.XDocument>  
 [<span data-ttu-id="a8339-141">XML 处理指令文本</span><span class="sxs-lookup"><span data-stu-id="a8339-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)  
 [<span data-ttu-id="a8339-142">XML 注释文本</span><span class="sxs-lookup"><span data-stu-id="a8339-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [<span data-ttu-id="a8339-143">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="a8339-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="a8339-144">XML 文本</span><span class="sxs-lookup"><span data-stu-id="a8339-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="a8339-145">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="a8339-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="a8339-146">XML 中的嵌入式表达式</span><span class="sxs-lookup"><span data-stu-id="a8339-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
