---
title: -subsystemversion
ms.date: 03/13/2018
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
ms.openlocfilehash: a977bc4cff822de551bf82d0f31707e9b2b6ea41
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348537"
---
# <a name="-subsystemversion-visual-basic"></a>-subsystemversion (Visual Basic)

指定可以运行生成的可执行文件的子系统的最低版本，以此确定可以运行该可执行文件的 Windows 版本。 大多数情况下，此选项确保该可执行文件可以利用早期 Windows 版本中未提供的特定安全功能。

> [!NOTE]
> 若要指定子系统本身，请使用 [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 编译器选项。

## <a name="syntax"></a>语法

```vb
-subsystemversion:major.minor
```

## <a name="parameters"></a>参数

`major.minor`

所需的子系统最低版本，以主版本和次要版本之间使用点标记的方式表示。 例如，如果将此选项的值设置为 6.01，则可以指定应用程序不能在低于 Windows 7 的操作系统上运行（如本主题后面的表中所述）。 必须将 `major` 和 `minor` 的值指定为整数。

`minor` 版本中的前导零不会更改版本，但尾随零会。 例如，6.1 和 6.01 表示相同的版本，但 6.10 表示另一个版本。 建议次要版本用两位数表示，以免混淆。

## <a name="remarks"></a>备注

下表列出了常见的 Windows 子系统版本。

|Windows 版本|子系统版本|
|---------------------|-----------------------|
|Windows 2000|5.00|
|Windows XP|5.01|
|Windows Server 2003|5.02|
|Windows Vista|6.00|
|Windows 7|6.01|
|Windows Server 2008|6.01|
|[!INCLUDE[win8](~/includes/win8-md.md)]|6.02|

## <a name="default-values"></a>默认值

-subsystemversion 编译器选项的默认值取决于以下列表中的条件：

- 只要设置了以下列表中的任意编译器选项，则默认值为 6.02：

  - [/target:appcontainerexe](../../../visual-basic/reference/command-line-compiler/target.md)

  - [/target:winmdobj](../../../visual-basic/reference/command-line-compiler/target.md)

  - [-platform:arm](../../../visual-basic/reference/command-line-compiler/platform.md)

- 如果使用 MSBuild，面向 .NET Framework 4.5，并且未设置先前在此列表中指定的任何编译器选项，则默认值为 6.00。

- 如果前面的条件均不符合，则默认值为 4.00。

## <a name="setting-this-option"></a>设置此选项

To set the **-subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML. 不能在 Visual Studio IDE 中设置此选项。 有关详细信息，请参阅本主题前面的“默认值”或[常用的 MSBuild 项目属性](/visualstudio/msbuild/common-msbuild-project-properties)。

## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)

- [MSBuild 属性](/visualstudio/msbuild/msbuild-properties)
