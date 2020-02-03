---
title: 引发异常
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: 18927d242c2ed957d2bc9f8b481beeed775a4e4e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741676"
---
# <a name="exception-throwing"></a>引发异常
本部分介绍的异常引发准则要求对执行失败的含义进行明确定义。 只要成员无法执行其指定操作（成员名称所体现的含义），就会导致执行失败。 例如，如果 `OpenFile` 方法无法向调用方返回打开的文件句柄，则会将其视为执行失败。

 大多数开发人员已经习惯使用异常来处理用法错误，例如除零或空引用。 在框架中，异常用于所有错误情况，包括执行错误。

 ❌ 不返回错误代码。

 异常是框架中报告错误的主要方式。

 ✔️通过引发异常来报告执行失败。

 ✔️考虑通过调用 `System.Environment.FailFast` （.NET Framework 2.0 功能）终止进程，而不是在代码遇到不安全的情况下引发异常，以便进一步执行。

 如果可能，❌ 不会对正常控制流使用异常。

 除系统故障和存在潜在争用条件的操作这两种情况外，框架设计者应设计 API，以便用户可以编写不会引发异常的代码。 例如，可以提供在调用成员之前检查前提条件的方法，以便用户可以编写不会引发异常的代码。

 用于检查另一个成员的前提条件的成员通常被称为 tester（测试者），实际执行该工作的成员称为 doer（实施者）。

 有些情况下，Tester-Doer 模式可能会产生不可接受的性能开销。 在这种情况下，应考虑所谓的试用分析模式（有关详细信息，请参阅[异常和性能](../../../docs/standard/design-guidelines/exceptions-and-performance.md)）。

 ✔️考虑引发异常的性能影响。 每秒以上100的引发率可能会显著影响大多数应用程序的性能。

 ✔️会记录公共可调用成员引发的所有异常，因为违反了成员协定（而不是系统失败），并将它们视为协定的一部分。

 作为协定一部分的异常在协定的不同版本中应保持一致（即，不应更改异常类型，并且不应添加新的异常）。

 ❌ 没有可以引发或不基于某个选项的公共成员。

 ❌ 没有将异常作为返回值或 `out` 参数返回的公共成员。

 如果选择从公共 API 返回异常而不是引发它们，会丧失基于异常的错误报告的优势。

 ✔️考虑使用异常生成器方法。

 从不同位置引发相同的异常是很常见的。 为避免代码膨胀，请使用可创建异常并初始化其属性的辅助方法。

 此外，引发异常的成员不会被内联。 或可通过将引发语句移动到生成器内来实现成员内联。

 ❌ 不会从异常筛选器块中引发异常。

 当异常筛选器引发异常时，CLR 会捕获该异常，筛选器会返回 false。 此行为与执行并显式返回 false 的过滤器行为无法区分，因此很难进行调试。

 ❌ 避免从 finally 块显式引发异常。 调用引发的方法可接受隐式引发的异常。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
- [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)
