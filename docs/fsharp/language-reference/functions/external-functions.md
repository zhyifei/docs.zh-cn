---
title: 外部函数 (F#)
description: 了解如何对在本机代码中调用函数的 F# 语言支持。
ms.date: 05/16/2016
ms.openlocfilehash: db0d3362d867b07b333951f3380c6735ff471d5e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "45973100"
---
# <a name="external-functions"></a>外部函数

本主题介绍对在本机代码中调用函数的 F# 语言支持。

## <a name="syntax"></a>语法

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>备注

在上述语法中，*自变量*表示参数提供给`System.Runtime.InteropServices.DllImportAttribute`属性。 第一个参数是一个字符串，表示包含此函数，不带.dll 扩展名的 DLL 的名称。 可以提供其他参数的公共属性的任何`System.Runtime.InteropServices.DllImportAttribute`类，如调用约定。

假设您有一个本机 c + + DLL，其中包含以下导出的函数。

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

可以使用以下代码从 F# 中调用此函数。

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

与本机代码互操作性称为*平台调用*，并且是 CLR 的功能。 有关详细信息，请参阅[与非托管代码交互操作](../../../../docs/framework/interop/index.md)。 该部分中的信息也适用于 F#。

## <a name="see-also"></a>请参阅

- [函数](index.md)
