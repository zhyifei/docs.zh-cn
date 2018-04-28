---
title: 入口点 (F#)
description: '了解如何设置为正式开始执行的可执行文件作为编译的 F # 程序的入口点。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 42e5fe7f85285f990ef92e9791ed5bdfacb85059
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="entry-point"></a>入口点

本主题介绍用于将入口点设置为 F # 程序的方法。


## <a name="syntax"></a>语法

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>备注
在上述语法中，*让函数绑定*是中的函数的定义`let`绑定。

可执行文件正式开始执行时编译的程序入口点。 通过应用指定的 F # 应用程序的入口点`EntryPoint`属性设为程序的`main`函数。 此函数 (通过创建`let`绑定) 必须是最后一个已编译文件中的最后一个函数。 最后编译的文件是项目中的最后一个文件或传递给命令行的最后一个文件。

入口点函数具有类型`string array -> int`。 在命令行上提供的自变量传递给`main`的字符串数组中的函数。 数组的第一个元素是第一个自变量;可执行文件的名称未包含在数组中，因为它是在某些其他语言中。 返回值用作进程的退出代码。 零通常指示成功;非零值指示错误。 没有特定的含义的返回代码则为非 0; 约定返回代码的意义进行了特定于应用程序。

下面的示例演示一个简单`main`函数。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

使用命令行执行此代码时`EntryPoint.exe 1 2 3`，输出如下所示。

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>隐式的入口点
当程序不具有**入口点**显式指示入口点，最后一个文件中的顶级绑定要编译的属性用作入口点。


## <a name="see-also"></a>请参阅
[函数](index.md)

[let 绑定](let-bindings.md)
