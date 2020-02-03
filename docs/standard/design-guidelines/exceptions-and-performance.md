---
title: 异常和性能
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: afa4e748599781a5979823320d8913ff5357d415
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741642"
---
# <a name="exceptions-and-performance"></a>异常和性能
一个常见的与异常相关的问题是，如果异常用于通常会失败的代码，则实现的性能将变得不可接受。 这确实是一个问题。 当成员引发异常时，其性能可能会慢几个数量级。 但是，在严格遵守禁止使用错误代码的异常准则的同时，仍可能实现良好的性能。 本部分中描述了两种建议的模式。

 ❌ 不使用错误代码，原因是异常可能会对性能产生负面影响。

 为了提高性能，可以使用 Tester-Doer 模式或 Try-Parse 模式，如以下两部分所述。

## <a name="tester-doer-pattern"></a>Tester-Doer 模式
 有时，通过将成员分成两部分，可以改善异常引发成员的性能。 让我们看看 <xref:System.Collections.Generic.ICollection%601> 接口的 <xref:System.Collections.Generic.ICollection%601.Add%2A> 方法。

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 如果集合是只读的，则方法 `Add` 引发。 在通常预期方法调用会失败的情况下，这可能会导致性能问题。 优化此问题的方法之一是在尝试添加值之前测试集合是否可写。

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 用于测试条件的成员（在我们的示例中为属性 `IsReadOnly`）称为 "测试人员"。 用于执行可能引发的操作的成员（本示例中的 `Add` 方法）称为 doer。

 ✔️考虑在常见方案中可能会引发异常的成员的 Doer 模式，以避免与异常相关的性能问题。

## <a name="try-parse-pattern"></a>Try-Parse 模式
 对于性能极其敏感的 API，应使用比上一部分中介绍的 Tester-Doer 模式更快的模式。 该模式要求调整成员名称，以使明确定义的测试用例成为成员语义的一部分。 例如，<xref:System.DateTime> 定义一个 <xref:System.DateTime.Parse%2A> 方法，当字符串的分析失败时，该方法将引发异常。 它还定义了一个相应的 <xref:System.DateTime.TryParse%2A> 方法，该方法尝试进行分析，但如果分析不成功，则返回 false，并返回使用 `out` 参数成功分析的结果。

```csharp
public struct DateTime
{
    public static DateTime Parse(string dateTime)
    {
        ...
    }
    public static bool TryParse(string dateTime, out DateTime result)
    {
        ...
    }
}
```

 使用此模式时，务必要严格定义 try 功能。 如果在已妥善定义 try 的情况下，成员仍因某个原因失败，则该成员仍必须引发相应异常。

 ✔️考虑在常见方案中可能会引发异常的成员的试验分析模式，以避免与异常相关的性能问题。

 ✔️对实现此模式的方法使用前缀 "Try" 和 Boolean 返回类型。

 ✔️使用 Try Parse 模式为每个成员提供异常引发成员。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
- [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)
