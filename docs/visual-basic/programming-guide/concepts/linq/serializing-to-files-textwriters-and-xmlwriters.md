---
title: "序列化为文件、 Textwriter 和 XmlWriters3 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f8f8672004b0704b00ff60e5b58256f664bcbd82
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="e3cde-102">序列化为文件、TextWriter 和 XmlWriter</span><span class="sxs-lookup"><span data-stu-id="e3cde-102">Serializing to Files, TextWriters, and XmlWriters</span></span>
<span data-ttu-id="e3cde-103">您可以序列化 XML 树<xref:System.IO.File>、 <xref:System.IO.TextWriter>，或<xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="e3cde-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="e3cde-104">您可以序列化的任何 XML 组件，包括<xref:System.Xml.Linq.XDocument>和<xref:System.Xml.Linq.XElement>，为通过使用字符串`ToString`方法。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="e3cde-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>  
  
 <span data-ttu-id="e3cde-105">如果您想要禁止格式化序列化为一个字符串时，可以使用<xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>方法。</xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e3cde-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="e3cde-106">序列化为文件时的默认行为是格式化 （缩进） 生成的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="e3cde-106">Thedefault behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="e3cde-107">缩进时，不会保留 XML 树中无意义的空白。</span><span class="sxs-lookup"><span data-stu-id="e3cde-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="e3cde-108">若要使用格式序列化时，使用不采用以下方法的重载之一<xref:System.Xml.Linq.SaveOptions>作为参数︰</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="e3cde-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <span data-ttu-id="e3cde-109"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e3cde-109"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="e3cde-110"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e3cde-110"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="e3cde-111">如果要选择不缩进，并保留无意义的空白 XML 树中，使用采用下列任一方法的重载之一<xref:System.Xml.Linq.SaveOptions>作为参数︰</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="e3cde-111">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <span data-ttu-id="e3cde-112"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e3cde-112"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="e3cde-113"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e3cde-113"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="e3cde-114">有关示例，请参见相应的参考主题。</span><span class="sxs-lookup"><span data-stu-id="e3cde-114">For examples, see the appropriate reference topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3cde-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3cde-115">See Also</span></span>  
 [<span data-ttu-id="e3cde-116">序列化 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3cde-116">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
