---
title: "如何：在 Visual Basic 中声明对象变量并为它分配对象"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f4a682c7ae32ace0b1f859d52963342546a83f29
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>如何：在 Visual Basic 中声明对象变量并为它分配对象
声明的变量[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)通过指定`As Object`中[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)。 通过将对象放在等号后的对象分配给此类变量 (`=`) 在赋值语句或初始化子句中。  
  
## <a name="example"></a>示例  
 下面的示例声明`Object`变量，并将分配到它的当前实例。  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 你可以通过将变量初始化为其声明的一部分组合的声明和分配。 下面的示例是等效于前面的示例。  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 <xref:System> 命名空间的引用。  
  
-   类、 结构或在其中放入的模块`Dim`语句。  
  
-   在其中放入赋值语句过程。  
  
## <a name="see-also"></a>另请参阅  
 [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [对象变量声明](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
