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
ms.openlocfilehash: 9895709076634ce156ba9d1009f79ba7ddd2ba56
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646384"
---
# <a name="declare-statement"></a>Declare Statement

声明对外部文件中实现的过程的引用。

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

## <a name="parts"></a>组成部分

|术语|定义|
|---|---|
|`attributelist`|可选。 请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。|
|`accessmodifier`|可选。 可以是以下值之一：<br /><br /> -   [公共](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [保护](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [朋友](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [私人](../../../visual-basic/language-reference/modifiers/private.md)<br />- [受保护的好友](../../language-reference/modifiers/protected-friend.md)<br />- [私人保护](../../language-reference/modifiers/private-protected.md)<br /><br /> 请参阅[视觉基础 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。|
|`Shadows`|可选。 请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。|
|`charsetmodifier`|可选。 指定字符集和文件搜索信息。 可以是以下值之一：<br /><br /> -   [安西](../../../visual-basic/language-reference/modifiers/ansi.md)（默认）<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [自动](../../../visual-basic/language-reference/modifiers/auto.md)|
|`Sub`|可选，但必须`Sub`显示`Function`或必须显示。 指示外部过程不返回值。|
|`Function`|可选，但必须`Sub`显示`Function`或必须显示。 指示外部过程返回值。|
|`name`|必需。 此外部引用的名称。 有关详细信息，请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。|
|`Lib`|必需。 引入一`Lib`个子句，用于标识包含外部过程的外部文件（DLL 或代码资源）。|
|`libname`|必需。 包含声明过程的文件的名称。|
|`Alias`|可选。 指示无法通过 中`name`指定的名称在其文件中标识正在声明的过程。 在 中`aliasname`指定其标识。|
|`aliasname`|如果使用关键字，`Alias`则需要。 以两种方式之一标识过程的字符串：<br /><br /> 其文件中的过程的入口点名称，在引号 （`""`） 内<br /><br /> \- 或 -<br /><br /> 编号 （`#`）， 后跟一个整数，指定程序在其文件中的入口点的序号|
|`parameterlist`|如果过程采用参数，则为必填项。 请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。|
|`returntype`|如果指定`Function`并且`Option Strict`为`On`，则为"必需"。 过程返回的值的数据类型。|

## <a name="remarks"></a>备注

有时，您需要调用在项目外部的文件（如 DLL 或代码资源）中定义的过程。 执行此操作时，Visual Basic 编译器无法访问正确调用该过程所需的信息，例如过程的位置、标识方式、其调用序列和返回类型以及它使用的字符串字符集。 该`Declare`语句创建对外部过程的引用，并提供此必要的信息。

只能在模块级别使用 `Declare`。 这意味着外部引用*的声明上下文*必须是类、结构或模块，不能是源文件、命名空间、接口、过程或块。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。

外部引用默认为[公共](../../../visual-basic/language-reference/modifiers/public.md)访问。 您可以使用访问修改器调整其访问级别。

## <a name="rules"></a>规则

- **属性。** 您可以将属性应用于外部引用。 应用的任何属性仅在项目中生效，而在外部文件中无效。

- **修饰 符。** 外部过程隐式[共享](../../../visual-basic/language-reference/modifiers/shared.md)。 声明外部引用时`Shared`不能使用关键字，也不能更改其共享状态。

  外部过程不能参与重写、实现接口成员或处理事件。 因此`Overrides`，您不能在`Overridable``NotOverridable``MustOverride``Implements``Handles`语句中使用 、、、、、、、、、在 语句中使用 关键字。 `Declare`

- **外部过程名称。** 您不必为其外部文件 （ 中的入口点名称 ）`name`中为此外部引用指定相同的名称 （in`aliasname`） 。 可以使用子`Alias`句指定入口点名称。 如果外部过程的名称与 Visual Basic 保留修改器或变量、过程或同一作用域中的任何其他编程元素具有相同的名称，则此功能非常有用。

  > [!NOTE]
  > 大多数 DLL 中的入口点名称区分大小写。

- **外部程序编号。** 或者，可以使用`Alias`子句指定外部文件导出表中的入口点的批号。 为此，您从`aliasname`数字符号 （ 开始。`#` 如果在 Visual Basic 中不允许外部过程名称中的任何字符，或者如果外部文件导出没有名称的过程，则此功能非常有用。

## <a name="data-type-rules"></a>数据类型规则

- **参数数据类型。** 如果是`Option Strict``On`，则必须在 中`parameterlist`指定每个参数的数据类型。 这可以是任何数据类型或枚举、结构、类或接口的名称。 在`parameterlist`中，使用`As`子句指定要传递给每个参数的参数的数据类型。

  > [!NOTE]
  > 如果未为 .NET 框架编写外部过程，则必须注意数据类型是否对应。 例如，如果声明外部引用 Visual Basic 6.0 过程具有`Integer`参数（Visual Basic 6.0 中的 16 位），则必须标识`Short``Declare`语句中的相应参数，因为这是 Visual Basic 中的 16 位整数类型。 同样，Visual `Long` Basic 6.0 中的数据宽度也不同`Date`，并且实现方式不同。

- **返回数据类型。** 如果外部过程为`Function``Option Strict``On`和 ，则必须指定返回给调用代码的值的数据类型。 这可以是任何数据类型或枚举、结构、类或接口的名称。

  > [!NOTE]
  > Visual Basic 编译器不验证数据类型是否与外部过程的类型兼容。 如果不匹配，则通用语言运行时会在运行时生成<xref:System.Runtime.InteropServices.MarshalDirectiveException>异常。

- **默认数据类型。** 如果`Option Strict``Off`和 未在 中`parameterlist`指定参数的数据类型，则 Visual Basic 编译器将相应的参数转换为[对象数据类型](../../../visual-basic/language-reference/data-types/object-data-type.md)。 同样，如果不指定`returntype`，编译器将返回数据类型为 。 `Object`

  > [!NOTE]
  > 由于您正在处理可能已写入其他平台上的外部过程，因此对数据类型进行任何假设或允许它们默认是危险的。 指定每个参数的数据类型和返回值（如果有）要安全得多。 这也提高了代码的可读性。

## <a name="behavior"></a>行为

- **范围。** 外部引用在其类、结构或模块中处于作用域中。

- **一生。** 外部引用的生存期与声明外部引用的类、结构或模块的生存期相同。

- **调用外部过程。** 调用外部过程的方式与调用`Function`或`Sub`过程的方式相同—，如果在表达式中返回值时使用它，或者在[调用语句](../../../visual-basic/language-reference/statements/call-statement.md)中指定它（如果它不返回值）。

  将参数传递给外部过程，完全按照`parameterlist``Declare`语句中指定的方式进行。 不考虑参数最初在外部文件中声明的方式。 同样，如果存在返回值，则完全按照 语句中`returntype``Declare`指定的方式使用它。

- **字符集。** 您可以指定`charsetmodifier`Visual Basic 在调用外部过程时应如何封送字符串。 修改`Ansi`器指示 Visual Basic 将所有字符串封送到 ANSI 值`Unicode`，修改器指示它将将所有字符串封送到 Unicode 值。 修改`Auto`器指示 Visual Basic 根据基于外部引用`name`的 .NET Framework 规则对字符串进行`aliasname`封送，或者如果指定。 默认值是 `Ansi`。

  `charsetmodifier`还指定 Visual Basic 应如何查找其外部文件中的外部过程。 `Ansi`和`Unicode`直接视觉基本查找它，而无需修改其名称在搜索期间。 `Auto`指示 Visual Basic 确定运行时平台的基本字符集，并可能修改外部过程名称，如下所示：

  - 在 ANSI 平台上（如 Windows 95、Windows 98 或 Windows 千年版）上，首先查找外部过程，无需修改名称。 如果失败，将"A"追加到外部过程名称的末尾，然后再次查找它。

  - 在 Unicode 平台上（如 Windows NT、Windows 2000 或 Windows XP）上，首先查找外部过程，无需修改名称。 如果失败，将"W"追加到外部过程名称的末尾，然后再次查找它。

- **机制。** Visual Basic 使用 .NET 框架*平台调用*（PInvoke） 机制解析和访问外部过程。 语句`Declare`和<xref:System.Runtime.InteropServices.DllImportAttribute>类都自动使用此机制，您不需要任何 PInvoke 的知识。 有关详细信息，请参阅[演练：调用 Windows API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)。

> [!IMPORTANT]
> 如果外部过程在通用语言运行时 （CLR） 之外运行，则它是*非托管代码*。 调用此类过程（例如 Windows API 函数或 COM 方法）时，可能会使应用程序面临安全风险。 有关详细信息，请参阅[非托管代码的安全编码准则](https://docs.microsoft.com/previous-versions/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code)。

## <a name="example"></a>示例

以下示例声明对返回当前用户名`Function`的过程的外部引用。 然后，它将外部过程`GetUserNameA`称为该过程的一`getUser`部分。

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>示例

提供了<xref:System.Runtime.InteropServices.DllImportAttribute>在非托管代码中使用函数的替代方法。 下面的示例声明导入的函数而不使用语句`Declare`。

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Imports 语句（.NET 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [操作员地址](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)
- [参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Call 语句](../../../visual-basic/language-reference/statements/call-statement.md)
- [演练：调用 Windows API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
