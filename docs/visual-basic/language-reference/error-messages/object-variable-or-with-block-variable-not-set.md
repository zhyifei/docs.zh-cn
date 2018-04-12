---
title: 未设置对象变量或 With 块变量
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e1f587e194acf744b6ec9b8f1bede3acef7b753
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="object-variable-or-with-block-variable-not-set"></a>未设置对象变量或 With 块变量
正在引用无效的对象变量。   出现此错误的原因可能有多种：  
  
-   如果不指定类型声明了变量。 如果不指定类型声明的变量，则默认为类型`Object`。  
  
     例如，与声明的变量`Dim x`类型的作用很`Object;`与声明的变量`Dim x As String`类型的作用很`String`。  
  
    > [!TIP]
    >  `Option Strict`语句不允许隐式类型化导致`Object`类型。 如果省略该类型时，将发生编译时错误。 请参阅[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。  
  
-   你尝试引用已设置为一个对象`Nothing`  
  
     .  
  
-   你尝试访问未正确声明一个数组变量的元素。  
  
     例如，数组声明为`products() As String`将触发该错误，如果你尝试引用数组的元素`products(3) = "Widget"`。 数组不包含任何元素，并被视为一个对象。  
  
-   你正尝试访问代码中`With...End With`阻止在初始化块之前。   A`With...End With`块必须通过执行初始化`With`语句入口点。  
  
> [!NOTE]
>  在早期版本的 Visual Basic 或 VBA 此错误也已通过将一个值分配给一个变量，而无需使用触发`Set`关键字 (`x = "name"`而不是`Set x = "name"`)。 `Set`关键字不再是在 Visual Basic.Net 中有效。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  设置`Option Strict`到`On`通过将下面的代码添加到文件的开头：  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  如果你不想要启用`Option Strict`，搜索你指定没有类型的任何变量的代码 (`Dim x`而不是`Dim x As String`) 并将预期的类型添加到声明。  
  
3.  请确保你已设置为对象变量不引用`Nothing`。  搜索关键字代码`Nothing`，并修改你的代码，以便该对象未设置为`Nothing`直到你在引用它。  
  
4.  请确保任何数组变量就会标注之前访问它们。 你可以将分配一个维度首次创建数组时 (`Dim x(5) As String`而不是`Dim x() As String`)，或使用`ReDim`关键字之前首次访问设置数组的维数。  
  
5.  请确保你`With`块初始化通过执行`With`语句入口点。  
  
## <a name="see-also"></a>另请参阅  
 [对象变量声明](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [With...End With 语句](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
