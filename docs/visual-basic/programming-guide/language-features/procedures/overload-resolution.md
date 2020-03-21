---
title: 重载决策
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
ms.openlocfilehash: 84d52bbbfb34c2e5d67ed6a1810ab3e32fafda22
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266867"
---
# <a name="overload-resolution-visual-basic"></a>重载决策 (Visual Basic)
当 Visual Basic 编译器遇到对在多个重载版本中定义的过程的调用时，编译器必须决定调用的重载。 它通过执行以下步骤来完成此工作：  
  
1. **辅助功能。** 它通过阻止调用代码调用它的访问级别消除了任何重载。  
  
2. **参数数。** 它消除了定义与调用中提供的参数数不同的任何重载。  
  
3. **参数数据类型。** 编译器给予实例方法优先于扩展方法。 如果发现任何实例方法只需要加宽转换以匹配过程调用，则所有扩展方法都将被删除，编译器仅继续使用实例方法候选项。 如果未找到此类实例方法，则继续使用实例和扩展方法。  
  
     在此步骤中，它消除了调用参数的数据类型无法转换为重载中定义的参数类型的任何重载。  
  
4. **缩小转换。** 它消除了任何需要从调用参数类型到定义的参数类型进行缩小转换的重载。 无论类型检查开关（[选项严格语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)）是`On`还是`Off`，都是如此。  
  
5. **最小加宽。** 编译器将剩余的重载成对。 对于每对，它比较已定义参数的数据类型。 如果其中一个重载中的类型都扩展到另一个重载中的相应类型，编译器将消除后者。 也就是说，它保留需要最少加宽量的重载。  
  
6. **单位候选人。** 它继续考虑成对的重载，直到只剩下一个重载，并且它解决了对该重载的调用。 如果编译器无法将重载减少到单个候选项，则会生成错误。  
  
 下图显示了确定要调用的一组重载版本中哪个的过程。  
  
 ![重载解析过程的流程图](./media/overload-resolution/determine-overloaded-version.gif "在重载版本之间解决")
  
 下面的示例说明了此重载解决过程。  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 在第一个调用中，编译器消除了第一个重载，因为第一个参数`Short`（ ） 的类型缩小到相应参数 （`Byte`的类型）。 然后，它消除了第三个重载，因为第二个重载`Short` `Single`（和 ） 中的每个参数类型在第三个重`Integer`载`Single`（和 ） 中扩展到相应的类型。 第二个重载需要较少的扩展，因此编译器使用它进行调用。  
  
 在第二个调用中，编译器不能在缩小的基础上消除任何重载。 它消除了第三个重载的原因与第一个调用相同，因为它可以调用第二个重载，而参数类型的扩展更少。 但是，编译器无法在第一个重载和第二个重载之间解析。 每个参数类型都有一个已定义的参数类型，该参数类型将扩展到另`Byte`一`Short`个类型`Single`（`Double`到 ，但为 ） 因此，编译器生成重载解析错误。  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>重载可选参数和参数参数  
 如果过程的两个重载具有相同的签名，但最后一个参数在一个参数中声明[为可选](../../../../visual-basic/language-reference/modifiers/optional.md)，另一个参数为[ParamArray，](../../../../visual-basic/language-reference/modifiers/paramarray.md)则编译器将按如下方式解析对该过程的调用：  
  
|如果调用提供最后一个参数为|编译器解析对重载的调用，将最后一个参数声明为|  
|---|---|  
|无值（省略参数）|`Optional`|  
|单个值|`Optional`|  
|逗号分隔列表中的两个或多个值|`ParamArray`|  
|任何长度的数组（包括空数组）|`ParamArray`|  
  
## <a name="see-also"></a>另请参阅

- [可选参数](./optional-parameters.md)
- [参数数组](./parameter-arrays.md)
- [过程重载](./procedure-overloading.md)
- [过程疑难解答](./troubleshooting-procedures.md)
- [如何：定义一个过程的多个版本](./how-to-define-multiple-versions-of-a-procedure.md)
- [如何：调用重载过程](./how-to-call-an-overloaded-procedure.md)
- [如何：重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [如何：重载参数数量不确定的过程](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [重载过程注意事项](./considerations-in-overloading-procedures.md)
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [扩展方法](./extension-methods.md)
