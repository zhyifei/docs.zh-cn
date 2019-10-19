---
title: -refout （Visual Basic）
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: c11d83ff37da41faa3dc6b66a87e2c52c5f6c7ac
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582875"
---
# <a name="-refout-visual-basic"></a>-refout （Visual Basic）

-refout 选项指定应输出引用程序集的文件路径。

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>语法

```console
-refout:filepath
```

## <a name="arguments"></a>自变量

`filepath`  
引用程序集的路径和文件名。 它通常应位于主要程序集的子文件夹中。 推荐约定（MSBuild 采用）是，将引用程序集放入与主程序集相关的“ref/”子文件夹中。 @No__t_0 中的所有文件夹都必须存在，编译器不会创建它们。

## <a name="remarks"></a>备注

从15.3 版开始 Visual Basic 支持 `-refout` 开关。

引用程序集是仅包含元数据的元数据程序集，但没有实现代码。 它们包括匿名类型之外的所有内容的类型和成员信息。 使用单个 `throw null` 语句替换其方法体。 使用 `throw null` 方法主体（而不是主体）的原因是，Peverify.exe 可以运行并通过（从而验证元数据的完整性）。

引用程序集包括程序集级别的[ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute)特性。 可以在源中指定此属性（之后编译器就不需要进行合成）。 由于此属性，运行时将拒绝加载引用程序集以便执行（但仍可以在只反射上下文中加载它们）。 反射程序集的工具需要确保它们将引用程序集作为仅反射加载;否则，运行时会引发 <xref:System.BadImageFormatException>。

`-refout` 和 [`-refonly`](refonly-compiler-option.md) 选项互斥。

## <a name="see-also"></a>请参阅

- [/refonly](refonly-compiler-option.md)
- [Visual Basic 命令行编译器](index.md)
- [示例编译命令行](sample-compilation-command-lines.md)
