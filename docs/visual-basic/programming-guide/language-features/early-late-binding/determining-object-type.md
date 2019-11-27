---
title: 确定对象类型
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: a77cc0603a0b61f58a4aa703c4b1e6ef4c26729c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345189"
---
# <a name="determining-object-type-visual-basic"></a>确定对象类型 (Visual Basic)
泛型对象变量（即，声明为 `Object`的变量）可以包含任何类中的对象。 使用 `Object`类型的变量时，可能需要根据对象的类执行不同的操作;例如，某些对象可能不支持特定的属性或方法。 Visual Basic 提供了两种方法来确定存储在对象变量中的对象类型： `TypeName` 函数和 `TypeOf...Is` 运算符。  
  
## <a name="typename-and-typeofis"></a>TypeName 和 TypeOf 。未  
 如果需要存储或显示对象的类名，`TypeName` 函数将返回一个字符串，是最佳选择，如以下代码片段所示：  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 `TypeOf...Is` 运算符是测试对象类型的最佳选择，因为它比使用 `TypeName`的等效字符串比较要快得多。 以下代码片段在 `If...Then...Else` 语句中使用 `TypeOf...Is`：  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 此处有一则注意事项。 如果对象是特定类型或派生自特定类型，则 `TypeOf...Is` 运算符返回 `True`。 几乎对 Visual Basic 所做的一切都涉及对象，这些对象包括通常不会视为对象的某些元素，如字符串和整数。 这些对象派生自，并从 <xref:System.Object>继承方法。 当传递 `Integer` 并使用 `Object`进行计算时，`TypeOf...Is` 运算符返回 `True`。 下面的示例报告参数 `InParam` `Object` 和 `Integer`：  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 下面的示例使用 `TypeOf...Is` 和 `TypeName` 来确定在 `Ctrl` 参数中传递给它的对象的类型。 `TestObject` 过程调用具有三种不同类型控件的 `ShowType`。  
  
#### <a name="to-run-the-example"></a>运行示例  
  
1. 创建新的 Windows 应用程序项目，并向窗体添加 <xref:System.Windows.Forms.Button> 控件、<xref:System.Windows.Forms.CheckBox> 控件和 <xref:System.Windows.Forms.RadioButton> 控件。  
  
2. 在窗体上的按钮中，调用 `TestObject` 过程。  
  
3. 将以下代码添加到你的窗体：  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [使用字符串名调用属性或方法](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [If...Then...Else 语句](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [String 数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Integer 数据类型](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
