---
title: 类、结构和接口的名称
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: 2c528348c0e84037a80df9797c56f03b51c73adc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727785"
---
# <a name="names-of-classes-structs-and-interfaces"></a>类、结构和接口的名称
以下命名准则适用于常规类型命名。

 ✔️使用 PascalCasing 将类和结构命名为名词或名词短语。

 这将类型名称与使用谓词短语命名的方法区分开来。

 ✔️利用形容词短语或偶尔用名词或名词短语来命名接口。

 应少使用名词和名词短语，它们可能会指示类型为抽象类而非接口。

 ❌ 不要为类名称指定前缀（例如，"C"）。

 ✔️考虑用基类的名称结束派生类的名称。

 这样可让名称非常易读，并清楚体现了关系。 代码中的相关例子有：`ArgumentOutOfRangeException`，这是一种 `Exception`，还有 `SerializableAttribute`，这是一种 `Attribute`。 但是，在应用此准则时，务必应进行合理判断；例如，`Button` 类是一种 `Control` 事件，尽管其名称中并未出现 `Control`。

 ✔️使用字母 I 来为接口名称加上前缀，以指示该类型是接口。

 例如，`IComponent`（描述性名词），`ICustomAttributeProvider`（名词短语）和 `IPersistable`（形容词）是合适的接口名称。与其他类型名称一样，应避免使用缩略形式。 对于其他类型名称，请避免缩写形式。

 ✔️确保在定义类接口对（其中类是接口的标准实现）时，接口名称上的 "I" 前缀仅有不同的名称。

## <a name="names-of-generic-type-parameters"></a>泛型类型参数的名称
 .NET Framework 2.0 中增添了泛型。 此功能引入了一种称为*类型参数*的新标识符。

 ✔️使用描述性名称命名泛型类型参数，除非单个字母名称完全一目了然，并且描述性名称不会添加值。

 ✔️考虑使用 `T` 作为具有一个单字母类型参数的类型的类型参数名称。

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 ✔️用 `T`为描述性类型参数名称加上前缀。

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 ✔️考虑，指示对参数名称中的类型参数施加的约束。

 例如，被限制为 `ISession` 的参数可能名为 `TSession`。

## <a name="names-of-common-types"></a>常见类型的名称
 当命名类型派生自或实现某些 .NET Framework 类型时，✔️按照下表中所述的指导原则进行操作。

|Base Type|派生/实现类型准则|
|---------------|------------------------------------------|
|`System.Attribute`|✔️将后缀 "Attribute" 添加到自定义特性类的名称中。|
|`System.Delegate`|✔️将后缀 "EventHandler" 添加到在事件中使用的委托的名称。<br /><br /> ✔️将后缀 "Callback" 添加到作为事件处理程序使用的委托的名称。<br /><br /> ❌ 不要将后缀 "Delegate" 添加到委托。|
|`System.EventArgs`|✔️添加后缀 "EventArgs"。|
|`System.Enum`|❌ 不从此类派生;改为使用您的语言支持的关键字;例如，在中C#，请使用 `enum` 关键字。<br /><br /> ❌ 不要添加后缀 "Enum" 或 "标志"。|
|`System.Exception`|✔️添加后缀 "Exception"。|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|✔️添加后缀 "Dictionary"。 请注意，`IDictionary` 是一种特定类型的集合，但此准则优先于后面更宽泛的集合准则。|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|✔️添加后缀 "Collection"。|
|`System.IO.Stream`|✔️添加后缀 "Stream"。|
|`CodeAccessPermission IPermission`|✔️添加后缀 "权限"。|

## <a name="naming-enumerations"></a>命名枚举
 一般情况下，枚举类型（也称为枚举）的名称应遵循标准的类型命名规则（PascalCasing 等）。 但还有专用于枚举的其他准则。

 ✔️为枚举使用单数类型名称，除非其值为位域。

 ✔️对将位域作为值的枚举使用复数类型名称，也称为标志枚举。

 ❌ 不要在枚举类型名称中使用 "Enum" 后缀。

 ❌ 不要在枚举类型名称中使用 "Flags" 或 "Flags" 后缀。

 ❌ 不在枚举值名称（例如，用于 ADO 枚举的 "ad"、用于丰富文本枚举的 "rtf" 等）上使用前缀。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
- [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
