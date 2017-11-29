---
title: "Property 过程 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cbdf49d5c3eb5ef71b25a060d62f55f19098f445
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="property-procedures-visual-basic"></a>Property 过程 (Visual Basic)
属性过程是一系列[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]操作模块、 类或结构上的自定义属性的语句。 属性过程也称为是*属性访问器*。  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]提供有关以下属性过程：  
  
-   A`Get`过程返回属性的值。 就是当访问表达式中的属性。  
  
-   A`Set`过程将属性设置为某个值，包括一个对象引用。 就是将值分配给属性。  
  
 你通常定义属性过程中使用的对`Get`和`Set`语句，但如果属性是只读的可以定义单独任一过程 ([Get 语句](../../../../visual-basic/language-reference/statements/get-statement.md)) 或只写 ([设置语句](../../../../visual-basic/language-reference/statements/set-statement.md))。  
  
 可以省略`Get`和`Set`过程时使用一个自动实现的属性。 有关详细信息，请参阅[自动实现的属性](./auto-implemented-properties.md)。  
  
 你可以在类、 结构和模块定义属性。 属性是`Public`默认情况下，这意味着可以从任意位置进行调用的应用程序可以访问该属性的容器中。  
  
 有关属性和变量的比较，请参阅[属性之间的差异和 Visual Basic 中的变量](./differences-between-properties-and-variables.md)。  
  
## <a name="declaration-syntax"></a>声明语法  
 属性本身被定义内包含的代码块[属性语句](../../../../visual-basic/language-reference/statements/property-statement.md)和`End Property`语句。 在此块中，每个属性过程将显示为包含在声明语句的内部块 (`Get`或`Set`) 和匹配`End`声明。  
  
 声明属性和其过程的语法如下所示：  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 `Modifiers`可以指定访问级别和与重载，重写、 共享和隐藏，相关的信息以及属性是否为只读或只写。 `AccessLevel`上`Get`或`Set`过程可以是任何级别，比属性本身为指定的访问级别限制性更强。 有关详细信息，请参阅[属性语句](../../../../visual-basic/language-reference/statements/property-statement.md)。  
  
### <a name="data-type"></a>数据类型  
 在中定义属性的数据类型和主体的访问级别`Property`语句，不在属性过程。 属性可以具有只有一个数据类型。 例如，不能定义属性来存储`Decimal`值而检索`Double`值。  
  
### <a name="access-level"></a>访问级别  
 但是，你可以定义一个属性的主体的访问级别，并进一步限制中其一个属性过程的访问级别。 例如，你可以定义`Public`属性，然后定义`Private Set`过程。 `Get`过程保持`Public`。 可以更改属性的过程之一的访问级别，你可以只是使其比主体的访问级别限制性更强。 有关详细信息，请参阅[如何： 声明具有混合访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md)。  
  
## <a name="parameter-declaration"></a>参数声明  
 声明每个参数使用的相同方式为[Sub 过程](./sub-procedures.md)，只不过的传递机制必须`ByVal`。  
  
 在参数列表中每个参数的语法如下所示：  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 如果参数是可选的你还必须提供默认值作为其声明的一部分。 用于指定默认值的语法如下所示：  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>属性值  
 在`Get`过程，返回值提供给调用表达式作为值的属性。  
  
 在`Set`过程中，新的属性值传递的参数给`Set`语句。 如果你将参数显式声明，必须将其声明与为属性相同的数据类型。 如果你未声明的参数，编译器将使用隐式参数`Value`来表示要分配给属性的新值。  
  
## <a name="calling-syntax"></a>调用语法  
 通过使对该属性引用的隐式调用属性过程。 你使用的属性名称为相同的方式将使用的变量的名称，只不过你必须为不是可选的所有自变量提供值，必须将自变量列表括在括号中。 如果未不提供任何参数，你可以选择省略括号。  
  
 隐式调用的语法`Set`过程是，如下所示：  
  
 `propertyname[(argumentlist)] = expression`  
  
 隐式调用的语法`Get`过程是，如下所示：  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>声明和调用图  
 以下属性将存储为两个构成的名称、 名字和姓氏的完整名称。 当调用的代码读取`fullName`、`Get`过程合并两个构成的名称，并返回的完整名称。 当调用的代码将分配新的完整名称，`Set`过程尝试将其分解为两个构成的名称。 如果找不到空间，它可以将其存储所有项作为第一个名称。  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 下面的示例演示对属性过程的典型调用`fullName`。  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [过程](./index.md)  
 [Function 过程](./function-procedures.md)  
 [运算符过程](./operator-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [在 Visual Basic 中属性和变量之间的差异](./differences-between-properties-and-variables.md)  
 [如何：创建属性](./how-to-create-a-property.md)  
 [如何：调用 Property 过程](./how-to-call-a-property-procedure.md)  
 [如何： 声明和 Visual Basic 中调用默认属性](./how-to-declare-and-call-a-default-property.md)  
 [如何：在属性中放置值](./how-to-put-a-value-in-a-property.md)  
 [如何：从属性获取值](./how-to-get-a-value-from-a-property.md)
