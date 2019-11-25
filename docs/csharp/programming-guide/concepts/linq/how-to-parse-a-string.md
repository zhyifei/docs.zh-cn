---
title: 如何：分析字符串 (C#)
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: 086a4baecee9ee927b08d6da53d16324ef32e8a8
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140977"
---
# <a name="how-to-parse-a-string-c"></a>如何：分析字符串 (C#)

本主题演示如何分析字符串，以在 C# 中创建 XML 树。

## <a name="example"></a>示例

下面的 C# 代码演示如何分析 XML 字符串：

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

根 `Contacts` 节点具有两个 `Contact` 节点。 若要访问已分析的 XML 中的某些特定数据，请使用 [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements) 方法，在这种情况下，将返回根 `Contacts` 节点的子元素。 以下示例将第一个 `Contact` 节点输出到控制台：

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

## <a name="see-also"></a>请参阅

- [如何查找具有特定属性的元素 (C#)](how-to-find-an-element-with-a-specific-attribute.md)
