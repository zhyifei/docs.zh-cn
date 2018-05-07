---
title: 表达式是一个值，因此不能作为赋值目标
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: dd5618bd0533f885a6aef8229b2d8cb1bc34c237
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>表达式是一个值，因此不能作为赋值目标
语句试图将值分配给表达式。 在运行时，可以仅向可写的变量、 属性或数组元素分配一个值。 下面的示例演示如何可能出现此错误。  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 相似的示例可能适用于属性和数组元素。  
  
 **间接访问。** 通过值类型的间接访问还会生成此错误。 请考虑下面的代码示例，它会尝试设置的值<xref:System.Drawing.Point>通过访问间接通过<xref:System.Windows.Forms.Control.Location%2A>。  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 前面的示例中的最后一个语句失败，因为它创建仅用于临时分配<xref:System.Drawing.Point>结构返回<xref:System.Windows.Forms.Control.Location%2A>属性。 结构是值类型，并运行该语句后的临时结构不会保留。 通过声明和使用的变量解决该问题<xref:System.Windows.Forms.Control.Location%2A>，从而创建更永久分配<xref:System.Drawing.Point>结构。 下面的示例演示可以替换前面的示例中的最后一个语句的代码。  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **错误 ID:** BC30068  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果该语句将值分配给一个表达式，将表达式替换单个可写的变量、 属性或数组元素。  
  
-   如果该语句进行间接访问通过值类型 （通常是一个结构），创建一个变量以保存值类型。  
  
-   分配给变量的适当结构 （或其他值类型）。  
  
-   使用变量来访问要为其分配值的属性。  
  
## <a name="see-also"></a>请参阅  
 [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)  
 [过程疑难解答](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
