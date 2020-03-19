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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401237"
---
# <a name="names-of-classes-structs-and-interfaces"></a>类、结构和接口的名称
以下命名准则适用于常规类型命名。

 ✔️使用 PascalCasing 命名类和带有名词或名词短语的结构。

 这将类型名称与用动词短语命名的方法区分开来。

 ✔️使用形容词短语，或偶尔使用名词或名词短语进行命名界面。

 名词和名词短语应很少使用，它们可能表示类型应为抽象类，而不是接口。

 ❌不要给类名前缀（例如，"C"）。

 ✔️考虑用基类的名称结束派生类的名称。

 这是非常可读的，并清楚地解释了这种关系。 代码中这方面的一些示例是： `ArgumentOutOfRangeException`，这是一种`Exception`，和`SerializableAttribute`，是 一`Attribute`种 。 但是，在适用本准则时，必须运用合理的判断;例如，`Button`类是一种`Control`事件，尽管`Control`未出现在其名称中。

 ✔️ DO 前缀接口名称与字母 I，以指示类型是接口。

 例如，（`IComponent`描述性名词）、（`ICustomAttributeProvider`名词短语）和`IPersistable`（形容词）是适当的接口名称。 与其他类型名称一样，请避免缩写。

 ✔️，在定义类接口对时，确保名称仅与接口名称上的"I"前缀不同，其中类是接口的标准实现。

## <a name="names-of-generic-type-parameters"></a>泛型类型参数的名称
 泛型已添加到 .NET 框架 2.0 中。 该功能引入了一种称为*类型参数*的标识符。

 ✔️ DO 名称泛型类型参数（带有描述性名称）除非单字母名称完全不言自明，并且描述性名称不会增加值。

 ✔️考虑使用`T`具有单字母类型参数的类型作为类型参数名称。

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 ✔️ DO 前缀描述性`T`类型参数名称。

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 ✔️考虑指示在参数名称中对类型参数放置的约束。

 例如，约束到`ISession`的参数可能称为`TSession`。

## <a name="names-of-common-types"></a>常见类型的名称
 ✔️命名派生自某些 .NET 框架类型或实现某些 .NET 框架类型时，请遵循下表中描述的准则。

|基类型|派生/实现类型指南|
|---------------|------------------------------------------|
|`System.Attribute`|✔️DO将后缀"属性"添加到自定义属性类的名称中。|
|`System.Delegate`|✔️DO将后缀"事件处理程序"添加到事件中使用的委托名称中。<br /><br /> ✔️将后缀"回调"添加到用作事件处理程序的委托名称以外的委托名称中。<br /><br /> ❌不要将后缀"委托"添加到委托。|
|`System.EventArgs`|✔️添加后缀"事件阿格"。|
|`System.Enum`|❌不要从此类派生;因此，请勿从此类派生。改用语言支持的关键字;例如，在 C# 中，`enum`使用 关键字。<br /><br /> ❌请勿添加后缀"枚举"或"标记"。|
|`System.Exception`|✔️添加后缀"异常"。|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|✔️添加后缀"字典"。 请注意，`IDictionary`这是特定类型的集合，但此准则优先于以下更常规的集合准则。|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|✔️添加后缀"集合"。|
|`System.IO.Stream`|✔️添加后缀"流"。|
|`CodeAccessPermission IPermission`|✔️添加后缀"权限"。|

## <a name="naming-enumerations"></a>命名枚举
 枚举类型（也称为枚举）的名称通常应遵循标准类型命名规则（PascalCasing 等）。 但是，还有其他特别适用于枚举的准则。

 ✔️DO使用单一类型名称进行枚举，除非其值为位字段。

 ✔️DO使用复数类型名称进行枚举，其中位字段为值，也称为标志枚举。

 ❌请勿在枚举类型名称中使用"枚举"后缀。

 ❌请勿在枚举类型名称中使用"标记"或"标记"后缀。

 ❌请勿在枚举值名称上使用前缀（例如，ADO 枚举的"ad"，富文本枚举的"rtf"等）。

 *部分© 2005， 2009 微软公司.保留所有权利。*

 *经 Pearson 教育公司许可，从[框架设计指南：可重用的约定、习语和模式 .NET 库重新打印，第二版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)由 Krzysztof Cwalina 和 Brad Abrams 出版，由艾迪森-韦斯利专业公司作为微软 Windows 开发系列的一部分于 2008 年 10 月 22 日出版。*

## <a name="see-also"></a>另请参阅

- [框架设计准则](../../../docs/standard/design-guidelines/index.md)
- [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
