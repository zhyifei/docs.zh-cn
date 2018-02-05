---
title: "按位置和名称传递自变量 (Visual Basic)"
ms.custom: 
ms.date: 02/01/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13f5e5a8da6a899d4920a25b250ca88b2a21f559
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2018
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>按位置和名称传递自变量 (Visual Basic)
当调用`Sub`或`Function`过程中，你可以将参数传递*按位置*— 在过程定义中出现的顺序 — 或将它们传递*按名称*，而无需考虑位置。  
  
 当你按名称传递自变量时，你指定参数的声明名称后跟冒号和等号 (`:=`) 后, 跟自变量值。 你可以提供命名自变量的任何顺序。  
  
 例如，以下`Sub`过程使用三个参数：  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 在调用此过程时，你可以提供的自变量按位置、 按名称，或通过使用这两者的混合。  
  
## <a name="passing-arguments-by-position"></a>按位置传递自变量  
 你可以调用`Display`具有其自变量方法按位置传递，并且用逗号分隔，如下面的示例中所示：  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 如果省略可选的参数位置自变量列表中，你必须保留它用逗号分隔的位置。 下面的示例调用`Display`方法，而`age`自变量：  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a>按名称传递自变量  
 或者，可以调用`Display`按名称传递自变量也用逗号分隔，如下面的示例中所示：  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 在调用了具有多个可选参数的过程时，通过以这种方式的名称传递自变量是特别有用。 如果按名称提供自变量，你不需要使用连续的逗号来表示缺少位置自变量。 按名称传递自变量还可以更轻松地跟踪的哪些参数将传递和你省略哪些功能。  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>混合自变量按位置和名称  

你可以提供自变量的位置和名称的单一过程调用中，如下面的示例中所示：  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 在前面的示例中，没有多余的逗号是保存的省略的位置所需`age`自变量，因为`birth`按名称传递了。  
  
在 Visual Basic 的 15.5 之前的版本，当你的混合位置和名称、 位置自变量形式提供参数时都必须放在第一个。 后按名称提供自变量，剩下的自变量必须所有传递的名称。  例如，以下调用`Display`方法显示编译器错误[BC30241： 名为应自变量](../../../misc/bc30241.md)。

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

从 Visual Basic 15.5 开始，位置自变量可以遵循命名自变量的结束位置自变量是否在正确的位置。 如果在 Visual Basic 15.5，调用下编译`Display`方法编译成功，而且不再生成编译器错误[BC30241](../../../misc/bc30241.md)。  

当你想要使用命名自变量以使代码更具可读性，混合和匹配位置和命名的自变量的任何顺序此能力是特别有用。 例如，以下`Person`类构造函数需要的类型的两个自变量`Person`，这两种可以是`Nothing`。 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

使用混合命名参数和位置参数有助于明确代码的意图清除时的值`father`和`mother`自变量是`Nothing`:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

若要执行具有命名自变量的位置自变量，必须将下面的元素添加到 Visual Basic 项目 (\*.vbproj) 文件：

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="restrictions-on-supplying-arguments-by-name"></a>提供自变量按名称的限制  

你不能按名称来避免输入所需的参数传递自变量。 可以省略仅的可选自变量。  
  
你不能按名称传递参数数组。 这是因为在调用过程时，你提供的参数数组中，逗号分隔的参数数量不确定，并且编译器不能将多个自变量与单个名称关联。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)  
 [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)  
 [可选参数](./optional-parameters.md)  
 [参数数组](./parameter-arrays.md)  
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
