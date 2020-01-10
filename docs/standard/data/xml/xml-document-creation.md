---
title: 创建 XML 文档
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
ms.openlocfilehash: a12555a02b45a964ff7efcbe00e0d2cb8637474a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709980"
---
# <a name="xml-document-creation"></a><span data-ttu-id="9d9e5-102">创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="9d9e5-102">XML Document Creation</span></span>
<span data-ttu-id="9d9e5-103">有两种创建 XML 文档的方法。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="9d9e5-104">一种方法是，创建不含参数的 XmlDocument。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="9d9e5-105">另一种方法是，创建 XmlDocument，并向它传递 XmlNameTable 参数。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="9d9e5-106">下面的示例展示了如何不使用任何参数新建空 XmlDocument。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="9d9e5-107">创建文档后，可以使用 Load 方法在文档中加载字符串、流、URL、文本读取器或 XmlReader 派生类中的数据。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="9d9e5-108">还有另一种加载方法 LoadXML 方法，可用于从字符串中读取 XML。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="9d9e5-109">若要详细了解各种 Load 方法，请参阅[将 XML 文档读取到 DOM 中](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="9d9e5-110">有一个类名为 XmlNameTable。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="9d9e5-111">此类是原子化字符串对象的表。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="9d9e5-112">该表使 XML 分析器可以高效地对 XML 文档中所有重复的元素和属性的名称使用相同的字符串对象。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="9d9e5-113">XmlNameTable 在文档创建（如上所示）时自动创建，并在文档加载时加载属性名和元素名称。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="9d9e5-114">如果已有包含名称表的文档，且这些名称在另一个文档中很有用，可以使用需要使用 XmlNameTable 参数的 Load 方法新建文档。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="9d9e5-115">使用此方法创建文档时，它使用现有 XmlNameTable，其中包含已从其他文档加载到其中的所有属性和元素。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="9d9e5-116">它可用于有效地比较元素和属性的名称。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="9d9e5-117">若要详细了解 XmlNameTable，请参阅[使用 XmlNameTable 比较对象](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="9d9e5-118">有关参考，请参阅 <xref:System.Xml.XmlNameTable>。</span><span class="sxs-lookup"><span data-stu-id="9d9e5-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d9e5-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d9e5-119">See also</span></span>

- [<span data-ttu-id="9d9e5-120">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="9d9e5-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
