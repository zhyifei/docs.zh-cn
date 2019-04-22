---
title: XML CDATA 文本 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: ee269ca5cf9635fec35165d1ea65d6a6483cadef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828586"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="3f09a-102">XML CDATA 文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f09a-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="3f09a-103">一个文本表示<xref:System.Xml.Linq.XCData>对象。</span><span class="sxs-lookup"><span data-stu-id="3f09a-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f09a-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f09a-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="3f09a-105">部件</span><span class="sxs-lookup"><span data-stu-id="3f09a-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="3f09a-106">必需。</span><span class="sxs-lookup"><span data-stu-id="3f09a-106">Required.</span></span> <span data-ttu-id="3f09a-107">表示 XML CDATA 节的开头。</span><span class="sxs-lookup"><span data-stu-id="3f09a-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="3f09a-108">必需。</span><span class="sxs-lookup"><span data-stu-id="3f09a-108">Required.</span></span> <span data-ttu-id="3f09a-109">若要在 XML CDATA 节中显示的文本内容。</span><span class="sxs-lookup"><span data-stu-id="3f09a-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="3f09a-110">必需。</span><span class="sxs-lookup"><span data-stu-id="3f09a-110">Required.</span></span> <span data-ttu-id="3f09a-111">表示部分的结尾。</span><span class="sxs-lookup"><span data-stu-id="3f09a-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f09a-112">返回值</span><span class="sxs-lookup"><span data-stu-id="3f09a-112">Return Value</span></span>  
 <span data-ttu-id="3f09a-113">一个 <xref:System.Xml.Linq.XCData> 对象。</span><span class="sxs-lookup"><span data-stu-id="3f09a-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f09a-114">备注</span><span class="sxs-lookup"><span data-stu-id="3f09a-114">Remarks</span></span>  
 <span data-ttu-id="3f09a-115">XML CDATA 节包含应包含，但未能分析，它包含的 xml 的原始文本。</span><span class="sxs-lookup"><span data-stu-id="3f09a-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="3f09a-116">XML CDATA 节可以包含任何文本。</span><span class="sxs-lookup"><span data-stu-id="3f09a-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="3f09a-117">这包括保留的 XML 字符。</span><span class="sxs-lookup"><span data-stu-id="3f09a-117">This includes reserved XML characters.</span></span> <span data-ttu-id="3f09a-118">XML CDATA 节结尾序列"]] >"。</span><span class="sxs-lookup"><span data-stu-id="3f09a-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="3f09a-119">这意味着以下几点：</span><span class="sxs-lookup"><span data-stu-id="3f09a-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="3f09a-120">因为嵌入的分隔符是有效的 XML CDATA 内容，不能使用嵌入式的表达式中的 XML CDATA 文本。</span><span class="sxs-lookup"><span data-stu-id="3f09a-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="3f09a-121">XML CDATA 节无法嵌套，因为`content`不能包含值"]] >"。</span><span class="sxs-lookup"><span data-stu-id="3f09a-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="3f09a-122">可以将 XML CDATA 文本分配给一个变量，或将其包含在 XML 元素文本。</span><span class="sxs-lookup"><span data-stu-id="3f09a-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f09a-123">XML 文本可以跨多个行，但不使用行继续符。</span><span class="sxs-lookup"><span data-stu-id="3f09a-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="3f09a-124">这使您可以从 XML 文档中复制内容并将其粘贴到 Visual Basic 程序直接。</span><span class="sxs-lookup"><span data-stu-id="3f09a-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="3f09a-125">Visual Basic 编译器将 XML CDATA 文本转换为调用<xref:System.Xml.Linq.XCData.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="3f09a-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f09a-126">示例</span><span class="sxs-lookup"><span data-stu-id="3f09a-126">Example</span></span>  
 <span data-ttu-id="3f09a-127">下面的示例创建一个包含文本的 CDATA 节"可以包含文字\<XML > 标记"。</span><span class="sxs-lookup"><span data-stu-id="3f09a-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="3f09a-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f09a-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="3f09a-129">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="3f09a-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="3f09a-130">XML 文本</span><span class="sxs-lookup"><span data-stu-id="3f09a-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="3f09a-131">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="3f09a-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
