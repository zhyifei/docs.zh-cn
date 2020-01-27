---
title: 형식 멤버의 이름
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
# <a name="names-of-type-members"></a>형식 멤버의 이름
형식은 메서드, 속성, 이벤트, 생성자 및 필드 등의 멤버로 이루어집니다. 다음 섹션에서는 형식 멤버 이름 지정에 대한 지침을 설명합니다.

## <a name="names-of-methods"></a>메서드 이름
 메서드가 작업을 수행하는 수단이기 때문에 디자인 지침에서는 메서드 이름이 동사 또는 동사구여야 합니다. 또한 이 지침을 따르면 명사 또는 형용사구인 속성 및 형식 이름과 메서드 이름을 구분할 수 있습니다.

 ✔️为谓词或谓词短语指定方法名称。

```csharp
public class String {
    public int CompareTo(...);
    public string[] Split(...);
    public string Trim();
}
```

## <a name="names-of-properties"></a>속성 이름
 다른 멤버와 달리 속성은 명사구 또는 형용사 이름이 지정되어야 합니다. 속성이 데이터를 나타내기 때문에 속성 이름은 이를 반영해야 합니다. PascalCasing은 속성 이름에 항상 사용됩니다.

 ✔️使用名词、名词短语或形容词名称属性。

 ❌ 没有与 "Get" 方法的名称相匹配的属性，如以下示例中所示：

 `public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`

 이 패턴은 일반적으로 속성이 실제로 메서드임을 나타냅니다.

 ✔️使用一个复数短语来描述集合中的项，而不是使用后跟 "List" 或 "Collection" 的短语来命名集合属性。

 ✔️使用赞成短语（`CanSeek` 而不是 `CantSeek`）命名布尔属性。 或者，还可以在布尔属性前面添加 "Is"、"Can" 或 "has" 前缀，但前提是在它添加值的位置。

 ✔️考虑为属性提供与其类型相同的名称。

 예를 들어, 다음 속성은 현재 올바르게 `Color`라는 열거형 값을 설정하므로 속성 이름은 `Color`입니다.

```csharp
public enum Color {...}
public class Control {
    public Color Color { get {...} set {...} }
}
```

## <a name="names-of-events"></a>이벤트 이름
 이벤트는 발생 중인 작업 또는 발생한 작업 중 하나를 가리킵니다. 따라서 메서드와 마찬가지로 이벤트는 동사를 사용하여 명명하고 동사 시제는 이벤트가 발생할 시간을 나타내는 데 사용됩니다.

 ✔️使用动词或动词短语来命名事件。

 예를 들면 `Clicked`, `Painting`, `DroppedDown` 등입니다.

 ✔️使用现有的和过去的时态为事件名称提供前后的概念。

 예를 들어 창이 닫히기 전에 발생하는 닫기 이벤트는 `Closing`이라고 하고 창이 닫힌 후에 발생하는 닫기 이벤트는 `Closed`라고 합니다.

 ❌ 不要使用 "Before" 或 "After" 前缀或 postfixes 来指示前和后事件。 위에서 설명한 대로 현재 및 과거 시제를 사용합니다.

 ✔️使用 "EventHandler" 后缀来命名事件处理程序（用作事件类型的委托），如以下示例中所示：

 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`

 ✔️确实使用两个名为 `sender` 的参数，并在事件处理程序中 `e`。

 보낸 사람 매개 변수는 이벤트를 발생시킨 개체를 나타냅니다. 보낸 사람 매개 변수는 보다 구체적인 형식을 적용할 수 있더라도 일반적으로 `object` 형식입니다.

 ✔️用 "EventArgs" 后缀命名事件参数类。

## <a name="names-of-fields"></a>필드 이름
 필드 명명 지침은 공용 및 보호된 고정 필드에 적용됩니다. 내부 및 개인 필드는 지침에서 다루지 않고 공용 또는 보호된 인스턴스 필드는 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)에서 허용하지 않습니다.

 ✔️在字段名称中使用 PascalCasing。

 ✔️使用名词、名词短语或形容词来命名字段。

 ❌ 不使用字段名称前缀。

 예를 들어 "g_" 또는 "s_"를 사용하여 고정 필드를 나타내지 마십시오.

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>另请参阅

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
