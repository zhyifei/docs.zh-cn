---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21cea76f31bdf2ac5fcf434ee759f874f917617b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653528"
---
# <a name="-refout-visual-basic"></a>-refout (Visual Basic)

-refout 选项指定应输出引用程序集的文件路径。

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>语法

```console
-refout:filepath
```

## <a name="arguments"></a>自变量

 `filepath` 路径和文件名引用程序集。 它通常应主程序集的子文件夹中。 推荐约定（MSBuild 采用）是，将引用程序集放入与主程序集相关的“ref/”子文件夹中。 中的所有文件夹`filepath`必须存在; 编译器不会创建它们。 

## <a name="remarks"></a>备注

Visual Basic 支持`-refout`切换从版本 15.3 开始。

引用程序集是包含元数据，但没有实现代码的仅包含元数据的程序集。 它们包括用于匿名类型以外的所有内容的类型和成员信息。 它们的方法体替换为单个`throw null`语句。 使用的原因`throw null`方法体 （而不是没有正文），以便 PEVerify 可以运行和传递 （因此验证元数据的完整性）。

引用程序集包括程序集级别[ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute)属性。 可以在源中指定此属性（之后编译器就不需要进行合成）。 由于此属性，运行时无法加载执行的引用程序集 （但仍可以在仅限反射上下文中加载它们）。 在程序集反映的工具需要确保它们的加载为仅限反射的; 的引用程序集否则，运行时会引发<xref:System.BadImageFormatException>。

`-refout` 和 [`-refonly`](refonly-compiler-option.md) 选项互斥。

## <a name="see-also"></a>请参阅
[-refonly](refonly-compiler-option.md)   
[Visual Basic 命令行编译器](index.md)  
[示例编译命令行](sample-compilation-command-lines.md)  

