---
title: 如何：查找父元素的属性 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 2e6c124d2653fb4426b3abb693f0b58daa5413c2
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593614"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="b2958-102">如何：查找父元素的属性 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b2958-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="b2958-103">本主题演示如何定位到父元素并查找其属性。</span><span class="sxs-lookup"><span data-stu-id="b2958-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="b2958-104">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="b2958-104">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="b2958-105">示例</span><span class="sxs-lookup"><span data-stu-id="b2958-105">Example</span></span>

<span data-ttu-id="b2958-106">此示例首先查找 `Author` 元素。</span><span class="sxs-lookup"><span data-stu-id="b2958-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="b2958-107">然后，查找父元素的 `id` 属性。</span><span class="sxs-lookup"><span data-stu-id="b2958-107">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="b2958-108">此示例使用下面的 XML 文档：[示例 XML 文件：图书 (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="b2958-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

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

<span data-ttu-id="b2958-109">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="b2958-109">This example produces the following output:</span></span>

```
Results are identical
id="bk101"
```
