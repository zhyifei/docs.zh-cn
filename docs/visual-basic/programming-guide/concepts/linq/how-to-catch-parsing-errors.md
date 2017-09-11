---
title: "如何︰ 捕捉分析错误 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
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
ms.openlocfilehash: 6065bb7656151392e4a5b7ad1078706284ba5616
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-catch-parsing-errors-visual-basic"></a><span data-ttu-id="b01ac-102">如何︰ 捕捉分析错误 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b01ac-102">How to: Catch Parsing Errors (Visual Basic)</span></span>
<span data-ttu-id="b01ac-103">本主题演示如何检测格式不正确或无效的 XML。</span><span class="sxs-lookup"><span data-stu-id="b01ac-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b01ac-104">使用<xref:System.Xml.XmlReader>。</xref:System.Xml.XmlReader>实现</span><span class="sxs-lookup"><span data-stu-id="b01ac-104"> is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="b01ac-105">如果不正确或无效的 XML 传递给[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]，基础<xref:System.Xml.XmlReader>类将引发异常。</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="b01ac-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="b01ac-106">分析 XML，如的各种方法<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>，不会捕捉异常; 然后可以通过您的应用程序捕捉异常。</xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b01ac-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
 <span data-ttu-id="b01ac-107">请注意，如果使用 XML 文本，则无法获取分析错误。</span><span class="sxs-lookup"><span data-stu-id="b01ac-107">Note that you cannot get parse errors if you use XML literals.</span></span> <span data-ttu-id="b01ac-108">Visual Basic 编译器将捕捉格式不正确或无效的 XML 错误。</span><span class="sxs-lookup"><span data-stu-id="b01ac-108">The Visual Basic compiler will catch errors of badly formed or invalid XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b01ac-109">示例</span><span class="sxs-lookup"><span data-stu-id="b01ac-109">Example</span></span>  
 <span data-ttu-id="b01ac-110">下面的代码尝试分析无效的 XML：</span><span class="sxs-lookup"><span data-stu-id="b01ac-110">The following code tries to parse invalid XML:</span></span>  
  
```vb  
Try  
    Dim contacts As XElement = XElement.Parse("<Contacts>" & vbCrLf & _  
        "    <Contact>" & vbCrLf & _  
        "        <Name>Jim Wilson</Name>" & vbCrLf & _  
        "    </Contact>" & vbCrLf & _  
        "</Contcts>")  
  
    Console.WriteLine(contacts)  
Catch e As System.Xml.XmlException  
    Console.WriteLine(e.Message)  
End Try  
```  
  
 <span data-ttu-id="b01ac-111">运行此代码时，会引发以下异常：</span><span class="sxs-lookup"><span data-stu-id="b01ac-111">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="b01ac-112">您可以预计的异常的相关信息<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>， <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>， <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>，和<xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>方法引发，请参阅<xref:System.Xml.XmlReader>文档。</xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b01ac-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b01ac-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b01ac-113">See Also</span></span>  
 [<span data-ttu-id="b01ac-114">分析 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b01ac-114">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
