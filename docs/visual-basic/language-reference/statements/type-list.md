---
title: 类型列表 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: a0d489684b8f98e871211e6d0d95d42284275954
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582893"
---
# <a name="type-list-visual-basic"></a>类型列表 (Visual Basic)

指定*泛型*编程元素的*类型参数*。 多个参数之间用逗号分隔。 下面是一个类型参数的语法。

## <a name="syntax"></a>语法

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a>部件

|术语|定义|
|---|---|
|`genericmodifier`|可选。 只能在泛型接口和委托中使用。 可以通过使用[Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)关键字或逆变，使用[In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)关键字声明类型协变。 请参阅 [协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)。|
|`typename`|必须的。 类型参数的名称。 这是占位符，将替换为相应类型参数提供的定义类型。|
|`constraintlist`|可选。 限制可为 `typename` 提供的数据类型的需求列表。 如果有多个约束，请将它们括在大括号（`{ }`）中，并用逗号分隔它们。 必须引入包含[As](../../../visual-basic/language-reference/statements/as-clause.md)关键字的约束列表。 在列表的开头只使用一次 `As`。|

## <a name="remarks"></a>备注

每个泛型编程元素都必须采用至少一个类型参数。 类型参数是客户端代码在创建泛型类型的实例时指定的特定类型（*构造元素*）的占位符。 可以定义泛型类、结构、接口、过程或委托。

有关何时定义泛型类型的详细信息，请参阅[Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)。 有关类型参数名称的详细信息，请参阅已[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。

## <a name="rules"></a>规则

- **括号.** 如果提供类型参数列表，则必须将其括在括号内，并且必须[使用关键字 of](../../../visual-basic/language-reference/statements/of-clause.md)引入列表。 在列表的开头只使用一次 `Of`。

- **约束.** 类型形参上的*约束*列表可以包括以下各项：

  - 任意数量的接口。 提供的类型必须实现此列表中的每个接口。

  - 最多一个类。 提供的类型必须从该类继承。

  - `New` 关键字。 提供的类型必须公开您的泛型类型可以访问的无参数构造函数。 如果通过一个或多个接口约束类型参数，则此方法很有用。 实现接口的类型不一定公开构造函数，并且根据构造函数的访问级别，泛型类型中的代码可能无法访问该构造函数。

  - @No__t_0 关键字或 `Structure` 关键字。 @No__t_0 关键字约束泛型类型参数，要求传递给它的任何类型参数都是引用类型，例如字符串、数组或委托，或者是从类创建的对象。 @No__t_0 关键字约束泛型类型参数，要求传递给它的任何类型参数都是值类型，例如结构、枚举或基本数据类型。 不能在同一 `constraintlist` 同时包含 `Class` 和 `Structure`。

  提供的类型必须满足 `constraintlist` 中包含的每项要求。

  每个类型参数的约束与其他类型参数上的约束无关。

## <a name="behavior"></a>行为

- **编译时替换。** 当你从泛型编程元素创建构造类型时，将为每个类型参数提供一个定义的类型。 Visual Basic 编译器将为泛型元素中出现的每个 `typename` 替换提供的类型。

- **缺少约束。** 如果未在类型参数上指定任何约束，则代码仅限于该类型参数的[对象数据类型](../../../visual-basic/language-reference/data-types/object-data-type.md)支持的操作和成员。

## <a name="example"></a>示例

下面的示例演示了泛型字典类的主干定义，其中包括用于向字典中添加新条目的主干函数。

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a>示例

由于 `dictionary` 是泛型的，因此使用它的代码可以从其创建各种对象，每个对象具有相同的功能，但作用不同的数据类型。 下面的示例显示了一个代码行，用于创建具有 `String` 项和 `Integer` 键的 `dictionary` 对象。

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a>示例

下面的示例演示前面的示例生成的等效主干定义。

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a>请参阅

- [Of](../../../visual-basic/language-reference/statements/of-clause.md)
- [New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)
- [Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Object 数据类型](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)
- [如何：使用泛型类](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
