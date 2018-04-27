---
title: 重载决策 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e62560d853c95bc4bba6ba829d8579ee4388858e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="overload-resolution-visual-basic"></a>重载决策 (Visual Basic)
当 Visual Basic 编译器遇到对多个重载版本中定义的过程的调用时，编译器必须确定哪个要调用的重载。 这是通过执行以下步骤：  
  
1.  **辅助功能。** 它会消除任何重载具有阻止调用代码中调用它的访问级别。  
  
2.  **参数数目。** 它会消除定义不同数量的参数提供的调用中的任何重载。  
  
3.  **参数数据类型。** 编译器会通过扩展方法的实例方法的优先级。 如果需要仅扩大转换来匹配的过程调用找到的任何实例方法，则所有扩展方法将都删除并编译器继续使用实例的方法候选。 如果未不找到任何此类的实例方法，它将使用实例方法和扩展方法继续。  
  
     在此步骤中，它会消除任何重载的调用的自变量的数据类型无法转换到的重载中定义的参数类型。  
  
4.  **收缩转换。** 它消除了需要从调用的自变量类型收缩转换为已定义的参数类型的任何重载。 这是 true 是否类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`On`或`Off`。  
  
5.  **最小扩大。** 编译器会将对其余的重载。 对于每个对，它将进行比较已定义的参数的数据的类型。 如果所有的重载之一中的类型扩大到另一部分中的相应类型，编译器可以消除后者。 也就是说，它将保留要求最少量的扩大转换的重载。  
  
6.  **单个候选项。** 它将继续考虑重载成对直到只有一个重载仍将保留，并解决了对该重载的调用。 如果编译器不能减少为单个候选重载，它会生成错误。  
  
 下图显示了确定其中的一组要调用的重载版本的过程。  
  
 ![重载解析过程的流程图](./media/overloadres.gif "OverloadRes")  
在重载版本中  
  
 下面的示例阐释了此重载决策过程。  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/overload-resolution_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/overload-resolution_2.vb)]  
  
 在第一个调用中，编译器消除第一个重载，因为第一个参数的类型 (`Short`) 收缩到相应的参数的类型 (`Byte`)。 因为每个自变量类型中的第二个重载，它会然后消除第三个重载 (`Short`和`Single`) 扩大到第三个重载中的对应类型 (`Integer`和`Single`)。 第二个重载都需要较少扩大转换，因此编译器将使用它的调用。  
  
 在第二个调用中，编译器不能消除任何基于收缩的重载。 因为它可以调用使用最少扩大量自变量类型的第二个重载，它会出于同一原因如下所示的第一个调用，消除第三个重载。 但是，编译器无法解析的第一个和第二个重载之间。 每个具有一个已定义的参数类型扩大到另一部分中的相应类型 (`Byte`到`Short`，但`Single`到`Double`)。 因此，编译器将生成重载解析错误。  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>重载可选和 ParamArray 自变量  
 如果过程的两个重载具有完全相同的签名，只不过声明的最后一个参数[可选](../../../../visual-basic/language-reference/modifiers/optional.md)之一中和[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)中另一个，则编译器将解析对作为该过程的调用如下所示：  
  
|如果调用提供了最后一个参数为|编译器将解析对声明为最后一个参数的重载的调用|  
|---|---|  
|（省略自变量） 没有值|`Optional`|  
|单个值|`Optional`|  
|以逗号分隔的列表中的两个或多个值|`ParamArray`|  
|（包括空数组） 任何长度的数组|`ParamArray`|  
  
## <a name="see-also"></a>请参阅  
 [可选参数](./optional-parameters.md)  
 [参数数组](./parameter-arrays.md)  
 [过程重载](./procedure-overloading.md)  
 [过程疑难解答](./troubleshooting-procedures.md)  
 [如何：定义一个过程的多个版本](./how-to-define-multiple-versions-of-a-procedure.md)  
 [如何：调用重载过程](./how-to-call-an-overloaded-procedure.md)  
 [如何：重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [如何：重载参数数量不确定的过程](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [重载过程注意事项](./considerations-in-overloading-procedures.md)  
 [重载](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [扩展方法](./extension-methods.md)
