---
title: 导入声明：open 关键字
description: 了解F#导入声明以及如何指定可在不使用完全限定名称的情况下引用其元素的模块或命名空间。
ms.date: 04/04/2019
ms.openlocfilehash: 816bac551692c3397290f64c6267ee22e4ce90fb
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630571"
---
# <a name="import-declarations-the-open-keyword"></a>导入声明：`open` 关键字

> [!NOTE]
> 本文中的 API 参考链接将转至 MSDN。  Docs.microsoft.com API 参考尚未完成。

*导入声明*指定了一个模块或命名空间, 在不使用完全限定名称的情况下, 可以引用这些元素。

## <a name="syntax"></a>语法

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>备注

每次使用完全限定的命名空间或模块路径引用代码都可以创建难以编写、读取和维护的代码。 相反, 可以`open`将关键字用于经常使用的模块和命名空间, 以便在引用该模块或命名空间的成员时, 可以使用名称的缩写, 而不是完全限定的名称。 此关键字与中的关键字`using`类似C#, 如`using namespace` Visual Basic 中C++ `Imports`所示。

提供的模块或命名空间必须位于同一项目或引用的项目或程序集中。 如果不是, 则可以添加对项目的引用, 也可以使用`-reference`命令`-`行选项`-r`(或其缩写形式)。 有关详细信息，请参阅[编译器选项](compiler-options.md)。

导入声明会使名称位于声明后的代码中, 直到封闭命名空间、模块或文件的结尾。

当使用多个导入声明时, 它们应该出现在单独的行上。

下面的代码演示如何使用`open`关键字来简化代码。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

如果F#在多个打开的模块或命名空间中出现多义性, 则编译器不会发出错误或警告。 出现歧义时, F#将优先于最近打开的模块或命名空间。 例如, 在下面的代码中, `empty` `empty`是`Seq.empty`指, 即使同时`List`位于和`Seq`模块中。

```fsharp
open List
open Seq
printfn "%A" empty
```

因此, 当您打开包含具有相同名称的成员的`List`模块`Seq`或命名空间 (如或) 时, 请务必小心; 相反, 请考虑使用限定名。 应避免代码依赖于导入声明顺序的任何情况。

## <a name="namespaces-that-are-open-by-default"></a>默认情况下打开的命名空间

有些命名空间非常频繁地在F#代码中使用, 而无需显式导入声明。 下表显示了默认情况下处于打开状态的命名空间。

|命名空间|描述|
|---------|-----------|
|`Microsoft.FSharp.Core`|包含内置F#类型`int`的基本类型定义, 例如和`float`。|
|`Microsoft.FSharp.Core.Operators`|包含基本算术运算`+` , 例如和。 `*`|
|`Microsoft.FSharp.Collections`|包含不可变的集合类`List` , `Array`如和。|
|`Microsoft.FSharp.Control`|包含控件构造的类型, 例如迟缓计算和异步工作流。|
|`Microsoft.FSharp.Text`|包含格式化 IO 的函数, 例如`printf`函数。|

## <a name="autoopen-attribute"></a>AutoOpen 特性

如果要在引用`AutoOpen`程序集时自动打开命名空间或模块, 则可以将该特性应用于程序集。 您还可以将`AutoOpen`属性应用于模块, 以便在打开父模块或命名空间时自动打开该模块。 有关详细信息, 请参阅[AutoOpenAttribute 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)。

## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess 特性

某些模块、记录或联合类型可以指定`RequireQualifiedAccess`属性。 引用这些模块、记录或联合的元素时, 必须使用限定名称, 而不管是否包含导入声明。 如果在定义常用名称的类型上策略性地使用此属性, 则有助于避免名称冲突, 从而使代码更能更灵活地应对库中的更改。 有关详细信息, 请参阅[RequireQualifiedAccessAttribute 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [命名空间](namespaces.md)
- [模块](modules.md)
