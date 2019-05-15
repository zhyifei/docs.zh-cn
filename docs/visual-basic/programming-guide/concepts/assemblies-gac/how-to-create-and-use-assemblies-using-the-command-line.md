---
title: 如何：创建和使用程序集使用命令行 (Visual Basic)
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: a30d4b3ea203a8b4d3ba621fc7b0310477ddf10d
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592681"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>如何：创建和使用程序集使用命令行 (Visual Basic)
程序集或动态链接库 (DLL) 会在运行时链接到程序。 为了演示如何生成和使用 DLL，请考虑以下方案：  
  
- `MathLibrary.DLL`：包含要在运行时调用的方法的库文件。 在此示例中，DLL 包含两个方法，即 `Add` 和 `Multiply`。  
  
- `Add`：包含方法 `Add` 的源文件。 它返回其参数的总和。 包含方法 `Add` 的类 `AddClass` 是命名空间 `UtilityMethods` 的成员。  
  
- `Mult`：包含方法 `Multiply` 的源代码。 它返回其参数的乘积。 包含方法 `Multiply` 的类 `MultiplyClass` 也是命名空间 `UtilityMethods` 的成员。  
  
- `TestCode`：包含 `Main` 方法的文件。 它使用 DLL 文件中的方法计算运行时参数的总和与乘积。  
  
## <a name="example"></a>示例  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 此文件包含使用 DLL 方法 `Add` 和 `Multiply` 的算法。 它首先分析从命令行输入的参数 `num1` 和 `num2`。 然后通过对 `AddClass` 类使用 `Add` 方法来计算总和，并通过对 `MultiplyClass` 类使用 `Multiply` 方法来计算乘积。  
  
 请注意，`Imports`文件的开头的语句，可使用非限定的类名来引用 DLL 方法在编译时，按如下所示：  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 否则，你必须使用完全限定的名称，如下所示：  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a>执行  
 若要运行程序，请输入 EXE 文件的名称，后跟两个数字，如下所示：  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a>请参阅

- [编程概念](../../../../visual-basic/programming-guide/concepts/index.md)
- [.NET 中的程序集](../../../../standard/assembly/index.md)
- [创建用于容纳 DLL 函数的类](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
