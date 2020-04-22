---
title: 导入声明：open 关键字
description: 了解 F# 导入声明及其如何指定模块或命名空间，这些模块或命名空间的元素无需使用完全限定的名称即可引用。
ms.date: 04/04/2019
ms.openlocfilehash: 0baef27c7dc3181b9da0defb1c793fec04269c09
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021540"
---
# <a name="import-declarations-the-open-keyword"></a>导入声明：`open` 关键字

> [!NOTE]
> 本文中的 API 参考链接将转至 MSDN。  Docs.microsoft.com API 参考尚未完成。

*导入声明*指定一个模块或命名空间，这些模块或命名空间的元素无需使用完全限定的名称即可引用。

## <a name="syntax"></a>语法

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>备注

每次使用完全限定的命名空间或模块路径引用代码可以创建难以编写、读取和维护的代码。 相反，`open`您可以将 关键字用于常用的模块和命名空间，以便在引用该模块或命名空间的成员时，可以使用名称的简短形式而不是完全限定的名称。 此关键字类似于 C#`using`中的关键字、Visual `using namespace` C++ 和`Imports`Visual Basic 中的关键字。

提供的模块或命名空间必须位于同一项目或引用的项目或程序集中。 如果不是，则可以添加对项目的引用，或使用`-reference`命令行选项（或其缩写。 `-r` 有关详细信息，请参阅[编译器选项](compiler-options.md)。

导入声明使声明后面的代码中的名称可用，最多到封闭命名空间、模块或文件的结尾。

使用多个导入声明时，它们应显示在单独的行上。

以下代码显示了`open`关键字用于简化代码的使用。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

当多个打开的模块或命名空间中出现相同名称时，F# 编译器不会发出错误或警告。 当出现模棱两可时，F# 优先考虑最近打开的模块或命名空间。 例如，在以下代码中，`empty`表示`Seq.empty`，即使`empty`位于 和`List``Seq`模块中也是如此。

```fsharp
open List
open Seq
printfn "%A" empty
```

因此，在打开模块或命名空间（如`List`或`Seq`包含具有相同名称的成员）时要小心;相反，请考虑使用限定名称。 应避免代码依赖于导入声明的顺序的任何情况。

## <a name="namespaces-that-are-open-by-default"></a>默认情况下打开的命名空间

某些命名空间在 F# 代码中非常频繁，因此无需显式导入声明即可隐式打开。 下表显示了默认情况下打开的命名空间。

|命名空间|说明|
|---------|-----------|
|`Microsoft.FSharp.Core`|包含内置类型（如 和`int``float`） 的基本 F# 类型定义。|
|`Microsoft.FSharp.Core.Operators`|包含基本算术运算，如`+``*`和 。|
|`Microsoft.FSharp.Collections`|包含不可变的集合类，`List`如 和`Array`。|
|`Microsoft.FSharp.Control`|包含控件构造的类型，如惰性评估和异步工作流。|
|`Microsoft.FSharp.Text`|包含格式化 IO 的功能，`printf`如函数。|

## <a name="autoopen-attribute"></a>自动打开属性

如果要在引用程序集`AutoOpen`时自动打开命名空间或模块，则可以将该属性应用于程序集。 您还可以将`AutoOpen`该属性应用于模块，以在打开父模块或命名空间时自动打开该模块。 有关详细信息，请参阅[Core.AutoOpenattribute 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)。

## <a name="requirequalifiedaccess-attribute"></a>需要限定访问属性

某些模块、记录或联合类型可以指定该`RequireQualifiedAccess`属性。 引用这些模块、记录或联合的元素时，无论是否包含导入声明，都必须使用限定名称。 如果在定义常用名称的类型上战略性地使用此属性，则有助于避免名称冲突，从而使代码对库中的更改更具弹性。 有关详细信息，请参阅[Core.要求限定Access属性类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [命名空间](namespaces.md)
- [模块](modules.md)
