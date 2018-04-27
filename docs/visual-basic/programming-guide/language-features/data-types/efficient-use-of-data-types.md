---
title: 有效使用数据类型 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4cac585cdc3072d595d2446e1937678f9ab03335
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="efficient-use-of-data-types-visual-basic"></a>有效使用数据类型 (Visual Basic)
未声明的变量和数据类型未声明的变量分配`Object`数据类型。 这使得可以轻松快速，编写程序，但它可能会导致它们执行速度更慢。  
  
## <a name="strong-typing"></a>强类型  
 指定的所有变量的数据类型被称为*强类型化*。 使用强类型有多种优点：  
  
-   它使你的变量的 IntelliSense 支持。 这样，你可以查看其属性和其他成员，作为你的代码中的类型。  
  
-   它可利用的编译器类型检查。 这将捕获在运行时由于如溢出错误而导致失败的语句。 它还不支持这些选项的对象上捕获对方法的调用。  
  
-   这会导致你的代码的执行速度更快。  
  
## <a name="most-efficient-data-types"></a>最有效的数据类型  
 从不包含小数的变量，整数数据类型是比非整型类型效率更高。 在 Visual Basic 中，`Integer`和`UInteger`是最有效的数值类型。  
  
 对于分数，`Double`是最有效的数据类型，因为在当前平台上的处理器执行以双精度浮点运算。 但是，与操作`Double`速度与整数类型，例如`Integer`。  
  
## <a name="specifying-data-type"></a>指定数据类型  
 使用[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)来声明特定类型的变量。 同时可以通过指定其访问级别[公共](../../../../visual-basic/language-reference/modifiers/public.md)，[受保护](../../../../visual-basic/language-reference/modifiers/protected.md)，[友元](../../../../visual-basic/language-reference/modifiers/friend.md)，或[私有](../../../../visual-basic/language-reference/modifiers/private.md)关键字，如下所示下面的示例。  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a>字符转换  
 `AscW`和`ChrW`在 Unicode 函数操作。 你应使用它们优先`Asc`和`Chr`，执行和跳出执行 Unicode，必须将其转换。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [数值数据类型](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [使用 IntelliSense](/visualstudio/ide/using-intellisense)
