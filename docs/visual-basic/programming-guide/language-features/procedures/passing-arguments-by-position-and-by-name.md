---
title: 按位置和按名称传递参数
ms.date: 02/01/2018
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
ms.openlocfilehash: b6588335f7634cc87a9fc14cbfc4ba80baad1abb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401435"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>按位置和名称传递自变量 (Visual Basic)

调用`Sub`或`Function`过程时，可以*按位置*传递参数（按过程定义中显示参数的顺序）传递参数，也可以*按名称*传递参数，而不考虑位置。

按名称传递参数时，指定参数声明的名称后跟冒号和等号 （`:=`），后跟参数值。 您可以按任意顺序提供命名参数。

例如，以下`Sub`过程采用三个参数：

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

调用此过程时，可以按位置、名称或使用两者的混合物提供参数。

## <a name="passing-arguments-by-position"></a>按位置传递参数

可以调用`Display`该方法，其参数通过位置，并通过逗号分隔，如以下示例所示：

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

如果在位置参数列表中省略可选参数，则必须使用逗号保留其位置。 下面的示例调用没有`Display``age`参数的方法：

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a>按名称传递参数

或者，可以使用通过名称`Display`传递的参数进行调用，也可以用逗号分隔，如以下示例所示：

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

以这种方式按名称传递参数在调用具有多个可选参数的过程时特别有用。 如果按名称提供参数，则不必使用连续逗号来表示缺少的位置参数。 按名称传递参数还便于跟踪您传递的参数以及省略的参数。

## <a name="mixing-arguments-by-position-and-by-name"></a>按位置和名称混合参数

您可以在单个过程调用中按位置和名称提供参数，如以下示例所示：

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

在前面的示例中，不需要额外的逗号来保留省略`age`的参数的位置，因为`birth`是按名称传递的。

在 15.5 之前的 Visual Basic 版本中，当您通过位置和名称的混合提供参数时，位置参数必须都放在第一位。 按名称提供参数后，所有剩余的参数都必须按名称传递。  例如，对`Display`该方法的以下调用显示编译器错误[BC30241：命名参数预期](../../../misc/bc30241.md)。

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

从 Visual Basic 15.5 开始，如果结束位置参数位于正确的位置，则位置参数可以遵循命名参数。 如果在 Visual Basic 15.5 下编译，则对`Display`该方法的上一个调用将成功编译，不再生成编译器错误[BC30241](../../../misc/bc30241.md)。

当您希望使用命名参数使代码更具可读性时，这种以任意顺序混合和匹配命名参数和位置参数的能力特别有用。 例如，以下`Person`类构造函数需要两个类型的`Person`参数，这两个参数都可以。 `Nothing`

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

使用混合命名和位置参数有助于在 和`father``mother`参数的值为`Nothing`时明确代码的意图：

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

要遵循具有命名参数的位置参数，必须向 Visual Basic 项目 （.vbproj）\*文件添加以下元素：

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

有关详细信息[，请参阅设置可视化基本语言版本](../../../language-reference/configure-language-version.md)。

## <a name="restrictions-on-supplying-arguments-by-name"></a>按名称提供参数的限制

不能按名称传递参数以避免输入所需的参数。 只能省略可选参数。

不能按名称传递参数数组。 这是因为当您调用 过程时，为参数数组提供无限数量的逗号分隔参数，并且编译器不能将多个参数与单个名称相关联。

## <a name="see-also"></a>另请参阅

- [程序](./index.md)
- [过程形参和实参](./procedure-parameters-and-arguments.md)
- [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)
- [按值和按引用传递参数](./passing-arguments-by-value-and-by-reference.md)
- [可选参数](./optional-parameters.md)
- [参数数组](./parameter-arrays.md)
- [选](../../../../visual-basic/language-reference/modifiers/optional.md)
- [RaiseEvent](../../../../visual-basic/language-reference/modifiers/paramarray.md)
