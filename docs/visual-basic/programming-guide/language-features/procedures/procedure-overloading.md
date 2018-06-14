---
title: 过程重载 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 0d1f2c4d8c88922659b3d91ed41d5e760e6e5233
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653909"
---
# <a name="procedure-overloading-visual-basic"></a>过程重载 (Visual Basic)
*重载*过程意味着在多个版本，使用相同名称但不同的参数列表中定义它。 重载的目的是定义过程的几个密切相关的版本，而无需将它们按名称区分开来。 通过不同的参数列表来执行此操作。  
  
## <a name="overloading-rules"></a>重载规则  
 重载过程，适用以下规则：  
  
-   **相同的名称**。 每个重载的版本必须使用相同的过程名称。  
  
-   **不同的签名**。 每个重载的版本必须不同于在至少一个以下方面的所有其他重载版本：  
  
    -   参数数目  
  
    -   参数的顺序  
  
    -   参数数据类型  
  
    -   类型参数 （对于泛型过程） 数  
  
    -   返回类型 （仅针对转换运算符）  
  
     过程名称，以及统称为前述各项*签名*的过程。 当调用重载的过程时，编译器将使用签名来检查调用正确与定义相匹配。  
  
-   **项不是签名的一部分**。 如果不改变签名，不能重载过程。 具体而言，不能通过一个或多个以下各项仅改变重载过程：  
  
    -   过程修饰符关键字，如`Public`， `Shared`，和 `Static`  
  
    -   参数或类型参数名称  
  
    -   类型参数约束 （针对泛型过程）  
  
    -   参数修饰符关键字，如`ByRef`和 `Optional`  
  
    -   它是否返回一个值  
  
    -   数据类型 （除转换运算符） 的返回值  
  
     上面的列表中的项不签名的一部分。 但不能使用它们来区分重载版本，你可以通过它们的签名区分正确的重载版本中对其进行修改。  
  
-   **后期绑定自变量**。 如果你想要将后期绑定的对象变量传递到重载版本，你必须声明为适当的参数<xref:System.Object>。  
  
## <a name="multiple-versions-of-a-procedure"></a>过程的多个版本  
 假设你正在编写`Sub`过程针对客户的平衡，和你发送一个事务想要能够按名称或帐户号，请参阅客户。 若要适应这种情况，可以定义两个不同`Sub`过程，如以下示例所示：  
  
 [!code-vb[VbVbcnProcedures#73](./codesnippet/VisualBasic/procedure-overloading_1.vb)]  
  
### <a name="overloaded-versions"></a>重载的版本  
 一种替代方法是重载的单一过程名称。 你可以使用[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字来定义为每个参数列表中，过程的一个版本，如下所示：  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/procedure-overloading_2.vb)]  
  
#### <a name="additional-overloads"></a>其他重载  
 如果你还想要接受在事务量`Decimal`或`Single`，可进一步重载`post`以允许这种变化形式。 如果你这样做这到每个前面的示例中的重载，你会有四个`Sub`过程，它们具有相同名称但具有四个不同的签名。  
  
## <a name="advantages-of-overloading"></a>重载的优点  
 重载过程的优点是在调用的灵活性。 若要使用`post`过程，声明在前面的示例中，调用代码可以获取的客户标识为`String`或`Integer`，然后在任一情况下调用相同的过程。 下面的示例阐释了这一点：  
  
 [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/procedure-overloading_4.vb)]  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [如何：定义一个过程的多个版本](./how-to-define-multiple-versions-of-a-procedure.md)  
 [如何：调用重载过程](./how-to-call-an-overloaded-procedure.md)  
 [如何：重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [如何：重载参数数量不确定的过程](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [重载过程注意事项](./considerations-in-overloading-procedures.md)  
 [重载决策](./overload-resolution.md)  
 [重载](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Visual Basic 中的泛型类型](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
