---
title: -refonly （Visual Basic）
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 8e64989ac1410b51991027ffcb33e8dae0c0284b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775569"
---
# <a name="-refonly-visual-basic"></a>-refonly （Visual Basic）

**-Refonly**选项指示编译的主输出应为引用程序集，而不是实现程序集。 `-refonly` 参数以无提示方式禁用输出 PDB，因为无法执行引用程序集。

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>语法

```console
-refonly
```

## <a name="remarks"></a>备注

从15.3 版开始 Visual Basic 支持 `-refonly` 开关。

引用程序集是一种特殊类型的程序集，该程序集只包含表示库的公共 API 图面所需的最少元数据量。 它们包括在生成工具中引用程序集时所有重要成员的声明，但不包括对其 API 协定没有明显影响的私有成员的所有成员实现和声明。 有关详细信息，请参阅 .NET 中的[引用程序集](../../../standard/assembly/reference-assemblies.md)指南。

`-refonly` 和 [`-refout`](refout-compiler-option.md) 选项互斥。

## <a name="see-also"></a>请参阅

- [/refout](refout-compiler-option.md)
- [Visual Basic 命令行编译器](index.md)
- [示例编译命令行](sample-compilation-command-lines.md)
