---
title: 如何：使用 Descendants 方法查找单个子代
ms.date: 07/20/2015
ms.assetid: 0c03468c-efc8-4140-98f3-fb67acd9e8e1
ms.openlocfilehash: 1c1192c85a7244a9a03a2cd55144abcfb02dcbf1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353001"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-visual-basic"></a>How to: Find a Single Descendant Using the Descendants Method (Visual Basic)
可以使用 <xref:System.Xml.Linq.XContainer.Descendants%2A> 轴方法快速编写代码来查找名称唯一的单个元素。 如果想要查找具有特定名称的特定后代，则此技术特别有用。 虽然可以编写代码以导航到需要的元素，但使用 <xref:System.Xml.Linq.XContainer.Descendants%2A> 轴编写代码通常更快更容易。  
  
## <a name="example"></a>示例  
 本示例使用 <xref:System.Linq.Enumerable.First%2A> 标准查询运算符。  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1>GC1 Value</GrandChild1>  
        </Child1>  
        <Child2>  
            <GrandChild2>GC2 Value</GrandChild2>  
        </Child2>  
        <Child3>  
            <GrandChild3>GC3 Value</GrandChild3>  
        </Child3>  
        <Child4>  
            <GrandChild4>GC4 Value</GrandChild4>  
        </Child4>  
    </Root>  
Dim grandChild3 As String = _  
    (From el In root...<GrandChild3> _  
    Select el).First()  
Console.WriteLine(grandChild3)  
```  
  
 此代码生成以下输出：  
  
```console  
GC3 Value  
```  
  
## <a name="example"></a>示例  
 下面的示例演示如何对命名空间中的 XML 进行同样的查询。 For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child1>  
                    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
                </aw:Child1>  
                <aw:Child2>  
                    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
                </aw:Child2>  
                <aw:Child3>  
                    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
                </aw:Child3>  
                <aw:Child4>  
                    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
                </aw:Child4>  
            </aw:Root>  
        Dim grandChild3 As String = _  
            (From el In root...<aw:GrandChild3> _  
            Select el).First()  
        Console.WriteLine(grandChild3)  
    End Sub  
End Module  
```  
  
 此代码生成以下输出：  
  
```console  
GC3 Value  
```  
  
## <a name="see-also"></a>请参阅

- [Basic Queries (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
