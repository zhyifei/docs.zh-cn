---
title: 类型成员的名称
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
ms.openlocfilehash: 81c837bd045992043208a59f6ee16803c1d6eb3c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744177"
---
# <a name="names-of-type-members"></a>类型成员的名称
类型的成员包括：方法、属性、事件、构造函数和字段。 以下各部分介绍各类型成员的命名准则。

## <a name="names-of-methods"></a>方法的名称
 由于方法是操作执行的途径，所以设计准则要求方法名称是谓词或谓词短语。 通过遵循这一准则，还可将方法名称与属性和类型名称（即名词或形容词短语）区分开来。

 ✔️为谓词或谓词短语指定方法名称。

```csharp
public class String {
    public int CompareTo(...);
    public string[] Split(...);
    public string Trim();
}
```

## <a name="names-of-properties"></a>属性的名称
 与其他成员不同，属性名称须为名词短语或形容词。 这是因为属性引用数据，且属性名称反映了这一点。 应始终为属性名称使用 PascalCasing。

 ✔️使用名词、名词短语或形容词名称属性。

 ❌ 没有与 "Get" 方法的名称相匹配的属性，如以下示例中所示：

 `public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`

 此模式通常表明该属性实际上应是一种方法。

 ✔️使用一个复数短语来描述集合中的项，而不是使用后跟 "List" 或 "Collection" 的短语来命名集合属性。

 ✔️使用赞成短语（`CanSeek` 而不是 `CantSeek`）命名布尔属性。 或者，还可以在布尔属性前面添加 "Is"、"Can" 或 "has" 前缀，但前提是在它添加值的位置。

 ✔️考虑为属性提供与其类型相同的名称。

 例如，以下属性可正确获取和设置名为 `Color` 的枚举值，因此属性名为 `Color`：

```csharp
public enum Color {...}
public class Control {
    public Color Color { get {...} set {...} }
}
```

## <a name="names-of-events"></a>事件的名称
 事件始终是指某个操作，这个操作可能正在发生，也可能已经发生。 因此与方法一样，事件用谓词命名，谓词时态用于指示事件引发的时间。

 ✔️使用动词或动词短语来命名事件。

 示例包括`Clicked`、`Painting` 和 `DroppedDown`。

 ✔️使用现有的和过去的时态为事件名称提供前后的概念。

 例如，在窗口关闭前引发的关闭事件可命名为 `Closing`，而在窗口关闭后后引发的关闭事件可命名为 `Closed`。

 ❌ 不要使用 "Before" 或 "After" 前缀或 postfixes 来指示前和后事件。 应按前述使用现在时态和过去时态。

 ✔️使用 "EventHandler" 后缀来命名事件处理程序（用作事件类型的委托），如以下示例中所示：

 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`

 ✔️确实使用两个名为 `sender` 的参数，并在事件处理程序中 `e`。

 sender 参数表示引发事件的对象。 sender 参数的类型通常是 `object`，即使可以使用更具体的类型。

 ✔️用 "EventArgs" 后缀命名事件参数类。

## <a name="names-of-fields"></a>字段的名称
 字段命名准则适用于静态公共字段和受保护字段。 原则不涉及内部和专用字段，而[成员设计准则](../../../docs/standard/design-guidelines/member.md)不允许使用公开字段或受保护的实例字段。

 ✔️在字段名称中使用 PascalCasing。

 ✔️使用名词、名词短语或形容词来命名字段。

 ❌ 不使用字段名称前缀。

 例如，不要使用 "g_" 或 "s_" 来指示静态字段。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
- [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
