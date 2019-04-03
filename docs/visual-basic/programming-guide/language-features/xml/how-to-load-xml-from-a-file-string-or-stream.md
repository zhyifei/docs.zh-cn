---
title: 如何：从文件、 字符串或 Stream (Visual Basic) 加载 XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 2b9da2062068ef25c5df97ef19b1502999ea78ed
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832133"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="62f6b-102">如何：从文件、 字符串或 Stream (Visual Basic) 加载 XML</span><span class="sxs-lookup"><span data-stu-id="62f6b-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>
<span data-ttu-id="62f6b-103">您可以创建[XML 文本](../../../../visual-basic/language-reference/xml-literals/index.md)和通过使用几种方法使用从外部源如文件、 字符串或流的内容填充它们。</span><span class="sxs-lookup"><span data-stu-id="62f6b-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="62f6b-104">以下示例中显示了这些方法。</span><span class="sxs-lookup"><span data-stu-id="62f6b-104">These methods are shown in the following examples.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a><span data-ttu-id="62f6b-105">若要从文件加载 XML</span><span class="sxs-lookup"><span data-stu-id="62f6b-105">To load XML from a file</span></span>  
  
-   <span data-ttu-id="62f6b-106">填充 XML 文本，如<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>对象从一个文件，使用`Load`方法。</span><span class="sxs-lookup"><span data-stu-id="62f6b-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="62f6b-107">此方法可以将文件路径、 文本流或 XML 流作为输入。</span><span class="sxs-lookup"><span data-stu-id="62f6b-107">This method can take a file path, text stream, or XML stream as input.</span></span>  
  
     <span data-ttu-id="62f6b-108">下面的代码示例演示如何使用<xref:System.Xml.Linq.XDocument.Load%28System.String%29>方法来填充<xref:System.Xml.Linq.XDocument>使用 XML 文本文件中的对象。</span><span class="sxs-lookup"><span data-stu-id="62f6b-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>  
  
     [!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]  
  
### <a name="to-load-xml-from-a-string"></a><span data-ttu-id="62f6b-109">若要从字符串加载 XML</span><span class="sxs-lookup"><span data-stu-id="62f6b-109">To load XML from a string</span></span>  
  
-   <span data-ttu-id="62f6b-110">填充 XML 文本，如<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>对象从一个字符串，可以使用`Parse`方法。</span><span class="sxs-lookup"><span data-stu-id="62f6b-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>  
  
     <span data-ttu-id="62f6b-111">下面的代码示例演示如何使用<xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType>方法来填充<xref:System.Xml.Linq.XDocument>使用 XML 字符串中的对象。</span><span class="sxs-lookup"><span data-stu-id="62f6b-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>  
  
     [!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]  
  
### <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="62f6b-112">若要从流加载 XML</span><span class="sxs-lookup"><span data-stu-id="62f6b-112">To load XML from a stream</span></span>  
  
-   <span data-ttu-id="62f6b-113">填充 XML 文本，如<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>对象从流中，可以使用`Load`方法或<xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="62f6b-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="62f6b-114">下面的代码示例演示如何使用<xref:System.Xml.Linq.XNode.ReadFrom%2A>方法来填充<xref:System.Xml.Linq.XDocument>对象与 XML 从 XML 流。</span><span class="sxs-lookup"><span data-stu-id="62f6b-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>  
  
 [!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="62f6b-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="62f6b-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="62f6b-116">XML 文本</span><span class="sxs-lookup"><span data-stu-id="62f6b-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="62f6b-117">XML</span><span class="sxs-lookup"><span data-stu-id="62f6b-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="62f6b-118">在 Visual Basic 中操控 XML</span><span class="sxs-lookup"><span data-stu-id="62f6b-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
