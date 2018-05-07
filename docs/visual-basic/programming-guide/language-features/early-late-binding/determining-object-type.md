---
title: 确定对象类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: a9852998abeae67b2a0e9dc3ffc85318ce5045da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="determining-object-type-visual-basic"></a>确定对象类型 (Visual Basic)
一般的对象变量 (即，变量声明为`Object`) 可以包含来自任何类的对象。 使用类型的变量时`Object`，可能需要采取不同的基于对象的类; 例如，某些对象可能不支持特定属性或方法。 Visual Basic 提供以下两种方法确定哪种类型的对象存储在一个对象变量：`TypeName`函数和`TypeOf...Is`运算符。  
  
## <a name="typename-and-typeofis"></a>E，TypeOf...是  
 `TypeName`函数返回一个字符串，并是最佳选择，当你需要存储或显示类对象的名称，如下面的代码段中所示：  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 `TypeOf...Is`运算符是用于测试的对象类型的最佳选择，因为它是比等效的字符串比较使用快得多`TypeName`。 下面的代码片段使用`TypeOf...Is`内`If...Then...Else`语句：  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 需要注意的一点是因为此处。 `TypeOf...Is`运算符返回`True`如果一个对象的特定类型，或从特定类型派生。 几乎所有操作都使用 Visual Basic 涉及对象，其中包括一些通常不被视为对象，如字符串和整数的元素。 这些对象派生自和继承方法从<xref:System.Object>。 当传递`Integer`和计算与`Object`、`TypeOf...Is`运算符返回`True`。 下面的示例报告参数`InParam`既是`Object`和`Integer`:  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 下面的示例使用这两个`TypeOf...Is`和`TypeName`来确定对象中传递给它的类型`Ctrl`自变量。 `TestObject`过程调用`ShowType`与三种不同的控件。  
  
#### <a name="to-run-the-example"></a>运行示例  
  
1.  创建新的 Windows 应用程序项目并添加<xref:System.Windows.Forms.Button>控件，<xref:System.Windows.Forms.CheckBox>控件，和一个<xref:System.Windows.Forms.RadioButton>到窗体控件。  
  
2.  从你的窗体上的按钮，调用`TestObject`过程。  
  
3.  向窗体中添加以下代码：  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>  
 [使用字符串名调用属性或方法](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)  
 [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [If...Then...Else 语句](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [String 数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [Integer 数据类型](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
