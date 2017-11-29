---
title: "导入声明：open 关键字 (F#)"
description: "了解有关 F # 导入声明和如何指定模块或命名空间可以无需使用完全限定的名称引用其元素。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1e98e48c-52e9-4314-8954-85d5583125f0
ms.openlocfilehash: a6d79bed3dd202657d06956edf9499a9b21a5f03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="import-declarations-the-open-keyword"></a>导入声明：`open`关键字

> [!NOTE]
本文中的 API 参考链接将转至 MSDN。  Docs.microsoft.com API 参考尚未完成。

*导入声明*指定模块或命名空间可以无需使用完全限定的名称引用其元素。


## <a name="syntax"></a>语法

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>备注
通过使用完全限定的命名空间或模块路径中引用代码每次可以创建很难写入、 读取和维护的代码。 相反，你可以使用`open`关键字经常使用的模块和命名空间，以便在引用该模块或命名空间的成员时，你可以使用名称的缩写形式，而不是完全限定的名称。 此关键字是类似于`using`关键字在 C# 中， `using namespace` Visual c + + 中和`Imports`在 Visual Basic 中。

模块或提供的命名空间必须是同一项目中或在引用的项目或程序集。 如果不是这样，你可以添加到项目中，引用或使用`-reference`命令`-`行选项 (或其缩写， `-r`)。 有关详细信息，请参阅[编译器选项](compiler-options.md)。

导入声明使这些名称在后面的声明，直至封闭命名空间、 模块或文件的末尾的代码中可用。

当使用多个导入声明时，它们应显示在单独的行。

下面的代码演示如何使用`open`关键字来简化代码。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

F # 编译器不发出错误或警告，当多义性出现时多个打开的模块或命名空间中出现相同的名称。 出现多义性时，F # 提供首选项设置为更最近打开的模块或命名空间。 例如，在下面的代码中，`empty`意味着`Seq.empty`，即使`empty`位于同时`List`和`Seq`模块。

```fsharp
open List
open Seq
printfn "%A" empty
```

因此，请注意当你打开模块或命名空间如`List`或`Seq`了包含具有相同的名称; 相反，请考虑使用限定的名称的成员。 应避免任何情况下，在其中的代码是依赖于导入声明的顺序。


## <a name="namespaces-that-are-open-by-default"></a>默认情况下打开的命名空间
一些命名空间相当频繁，因此无需显式导入声明它们也隐式打开的 F # 代码中使用。 下表显示默认情况下打开的命名空间。

|命名空间|描述|
|---------|-----------|
|`Microsoft.FSharp.Core`|包含基本 F # 类型的内置类型定义，例如`int`和`float`。|
|`Microsoft.FSharp.Core.Operators`|包含基本算术运算，例如`+`和`*`。|
|`Microsoft.FSharp.Collections`|包含不可变集合类，例如`List`和`Array`。|
|`Microsoft.FSharp.Control`|包含用于控制构造，如迟缓计算和异步工作流类型。|
|`Microsoft.FSharp.Text`|包含函数的格式化 IO，如`printf`函数。|

## <a name="autoopen-attribute"></a>AutoOpen 特性
你可以将应用`AutoOpen`特性的程序集，如果你想要引用的程序集时自动打开命名空间或模块。 你还可以应用`AutoOpen`属性设为要打开的父模块或命名空间时自动打开该模块的模块。 有关详细信息，请参阅[Core.AutoOpenAttribute 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)。


## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess 特性
可以指定某些模块、 记录或联合类型`RequireQualifiedAccess`属性。 在引用这些模块、 记录或联合中的元素时，你必须使用无论是否包括导入声明限定的名称。 如果你上使用此特性有策略地进行定义常用的类型使用的名称，帮助避免名称冲突，从而使代码更具弹性到库中的更改。 有关详细信息，请参阅[Core.RequireQualifiedAccessAttribute 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)。


## <a name="see-also"></a>另请参阅
[# 语言参考](index.md)

[命名空间](namespaces.md)

[模块](modules.md)

