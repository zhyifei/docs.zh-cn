---
title: 如何：查找父元素的属性 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: f30c810483d8253132b9fe3e0959d04a8b4d26a0
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690060"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="50ba5-102">如何：查找父元素的属性 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="50ba5-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="50ba5-103">本主题演示如何定位到父元素并查找其属性。</span><span class="sxs-lookup"><span data-stu-id="50ba5-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="50ba5-104">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="50ba5-104">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="50ba5-105">示例</span><span class="sxs-lookup"><span data-stu-id="50ba5-105">Example</span></span>

<span data-ttu-id="50ba5-106">此示例首先查找 `Author` 元素。</span><span class="sxs-lookup"><span data-stu-id="50ba5-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="50ba5-107">然后，查找父元素的 `id` 属性。</span><span class="sxs-lookup"><span data-stu-id="50ba5-107">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="50ba5-108">此示例使用下面的 XML 文档：[示例 XML 文件：图书 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="50ba5-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>

```csharp
XDocument books = XDocument.Load("Books.xml");

XElement author =
    books
    .Root
    .Element("Book")
    .Element("Author");

// LINQ to XML query
XAttribute att1 =
    author
    .Parent
    .Attribute("id");

// XPath expression
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();

if (att1 == att2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(att1);
```

<span data-ttu-id="50ba5-109">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="50ba5-109">This example produces the following output:</span></span>

```
Results are identical
id="bk101"
```
