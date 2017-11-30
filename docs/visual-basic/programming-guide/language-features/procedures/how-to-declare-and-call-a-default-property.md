---
title: "如何：在 Visual Basic 中声明和调用默认属性"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8baa03e37325a6ad7065ec1a60052b3ea6a46c6f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>如何：在 Visual Basic 中声明和调用默认属性
A*默认属性*是一个类或结构的属性，你的代码可以访问而无需指定它。 当调用的代码代表一个类或结构，但不是属性的名称，上下文允许访问某一属性，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]解析对该类或结构的默认属性的访问权限，如果存在。  
  
 类或结构最多可以有一个默认属性。 但是，可以重载默认属性，也具有多个它的版本。  
  
 有关详细信息，请参阅[默认](../../../../visual-basic/language-reference/modifiers/default.md)。  
  
### <a name="to-declare-a-default-property"></a>若要声明默认属性  
  
1.  以常规方式声明属性。 未指定`Shared`或`Private`关键字。  
  
2.  包括`Default`属性声明中的关键字。  
  
3.  指定的属性的至少一个参数。 不能定义不采用至少一个参数的默认属性。  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a>若要调用默认属性  
  
1.  声明包含的类或结构类型的变量。  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  使用的表达式中单独的变量名称通常要包括的属性名称。  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  变量名后面加上括号中的参数列表。 默认属性必须采用至少一个自变量。  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  若要检索的默认属性值，使用的变量的名称，用在表达式中前面或后面相等的自变量列表 (`=`) 在赋值语句登录。  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  若要设置的默认属性值，请将变量的名称，使用自变量列表，在赋值语句的左侧。  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  将像访问任何其他属性一样，始终可以指定默认属性名以及变量名。  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a>示例  
 下面的示例在类上声明了默认属性。  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a>示例  
 下面的示例演示如何调用默认属性`myProperty`类`class1`。 三个赋值语句将值存储在`myProperty`，和<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>调用读取这些值。  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 默认属性的最常见用途是<xref:Microsoft.VisualBasic.Collection.Item%2A>在各个集合类的属性。  
  
## <a name="robust-programming"></a>可靠编程  
 默认属性可能会导致小减少源代码的字符，但它们会导致代码更难阅读。 如果在发出对类或结构名称的引用时，调用代码不熟悉类或结构，它无法确定该引用访问的类或结构本身或默认属性。 这可能导致编译器错误或细微的运行时逻辑错误。  
  
 你可以始终使用某种程度上减少默认属性的几率[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)设置编译器类型检查到`On`。  
  
 如果你计划可以使用预定义的类或结构中你的代码，必须确定它是否具有默认属性，以及如果是这样，其名称是什么。  
  
 由于这些缺点，应考虑未定义默认属性。 为了代码的可读性，你应还考虑始终显式引用所有属性，包括默认属性。  
  
## <a name="see-also"></a>另请参阅  
 [属性过程](./property-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [Property 语句](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [默认](../../../../visual-basic/language-reference/modifiers/default.md)  
 [在 Visual Basic 中属性和变量之间的差异](./differences-between-properties-and-variables.md)  
 [如何：创建属性](./how-to-create-a-property.md)  
 [如何：声明具有混合访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [如何：调用 Property 过程](./how-to-call-a-property-procedure.md)  
 [如何：在属性中放置值](./how-to-put-a-value-in-a-property.md)  
 [如何：从属性获取值](./how-to-get-a-value-from-a-property.md)
