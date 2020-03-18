---
title: 如何查找父级的属性 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: bfe7554a5c767adde5e7170c8e1ea0537155f6df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141174"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="4dadc-102">如何查找父级的属性 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="4dadc-102">How to find an attribute of the parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="4dadc-103">本主题演示如何定位到父元素并查找其属性。</span><span class="sxs-lookup"><span data-stu-id="4dadc-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="4dadc-104">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="4dadc-104">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="4dadc-105">示例</span><span class="sxs-lookup"><span data-stu-id="4dadc-105">Example</span></span>

<span data-ttu-id="4dadc-106">此示例首先查找 `Author` 元素。</span><span class="sxs-lookup"><span data-stu-id="4dadc-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="4dadc-107">然后，查找父元素的 `id` 属性。</span><span class="sxs-lookup"><span data-stu-id="4dadc-107">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="4dadc-108">本示例使用以下 XML 文档：[示例 XML 文件：图书 (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="4dadc-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

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

<span data-ttu-id="4dadc-109">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="4dadc-109">This example produces the following output:</span></span>

```output
Results are identical
id="bk101"
```
