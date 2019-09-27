---
title: Property 语句（Visual Basic）
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 2c3e417aad404171a43342dc92773615ec350ef5
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332751"
---
# <a name="property-statement"></a>Property Statement

声明属性的名称，以及用于存储和检索属性值的属性过程。

## <a name="syntax"></a>语法

```vb
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
    [ <attributelist> ] [ accessmodifier ] Get
        [ statements ]
    End Get
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )
        [ statements ]
    End Set
End Property
- or -
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
```

## <a name="parts"></a>部件

- `attributelist`

  可选。 应用于此属性的属性列表，或 `Get` 或 @no__t 过程。 请参阅[特性列表](attribute-list.md)。

- `Default`

  可选。 指定此属性是在其上定义该属性的类或结构的默认属性。 默认属性必须接受参数，并且可以在不指定属性名称的情况下进行设置和检索。 如果将属性声明为 `Default`，则不能对属性或其任一属性过程使用 @no__t。

- `accessmodifier`

  可选，在 `Property` 语句上，最多是一个 @no__t 和 `Set` 语句。 可以是以下各项之一：

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Private](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Private Protected](../modifiers/private-protected.md)

  请参阅 [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)。

- `propertymodifiers`

  可选。 可以是以下各项之一：

  - [重载](../modifiers/overloads.md)

  - [Overrides](../modifiers/overrides.md)

  - [Overridable](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  可选。 请参阅[共享](../modifiers/shared.md)。

- `Shadows`

  可选。 请参阅[阴影](../modifiers/shadows.md)。

- `ReadOnly`

  可选。 请参阅[ReadOnly](../modifiers/readonly.md)。

- `WriteOnly`

  可选。 请参阅[WriteOnly](../modifiers/writeonly.md)。

- `Iterator`

  可选。 请参阅[迭代器](../modifiers/iterator.md)。

- `name`

  必需。 属性的名称。 请参阅 [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)。

- `parameterlist`

  可选。 表示此属性的参数的局部变量名称列表，以及 `Set` 过程的可能的其他参数。 请参阅[参数列表](parameter-list.md)。

- `returntype`

  如果 `Option Strict` @no__t，则为必需。 此属性返回的值的数据类型。

- `Implements`

  可选。 指示此属性实现一个或多个属性，每个属性都是由该属性的包含类或结构实现的接口中定义的。 请参阅[Implements 语句](implements-statement.md)。

- `implementslist`

  如果提供 `Implements`，则是必需的。 要实现的属性列表。

  `implementedproperty [ , implementedproperty ... ]`

  每个 `implementedproperty` 都具有以下语法和部件：

  `interface.definedname`

  |部件|描述|
  |---|---|
  |`interface`|必需。 此属性的包含类或结构实现的接口的名称。|
  |`definedname`|必需。 在 `interface` 中定义属性时所依据的名称。|

- `Get`

  可选。 如果将属性标记 `ReadOnly`，则是必需的。 启动 `Get` 属性过程，该过程用于返回属性的值。  不能将 `Get` 语句与[自动实现的属性](../../programming-guide/language-features/procedures/auto-implemented-properties.md)一起使用。

- `statements`

  可选。 要在 @no__t 或 @no__t 过程中运行的语句块。

- `End Get`

  终止 @no__t 的属性过程。

- `Set`

  可选。 如果将属性标记 `WriteOnly`，则是必需的。 启动一个 `Set` 属性过程，该过程用于存储属性的值。  不能将 `Set` 语句与[自动实现的属性](../../programming-guide/language-features/procedures/auto-implemented-properties.md)一起使用。

- `End Set`

  终止 @no__t 的属性过程。

- `End Property`

  终止此属性的定义。

## <a name="remarks"></a>备注

@No__t-0 语句引入了属性的声明。 属性可以有 `Get` 过程（只读）、@no__t 一过程（只写）或两者（读写）。 使用自动实现的属性时，可以省略 @no__t 0 和 @no__t 的过程。 有关详细信息，请参阅[自动实现的属性](../../programming-guide/language-features/procedures/auto-implemented-properties.md)。

只能在类级别使用 `Property`。 这意味着属性的*声明上下文*必须是类、结构、模块或接口，不能是源文件、命名空间、过程或块。 有关详细信息，请参阅[声明上下文和默认访问级别](declaration-contexts-and-default-access-levels.md)。

默认情况下，属性使用公共访问。 您可以在 `Property` 语句上使用访问修饰符调整属性的访问级别，并且可以根据需要将其一个属性过程调整到限制性更强的访问级别。

Visual Basic 在属性赋值期间将参数传递给 @no__t 的过程。 如果没有为 @no__t 提供参数-0，集成开发环境（IDE）将使用名为 `value` 的隐式参数。 此参数保存要赋给属性的值。 通常将此值存储在私有本地变量中，并在调用 @no__t 0 过程时返回。

## <a name="rules"></a>规则

- **混合访问级别。** 如果要定义读写属性，则可以选择为 `Get` 或 @no__t 过程指定不同的访问级别，但不能同时指定两者。 如果执行此操作，则过程访问级别必须比属性的访问级别更严格。 例如，如果将该属性声明 `Friend`，则可以将 `Set` 过程声明为 `Private` 但不 `Public`。

  如果要定义 `ReadOnly` 或 `WriteOnly` 属性，则单个属性过程（分别为 `Get` 或 @no__t 3）表示所有属性。 不能为此类过程声明不同的访问级别，因为这会为属性设置两个访问级别。

- **返回类型。** @No__t-0 语句可以声明其返回的值的数据类型。 您可以指定任何数据类型或枚举、结构、类或接口的名称。

  如果不指定 `returntype`，则属性将返回 `Object`。

- **部署.** 如果此属性使用 `Implements` 关键字，则包含类或结构必须在其 @no__t 2 或 @no__t 3 语句之后立即具有 @no__t 1 语句。 @No__t-0 语句必须包含 `implementslist` 中指定的每个接口。 但是，接口定义 `Property` （在 `definedname`）的名称不必与此属性的名称相同（在 `name`）中。

## <a name="behavior"></a>行为

- **从属性过程返回。** 当 @no__t 0 或 `Set` 过程返回到调用代码时，执行将继续执行调用它的语句后面的语句。

  @No__t-0 和 @no__t 1 语句导致直接从属性过程退出。 任意数量的 @no__t （0）和 @no__t 语句均可出现在过程中的任何位置，你可以混合使用 @no__t 2 和 @no__t 3 语句。

- **返回值。** 若要从 @no__t 0 过程返回值，可以将该值分配给属性名称，或者将其包含在 @no__t 1 语句中。 下面的示例将返回值分配给属性名称 `quoteForTheDay`，然后使用 `Exit Property` 语句返回。

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  如果使用 @no__t 值而不将值分配给 `name`，则 @no__t 2 过程将返回属性数据类型的默认值。

  @No__t-0 语句同时分配 @no__t 过程返回值并退出过程。 下面的示例演示了这一点。

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a>示例

下面的示例声明类中的一个属性。

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a>请参阅

- [自动实现的属性](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [对象和类](../../programming-guide/language-features/objects-and-classes/index.md)
- [Get 语句](get-statement.md)
- [Set 语句](set-statement.md)
- [参数列表](parameter-list.md)
- [默认](../modifiers/default.md)
