---
title: XML CDATA 文本
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 72e899e7bd30f2edf0e88207bb3b75bdf36fa11c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349434"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="80a91-102">XML CDATA 文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80a91-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="80a91-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span><span class="sxs-lookup"><span data-stu-id="80a91-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80a91-104">语法</span><span class="sxs-lookup"><span data-stu-id="80a91-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="80a91-105">部件</span><span class="sxs-lookup"><span data-stu-id="80a91-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="80a91-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="80a91-106">Required.</span></span> <span data-ttu-id="80a91-107">Denotes the start of the XML CDATA section.</span><span class="sxs-lookup"><span data-stu-id="80a91-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="80a91-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="80a91-108">Required.</span></span> <span data-ttu-id="80a91-109">Text content to appear in the XML CDATA section.</span><span class="sxs-lookup"><span data-stu-id="80a91-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="80a91-110">必须的。</span><span class="sxs-lookup"><span data-stu-id="80a91-110">Required.</span></span> <span data-ttu-id="80a91-111">Denotes the end of the section.</span><span class="sxs-lookup"><span data-stu-id="80a91-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80a91-112">返回值</span><span class="sxs-lookup"><span data-stu-id="80a91-112">Return Value</span></span>  
 <span data-ttu-id="80a91-113">一个 <xref:System.Xml.Linq.XCData> 对象。</span><span class="sxs-lookup"><span data-stu-id="80a91-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80a91-114">备注</span><span class="sxs-lookup"><span data-stu-id="80a91-114">Remarks</span></span>  
 <span data-ttu-id="80a91-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span><span class="sxs-lookup"><span data-stu-id="80a91-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="80a91-116">A XML CDATA section can contain any text.</span><span class="sxs-lookup"><span data-stu-id="80a91-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="80a91-117">This includes reserved XML characters.</span><span class="sxs-lookup"><span data-stu-id="80a91-117">This includes reserved XML characters.</span></span> <span data-ttu-id="80a91-118">The XML CDATA section ends with the sequence "]]>".</span><span class="sxs-lookup"><span data-stu-id="80a91-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="80a91-119">This implies the following points:</span><span class="sxs-lookup"><span data-stu-id="80a91-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="80a91-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span><span class="sxs-lookup"><span data-stu-id="80a91-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="80a91-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span><span class="sxs-lookup"><span data-stu-id="80a91-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="80a91-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span><span class="sxs-lookup"><span data-stu-id="80a91-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80a91-123">An XML literal can span multiple lines but does not use line continuation characters.</span><span class="sxs-lookup"><span data-stu-id="80a91-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="80a91-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span><span class="sxs-lookup"><span data-stu-id="80a91-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="80a91-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="80a91-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80a91-126">示例</span><span class="sxs-lookup"><span data-stu-id="80a91-126">Example</span></span>  
 <span data-ttu-id="80a91-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span><span class="sxs-lookup"><span data-stu-id="80a91-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="80a91-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="80a91-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="80a91-129">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="80a91-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="80a91-130">XML 文本</span><span class="sxs-lookup"><span data-stu-id="80a91-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="80a91-131">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="80a91-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
