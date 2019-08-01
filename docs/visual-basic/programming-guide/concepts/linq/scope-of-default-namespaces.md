---
title: Visual Basic 中的默认命名空间的范围
ms.date: 07/20/2015
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
ms.openlocfilehash: af868454c9d1dce7d8bf5a1902f64eff8db8780c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710357"
---
# <a name="scope-of-default-namespaces-in-visual-basic"></a>Visual Basic 中的默认命名空间的范围
XML 树中表示的默认命名空间不在查询范围内。 如果您的 XML 在默认命名空间内，仍须声明一个 <xref:System.Xml.Linq.XNamespace> 变量，并将该变量与本地名称组合在一起，生成一个限定名，在查询中使用。  
  
 查询 XML 树时遇到的一个最常见问题是，如果 XML 树具有默认命名空间，开发人员在编写查询时，有时会将 XML 视为不在命名空间内。  
  
 本主题的第一个示例集演示一种加载但是按不正确方式查询默认命名空间中的 XML 的典型方式。  
  
 第二个示例集演示必需的更正，以便可以查询命名空间中的 XML。  
  
## <a name="example"></a>示例  
 此示例演示如何在命名空间中创建 XML 和一个返回空结果集的查询。  
  
### <a name="code"></a>代码  
  
```vb  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>注释  
 此示例产生下面的结果：  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a>示例  
 本示例演示如何在命名空间中创建 XML 和一个正确编码的查询。  
  
 与上述错误编码的示例相比, 使用 Visual Basic 时的正确方法是声明和初始化一个全局默认命名空间。 这样会将所有 XML 属性放入该默认命名空间。 无需对该示例做任何其他修改，即可使它正常运行。  
  
### <a name="code"></a>代码  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>注释  
 此示例产生下面的结果：  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a>请参阅

- [命名空间概述 (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
