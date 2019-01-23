---
title: XML 处理指令文本 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: cb9ad1d687203dff497e4cd451933a8bbbdf4bf6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491228"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="60954-102">XML 处理指令文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60954-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="60954-103">一个文本表示<xref:System.Xml.Linq.XProcessingInstruction>对象。</span><span class="sxs-lookup"><span data-stu-id="60954-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60954-104">语法</span><span class="sxs-lookup"><span data-stu-id="60954-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="60954-105">部件</span><span class="sxs-lookup"><span data-stu-id="60954-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="60954-106">必需。</span><span class="sxs-lookup"><span data-stu-id="60954-106">Required.</span></span> <span data-ttu-id="60954-107">表示 XML 处理指令文本的开头。</span><span class="sxs-lookup"><span data-stu-id="60954-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="60954-108">必需。</span><span class="sxs-lookup"><span data-stu-id="60954-108">Required.</span></span> <span data-ttu-id="60954-109">命名，该值指示哪个应用程序的处理指令目标。</span><span class="sxs-lookup"><span data-stu-id="60954-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="60954-110">不能以"xml"或"XML"开头。</span><span class="sxs-lookup"><span data-stu-id="60954-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="60954-111">可选。</span><span class="sxs-lookup"><span data-stu-id="60954-111">Optional.</span></span> <span data-ttu-id="60954-112">指示应用程序的目标字符串`piName`应处理 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="60954-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="60954-113">必需。</span><span class="sxs-lookup"><span data-stu-id="60954-113">Required.</span></span> <span data-ttu-id="60954-114">表示处理指令的结尾。</span><span class="sxs-lookup"><span data-stu-id="60954-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60954-115">返回值</span><span class="sxs-lookup"><span data-stu-id="60954-115">Return Value</span></span>  
 <span data-ttu-id="60954-116">一个 <xref:System.Xml.Linq.XProcessingInstruction> 对象。</span><span class="sxs-lookup"><span data-stu-id="60954-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60954-117">备注</span><span class="sxs-lookup"><span data-stu-id="60954-117">Remarks</span></span>  
 <span data-ttu-id="60954-118">XML 处理指令文本指示应用程序应如何处理 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="60954-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="60954-119">在应用程序加载 XML 文档时，应用程序可以检查 XML 处理指令，以确定如何处理文档。</span><span class="sxs-lookup"><span data-stu-id="60954-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="60954-120">应用程序要解释的含义`piName`和`piData`。</span><span class="sxs-lookup"><span data-stu-id="60954-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="60954-121">XML 文档文本使用类似于 XML 处理指令的语法。</span><span class="sxs-lookup"><span data-stu-id="60954-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="60954-122">有关详细信息，请参阅[XML 文档文本](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="60954-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60954-123">`piName`元素不能以开头的字符串"xml"或"XML"，因为 XML 1.0 规范保留了这些标识符。</span><span class="sxs-lookup"><span data-stu-id="60954-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="60954-124">可以将 XML 处理指令文本分配给一个变量，或将其包含在 XML 文档文本。</span><span class="sxs-lookup"><span data-stu-id="60954-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60954-125">XML 文本可以跨多个行，而无需行继续符。</span><span class="sxs-lookup"><span data-stu-id="60954-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="60954-126">这使您可以从 XML 文档中复制内容并将其粘贴到 Visual Basic 程序直接。</span><span class="sxs-lookup"><span data-stu-id="60954-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="60954-127">Visual Basic 编译器将 XML 处理指令文本转换为调用<xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="60954-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60954-128">示例</span><span class="sxs-lookup"><span data-stu-id="60954-128">Example</span></span>  
 <span data-ttu-id="60954-129">以下示例创建标识 XML 文档的样式表的处理指令。</span><span class="sxs-lookup"><span data-stu-id="60954-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="60954-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="60954-130">See also</span></span>
- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="60954-131">XML 文档文本</span><span class="sxs-lookup"><span data-stu-id="60954-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="60954-132">XML 文本</span><span class="sxs-lookup"><span data-stu-id="60954-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="60954-133">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="60954-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
