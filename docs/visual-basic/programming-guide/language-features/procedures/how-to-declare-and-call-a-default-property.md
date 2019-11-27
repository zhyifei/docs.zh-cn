---
title: 如何：声明和调用默认属性
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: b01188ed8a9ff4da95a6975dcac3509625fdffb2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349685"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>如何：在 Visual Basic 中声明和调用默认属性
*默认属性*是您的代码无需指定即可访问的类或结构属性。 当调用代码命名类或结构而不是属性，并且上下文允许访问属性时，Visual Basic 解析对该类或结构的默认属性（如果存在）的访问。  
  
 一个类或结构最多只能有一个默认属性。 不过，你可以重载一个默认属性，并拥有多个版本的属性。  
  
 有关详细信息，请参阅[默认值](../../../../visual-basic/language-reference/modifiers/default.md)。  
  
### <a name="to-declare-a-default-property"></a>声明默认属性  
  
1. 以正常方式声明属性。 不要指定 `Shared` 或 `Private` 关键字。  
  
2. 在属性声明中包括 `Default` 关键字。  
  
3. 至少为属性指定一个参数。 不能定义不接受至少一个参数的默认属性。  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a>调用默认属性  
  
1. 声明包含类或结构类型的变量。  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. 在通常包含属性名称的表达式中单独使用变量名。  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. 在变量名称后面加上括号中的参数列表。 默认属性必须至少采用一个参数。  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. 若要检索默认属性值，请在表达式中使用变量名称，或在赋值语句中使用等号（`=`）。  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. 若要设置默认属性值，请在赋值语句左侧使用带有参数列表的变量名称。  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. 您始终可以将默认属性名称与变量名称一起指定，就像访问任何其他属性一样。  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a>示例  
 下面的示例声明类的默认属性。  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a>示例  
 下面的示例演示如何调用类 `class1``myProperty` 上的默认属性。 这三个赋值语句将值存储在 `myProperty`中，<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 调用读取这些值。  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 默认属性最常见的用法是不同集合类的 <xref:Microsoft.VisualBasic.Collection.Item%2A> 属性。  
  
## <a name="robust-programming"></a>可靠的编程  
 默认属性可能会减少源代码中的字符，但会使代码更难以阅读。 如果调用代码不熟悉你的类或结构，则当它对类或结构名称进行引用时，该引用是否访问类或结构本身，或者默认属性，则不能确定这一点。 这可能会导致编译器错误或细微的运行时逻辑错误。  
  
 通过始终使用[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)将编译器类型检查设置为 `On`，可以稍微降低默认属性错误的几率。  
  
 如果打算在代码中使用预定义的类或结构，则必须确定它是否具有默认属性，如果是，则必须确定其名称。  
  
 由于这些缺点，你应考虑不要定义默认属性。 为实现代码可读性，还应考虑始终显式引用所有属性，甚至是默认属性。  
  
## <a name="see-also"></a>另请参阅

- [属性过程](./property-procedures.md)
- [过程参数和自变量](./procedure-parameters-and-arguments.md)
- [Property 语句](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Default](../../../../visual-basic/language-reference/modifiers/default.md)
- [Visual Basic 中的属性和变量之间的差异](./differences-between-properties-and-variables.md)
- [如何：创建属性](./how-to-create-a-property.md)
- [如何：声明具有混合访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md)
- [如何：调用 Property 过程](./how-to-call-a-property-procedure.md)
- [如何：在属性中放置值](./how-to-put-a-value-in-a-property.md)
- [如何：从属性获取值](./how-to-get-a-value-from-a-property.md)
