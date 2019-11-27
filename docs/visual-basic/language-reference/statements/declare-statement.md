---
title: Declare Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Declare
- vb.Lib
- vb.Any
helpviewer_keywords:
- Lib keyword [Visual Basic]
- declaring procedures [Visual Basic], Declare statement
- functions [Visual Basic], function procedures
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- procedures [Visual Basic], external
- Alias keyword [Visual Basic]
- external references [Visual Basic], Visual Basic
- DLLs, declaring procedures
- Declare statement [Visual Basic]
- declarations [Visual Basic], external
- Visual Basic code, Function procedures
- As keyword [Visual Basic], in Declare statement
- resources [Visual Basic], declaring
- Public keyword [Visual Basic], Declare statement
- platform invoke, Visual Basic external references
- Sub procedures [Visual Basic], declarations
- APIs, declaring API functions
- Visual Basic code, Sub procedures
- Function procedures [Visual Basic], declaring
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
ms.openlocfilehash: 48a36e3ecdef40810ea7a3194e85b5b646154331
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354092"
---
# <a name="declare-statement"></a>Declare Statement

声明对外部文件中所实现过程的引用。

## <a name="syntax"></a>语法

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ]
' -or-
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]
```

## <a name="parts"></a>部件

|术语|Definition|
|---|---|
|`attributelist`|可选。 请参阅[特性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。|
|`accessmodifier`|可选。 可以是以下各项之一：<br /><br /> -   [公有](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [保护](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [朋友](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [私有](../../../visual-basic/language-reference/modifiers/private.md)<br />- [受保护的朋友](../../language-reference/modifiers/protected-friend.md)<br />- [私有保护](../../language-reference/modifiers/private-protected.md)<br /><br /> 请参阅 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。|
|`Shadows`|可选。 请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。|
|`charsetmodifier`|可选。 指定字符集和文件搜索信息。 可以是以下各项之一：<br /><br /> -   [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) （默认值）<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [自动](../../../visual-basic/language-reference/modifiers/auto.md)|
|`Sub`|可选，但必须出现 `Sub` 或 `Function`。 指示外部过程不返回值。|
|`Function`|可选，但必须出现 `Sub` 或 `Function`。 指示外部过程返回值。|
|`name`|必需。 此外部引用的名称。 有关详细信息，请参阅已[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。|
|`Lib`|必需。 引入 `Lib` 子句，该子句标识包含外部过程的外部文件（DLL 或代码资源）。|
|`libname`|必需。 包含已声明过程的文件的名称。|
|`Alias`|可选。 指示无法在其文件中按照 `name`中指定的名称标识所声明的过程。 在 `aliasname`中指定其标识。|
|`aliasname`|如果使用 `Alias` 关键字，则为必需。 通过以下两种方式之一标识过程的字符串：<br /><br /> 过程在其文件中的入口点名称，在引号（`""`）中<br /><br /> \- 或 -<br /><br /> 数字符号（`#`），后跟一个整数，该整数指定过程入口点在其文件中的序号|
|`parameterlist`|如果过程使用参数，则为必需。 请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。|
|`returntype`|如果指定 `Function` 并且 `Option Strict` `On`，则为必需。 过程返回的值的数据类型。|

## <a name="remarks"></a>备注

有时，您需要调用项目外的文件（如 DLL 或代码资源）中定义的过程。 当你执行此操作时，Visual Basic 编译器不能访问正确调用过程所需的信息，例如过程所在的位置、标识方法、调用序列和返回类型，以及它使用的字符串字符集。 `Declare` 语句创建对外部过程的引用并提供此必要信息。

只能在模块级别使用 `Declare`。 这意味着外部引用的*声明上下文*必须是类、结构或模块，不能是源文件、命名空间、接口、过程或块。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。

外部引用默认为[公共](../../../visual-basic/language-reference/modifiers/public.md)访问。 您可以使用访问修饰符调整其访问级别。

## <a name="rules"></a>规则

- **属性.** 您可以将属性应用于外部引用。 所应用的任何属性仅在您的项目中有效，而不是在外部文件中。

- **组成.** 外部过程是隐式[共享](../../../visual-basic/language-reference/modifiers/shared.md)的。 声明外部引用时，不能使用 `Shared` 关键字，也不能更改其共享状态。

  外部过程不能参与重写、实现接口成员或处理事件。 因此，不能在 `Implements`语句中使用 `Overrides`、`Overridable`、`NotOverridable`、`MustOverride`、`Handles` 或 `Declare` 关键字。

- **外部过程名称。** 您不必为此外部引用指定与过程在其外部文件（`aliasname`）中的入口点名称相同的名称（在 `name`中）。 您可以使用 `Alias` 子句来指定入口点名称。 如果外部过程与同一范围内的 Visual Basic 保留修饰符、变量、过程或任何其他编程元素同名，这会很有用。

  > [!NOTE]
  > 大多数 Dll 中的入口点名称都区分大小写。

- **外部过程号。** 或者，您可以使用 `Alias` 子句来指定外部文件的导出表中入口点的序号。 为此，您开始 `aliasname` 数字符号（`#`）。 如果 Visual Basic 中不允许使用外部过程名称中的任何字符，或者如果外部文件导出没有名称的过程，则这会很有用。

## <a name="data-type-rules"></a>数据类型规则

- **参数数据类型。** 如果 `On``Option Strict`，则必须在 `parameterlist`中指定每个参数的数据类型。 这可以是任何数据类型，也可以是枚举、结构、类或接口的名称。 在 `parameterlist`中，使用 `As` 子句来指定要传递给每个参数的参数的数据类型。

  > [!NOTE]
  > 如果没有为 .NET Framework 编写外部过程，则必须注意数据类型是对应的。 例如，如果使用 `Integer` 参数声明对 Visual Basic 6.0 过程的外部引用（Visual Basic 6.0 中的16位），则必须将相应的参数标识为 `Declare` 语句中的 `Short`，因为这是 Visual Basic 中的16位整数类型。 同样，`Long` 在 Visual Basic 6.0 中具有不同的数据宽度，`Date` 的实现方式不同。

- **返回数据类型。** 如果外部过程是 `Function` 并且 `Option Strict` `On`，则必须指定返回到调用代码的值的数据类型。 这可以是任何数据类型，也可以是枚举、结构、类或接口的名称。

  > [!NOTE]
  > Visual Basic 编译器不会验证数据类型是否与外部过程的数据类型兼容。 如果存在不匹配的情况，则公共语言运行时将在运行时生成 <xref:System.Runtime.InteropServices.MarshalDirectiveException> 异常。

- **默认数据类型。** 如果 `Off` `Option Strict` 并且未在 `parameterlist`指定参数的数据类型，则 Visual Basic 编译器会将相应的参数转换为[对象数据类型](../../../visual-basic/language-reference/data-types/object-data-type.md)。 同样，如果不指定 `returntype`，编译器会将返回数据类型作为 `Object`。

  > [!NOTE]
  > 因为你要处理的是可能已在其他平台上编写的外部过程，所以对数据类型进行任何假设或允许其默认值是危险的。 最安全的方法是指定每个参数的数据类型和返回值（如果有）。 这也会提高代码的可读性。

## <a name="behavior"></a>行为

- **内.** 外部引用在其类、结构或模块的范围内。

- **生存期.** 外部引用与声明它的类、结构或模块具有相同的生存期。

- **调用外部过程。** 调用外部过程的方法与调用 `Function` 或 `Sub` 过程的方法相同，方法是在表达式中使用它，如果返回值，则在表达式中使用它; 如果不返回值，则在[Call 语句](../../../visual-basic/language-reference/statements/call-statement.md)中指定。

  您可以按 `Declare` 语句中 `parameterlist` 的指定完全将参数传递给外部过程。 不要考虑参数最初在外部文件中的声明方式。 同样，如果有返回值，则按 `Declare` 语句中 `returntype` 的指定方式使用。

- **字符集。** 您可以在 `charsetmodifier` Visual Basic 在调用外部过程时如何封送字符串。 `Ansi` 修饰符指示 Visual Basic 将所有字符串封送为 ANSI 值，`Unicode` 修饰符指示它将所有字符串封送为 Unicode 值。 `Auto` 修饰符根据外部引用 `name`或 `aliasname` （如果已指定）指示 Visual Basic 封送 .NET Framework 字符串。 默认值为 `Ansi`。

  `charsetmodifier` 还指定了 Visual Basic 应该如何查找外部文件中的外部过程。 `Ansi` 和 `Unicode` 直接 Visual Basic 在搜索过程中进行查找，而不修改其名称。 `Auto` 指示 Visual Basic 确定运行时平台的基本字符集，并可能修改外部过程名称，如下所示：

  - 在 ANSI 平台（如 Windows 95、Windows 98 或 Windows Millennium Edition）上，首先查找不带名称修改的外部过程。 如果此操作失败，请在外部过程名称末尾追加 "A"，并再次查找。

  - 在 Unicode 平台（如 Windows NT、Windows 2000 或 Windows XP）上，首先查找外部过程，而不修改名称。 如果此操作失败，请将 "W" 追加到外部过程名称的末尾，并再次查找。

- **机制.** Visual Basic 使用 .NET Framework*平台调用*（PInvoke）机制来解析和访问外部过程。 `Declare` 语句和 <xref:System.Runtime.InteropServices.DllImportAttribute> 类都自动使用这种机制，无需任何对 PInvoke 的了解。 有关详细信息，请参阅[演练：调用 Windows api](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)。

> [!IMPORTANT]
> 如果外部过程在公共语言运行时（CLR）之外运行，则它是不*受管理的代码*。 如果调用此类过程（例如 Windows API 函数或 COM 方法），则可能会向应用程序带来安全风险。 有关详细信息，请参阅[非托管代码的安全编码指导原则](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md)。

## <a name="example"></a>示例

下面的示例声明一个对返回当前用户名的 `Function` 过程的外部引用。 然后，它调用外部过程作为 `getUser` 过程的一部分 `GetUserNameA`。

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>示例

<xref:System.Runtime.InteropServices.DllImportAttribute> 提供了一种在非托管代码中使用函数的替代方法。 下面的示例声明一个导入的函数，而不使用 `Declare` 语句。

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Imports 语句（.NET 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)
- [参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Call 语句](../../../visual-basic/language-reference/statements/call-statement.md)
- [演练：调用 Windows API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
