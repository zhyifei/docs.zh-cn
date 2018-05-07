---
title: 过程疑难解答 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: f66e7f7444f2d3b1bb58bae6008f8896c81c2f76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-procedures-visual-basic"></a>过程疑难解答 (Visual Basic)
此页列出在使用过程时可能发生的一些常见问题。  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>从一个函数的过程中返回数组类型  
 如果`Function`过程返回数组数据类型，则无法使用`Function`将值存储在数组的元素的名称。 如果你尝试执行此操作，编译器会将它解释为对的调用`Function`。 下面的示例生成编译器错误。  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 语句`allOnes(i) = 1`生成一个编译器错误，因为它似乎是调用`allOnes`用错误数据类型参数 (singleton`Integer`而不是`Integer`数组)。 语句`Return allOnes()`生成一个编译器错误，因为它似乎是调用`allOnes`不带参数。  
  
 **正确的方法：**能够修改要返回的数组的元素，定义一个内部数组为本地变量。 下面的示例编译而不出错。  
  
 [!code-vb[VbVbcnProcedures#66](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]  
  
## <a name="argument-not-being-modified-by-procedure-call"></a>未修改的自变量由过程调用  
 如果你想要允许更改基础中调用代码的自变量的编程元素的过程，必须通过引用传递。 但即使按值传递过程仍可访问的元素的引用类型参数。  
  
-   **基础变量**。 若要允许替换基础变量元素本身的值的过程，该过程必须声明参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)。 此外，调用代码必须不将自变量在括号中，因为这样将重写`ByRef`传递机制。  
  
-   **引用类型元素**。 如果声明的参数[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)，过程不能修改基础变量元素本身。 但是，如果参数为引用类型，该过程可以修改它指向的该对象的成员，即使它不能替换变量的值一样。 例如，如果参数是一个数组变量，该过程不能将新数组赋给它，但它可以更改一个或多个它的元素。 更改的元素会反映在调用代码中的基础数组变量。  
  
 下面的示例定义两个过程可通过值采用一个数组变量并运行对其元素。 过程`increase`只需添加一个对每个元素。 过程`replace`将一个新数组分配给参数`a()`，然后添加一个用于每个元素。 但是，重新分配不会影响调用代码中的基础数组变量因为`a()`声明`ByVal`。  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]  
  
 下面的示例调用`increase`和`replace`。  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]  
  
 第一个`MsgBox`调用显示"后 increase(n): 11、 21、 31、 41"。 因为`n`是引用类型，`increase`可以更改的成员，即使它传递`ByVal`。  
  
 第二个`MsgBox`调用显示"后 replace(n): 11、 21、 31、 41"。 因为`n`传递`ByVal`，`replace`不能修改变量`n`通过向它分配一个新数组。 当`replace`创建新的数组实例`k`并将其分配到本地变量`a`，它将失去对引用`n`传递中调用代码。 当它递增的成员`a`，只有本地数组`k`受到影响。  
  
 **正确的方法：**能够修改本身的基础变量元素，它通过引用传递。 下面的示例演示的声明中的更改`replace`允许它将替换中调用代码的另一个数组。  
  
 [!code-vb[VbVbcnProcedures#64](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]  
  
## <a name="unable-to-define-an-overload"></a>无法定义重载  
 如果你想要定义一个过程的重载的版本，则必须使用相同的名称，但不同的签名。 如果编译器无法区分具有相同签名的重载将声明，它会生成错误。  
  
 *签名*的过程由过程名称和参数列表。 每个重载必须有与所有其他重载相同的名称，但必须从中至少一个签名的其他组件的所有不同。 有关详细信息，请参阅[过程重载](./procedure-overloading.md)。  
  
 以下各项，即使它们涉及到参数列表中，不是签名的过程的组件：  
  
-   过程修饰符关键字，如`Public`， `Shared`，和 `Static`  
  
-   参数名称  
  
-   参数修饰符关键字，如`ByRef`和 `Optional`  
  
-   数据类型 （除转换运算符） 的返回值  
  
 不能通过一个或多个前述各项仅改变重载过程。  
  
 **正确的方法：**能够定义的过程重载，您必须改变签名。 因为你必须使用相同的名称，您必须改变数量、 顺序或参数的数据类型。 在泛型过程中，可以使用不同类型参数的数目。 在转换运算符 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md))，您可以改变的返回类型。  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>重载决策可选和 ParamArray 自变量  
 如果重载具有一个或多个过程[可选](../../../../visual-basic/language-reference/modifiers/optional.md)参数或[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数，则必须避免复制任何*隐式重载*。 有关信息，请参阅[中重载过程注意事项](./considerations-in-overloading-procedures.md)。  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a>调用重载过程的错误版本  
 如果过程有多个重载的版本，你应熟悉所有其参数列表，并了解如何通过 Visual Basic 来解决在重载之间的调用。 否则，你可以调用预期以外的重载。  
  
 就能确定你想要调用的重载，请务必遵守以下规则：  
  
-   提供正确数量的自变量，并按正确的顺序。  
  
-   理想情况下，你的自变量应具有作为相应的参数完全相同的数据类型。 在任何情况下，每个自变量的数据类型必须扩大到其对应的参数。 这是如此[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)设置为`Off`。 如果某个重载需要从你的自变量列表中，重载任何收缩转换不能调用。  
  
-   如果你提供需要扩大转换的自变量，请为相应的参数数据类型尽可能接近，其数据类型。 如果两个或多个重载接受您的自变量数据类型，编译器将解析对调用进行最少量的扩大转换的重载的调用。  
  
 你可以通过使用降低的数据类型不匹配的机率[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)转换关键字做准备你的自变量时。  
  
### <a name="overload-resolution-failure"></a>重载决策失败  
 当调用重载的过程时，编译器将尝试消除所有但的重载之一。 如果成功，它会解析到该重载的调用。 如果它消除了所有重载，或者如果它不能减少为单个候选符合条件的重载，它会生成错误。  
  
 下面的示例阐释了重载决策过程。  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]  
  
 在第一个调用中，编译器消除第一个重载，因为第一个参数的类型 (`Short`) 收缩到相应的参数的类型 (`Byte`)。 因为每个自变量类型中的第二个重载，它会然后消除第三个重载 (`Short`和`Single`) 扩大到第三个重载中的对应类型 (`Integer`和`Single`)。 第二个重载都需要较少扩大转换，因此编译器将使用它的调用。  
  
 在第二个调用中，编译器不能消除任何基于收缩的重载。 因为它可以调用使用最少扩大量自变量类型的第二个重载，它会出于同一原因如下所示的第一个调用，消除第三个重载。 但是，编译器无法解析的第一个和第二个重载之间。 每个具有一个已定义的参数类型扩大到另一部分中的相应类型 (`Byte`到`Short`，但`Single`到`Double`)。 因此，编译器将生成重载解析错误。  
  
 **正确的方法：**能够调用清楚无误地重载的过程，使用[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)以匹配的参数类型的参数数据类型。 下面的示例演示调用`z`对第二个重载强制解析。  
  
 [!code-vb[VbVbcnProcedures#65](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>重载决策可选和 ParamArray 自变量  
 如果过程的两个重载具有完全相同的签名，只不过声明的最后一个参数[可选](../../../../visual-basic/language-reference/modifiers/optional.md)之一中和[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)中另一个，则编译器将解析对该过程的调用根据最接近的匹配。 有关详细信息，请参阅[重载解析](./overload-resolution.md)。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [Sub 过程](./sub-procedures.md)  
 [Function 过程](./function-procedures.md)  
 [属性过程](./property-procedures.md)  
 [运算符过程](./operator-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [过程重载](./procedure-overloading.md)  
 [重载过程注意事项](./considerations-in-overloading-procedures.md)  
 [重载决策](./overload-resolution.md)
