---
title: "XML 处理指令文本 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
dev_langs:
- VB
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
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
ms.openlocfilehash: 2ae976530ed3028677a1fef39db92265591df530
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="4f38f-102">XML 处理指令文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f38f-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="4f38f-103">一个文字表示<xref:System.Xml.Linq.XProcessingInstruction>对象。</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="4f38f-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f38f-104">语法</span><span class="sxs-lookup"><span data-stu-id="4f38f-104">Syntax</span></span>  
  
```  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="4f38f-105">部件</span><span class="sxs-lookup"><span data-stu-id="4f38f-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="4f38f-106">必需。</span><span class="sxs-lookup"><span data-stu-id="4f38f-106">Required.</span></span> <span data-ttu-id="4f38f-107">表示 XML 处理指令文本的开头。</span><span class="sxs-lookup"><span data-stu-id="4f38f-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="4f38f-108">必需。</span><span class="sxs-lookup"><span data-stu-id="4f38f-108">Required.</span></span> <span data-ttu-id="4f38f-109">将命名为指示哪个应用程序处理指令的目标。</span><span class="sxs-lookup"><span data-stu-id="4f38f-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="4f38f-110">不能以"xml"或"XML"开头。</span><span class="sxs-lookup"><span data-stu-id="4f38f-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="4f38f-111">可选。</span><span class="sxs-lookup"><span data-stu-id="4f38f-111">Optional.</span></span> <span data-ttu-id="4f38f-112">字符串，它指示的目标应用程序如何`piName`应处理 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="4f38f-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="4f38f-113">必需。</span><span class="sxs-lookup"><span data-stu-id="4f38f-113">Required.</span></span> <span data-ttu-id="4f38f-114">表示处理指令的结尾。</span><span class="sxs-lookup"><span data-stu-id="4f38f-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f38f-115">返回值</span><span class="sxs-lookup"><span data-stu-id="4f38f-115">Return Value</span></span>  
 <span data-ttu-id="4f38f-116"><xref:System.Xml.Linq.XProcessingInstruction>对象。</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="4f38f-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f38f-117">备注</span><span class="sxs-lookup"><span data-stu-id="4f38f-117">Remarks</span></span>  
 <span data-ttu-id="4f38f-118">XML 处理指令文本指示应用程序应如何处理 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="4f38f-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="4f38f-119">当应用程序加载 XML 文档时，应用程序可以检查以确定如何处理该文档的 XML 处理指令。</span><span class="sxs-lookup"><span data-stu-id="4f38f-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="4f38f-120">应用程序解释的含义`piName`和`piData`。</span><span class="sxs-lookup"><span data-stu-id="4f38f-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="4f38f-121">XML 文档文本使用类似于 XML 处理指令的语法。</span><span class="sxs-lookup"><span data-stu-id="4f38f-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="4f38f-122">有关详细信息，请参阅[XML 文档文本](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="4f38f-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f38f-123">`piName`元素不能以字符串"xml"或"XML"开头，因为 XML 1.0 规范保留这些标识符。</span><span class="sxs-lookup"><span data-stu-id="4f38f-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="4f38f-124">可以将 XML 处理指令文本分配给一个变量，或将其包含在 XML 文档文本。</span><span class="sxs-lookup"><span data-stu-id="4f38f-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f38f-125">XML 文本可以跨多行，而无需使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="4f38f-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="4f38f-126">这使您可以从 XML 文档中复制内容并将其粘贴直接到[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]程序。</span><span class="sxs-lookup"><span data-stu-id="4f38f-126">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="4f38f-127">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器将调用转换为 XML 处理指令文本<xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>构造函数。</xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="4f38f-127">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f38f-128">示例</span><span class="sxs-lookup"><span data-stu-id="4f38f-128">Example</span></span>  
 <span data-ttu-id="4f38f-129">下面的示例创建一个处理指令确定 XML 文档的样式表。</span><span class="sxs-lookup"><span data-stu-id="4f38f-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 <span data-ttu-id="4f38f-130">[!code-vb[VbXMLSamples #&28;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4f38f-130">[!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f38f-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f38f-131">See Also</span></span>  
 <span data-ttu-id="4f38f-132"><xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="4f38f-132"><xref:System.Xml.Linq.XProcessingInstruction></span></span>   
<span data-ttu-id="4f38f-133"> [XML 文档文本](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span><span class="sxs-lookup"><span data-stu-id="4f38f-133"> [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span></span>  
<span data-ttu-id="4f38f-134"> [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="4f38f-134"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="4f38f-135"> [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="4f38f-135"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span></span>
