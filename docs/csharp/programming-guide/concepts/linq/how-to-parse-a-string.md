---
title: 如何：分析字符串 (C#)
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: 16310e37afec950c372c7b47637986bb0eb399b8
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956611"
---
# <a name="how-to-parse-a-string-c"></a><span data-ttu-id="da200-102">如何：分析字符串 (C#)</span><span class="sxs-lookup"><span data-stu-id="da200-102">How to: Parse a String (C#)</span></span>

<span data-ttu-id="da200-103">本主题演示如何分析字符串，以在 C# 中创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="da200-103">This topic shows how to parse a string to create an XML tree in C#.</span></span>

## <a name="example"></a><span data-ttu-id="da200-104">示例</span><span class="sxs-lookup"><span data-stu-id="da200-104">Example</span></span>

<span data-ttu-id="da200-105">下面的 C# 代码演示如何分析 XML 字符串：</span><span class="sxs-lookup"><span data-stu-id="da200-105">The following C# code shows how to parse an XML string:</span></span>

```csharp
XElement contacts = XElement.Parse(
    @"<Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type=""home"">206-555-0144</Phone>
            <Phone Type=""work"">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type=""mobile"">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>");
Console.WriteLine(contacts);
```

<span data-ttu-id="da200-106">根 `Contacts` 节点具有两个 `Contact` 节点。</span><span class="sxs-lookup"><span data-stu-id="da200-106">The root `Contacts` node has two `Contact` nodes.</span></span> <span data-ttu-id="da200-107">若要访问已分析的 XML 中的某些特定数据，请使用 [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements) 方法，在这种情况下，将返回根 `Contacts` 节点的子元素。</span><span class="sxs-lookup"><span data-stu-id="da200-107">To access some specific data in your parsed XML, use the [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements) method, which in this case returns the child elements of the root `Contacts` node.</span></span> <span data-ttu-id="da200-108">以下示例将第一个 `Contact` 节点输出到控制台：</span><span class="sxs-lookup"><span data-stu-id="da200-108">The following example prints the first `Contact` node to the console:</span></span>

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

## <a name="see-also"></a><span data-ttu-id="da200-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="da200-109">See also</span></span>

- [<span data-ttu-id="da200-110">如何：查找具有特定属性的元素 (C#)</span><span class="sxs-lookup"><span data-stu-id="da200-110">How to: Find an Element with a Specific Attribute (C#)</span></span>](how-to-find-an-element-with-a-specific-attribute.md)
