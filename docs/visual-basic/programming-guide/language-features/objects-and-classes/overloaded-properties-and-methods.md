---
title: 重载属性和方法
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: a5017d371f8a01436020443b2e3466c78fc35d21
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346091"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>重载属性和方法（Visual Basic）

重载是在具有相同名称但参数类型不同的类中创建多个过程、实例构造函数或属性。

## <a name="overloading-usage"></a>重载用法

当对象模型要求对不同数据类型进行操作的过程使用相同的名称时，重载特别有用。 例如，可以显示几种不同数据类型的类可能具有如下所示的 `Display` 过程：

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

如果没有重载，则需要为每个过程创建不同的名称，即使它们执行相同的操作，如下所示：

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

重载使您可以更轻松地使用属性或方法，因为它提供了可使用的数据类型选择。 例如，先前讨论的重载 `Display` 方法可通过以下代码行调用：

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

在运行时，Visual Basic 会根据你指定的参数的数据类型调用正确过程。

## <a name="overloading-rules"></a>重载规则

 通过添加两个或多个具有相同名称的属性或方法，可以为类创建重载成员。 除重载的派生成员以外，每个重载成员都必须具有不同的参数列表，并且在重载属性或过程时，不能将以下各项用作区分功能：

- 应用于成员或成员的参数的修饰符，如 `ByVal` 或 `ByRef`。

- 参数的名称

- 过程的返回类型

当重载时，`Overloads` 关键字是可选的，但是如果任何重载成员使用 `Overloads` 关键字，则所有其他具有相同名称的重载成员也必须指定此关键字。

派生类可以重载具有相同参数和参数类型的成员的继承成员，这一过程称为*按名称和签名进行隐藏*。 如果在按名称和签名进行隐藏时使用 `Overloads` 关键字，则将使用该成员的派生类的实现，而不是基类中的实现，并且该成员的所有其他重载将可用于派生类的实例。

如果在使用具有相同参数和参数类型的成员重载某个继承成员时省略了 `Overloads` 关键字，则会被*名称隐藏*。 按名称隐藏将替换成员的继承实现，并使所有其他重载不可用于派生类及其 decedents 的实例。

`Overloads` 和 `Shadows` 修饰符不能同时用于相同的属性或方法。

### <a name="example"></a>示例

下面的示例创建了重载方法，这些方法接受美元的 `String` 或 `Decimal` 表示形式，并返回包含销售税的字符串。

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>使用此示例创建重载方法

1. 打开一个新的项目并添加一个名为 `TaxClass`的类。

2. 向 `TaxClass` 类添加下面的代码。

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. 将以下过程添加到窗体。

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. 向窗体添加一个按钮，并从按钮的 `Button1_Click` 事件调用 `ShowTax` 过程。

5. 运行项目，然后单击窗体上的按钮以测试重载的 `ShowTax` 过程。

在运行时，编译器选择与所使用的参数匹配的适当重载函数。 单击该按钮时，将首先调用重载的方法，该方法是一个字符串和消息 "Price 为字符串" 的 `Price` 参数。 税率为 $5.12 "。 第二次使用 `Decimal` 的值调用 `TaxAmount`，"Price" 为 Decimal。 税率为 $5.12 "。

## <a name="see-also"></a>另请参阅

- [对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Visual Basic 中的阴影](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [继承的基础知识](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [ParamArray](../../../../visual-basic/language-reference/modifiers/byval.md)
- [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
