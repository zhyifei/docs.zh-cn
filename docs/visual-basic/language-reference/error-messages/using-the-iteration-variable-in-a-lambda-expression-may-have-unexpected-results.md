---
title: "在 lambda 表达式中使用迭代变量可能会产生意外的结果"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords: BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb707cd4e09a149d21b70bb0f998a40c7ed58b49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>在 lambda 表达式中使用迭代变量可能会产生意外的结果
Lambda 表达式中使用迭代变量可能会产生意外的结果。 相反，创建一个在循环内的局部变量，并将其分配的迭代变量的值。  
  
 在循环内声明的 lambda 表达式中使用循环迭代变量时，会出现此警告。 例如，下面的示例会导致出现警告。  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 下面的示例演示了可能出现的意外的结果。  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 `For`循环创建的 lambda 表达式的一个数组，其中每个返回的循环迭代变量的值`i`。 当 lambda 表达式的计算`For Each`循环中，你可能会看到 0、 1、 2、 3 和 4 显示的连续值`i`中`For`循环。 相反，您看到的最终值`i`显示五次：  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC42324  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   将迭代变量的值分配到局部变量，并在 lambda 表达式中使用本地变量。  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            Dim j = i  
            array1(i) = Function() j  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a>另请参阅  
 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
