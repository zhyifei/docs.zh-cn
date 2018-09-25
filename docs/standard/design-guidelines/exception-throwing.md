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
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47077832"
---
# <a name="exception-throwing"></a>异常引发
在本部分中所述的异常引发指南要求很好的执行失败的含义的定义。 执行失败时发生此事件成员不能执行它已执行的操作 （的成员名称表示）。 例如，如果`OpenFile`方法不能返回到调用方的打开的文件句柄，它将被认为执行失败。  
  
 大多数开发人员已变得越来越熟悉使用除之类的用法错误由零或 null 引用异常。 在 Framework 中，异常用于所有错误条件，包括执行错误。  
  
 **X DO NOT** 返回错误代码。  
  
 例外情况是在框架中的错误报告的主要方式。  
  
 **✓ DO** 引发异常来报告执行失败数。  
  
 **✓ CONSIDER** 通过调用来终止进程`System.Environment.FailFast`（.NET Framework 2.0 功能） 而不是引发异常，如果你的代码遇到进一步执行不安全的情况。  
  
 **X DO NOT** 正常流控制，如有可能使用异常。  
  
 除系统故障和潜在的争用情况的操作，框架设计人员应设计 Api，以便用户可以编写代码，不会引发异常。 例如，可以提供一种方法，因此用户可以编写不会引发异常的代码在调用成员之前检查前置条件。  
  
 用于检查另一个成员的前置条件的成员通常称为测试人员，并调用 doer 实际执行该操作，该成员。  
  
 有些情况下 Tester-doer 模式可以具有不可接受的性能开销。 在这种情况下，应考虑所谓的重分析模式 (请参阅[异常和性能](../../../docs/standard/design-guidelines/exceptions-and-performance.md)有关详细信息)。  
  
 **✓ CONSIDER** 引发异常的性能影响。 Throw 速率大于每秒 100 会显著影响大多数应用程序的性能。  
  
 **✓ DO** 由于的成员冲突而引发的公开可调用的成员的所有异常协定 （而不是系统故障），并将它们视为协定的一部分的文档。  
  
 作为协定的一部分的异常应不从一个版本更改为下一步 （即，不应更改异常类型，和不应添加新的异常）。  
  
 **X DO NOT** 具有或不会引发的公共成员根据某些选项。  
  
 **X DO NOT** 具有作为返回值返回异常的公共成员或`out`参数。  
  
 返回从公共 Api 而不是抛出异常，无法实现的许多优势的基于异常的错误报告。  
  
 **✓ CONSIDER** 使用异常生成器方法。  
  
 它是通常会从不同位置引发同一异常。 若要避免代码膨胀，使用创建的异常并初始化其属性的帮助器方法。  
  
 此外，会引发异常的成员未获得内联。 移动生成器将 throw 语句可能会允许成员进行内联。  
  
 **X DO NOT** 异常筛选器块中引发异常。  
  
 当异常筛选器引发异常时，由 CLR，捕获的异常，该筛选器返回 false。 此行为是无法区分从筛选器执行并显式返回 false，因此很难进行调试。  
  
 **X AVOID** 显式引发 finally 块中的异常。 隐式引发的异常导致的调用引发的方法是可接受的。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)
