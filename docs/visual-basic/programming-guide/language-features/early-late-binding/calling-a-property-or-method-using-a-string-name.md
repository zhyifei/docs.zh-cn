---
title: 使用字符串名调用属性或方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
ms.openlocfilehash: 0683047865f520a09b2d2fe196096286b7d78714
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965395"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>使用字符串名调用属性或方法 (Visual Basic)
在大多数情况下, 你可以在设计时发现对象的属性和方法, 并编写代码来处理它们。 但是, 在某些情况下, 您可能事先不知道对象的属性和方法, 或者您可能只是想让最终用户能够在运行时指定属性或执行方法。  
  
## <a name="callbyname-function"></a>CallByName 函数  
 例如, 考虑一个客户端应用程序, 该应用程序通过将运算符传递到 COM 组件来计算用户输入的表达式。 假设您不断地向需要新运算符的组件添加新函数。 使用标准对象访问技术时, 必须先重新编译并重新发布客户端应用程序, 然后才能使用新的运算符。 若要避免这种情况, 可以`CallByName`使用函数将新运算符作为字符串传递, 而无需更改应用程序。  
  
 `CallByName`函数使您可以在运行时使用字符串来指定属性或方法。 `CallByName`函数的签名如下所示:  
  
 *Result*(Object、ProcedureName、CallType、Arguments ()) = `CallByName`  
  
 第一个参数 "*对象*" 采用要对其执行操作的对象的名称。 *ProcedureName*参数采用一个字符串, 该字符串包含要调用的方法或属性过程的名称。 *CallType*参数采用一个常数, 该常数表示要调用的过程的类型: 方法 (`Microsoft.VisualBasic.CallType.Method`)、属性读取 (`Microsoft.VisualBasic.CallType.Get`) 或属性集 (`Microsoft.VisualBasic.CallType.Set`)。 *参数*自变量是可选的, 它采用类型`Object`为的数组, 该数组包含过程的所有参数。  
  
 你可以在`CallByName`当前解决方案中将与类一起使用, 但它通常用于从 .NET Framework 程序集访问 COM 对象或对象。  
  
 假设你添加对程序集的引用, 该程序集包含`MathClass`名为的类, 该类具有`SquareRoot`名为的新函数, 如以下代码所示:  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 应用程序可以使用文本框控件控制将调用的方法及其参数。 例如, 如果`TextBox1`包含要计算的表达式, 并`TextBox2`用于输入函数的名称, 则可以使用`SquareRoot`以下代码在中`TextBox1`对表达式调用函数:  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 如果在中输入 "64" `TextBox1`, 在中`TextBox2`输入 "SquareRoot", 然后调用`CallMath`该过程, 则计算中`TextBox1`的数字的平方根。 该示例中的代码调用`SquareRoot`函数 (该函数采用包含要作为必选参数进行计算的表达式的字符串) 并返回中`TextBox1`的 "8" (64 的平方根)。 当然, 如果用户在中`TextBox2`输入了无效的字符串, 且该字符串包含属性的名称而不是方法, 或者如果该方法有额外的必需参数, 则会发生运行时错误。 使用`CallByName`来预见这些错误或任何其他错误时, 必须添加可靠的错误处理代码。  
  
> [!NOTE]
> 尽管函数在某些情况下可能有用, 但你必须权衡其对性能影响的有用性, 使用`CallByName`调用过程比后期绑定调用略慢。 `CallByName` 如果调用的是重复调用的函数 (如循环`CallByName`内), 则可能会对性能产生严重影响。  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [确定对象类型](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
