---
title: 重载过程注意事项 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: e1768d0ac03cb6730c4337d7476ae163e75adfd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654325"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>重载过程注意事项 (Visual Basic)
重载过程，你必须使用不同*签名*为每个重载版本。 这通常意味着每个版本，必须指定不同的参数列表。 有关详细信息，请参阅"不同的签名"[过程重载](./procedure-overloading.md)。  
  
 您可以重载`Function`具有过程`Sub`过程中，和反之亦然，只要它们具有不同签名。 仅在于其中一个的返回值，另一个不，不能区分两个重载。  
  
 您可以重载属性相同的方式重载过程，并采用相同的限制。 但是，不能重载过程具有属性，反之亦然。  
  
## <a name="alternatives-to-overloaded-versions"></a>重载版本的替代方法  
 特别是可选的自变量存在或其数量是变量时，有时需要重载版本的替代方法。  
  
 请记住，所有语言，不一定支持可选自变量和参数数组限制为 Visual Basic。 如果你正在编写一个可从任何几种语言编写的代码调用的过程，那么重载版本提供最大的灵活性。  
  
### <a name="overloads-and-optional-arguments"></a>重载和可选自变量  
 当调用的代码 （可选） 可以提供，或者忽略一个或多个自变量时，可以定义多个重载的版本，或使用可选参数。  
  
#### <a name="when-to-use-overloaded-versions"></a>何时使用重载的版本  
 你可以考虑在以下情况下定义一系列的重载版本：  
  
-   在过程代码中的逻辑是具体取决于调用代码是否提供可选的参数，或不明显不同。  
  
-   过程代码不能可靠地测试是否调用的代码已提供可选的参数。 这是这种情况，例如，如果没有可能的候选对于默认值，调用代码可能不需要提供。  
  
#### <a name="when-to-use-optional-parameters"></a>何时使用可选参数  
 你可能希望在以下情况下的一个或多个可选参数：  
  
-   唯一的必需的操作时调用的代码不会提供可选的参数是将参数设置为默认值。 在这种情况下，该过程代码可能会不太复杂如果定义单个版本与一个或多`Optional`参数。  
  
 有关详细信息，请参阅[可选参数](./optional-parameters.md)。  
  
### <a name="overloads-and-paramarrays"></a>重载和参数  
 如果调用代码可以通过数目可变的参数，可以定义多个重载的版本，或使用参数数组。  
  
#### <a name="when-to-use-overloaded-versions"></a>何时使用重载的版本  
 你可以考虑在以下情况下定义一系列的重载版本：  
  
-   你知道，调用代码永远不会将传递多个值一小部分给参数数组。  
  
-   在过程代码中的逻辑是明显不同，具体取决于在调用代码传递多少个值。  
  
-   调用代码可以将不同数据类型的值传递。  
  
#### <a name="when-to-use-a-parameter-array"></a>何时使用参数数组  
 更好地由`ParamArray`参数在以下情况：  
  
-   你不能预测多少个值调用代码可以将传递给参数数组中，并且它可能有大量。  
  
-   过程逻辑适于本身进行循环访问所有通过调用代码，执行对每个值实质上是相同的操作的值。  
  
 有关详细信息，请参阅[参数数组](./parameter-arrays.md)。  
  
## <a name="implicit-overloads-for-optional-parameters"></a>可选参数的的隐式重载  
 使用为过程[可选](../../../../visual-basic/language-reference/modifiers/optional.md)参数相当于两个重载过程，一个使用可选参数，而无需它的一个。 无法使用对应其中任一参数列表来重载这样的过程。 以下声明说明这一点。  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 对于带多个可选参数的过程，没有隐式重载，到达由前面的示例中的相似逻辑的一组。  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>隐式重载 ParamArray 参数  
 编译器将使用的过程视为[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数具有无限数目的重载，不同于彼此中什么调用代码将传递给参数数组，如下所示：  
  
-   当调用的代码不会提供的自变量的一个重载 `ParamArray`  
  
-   当调用的代码提供的一维数组的一个重载`ParamArray`元素类型  
  
-   对于每个正整数，一个重载的调用的代码提供该数量的参数，每个时`ParamArray`元素类型  
  
 以下声明说明了这些隐式重载。  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 无法重载采用一维数组的参数数组的参数列表的此类的过程。 但是，你可以使用其他隐式重载的签名。 以下声明说明这一点。  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>作为替代方法重载无类型编程  
 如果你想要允许不同的数据类型传递给参数调用的代码，替代方法是无类型编程。 你可以设置类型检查切换到`Off`使用[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)或[/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md)编译器选项。 然后无需声明参数的数据类型。 但是，此方法具有以下缺点相比重载：  
  
-   无类型编程生成效率较低的执行代码。  
  
-   该过程必须测试预期将传递每个数据类型。  
  
-   如果调用代码传递过程不支持的数据类型，编译器无法发出错误。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [过程疑难解答](./troubleshooting-procedures.md)  
 [如何：定义一个过程的多个版本](./how-to-define-multiple-versions-of-a-procedure.md)  
 [如何：调用重载过程](./how-to-call-an-overloaded-procedure.md)  
 [如何：重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [如何：重载参数数量不确定的过程](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [重载决策](./overload-resolution.md)  
 [重载](../../../../visual-basic/language-reference/modifiers/overloads.md)
