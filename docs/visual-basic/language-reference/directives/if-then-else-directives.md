---
title: '#如果......#Else 指令'
ms.date: 04/11/2018
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69ce56d770de5f004f204b1764fd51d948ba92c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ifthenelse-directives"></a>#If...Then...#Else 指令
有条件地编译选定的 Visual Basic 代码块。  
  
## <a name="syntax"></a>语法  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a>部件  
 `expression`  
 所需的`#If`和`#ElseIf`语句，可选在其他位置。 任何表达式，以独占方式包含一个或多个条件编译器常量、 文本和运算符，计算结果为`True`或`False`。  
  
 `statements`  
 所需的`#If`语句块，可选在其他位置。 Visual Basic 程序线条或如果关联的表达式的计算结果为编译的编译器指令`True`。  
  
 `#End If`  
 终止`#If`语句块。  
  
## <a name="remarks"></a>备注  
 行为、 表面上`#If...Then...#Else`指令显示相同的为`If...Then...Else`语句。 但是，`#If...Then...#Else`指令评估什么编译的编译器，而`If...Then...Else`语句在运行时计算条件。  
  
 条件编译通常用于编译不同平台的同一个程序。 它还用来防止调试可执行文件中显示的代码。 在条件编译期间被排除的代码完全省略从最终的可执行文件，因此它具有大小或性能没有影响。  
  
 而不考虑任何评估的结果，将计算所有表达式使用`Option Compare Binary`。 `Option Compare`语句不会影响中的表达式`#If`和`#ElseIf`语句。  
  
> [!NOTE]
>  任何单行形式的`#If`， `#Else`， `#ElseIf`，和`#End If`指令存在。 没有其他代码可出现在任何指令所在的行。 

条件编译块内的语句必须是完整的逻辑语句。 例如，你不能有条件地编译只有函数的属性，但你可以有条件地声明及其属性以及函数：

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a>示例
 此示例使用`#If...Then...#Else`构造来确定是否编译某些语句。  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a>请参阅  
[#Const 指令](../../../visual-basic/language-reference/directives/const-directive.md)  
[If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
[条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
<xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>   


