---
title: 结构和其他编程元素
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 73d3f999e95c484dff3f5409f2cdb9032b64fe38
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266854"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a>结构和其他编程元素 (Visual Basic)
您可以将结构与数组、对象和过程结合使用，也可以彼此结合使用。 交互使用与这些元素单独使用的语法相同。  
  
> [!NOTE]
> 不能初始化结构声明中的任何结构元素。 只能将值分配给已声明为结构类型的变量的元素。  
  
## <a name="structures-and-arrays"></a>结构和数组  
 结构可以包含数组作为其一个或多个元素。 下面的示例对此进行了演示。  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure
```  
  
 访问结构中数组的值的方式与访问对象的属性的方式相同。 下面的示例对此进行了演示。  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 您还可以声明结构数组。 下面的示例对此进行了演示。  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 您可以遵循相同的规则来访问此数据体系结构的组件。 下面的示例对此进行了演示。  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a>结构和对象  
 结构可以包含对象作为其一个或多个元素。 下面的示例对此进行了演示。  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 应在此类声明中使用特定对象类，而不是`Object`。  
  
## <a name="structures-and-procedures"></a>结构和程序  
 可以将结构作为过程参数传递。 下面的示例对此进行了演示。  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 前面的示例*通过 引用*传递结构，这允许过程修改其元素，以便更改在调用代码中生效。 如果要保护结构免受此类修改，则按值传递它。  
  
 您还可以从`Function`过程返回结构。 下面的示例对此进行了演示。  
  
```vb  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## <a name="structures-within-structures"></a>结构内部的结构  
 结构可以包含其他结构。 下面的示例对此进行了演示。  
  
```vb  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 您还可以使用此技术封装在不同模块中定义的结构中一个模块中定义的结构。  
  
 结构可以包含任意深度的其他结构。  
  
## <a name="see-also"></a>另请参阅

- [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [如何：声明结构](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [结构变量](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [结构和类](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)
