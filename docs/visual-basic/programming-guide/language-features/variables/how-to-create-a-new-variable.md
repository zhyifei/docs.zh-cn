---
title: "如何：创建新变量 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6806dcbe9e00cbae77181b79d74ddb9a1e1493f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>如何：创建新变量 (Visual Basic)
创建的变量[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)。  
  
### <a name="to-create-a-new-variable"></a>创建新变量  
  
1.  声明中的变量`Dim`语句。  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  包括变量的特征的规范，例如[私有](../../../../visual-basic/language-reference/modifiers/private.md)，[静态](../../../../visual-basic/language-reference/modifiers/static.md)，[阴影](../../../../visual-basic/language-reference/modifiers/shadows.md)，或[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)。 有关详细信息，请参阅[声明元素的特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)。  
  
    ```  
    Public Static newCustomer  
    ```  
  
     不需要`Dim`关键字如果在声明中使用其他关键字。  
  
3.  变量的名称，必须遵循规范后接[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]规则和约定。 有关详细信息，请参阅[声明元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  名后面加上[作为](../../../../visual-basic/language-reference/statements/as-clause.md)子句以指定变量的数据类型。  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     如果不指定数据类型，它将使用默认值： `Object`。  
  
5.  请按照`As`子句以等号 (`=`) 和等号后使用变量的初始值。  
  
     [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]将指定的值分配给变量，每次运行时`Dim`语句。 如果不指定初始值，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]它首先进入包含的代码时赋给变量的数据类型的默认初始值`Dim`语句。  
  
     如果变量为引用类型，你可以通过包括创建其类的实例[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)中的关键字`As`子句。 如果不使用`New`，该变量的初始值是[执行任何操作](../../../../visual-basic/language-reference/nothing.md)。  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [变量](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [已声明的元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [已声明元素的特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [语句](../../../../visual-basic/language-reference/statements/index.md)  
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
