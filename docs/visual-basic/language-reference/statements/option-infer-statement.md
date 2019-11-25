---
title: Option Infer 语句
ms.date: 07/20/2015
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
ms.openlocfilehash: 53bc9d41f28f63061db2012395480aa6be7515dd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346499"
---
# <a name="option-infer-statement"></a>Option Infer 语句

允许声明变量时使用局部类型推理。

## <a name="syntax"></a>语法

```vb
Option Infer { On | Off }
```

## <a name="parts"></a>部件

|术语|定义|
|---|---|
|`On`|可选。 启用局部类型推理。|
|`Off`|可选。 禁用局部类型推理。|

## <a name="remarks"></a>备注

若要在文件中设置 `Option Infer`，请在任何其他源代码之前、文件顶部键入 `Option Infer On` 或 `Option Infer Off`。 如果为文件中 `Option Infer` 设置的值与在 IDE 中或在命令行上设置的值冲突，则文件中的值优先。

将 `Option Infer` 设置为 `On`时，你可以无需显式声明数据类型就声明本地变量。 编译器会从其初始化表达式的类型推断出变量的数据类型。

在下图中，`Option Infer` 处于打开状态。 声明 `Dim someVar = 2` 中的变量由类型推理声明为整数。

The following screenshot shows IntelliSense when Option Infer is on:

![Screenshot showing IntelliSense view when Option Infer is on.](./media/option-infer-statement/option-infer-as-integer-on.png)

在下图中，`Option Infer` 处于关闭状态。 声明 `Dim someVar = 2` 中的变量由类型推理声明为 `Object`。 In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).

The following screenshot shows IntelliSense when Option Infer is off:

![Screenshot showing IntelliSense view when Option Infer is off.](./media/option-infer-statement/option-infer-as-object-off.png)

> [!NOTE]
> 变量声明为 `Object` 时，可在程序运行时更改运行时类型。 Visual Basic performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower. For information about boxing and unboxing, see the [Visual Basic Language Specification](~/_vblang/spec/conversions.md#value-type-conversions).

类型推理适用于过程级，且在类、结构、模块或接口中的过程之外不适用。

For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).

## <a name="when-an-option-infer-statement-is-not-present"></a>当 Option Infer 语句不存在时

If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used. If the command-line compiler is used, the [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.

#### <a name="to-set-option-infer-in-the-ide"></a>若要在 IDE 中设置 Option Infer

1. 在“解决方案资源管理器”中，选择一个项目。 在“项目”菜单上，单击“属性”。

2. 单击“编译”选项卡。

3. Set the value in the **Option infer** box.

When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box. To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**. 在“选项”对话框中，展开“项目和解决方案”，然后单击“VB 默认值”。 The initial default setting in **VB Defaults** is `On`.

#### <a name="to-set-option-infer-on-the-command-line"></a>若要设置命令行上的 Option Infer

Include the [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.

## <a name="default-data-types-and-values"></a>默认数据类型和值

下表描述了指定 `Dim` 语句中数据类型和初始值设定项的各种组合的结果。

|是否指定数据类型？|是否指定初始值设定项？|示例|结果|
|---|---|---|---|
|No|No|`Dim qty`|如果 `Option Strict` 处于关闭状态（默认），则将变量设置为 `Nothing`。<br /><br /> 如果 `Option Strict` 处于打开状态，则发生编译时错误。|
|No|是|`Dim qty = 5`|如果 `Option Infer` 处于打开状态（默认），则变量采用初始值设定项的数据类型。 See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> 如果 `Option Infer` 和 `Option Strict` 均处于关闭状态，则变量采用 `Object` 的数据类型。<br /><br /> 如果 `Option Infer` 处于关闭状态但 `Option Strict` 处于打开状态，则发生编译时错误。|
|是|No|`Dim qty As Integer`|将变量初始化为数据类型的默认值。 For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).|
|是|是|`Dim qty  As Integer = 5`|如果初始值设定项的数据类型不可转换为指定数据类型，则会发生编译时错误。|

## <a name="example"></a>示例

下例演示了 `Option Infer` 语句启用局部类型推理的方式。

[!code-vb[VbVbalrTypeInference#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#6)]

## <a name="example"></a>示例

下例演示了变量被标识为 `Object` 时运行时类型可以改变的情况。

[!code-vb[VbVbalrTypeInference#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#11)]

## <a name="see-also"></a>请参阅

- [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)
- [局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Compare 语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Option Explicit 语句](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [“选项”对话框 ->“项目”->“Visual Basic 默认值”](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [装箱和取消装箱](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
