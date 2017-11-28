---
title: "如何：针对命名空间中的 XML 编写查询 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 194e12f88f7c22c365a18bc2dd42a3dd26b5c569
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a>如何：针对命名空间中的 XML 编写查询 (C#)
若要针对命名空间中的 XML 编写查询，必须使用具有正确命名空间的 <xref:System.Xml.Linq.XName> 对象。  
  
 对于 C#，最常用的方法是使用包含 URI 的字符串初始化 <xref:System.Xml.Linq.XNamespace>，然后使用加法运算符重载来组合命名空间和本地名称。  
  
 本主题的第一个示例集演示如何在默认命名空间中创建一个 XML 树。 第二个示例集演示如何在带有前缀的命名空间中创建一个 XML 树。  
  
## <a name="example"></a>示例  
 下面的示例创建一个位于默认命名空间中的 XML 树。 然后检索元素的集合。  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 该示例产生下面的输出：  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a>示例  
 在 C# 中，无论是在使用带前缀的命名空间的 XML 树上编写查询，还是在使用默认命名空间的 XML 树上编写查询，都使用相同的方式。  
  
 下面的示例创建一个位于具有前缀的默认命名空间中的 XML 树。 然后检索元素的集合。  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
    <aw:Child>1</aw:Child>  
    <aw:Child>2</aw:Child>  
    <aw:Child>3</aw:Child>  
    <aw:AnotherChild>4</aw:AnotherChild>  
    <aw:AnotherChild>5</aw:AnotherChild>  
    <aw:AnotherChild>6</aw:AnotherChild>  
</aw:Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 该示例产生下面的输出：  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a>另请参阅  
 [使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
