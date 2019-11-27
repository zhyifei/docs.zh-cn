---
title: 使用字符串名调用属性或方法
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
ms.openlocfilehash: cb584f0dfbd905ca071f9a86b1eab231f3017538
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345213"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>使用字符串名调用属性或方法 (Visual Basic)
在大多数情况下，你可以在设计时发现对象的属性和方法，并编写代码来处理它们。 但是，在某些情况下，您可能事先不知道对象的属性和方法，或者您可能只是想让最终用户能够在运行时指定属性或执行方法。  
  
## <a name="callbyname-function"></a>CallByName 函数  
 例如，考虑一个客户端应用程序，该应用程序通过将运算符传递到 COM 组件来计算用户输入的表达式。 假设您不断地向需要新运算符的组件添加新函数。 使用标准对象访问技术时，必须先重新编译并重新发布客户端应用程序，然后才能使用新的运算符。 若要避免这种情况，可以使用 `CallByName` 函数将新运算符作为字符串传递，而无需更改应用程序。  
  
 `CallByName` 函数允许你在运行时使用字符串来指定属性或方法。 `CallByName` 函数的签名如下所示：  
  
 *Result* = `CallByName`（*Object*、 *ProcedureName*、 *CallType*、 *Arguments*（））  
  
 第一个参数 "*对象*" 采用要对其执行操作的对象的名称。 *ProcedureName*参数采用一个字符串，该字符串包含要调用的方法或属性过程的名称。 *CallType*参数采用一个常数，该常数表示要调用的过程的类型：方法（`Microsoft.VisualBasic.CallType.Method`）、属性读取（`Microsoft.VisualBasic.CallType.Get`）或属性集（`Microsoft.VisualBasic.CallType.Set`）。 *Arguments*参数是可选的，它采用类型为 `Object` 的数组，该数组包含过程的所有参数。  
  
 您可以在当前解决方案中将 `CallByName` 与类一起使用，但它通常用于从 .NET Framework 程序集访问 COM 对象或对象。  
  
 假设你添加了一个对程序集的引用，该程序集包含名为 `MathClass`的类，该类具有名为 `SquareRoot`的新函数，如以下代码所示：  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 应用程序可以使用文本框控件控制将调用的方法及其参数。 例如，如果 `TextBox1` 包含要计算的表达式，并且 `TextBox2` 用于输入函数的名称，则可以使用以下代码对 `TextBox1`中的表达式调用 `SquareRoot` 函数：  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 如果在 `TextBox1`中输入 "64"，`TextBox2`中的 "SquareRoot"，然后调用 `CallMath` 过程，则计算 `TextBox1` 中的数字的平方根。 该示例中的代码调用 `SquareRoot` 函数（该函数使用一个字符串，该字符串包含要作为必选参数进行计算的表达式），并在 `TextBox1` （64的平方根）中返回 "8"。 当然，如果用户在 `TextBox2`中输入无效的字符串，如果该字符串包含属性的名称而不是方法，或者如果该方法具有额外的必需参数，则会发生运行时错误。 使用 `CallByName` 预测这些错误或任何其他错误时，必须添加可靠的错误处理代码。  
  
> [!NOTE]
> 尽管在某些情况下 `CallByName` 函数可能很有用，但必须根据性能影响来权衡其有用性，因为使用 `CallByName` 调用过程比后期绑定调用稍微慢一些。 如果调用的是重复调用的函数（如在循环内），`CallByName` 可能会对性能产生严重影响。  
  
## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [确定对象类型](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
