---
title: 外部函数
description: 了解如何F#在本机代码中调用函数的语言支持。
ms.date: 05/16/2016
ms.openlocfilehash: 73e38d8942bfc8ddb3c51d126d7678e84903326b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642048"
---
# <a name="external-functions"></a>外部函数

本主题介绍F#在本机代码中调用函数的语言支持。

## <a name="syntax"></a>语法

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>备注

在上述语法中，*自变量*表示参数提供给`System.Runtime.InteropServices.DllImportAttribute`属性。 第一个参数是一个字符串，表示包含此函数，不带.dll 扩展名的 DLL 的名称。 可以提供其他参数的公共属性的任何`System.Runtime.InteropServices.DllImportAttribute`类，如调用约定。

假设您有一个本机C++包含以下导出的函数的 DLL。

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

可以调用该函数从F#通过使用下面的代码。

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

与本机代码互操作性称为*平台调用*，并且是 CLR 的功能。 有关详细信息，请参阅[与非托管代码交互操作](../../../../docs/framework/interop/index.md)。 该部分中的信息是适用于F#。

## <a name="see-also"></a>请参阅

- [函数](index.md)
