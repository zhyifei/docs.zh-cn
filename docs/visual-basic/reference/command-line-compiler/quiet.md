---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: a22773e2e37eb60ab6f1e88305266f41764311e7
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612584"
---
# <a name="-quiet"></a>-quiet

阻止编译器显示与语法相关的错误和警告的代码。

## <a name="syntax"></a>语法

```
-quiet
```

## <a name="remarks"></a>备注

默认情况，`-quiet` 是无效的。 当编译器报告相关的语法错误或警告时，它还将输出从源代码行。 对于分析编译器输出的应用程序，它可能会更方便的编译器输出的诊断的文本。

在以下示例中，`Module1`输出的错误包括源代码，而无需在编译时`-quiet`。

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

输出：

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

使用编译`-quiet`，编译器只输出如下：

```
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> `-quiet`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。

## <a name="example"></a>示例

下面的代码编译`T2.vb`，不会显示相关的语法的编译器诊断的代码：

```
vbc -quiet t2.vb
```

## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
