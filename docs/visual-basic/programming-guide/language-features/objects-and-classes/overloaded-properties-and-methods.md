---
title: 重载的属性和方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: c0aa7c4a13e049045743044a98020a1aab2cf1a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652189"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>重载的属性和方法 (Visual Basic)

重载是创建多个过程、 实例构造函数或在具有相同名称但不同的自变量类型的类的属性。  
  
## <a name="overloading-usage"></a>重载使用情况

 当您的对象模型指示你使用的操作对不同数据类型的过程相同的名称，则重载是特别有用。 例如，可以显示多种不同的数据类型的类可能具有`Display`过程如下所示：  
  
 [!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]
  
 如果没有重载，你将需要创建不同的名称，为每个过程，即使它们执行相同的操作中，如下所示：  
  
 [!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]
  
 重载，使得更轻松地使用属性或方法，因为它提供了一种可以使用的数据类型。 例如，重载`Display`以前可以使用以下代码行的任何调用讨论的方法：  
  
 [!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]
  
 在运行时，Visual Basic 调用正确的过程基于你指定的参数的数据类型。  
  
## <a name="overloading-rules"></a>重载规则

 通过添加两个或多个属性或方法具有相同名称创建的类重载的成员。 除非是重载派生成员，每个重载的成员必须具有不同的参数列表和重载属性或过程时，不作为区别性功能使用以下各项：  
  
-   修饰符，如`ByVal`或`ByRef`，适用于成员或参数的成员。  
  
-   参数的名称  
  
-   返回类型的过程  
  
 `Overloads`关键字时是可选的重载，但如果任一重载成员均使用`Overloads`关键字，则所有其他重载的成员具有相同名称还必须指定此关键字。  
  
 派生的类可以重载具有相同的参数和参数类型，该过程称为的成员的继承的成员*按名称和签名隐藏*。 如果`Overloads`按名称和签名隐藏，派生的类的成员的实现将使用而不是在基的类中，实现和所有其他重载对于该成员将可供使用的实例时所使用关键字派生的类。  
  
 如果`Overloads`重载具有成员的具有相同的参数和参数类型，继承的成员时省略关键字，则该重载称为*通过名称来隐藏*。 通过名称来隐藏替换继承的成员，实现，并使所有其他重载到的实例派生的类和其对于不可用。  
  
 `Overloads`和`Shadows`修饰符不能同时使用具有相同的属性或方法。  
  
### <a name="example"></a>示例

 下面的示例创建接受的重载的方法`String`或`Decimal`美元总金额和返回包含增值税的字符串表示形式。  
  
#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>若要使用此示例创建了重载的方法
  
1.  打开一个新项目并添加一个名为类`TaxClass`。  
  
2.  向 `TaxClass` 类添加下面的代码。  
  
     [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]
  
3.  向窗体中添加下面的过程。  
  
     [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]
  
4.  将按钮添加到表单中，然后调用`ShowTax`过程从`Button1_Click`该按钮的事件。  
  
5.  运行该项目并单击要测试的重载的窗体上的按钮`ShowTax`过程。  
  
 在运行时，编译器将选择相应的重载的函数正在使用的参数匹配。 重载的方法时单击按钮时，都会首先调用与`Price`参数是一个字符串和消息，"价格是一个字符串。 税金是 $5.12"显示。 `TaxAmount` 使用调用`Decimal`值的第二个时间和消息时，请"价格是十进制。 税金是 $5.12"显示。  
  
## <a name="see-also"></a>请参阅

 [对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [在 Visual Basic 中隐藏](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [继承的基础知识](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [重载](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
