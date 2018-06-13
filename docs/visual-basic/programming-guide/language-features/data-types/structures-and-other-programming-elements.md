---
title: 结构和其他编程元素 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 7b375c5a45998fc0bd06f7c075f23a30dd377295
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652020"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a>结构和其他编程元素 (Visual Basic)
你可以结合使用数组、 对象和过程，以及与每个其他使用结构。 交互使用相同的语法，如单独使用这些元素。  
  
> [!NOTE]
>  无法初始化任何结构声明中的结构元素。 您可以分配到已被声明为结构类型的变量的元素的值。  
  
## <a name="structures-and-arrays"></a>结构和数组  
 结构可以包含数组作为一个或多个它的元素。 下面的示例阐释了这一点。  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 你可以访问数组结构中的值相同的方式访问对象的属性。 下面的示例阐释了这一点。  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 你也可以声明结构的数组。 下面的示例阐释了这一点。  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 按照相同的规则来访问此数据体系结构的组件。 下面的示例阐释了这一点。  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a>结构和对象  
 结构只能包含一个作为一个或多个它的元素的对象。 下面的示例阐释了这一点。  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 应在此类声明中，使用特定的对象类而不是`Object`。  
  
## <a name="structures-and-procedures"></a>结构和过程  
 可以将结构作为过程自变量传递。 下面的示例阐释了这一点。  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 前面的示例将此结构传递*通过引用*，这样，过程来修改其元素，以便在调用代码中所做的更改生效。 如果你想要保护避免这种修改的结构，则按值传递它。  
  
 你还可以返回的结构从`Function`过程。 下面的示例阐释了这一点。  
  
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
  
## <a name="structures-within-structures"></a>结构中的结构  
 结构可以包含其他结构。 下面的示例阐释了这一点。  
  
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
  
 此方法还可用于封装在另一个模块中定义结构中的一个模块中定义的结构。  
  
 结构可以包含其他结构到任意深度。  
  
## <a name="see-also"></a>请参阅  
 [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [如何：声明结构](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [结构变量](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 [结构和类](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)
