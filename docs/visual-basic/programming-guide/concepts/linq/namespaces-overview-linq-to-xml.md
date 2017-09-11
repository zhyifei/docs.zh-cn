---
title: "命名空间概述 (LINQ to XML) |Microsoft 文档"
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
ms.assetid: b8eb31fa-4b26-4acf-8050-6e705687f458
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
ms.openlocfilehash: 7e9536615871b83099a11e46125ed85b44d9335d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="namespaces-overview-linq-to-xml"></a><span data-ttu-id="5cb8b-102">命名空间概述 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="5cb8b-102">Namespaces Overview (LINQ to XML)</span></span>
<span data-ttu-id="5cb8b-103">本主题介绍命名空间、<xref:System.Xml.Linq.XName>类和<xref:System.Xml.Linq.XNamespace>类。</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5cb8b-103">This topic introduces namespaces, the <xref:System.Xml.Linq.XName> class, and the <xref:System.Xml.Linq.XNamespace> class.</span></span>  
  
## <a name="xml-names"></a><span data-ttu-id="5cb8b-104">XML 名称</span><span class="sxs-lookup"><span data-stu-id="5cb8b-104">XML Names</span></span>  
 <span data-ttu-id="5cb8b-105">XML 名称常常是导致 XML 编程复杂性的原因。</span><span class="sxs-lookup"><span data-stu-id="5cb8b-105">XML names are often a source of complexity in XML programming.</span></span> <span data-ttu-id="5cb8b-106">XML 名称由 XML 命名空间（也称为 XML 命名空间 URI）和本地名称组成。</span><span class="sxs-lookup"><span data-stu-id="5cb8b-106">An XML name consists of an XML namespace (also called an XML namespace URI) and a local name.</span></span> <span data-ttu-id="5cb8b-107">XML 命名空间类似于基于 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 的程序中的命名空间。</span><span class="sxs-lookup"><span data-stu-id="5cb8b-107">An XML namespace is similar to a namespace in a [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]-based program.</span></span> <span data-ttu-id="5cb8b-108">它能够唯一限定元素和属性的名称。</span><span class="sxs-lookup"><span data-stu-id="5cb8b-108">It enables you to uniquely qualify the names of elements and attributes.</span></span> <span data-ttu-id="5cb8b-109">这有助于避免 XML 文档各个部分之间的名称冲突。</span><span class="sxs-lookup"><span data-stu-id="5cb8b-109">This helps avoid name conflicts between various parts of an XML document.</span></span> <span data-ttu-id="5cb8b-110">声明 XML 命名空间后，您可以选择只须在该命名空间中是唯一的本地名称。</span><span class="sxs-lookup"><span data-stu-id="5cb8b-110">When you have declared an XML namespace, you can select a local name that only has to be unique within that namespace.</span></span>  
  
 <span data-ttu-id="5cb8b-111">XML 名称的另一个方面是 XML*命名空间前缀*。</span><span class="sxs-lookup"><span data-stu-id="5cb8b-111">Another aspect of XML names is XML *namespace prefixes*.</span></span> <span data-ttu-id="5cb8b-112">XML 名称的复杂性大都是由 XML 前缀引起的。</span><span class="sxs-lookup"><span data-stu-id="5cb8b-112">XML prefixes cause most of the complexity of XML names.</span></span> <span data-ttu-id="5cb8b-113">这些前缀可用来创建 XML 命名空间的快捷方式，从而使 XML 文档更加简洁易懂。</span><span class="sxs-lookup"><span data-stu-id="5cb8b-113">These prefixes enable you to create a shortcut for an XML namespace, which makes the XML document more concise and understandable.</span></span> <span data-ttu-id="5cb8b-114">但是，XML 前缀仅在其上下文中才有意义，这就增加了复杂性。</span><span class="sxs-lookup"><span data-stu-id="5cb8b-114">However, XML prefixes depend on their context to have meaning, which adds complexity.</span></span> <span data-ttu-id="5cb8b-115">例如，XML 前缀 `aw` 可以与 XML 树的一部分中的一个 XML 命名空间关联，也可以与该 XML 树的另一部分中的另一个 XML 命名空间关联。</span><span class="sxs-lookup"><span data-stu-id="5cb8b-115">For example, the XML prefix `aw` could be associated with one XML namespace in one part of an XML tree, and with a different XML namespace in a different part of the XML tree.</span></span>  
  
 <span data-ttu-id="5cb8b-116">如果通过 Visual Basic 和 XML 文本使用 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]，则在命名空间中处理文档时必须使用命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="5cb8b-116">When using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] with Visual Basic and XML literals, you must use namespace prefixes when working with documents in namespaces.</span></span>  
  
 <span data-ttu-id="5cb8b-117">在[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]，表示 XML 名称的类是<xref:System.Xml.Linq.XName>。</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5cb8b-117">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], the class that represents XML names is <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="5cb8b-118">XML 名称在整个频繁出现[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]API 中，任何时候只要需要 XML 名称，您将发现<xref:System.Xml.Linq.XName>参数。</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5cb8b-118">XML names appear frequently throughout the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API, and wherever an XML name is required, you will find an <xref:System.Xml.Linq.XName> parameter.</span></span> <span data-ttu-id="5cb8b-119">但是，很少会直接使用<xref:System.Xml.Linq.XName>。</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5cb8b-119">However, you rarely work directly with an <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="5cb8b-120"><xref:System.Xml.Linq.XName>包含一个从字符串的隐式转换。</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5cb8b-120"><xref:System.Xml.Linq.XName> contains an implicit conversion from string.</span></span>  
  
 <span data-ttu-id="5cb8b-121">有关详细信息，请参阅<xref:System.Xml.Linq.XNamespace>和<xref:System.Xml.Linq.XName>。</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="5cb8b-121">For more information, see <xref:System.Xml.Linq.XNamespace> and <xref:System.Xml.Linq.XName>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cb8b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cb8b-122">See Also</span></span>  
 [<span data-ttu-id="5cb8b-123">使用 XML 命名空间 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5cb8b-123">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
