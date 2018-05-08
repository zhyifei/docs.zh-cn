---
title: 如何：声明具有混合访问级别的属性 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: 8d25086fe6f8b5f5300006466ef49782cb065edf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>如何：声明具有混合访问级别的属性 (Visual Basic)
如果你想`Get`和`Set`要具有不同的访问级别的属性的过程，你可以使用中的更多的权限级别`Property`语句和中限制性更强的级别`Get`或`Set`语句。 当你想要能够获取属性的值的代码的某些部分和某些其他部分的代码将无法更改的值时，可以在属性上使用混合的访问级别。  
  
 有关访问级别的详细信息，请参阅[访问 Visual Basic 中的级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>若要声明具有混合的访问级别的属性  
  
1.  将该属性声明以常规方式，并指定限制性较弱的访问级别 (如`Public`) 中`Property`语句。  
  
2.  声明是`Get`或`Set`指定限制性更强的访问级别的过程 (如`Friend`)。  
  
3.  不要在另一个属性过程指定访问级别。 它假定中声明的访问级别`Property`语句。 你可以限制仅其中一个属性过程上的访问。  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     在前面的示例中，`Get`过程具有相同`Protected`访问属性本身，而`Set`过程有`Private`访问。 从派生的类`employee`可以读取`salary`值，但只有`employee`类可将其设置。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [属性过程](./property-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [Property 语句](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [在 Visual Basic 中属性和变量之间的差异](./differences-between-properties-and-variables.md)  
 [如何：创建属性](./how-to-create-a-property.md)  
 [如何：调用 Property 过程](./how-to-call-a-property-procedure.md)  
 [如何： 声明和 Visual Basic 中调用默认属性](./how-to-declare-and-call-a-default-property.md)  
 [如何：在属性中放置值](./how-to-put-a-value-in-a-property.md)  
 [如何：从属性获取值](./how-to-get-a-value-from-a-property.md)
