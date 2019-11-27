---
title: 如何：从文件、字符串或流加载 XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 7a2a0513a066ae8ea8a70f7a5ae340ab29de7d25
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330963"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="bcca8-102">如何：从文件、字符串或流加载 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcca8-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>

<span data-ttu-id="bcca8-103">通过使用几种方法，可以创建[XML 文本](../../../../visual-basic/language-reference/xml-literals/index.md)，并使用外部源（例如文件、字符串或流）中的内容填充这些文本。</span><span class="sxs-lookup"><span data-stu-id="bcca8-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="bcca8-104">下面的示例演示了这些方法。</span><span class="sxs-lookup"><span data-stu-id="bcca8-104">These methods are shown in the following examples.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a><span data-ttu-id="bcca8-105">从文件加载 XML</span><span class="sxs-lookup"><span data-stu-id="bcca8-105">To load XML from a file</span></span>

<span data-ttu-id="bcca8-106">若要从文件中填充 XML 文本（如 <xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XDocument> 对象），请使用 `Load` 方法。</span><span class="sxs-lookup"><span data-stu-id="bcca8-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="bcca8-107">此方法可采用文件路径、文本流或 XML 流作为输入。</span><span class="sxs-lookup"><span data-stu-id="bcca8-107">This method can take a file path, text stream, or XML stream as input.</span></span>

<span data-ttu-id="bcca8-108">下面的代码示例演示如何使用 <xref:System.Xml.Linq.XDocument.Load%28System.String%29> 方法，通过文本文件使用 XML 填充 <xref:System.Xml.Linq.XDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="bcca8-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a><span data-ttu-id="bcca8-109">从字符串加载 XML</span><span class="sxs-lookup"><span data-stu-id="bcca8-109">To load XML from a string</span></span>

<span data-ttu-id="bcca8-110">若要从字符串填充 XML 文本（如 <xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XDocument> 对象），可以使用 `Parse` 方法。</span><span class="sxs-lookup"><span data-stu-id="bcca8-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>

<span data-ttu-id="bcca8-111">下面的代码示例演示如何使用 <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> 方法，使用字符串中的 XML 填充 <xref:System.Xml.Linq.XDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="bcca8-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="bcca8-112">从流加载 XML</span><span class="sxs-lookup"><span data-stu-id="bcca8-112">To load XML from a stream</span></span>

<span data-ttu-id="bcca8-113">若要从流中填充 XML 文本（如 <xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XDocument> 对象），可以使用 `Load` 方法或 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="bcca8-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="bcca8-114">下面的代码示例演示如何使用 <xref:System.Xml.Linq.XNode.ReadFrom%2A> 方法，通过 xml 流中的 XML 填充 <xref:System.Xml.Linq.XDocument> 的对象。</span><span class="sxs-lookup"><span data-stu-id="bcca8-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a><span data-ttu-id="bcca8-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcca8-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bcca8-116">XML 文本</span><span class="sxs-lookup"><span data-stu-id="bcca8-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="bcca8-117">XML</span><span class="sxs-lookup"><span data-stu-id="bcca8-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="bcca8-118">在 Visual Basic 中操控 XML</span><span class="sxs-lookup"><span data-stu-id="bcca8-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
