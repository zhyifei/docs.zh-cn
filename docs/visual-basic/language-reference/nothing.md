---
title: Nothing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: 12c88db49dc7723fc269195e7d174bfa822c64d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963751"
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
表示任意数据类型的默认值。 对于引用类型, 默认值为`null`引用。 对于值类型, 默认值取决于值类型是否可以为 null。  
  
> [!NOTE]
> 对于不可为 null 的值类型`Nothing` , Visual Basic 中的`null`不同C#于中的。 在 Visual Basic 中, 如果将不可以为 null 的值类型的变量设置`Nothing`为, 则该变量将设置为其声明的类型的默认值。 在C#中, 如果将不可以为 null 的值类型的变量分配`null`给, 则会发生编译时错误。  
  
## <a name="remarks"></a>备注  
 `Nothing`表示数据类型的默认值。 默认值取决于变量是值类型还是引用类型。  
  
 *值类型*的变量直接包含其值。 值类型包括所有数值数据类型、 `Boolean`、 `Char`、 `Date`、所有结构和所有枚举。 *引用类型*的变量存储对内存中对象的实例的引用。 引用类型包括类、数组、委托和字符串。 有关更多信息，请参见 [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。  
  
 如果变量是值类型, 则的行为`Nothing`取决于变量是否为可为 null 的数据类型。 若要表示可以为 null 的值类型`?` , 请向类型名称添加修饰符。 分配`Nothing`给可以为 null 的变量会将`null`值设置为。 有关详细信息和示例, 请参阅[可以为 null 的值类型](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)。  
  
 如果变量是不可为 null 的值类型, 则分配`Nothing`给它会将它设置为其声明类型的默认值。 如果该类型包含变量成员, 则它们都设置为其默认值。 下面的示例对标量类型进行了说明。  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 如果变量为引用类型, 则为变量赋值`Nothing`会将其设置`null`为变量类型的引用。 设置为`null`引用的变量不与任何对象关联。 下面的示例演示这一操作。  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 当检查引用 (或可以为 null 的值类型) 变量`null`是否为时, `= Nothing`请`<> Nothing`不要使用或。 始终使用`Is Nothing`或`IsNot Nothing`。  
  
 对于 Visual Basic 中的字符串, 空字符串等于`Nothing`。 因此, `"" = Nothing`为 true。  
  
 下面的示例演示使用`Is`和`IsNot`运算符的比较。  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 如果在不使用`As`子句的情况下声明变量并将其设置为`Nothing`, 则该`Object`变量的类型为。 这是`Dim something = Nothing`一个示例。 当处于打开状态且处于关闭状态时`Option Strict` , `Option Infer`会发生编译时错误。  
  
 将分配`Nothing`给对象变量时, 它将不再引用任何对象实例。 如果变量以前引用了某个实例, 则将其设置为`Nothing`不会终止实例本身。 实例终止, 仅在垃圾回收器 (GC) 检测到没有剩余活动引用时, 才会释放与之关联的内存和系统资源。  
  
 `Nothing`<xref:System.DBNull>与对象不同, 后者表示未初始化的变量或不存在的数据库列。  
  
## <a name="see-also"></a>请参阅

- [Dim 语句](../../visual-basic/language-reference/statements/dim-statement.md)
- [对象生存期:如何创建和销毁对象](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [生存期 (Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Is 运算符](../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot 运算符](../../visual-basic/language-reference/operators/isnot-operator.md)
- [可以为 null 的值类型](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
