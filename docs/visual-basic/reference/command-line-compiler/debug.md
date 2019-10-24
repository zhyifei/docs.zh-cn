---
title: /debug (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: 27485cda9bb2af980b300180134fd7e99ffceeba
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775675"
---
# <a name="-debug-visual-basic"></a>-debug （Visual Basic）

使编译器生成调试信息并将其放在输出文件中。

## <a name="syntax"></a>语法

```console
-debug[+ | -]
```

或

```console
-debug:[full | pdbonly]
```

## <a name="arguments"></a>自变量

|术语|定义|
|---|---|
|`+` &#124; `-`|可选。 指定 `+` 或 `/debug` 会导致编译器生成调试信息并将其放置在 .pdb 文件中。 指定 `-` 与不指定 `/debug` 具有相同的效果。|
|`full` &#124; `pdbonly`|可选。 指定编译器生成的调试信息的类型。 如果不指定 `/debug:pdbonly`，则默认值为 `full`，这使你能够将调试器附加到正在运行的程序。 @No__t_0 参数允许在调试器中启动程序时进行源代码调试，但仅在将正在运行的程序附加到调试器时才显示程序集语言代码。|

## <a name="remarks"></a>备注

使用此选项创建调试版本。 如果未指定 `/debug`、`/debug+` 或 `/debug:full`，则将无法调试程序的输出文件。

默认情况下，不会发出调试信息（`/debug-`）。 若要发出调试信息，请指定 `/debug` 或 `/debug+`。

有关如何配置应用程序的调试性能的信息，请参阅[令映像更易于调试](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md)。

|在 Visual Studio 集成开发环境中设置-调试|
|---|
|1. 在**解决方案资源管理器**中选择一个项目后，在 "**项目**" 菜单上单击 "**属性**"。 <br />2. 单击 "**编译**" 选项卡。<br />3. 单击 "**高级编译选项**"。<br />4. 修改 "**生成调试信息**" 框中的值。|

## <a name="example"></a>示例

下面的示例将调试信息放在 `App.exe` 输出文件中。

```console
vbc -debug -out:app.exe test.vb
```

## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
