---
title: 如何：查询使用反射 (LINQ) (Visual Basic 中) 的程序集的元数据
ms.date: 07/20/2015
ms.assetid: 53caa336-ab83-4181-b0f6-5c87c5f9e4ee
ms.openlocfilehash: cea1469e6f0acc9c958be9247d7d3d750d881afe
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586346"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-visual-basic"></a>如何：查询使用反射 (LINQ) (Visual Basic 中) 的程序集的元数据
下面的示例演示了如何将 LINQ 与反射配合使用以检索有关与指定搜索条件匹配的方法的特定元数据。 在这种情况下，该查询将在返回数组等可枚举类型的程序集中查找所有方法的名称。  
  
## <a name="example"></a>示例  
  
```vb  
Imports System.Reflection  
Imports System.IO  
Imports System.Linq  
Module Module1  
  
    Sub Main()  
        Dim asmbly As Assembly =   
            Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089")  
  
        Dim pubTypesQuery = From type In asmbly.GetTypes()   
                            Where type.IsPublic   
                            From method In type.GetMethods()   
                            Where method.ReturnType.IsArray = True   
                            Let name = method.ToString()   
                            Let typeName = type.ToString()   
                            Group name By typeName Into methodNames = Group  
  
        Console.WriteLine("Getting ready to iterate")  
        For Each item In pubTypesQuery  
            Console.WriteLine(item.methodNames)  
  
            For Each type In item.methodNames  
                Console.WriteLine(" " & type)  
            Next  
        Next  
        Console.ReadKey()  
    End Sub  
  
End Module  
```  
  
 该示例使用 <xref:System.Reflection.Assembly.GetTypes%2A> 方法返回指定程序集中的类型的数组。 [Where 子句](../../../../visual-basic/language-reference/queries/where-clause.md)应用筛选器，以便返回仅公共类型。 对于每个公共类型，子查询使用从 <xref:System.Type.GetMethods%2A> 调用返回的 <xref:System.Reflection.MethodInfo> 数组生成。 筛选这些结果，以仅返回其返回类型为数组或实现 <xref:System.Collections.Generic.IEnumerable%601> 的其他类型的方法。 最后，通过使用类型名称作为键来对这些结果进行分组。  
  
## <a name="compiling-the-code"></a>编译代码  
创建一个 VB.NET 控制台应用程序项目，与`Imports`System.Linq 命名空间的语句。
  
## <a name="see-also"></a>请参阅

- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
