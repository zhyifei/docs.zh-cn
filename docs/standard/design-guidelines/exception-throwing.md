---
title: 异常引发
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fbbe84811e3fa096b9e13c459143311bb75a198
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397902"
---
# <a name="exception-throwing"></a>异常抛出
本部分中描述的异常抛出准则要求对执行失败的含义进行明确定义。只要成员无法执行其设计要执行的操作（由成员名称表示的），就会发生执行失败。 例如，如果 `OpenFile` 方法无法将打开的文件句柄返回给调用者，则会将其视为执行失败。
 
大多数开发人员已经习惯使用异常来处理使用错误，例如除零或空引用。在框架中，异常用于所有错误条件，包括执行错误。
  
**X 不要** 返回错误代码。  
  
异常是框架中报告错误的主要方式。 
  
**✓ 务必** 通过抛出异常来报告执行失败。  
  
**✓ 考虑** 在遇到代码进一步执行不安全的情况下，通过调用 `System.Environment.FailFast` （.NET Framework 2.0 的功能）来终止进程，而不是抛出异常。
  
**X 不要** 为正常的控制流使用异常，如有可能的话。

除了系统故障和具有潜在竞争条件的操作之外，框架设计者应该设计API，以便用户可以编写不会抛出异常的代码。例如，您可以提供在调用成员之前检查前提条件的方法，以便用户可以编写不会抛出异常的代码。

用于检查另一个成员的前提条件的成员通常被称为 tester（测试者），实际执行该工作的成员称为 doer（实施者）。  

有些情况下，Tester-Doer 模式可能会产生不可接受的性能开销。在这种情况下，应考虑所谓的 Try-Parse 模式（有关更多信息，请参阅[异常和性能](../../../docs/standard/design-guidelines/exceptions-and-performance.md)）。

**✓ 考虑** 抛出异常的性能影响。每秒100次以上的抛出率可能会显著影响大多数应用程序的性能。
  
**✓ 务必** 记录由于违反成员协定（而不是系统故障）而被公开调用的成员抛出的所有异常，并将其视为协定的一部分。
  
作为协定的一部分的异常在一个版本到下一个版本中不应更改（即，不应更改异常类型，并且不应添加新的异常）。

**X 不要** 有基于某种选项可以抛出或不抛出异常的公共成员。
  
**X 不要** 有将异常作为返回值或 `out` 参数的公共成员。
  
从公共 API 返回异常而不是抛出它们会破坏基于异常的错误报告的优势。
  
**✓ 考虑** 使用异常生成器方法。

从不同位置抛出相同的异常是很常见的。为避免代码膨胀，请使用创建异常并初始化其属性的辅助方法。

此外，抛出异常的成员不会被内联。将抛出语句移动到生成器内可能会允许成员内联。
  
**X 不要** 从异常过滤器块中抛出异常。

当异常过滤器引发异常时，CLR 会捕获该异常，该过滤器会返回 false。此行为与执行并明确返回 false 的过滤器无法区分，因此很难进行调试。
  
**X AVOID** 避免显式抛出 finally 块中的异常。调用抛出的方法导致的隐式抛出异常是可以接受的。
  
*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*
  
*经 Pearson Education, Inc 授权，转载自《框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版》(https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)
