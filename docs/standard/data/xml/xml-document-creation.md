---
title: "创建 XML 文档"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a0806e34cfbf7c8e0b5ba995ca4876b8d10405e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-creation"></a><span data-ttu-id="053dc-102">创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="053dc-102">XML Document Creation</span></span>
<span data-ttu-id="053dc-103">有两种创建 XML 文档的方法。</span><span class="sxs-lookup"><span data-stu-id="053dc-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="053dc-104">一种方法是创建**XmlDocument**不带任何参数。</span><span class="sxs-lookup"><span data-stu-id="053dc-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="053dc-105">另一种方法是创建**XmlDocument**并将其作为参数传递 XmlNameTable。</span><span class="sxs-lookup"><span data-stu-id="053dc-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="053dc-106">下面的示例演示如何创建新的空**XmlDocument**不使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="053dc-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="053dc-107">创建文档后，你可以加载数据从字符串、 流、 URL、 文本读取器，或**XmlReader**派生类使用**加载**方法。</span><span class="sxs-lookup"><span data-stu-id="053dc-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="053dc-108">还有另一种负载方法， **LoadXML**方法，从字符串读取 XML。</span><span class="sxs-lookup"><span data-stu-id="053dc-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="053dc-109">有关详细信息的各种**负载**方法，请参阅[XML 文档读入 DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)。</span><span class="sxs-lookup"><span data-stu-id="053dc-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="053dc-110">没有名为的类**XmlNameTable**。</span><span class="sxs-lookup"><span data-stu-id="053dc-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="053dc-111">此类是原子化字符串对象的表。</span><span class="sxs-lookup"><span data-stu-id="053dc-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="053dc-112">该表使 XML 分析器可以高效地对 XML 文档中所有重复的元素和属性的名称使用相同的字符串对象。</span><span class="sxs-lookup"><span data-stu-id="053dc-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="053dc-113">**XmlNameTable**如上所示创建并加载文档时，具有属性和元素名称加载文档时将自动创建。</span><span class="sxs-lookup"><span data-stu-id="053dc-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="053dc-114">如果你已有的文档包含名称表，并且这些名称可用于另一个文档，则可以创建新的文档使用**负载**采用的方法**XmlNameTable**作为参数。</span><span class="sxs-lookup"><span data-stu-id="053dc-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="053dc-115">当使用此方法创建文档时，它会使用现有**XmlNameTable**包含所有属性和元素已从其他文档加载到它。</span><span class="sxs-lookup"><span data-stu-id="053dc-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="053dc-116">它可用于有效地比较元素和属性的名称。</span><span class="sxs-lookup"><span data-stu-id="053dc-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="053dc-117">有关详细信息**XmlNameTable**，请参阅[使用 XmlNameTable 比较对象](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)。</span><span class="sxs-lookup"><span data-stu-id="053dc-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="053dc-118">有关参考，请参阅<xref:System.Xml.XmlNameTable>。</span><span class="sxs-lookup"><span data-stu-id="053dc-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053dc-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="053dc-119">See Also</span></span>  
 [<span data-ttu-id="053dc-120">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="053dc-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
