---
title: -refout （Visual Basic）
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 552e611f222bfcc3ce12520ecdb891fd7b8b21de
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775545"
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

引用程序集是一种特殊类型的程序集，该程序集只包含表示库的公共 API 图面所需的最少元数据量。 它们包括在生成工具中引用程序集时所有重要成员的声明，但不包括对其 API 协定没有明显影响的私有成员的所有成员实现和声明。 有关详细信息，请参阅 .NET 中的[引用程序集](../../../standard/assembly/reference-assemblies.md)指南。

`-refout` 和 [`-refonly`](refonly-compiler-option.md) 选项互斥。

## <a name="see-also"></a>请参阅

- [/refonly](refonly-compiler-option.md)
- [Visual Basic 命令行编译器](index.md)
- [示例编译命令行](sample-compilation-command-lines.md)
