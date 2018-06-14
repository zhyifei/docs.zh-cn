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
ms.openlocfilehash: 75d41883aefbaa54eb836d89bbfc034d99b7bba0
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
ms.locfileid: "34233972"
---
# <a name="declare-statement"></a>Declare Statement
声明对外部文件中实现的过程的引用。  
  
## <a name="syntax"></a>语法  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ]  
' -or-  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`attributelist`|可选。 请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。|  
|`accessmodifier`|可选。 可以是以下各项之一：<br /><br /> -   [公共](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [受保护](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [友元](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [私有](../../../visual-basic/language-reference/modifiers/private.md)<br />- [受保护的友元](../../language-reference/modifiers/protected-friend.md)<br />- [私有受保护](../../language-reference/modifiers/private-protected.md)<br /><br /> 请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。|  
|`Shadows`|可选。 请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。|  
|`charsetmodifier`|可选。 指定字符集和文件搜索信息。 可以是以下各项之一：<br /><br /> -   [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) （默认值）<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [自动](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|可选，但请`Sub`或`Function`必须出现。 指示外部过程不返回值。|  
|`Function`|可选，但请`Sub`或`Function`必须出现。 指示外部过程返回一个值。|  
|`name`|必须的。 此外部引用的名称。 有关详细信息，请参阅[声明元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。|  
|`Lib`|必须的。 引入了`Lib`子句，用于标识包含外部过程的外部文件 （DLL 或代码资源）。|  
|`libname`|必须的。 包含声明的过程的文件的名称。|  
|`Alias`|可选。 指示正在声明的过程，不能由中指定的名称在其文件中将标识`name`。 指定在其标识`aliasname`。|  
|`aliasname`|如果你使用是必需的`Alias`关键字。 标识两种方式之一中的过程的字符串：<br /><br /> 在其文件中，用引号括起来的过程的入口点名称 (`""`)<br /><br /> -或-<br /><br /> 数字符号 (`#`) 跟一个整数，指定在其文件中的过程的入口点的序号|  
|`parameterlist`|所需如果该过程采用参数。 请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。|  
|`returntype`|如果存在`Function`指定和`Option Strict`是`On`。 该过程返回的值的数据类型。|  
  
## <a name="remarks"></a>备注  
 有时，你需要调用在项目外部 （如 DLL 或代码资源中） 的文件中定义的过程。 执行此操作时，Visual Basic 编译器没有正确调用该过程所需的信息，如过程所在的位置、 标识的方式，其调用的序列和返回类型和字符串字符集，它使用的访问。 `Declare`语句创建对外部过程的引用，并提供这些必需的信息。  
  
 只能在模块级别使用 `Declare`。 这意味着*声明上下文*的外部引用必须为类、 结构或模块，并且不能为源文件、 命名空间、 接口、 过程或块。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
 外部引用默认为[公共](../../../visual-basic/language-reference/modifiers/public.md)访问。 你可以调整其访问级别有访问修饰符。  
  
## <a name="rules"></a>规则  
  
-   **属性。** 可以将特性应用于的外部引用。 你应用的任何特性都有效，仅在你的项目中，不是外部文件中。  
  
-   **修饰符。** 外部过程是隐式[共享](../../../visual-basic/language-reference/modifiers/shared.md)。 不能使用`Shared`关键字声明的外部引用，以及你不能更改它的共享的状态时。  
  
     外部过程不能参与重写、 实现接口成员，或处理的事件。 相应地，不能使用`Overrides`， `Overridable`， `NotOverridable`， `MustOverride`， `Implements`，或`Handles`中的关键字`Declare`语句。  
  
-   **外部过程名称。** 无需为相同的名称的此外部引用 (在`name`) 作为其外部文件中的过程的入口点名称 (`aliasname`)。 你可以使用`Alias`子句来指定入口点名称。 这可以是外部的过程相同的作用域中具有同名 Visual Basic 保留的修饰符或变量、 过程或其他任何编程元素的情况下很有用。  
  
    > [!NOTE]
    >  大多数 Dll 中的入口点名称都区分大小写。  
  
-   **外部过程数。** 或者，可以使用`Alias`子句来指定外部文件的导出表内的入口点的序号。 若要执行此操作，开始时`aliasname`数字符号 (`#`)。 如果外部过程名称中的任何字符不允许在 Visual Basic 中，或如果外部文件导出没有名称的过程，这可能很有用。  
  
## <a name="data-type-rules"></a>数据类型规则  
  
-   **参数数据类型。** 如果`Option Strict`是`On`，必须指定在每个参数的数据类型`parameterlist`。 这可以是任何数据类型或枚举、 结构、 类或接口的名称。 在`parameterlist`，你使用`As`子句，以指定要传递给每个参数的自变量的数据类型。  
  
    > [!NOTE]
    >  如果不是外部过程已为.NET Framework 编写，您必须采取措施的数据类型相对应。 例如，如果声明对使用为 Visual Basic 6.0 过程的外部引用`Integer`参数 （在 Visual Basic 6.0 中为 16 位），你必须确定相应的自变量作为`Short`中`Declare`语句，因为这是 16 位在 Visual Basic 中的位整数类型。 同样，`Long`在 Visual Basic 6.0 中，具有不同数据宽度和`Date`实现方式有所不同。  
  
-   **返回数据类型。** 如果外部过程是`Function`和`Option Strict`是`On`，必须指定返回到调用代码的值的数据类型。 这可以是任何数据类型或枚举、 结构、 类或接口的名称。  
  
    > [!NOTE]
    >  Visual Basic 编译器不验证您的数据类型与外部过程的这些兼容。 如果存在不匹配，公共语言运行时生成<xref:System.Runtime.InteropServices.MarshalDirectiveException>运行时异常。  
  
-   **默认数据类型。** 如果`Option Strict`是`Off`，而且你不指定中的参数的数据类型`parameterlist`，Visual Basic 编译器将转换为相应的自变量[Object 数据类型](../../../visual-basic/language-reference/data-types/object-data-type.md)。 同样，如果不指定`returntype`，编译器采用要返回的数据类型`Object`。  
  
    > [!NOTE]
    >  因为处理可能在不同平台写入外部过程时，这很危险要进行任何假设数据类型或要允许它们采用默认设置。 如果有的话，它会以指定数据类型的每个参数和返回值，安全很多。 这还可以提高代码的可读性。  
  
## <a name="behavior"></a>行为  
  
-   **作用域。** 外部引用是在其类、 结构或模块整个范围内。  
  
-   **生存期。** 外部引用具有相同的生存期类、 结构或在其中声明的模块。  
  
-   **调用外部过程。** 调用外部过程调用的相同方式`Function`或`Sub`过程 — 通过在表达式中使用它，如果它返回一个值，或指定在[Call 语句](../../../visual-basic/language-reference/statements/call-statement.md)如果它不返回值。  
  
     将自变量传递给完全按照指定的外部过程`parameterlist`中`Declare`语句。 不会考虑外部文件中最初声明这些参数已如何。 同样，如果没有返回值，将其完全用作指定的`returntype`中`Declare`语句。  
  
-   **字符集。** 你可以指定在`charsetmodifier`如何 Visual Basic 应封送字符串时它调用外部过程。 `Ansi`修饰符将定向 Visual Basic 进行封送处理所有字符串转换为 ANSI 值和`Unicode`修饰符将其封送所有字符串转换为 Unicode 值。 `Auto`修饰符将定向到封送字符串根据.NET Framework 的 Visual Basic 规则基于外部引用`name`，或`aliasname`如果指定。 默认值为 `Ansi`。  
  
     `charsetmodifier` 此外可以指定 Visual Basic 应如何查找其外部文件中的外部过程。 `Ansi` 和`Unicode`同时直接 Visual Basic，而无需在搜索过程中修改其名称进行查找。 `Auto` 指示 Visual Basic 来确定运行时平台的基本字符集并可能修改外部过程名称，如下所示：  
  
    -   在 ANSI 平台，如 Windows 95、 Windows 98 或 Windows Millennium Edition 上首先查找带有任何名称修改的外部过程。 如果失败，外部过程名称末尾追加"A"，并再次查找。  
  
    -   在 Unicode 平台上，例如 Windows NT、 Windows 2000 或 Windows XP 中，首先查找带有任何名称修改的外部过程。 如果失败，则追加"W"到末尾外部过程的名称，并再次查找。  
  
-   **机制。** Visual Basic 使用.NET Framework*平台调用*(PInvoke) 机制来解析和访问外部过程。 `Declare`语句和<xref:System.Runtime.InteropServices.DllImportAttribute>这两个类自动使用此机制，并不需要知道 PInvoke。 有关详细信息，请参阅[演练： 调用 Windows Api](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)。  
  
> [!IMPORTANT]
>  如果外部过程外部公共语言运行时 (CLR) 运行，则*非托管代码*。 在调用此类过程，例如 Win32 API 函数或 COM 方法，则可能会公开应用程序以便对安全风险。 有关详细信息，请参阅[非托管代码的安全编码准则](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md)。  
  
## <a name="example"></a>示例  
 下面的示例声明的外部引用`Function`返回当前的用户名称的过程。 然后，它调用外部过程`GetUserNameA`作为的一部分`getUser`过程。  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_1.vb)]  
  
## <a name="example"></a>示例  
 <xref:System.Runtime.InteropServices.DllImportAttribute>提供的替代方式的非托管代码中使用函数。 下面的示例声明一个导入的函数而无需使用`Declare`语句。  
  
 [!code-vb[VbVbalrStatements#16](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_2.vb)]  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_3.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>  
 [Imports 语句（.NET 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [Call 语句](../../../visual-basic/language-reference/statements/call-statement.md)  
 [演练：调用 Windows API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
