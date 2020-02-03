---
title: XName 对象的预先原子化 (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
ms.openlocfilehash: c0e75afa797d2b20f32fc55e6c19d0c1593d174c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740789"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a>XName 对象的预原子化（LINQ to XML）（Visual Basic）

提高 LINQ to XML 中的性能的一种方法是预原子化 <xref:System.Xml.Linq.XName> 对象。 预原子化是指在通过使用 <xref:System.Xml.Linq.XElement> 和 <xref:System.Xml.Linq.XAttribute> 类的构造函数创建 XML 树之前，为 <xref:System.Xml.Linq.XName> 对象分配一个字符串。 然后传递初始化的 <xref:System.Xml.Linq.XName> 对象，而不是将字符串传递给构造函数（此过程将使用从字符串到 <xref:System.Xml.Linq.XName> 的隐式转换）。

当创建其中重复出现特定名称的大型 XML 树时，这样可以提高性能。 为此，请在构造 XML 树之前声明和初始化 <xref:System.Xml.Linq.XName> 对象，然后使用 <xref:System.Xml.Linq.XName> 对象，而不是指定元素和属性名称的字符串。 当创建大量具有相同名称的元素（或属性）时，此技术可以显著提高性能。

应针对您的方案测试预原子化以确定是否应使用它。

## <a name="example"></a>示例

下面的示例演示这一操作：

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

此示例生成以下输出：

```xml
<Root>
  <Data ID="1">4,100,000</Data>
  <Data ID="2">3,700,000</Data>
  <Data ID="3">1,150,000</Data>
</Root>
```

下面的示例演示针对命名空间中的 XML 文档的相同技术：

```vb
Dim aw As XNamespace = "http://www.adventure-works.com"
Dim root1 As XName = aw + "Root"
Dim data As XName = aw + "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XAttribute(XNamespace.Xmlns + "aw", aw),
                          New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

此示例生成以下输出：

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Data ID="1">4,100,000</aw:Data>
  <aw:Data ID="2">3,700,000</aw:Data>
  <aw:Data ID="3">1,150,000</aw:Data>
</aw:Root>
```

下面的示例更类似于实际中可能遇到的情况。 在此示例中，元素的内容由查询提供：

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"
  
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root2 As New XElement(root1, From i In Enumerable.Range(1, 100000)
                                 Select New XElement(data, New XAttribute(ID, i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```  

上一示例的执行性能优于下面的示例（其中未对名称进行预原子化）：

```vb
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root As New XElement("Root", From i In Enumerable.Range(1, 100000)
                                 Select New XElement("Data", New XAttribute("ID", i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```

## <a name="see-also"></a>另请参阅

- [性能（LINQ to XML）（Visual Basic）](performance-linq-to-xml.md)
- [原子化的 XName 和 XNamespace 对象（LINQ to XML）（Visual Basic）](atomized-xname-and-xnamespace-objects-linq-to-xml.md)
