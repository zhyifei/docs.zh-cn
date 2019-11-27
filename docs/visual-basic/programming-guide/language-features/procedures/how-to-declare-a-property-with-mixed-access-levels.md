---
title: 如何：声明具有混合访问级别的属性
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
ms.openlocfilehash: d74e23f33fbf7d9d29ab84b9b1bd4fc08863ac48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349694"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>如何：声明具有混合访问级别的属性 (Visual Basic)
如果希望属性上的 `Get` 和 `Set` 过程具有不同的访问级别，则可以在 `Property` 语句中使用更高的权限级别，在 `Get` 或 `Set` 语句中使用更严格的级别。 如果希望代码的某些部分能够获取属性的值，并且代码的某些其他部分可以更改值，则可以对属性使用混合访问级别。  
  
 有关访问级别的详细信息，请参阅[Visual Basic 中的访问级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>声明具有混合访问级别的属性  
  
1. 以正常方式声明属性，并在 `Property` 语句中指定限制性较低的访问级别（如 `Public`）。  
  
2. 声明 `Get` 或指定限制性更强的访问级别的 `Set` 过程（如 `Friend`）。  
  
3. 不要指定其他属性过程的访问级别。 它假定在 `Property` 语句中声明了访问级别。 你可以仅对其中一个属性过程进行访问限制。  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     在前面的示例中，`Get` 过程与属性本身具有相同的 `Protected` 访问权限，而 `Set` 过程具有 `Private` 访问权限。 派生自 `employee` 的类可以读取 `salary` 值，但只有 `employee` 类才能进行设置。  
  
## <a name="see-also"></a>另请参阅

- [过程](./index.md)
- [属性过程](./property-procedures.md)
- [过程参数和自变量](./procedure-parameters-and-arguments.md)
- [Property 语句](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Visual Basic 中的属性和变量之间的差异](./differences-between-properties-and-variables.md)
- [如何：创建属性](./how-to-create-a-property.md)
- [如何：调用 Property 过程](./how-to-call-a-property-procedure.md)
- [如何：在 Visual Basic 中声明和调用默认属性](./how-to-declare-and-call-a-default-property.md)
- [如何：在属性中放置值](./how-to-put-a-value-in-a-property.md)
- [如何：从属性获取值](./how-to-get-a-value-from-a-property.md)
