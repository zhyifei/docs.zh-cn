---
title: 异常和性能
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d664b7b61394bd9bfe6d0abd7130f9f0191e7a03
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083541"
---
# <a name="exceptions-and-performance"></a>异常和性能
与异常相关的一个常见问题是，如果异常用于经常会失败的代码，则实现的性能将是不可接受的。这确实是一个问题。当成员抛出异常时，其性能可能会慢几个数量级。但是，在严格遵守禁止使用错误代码的异常准则的同时，也可以实现良好的性能。本部分中描述了两种建议的模式。
  
**X 不要** 因为担心异常可能会对性能产生负面影响而使用错误代码。
  
为了提高性能，可以使用 Tester-Doer 模式或 Try-Parse 模式，如下两节所述。
  
## <a name="tester-doer-pattern"></a>Tester-Doer 模式  
有时，通过将成员分成两部分，可以改善抛出异常成员的性能。让我们看看 <xref:System.Collections.Generic.ICollection%601>接口的<xref:System.Collections.Generic.ICollection%601.Add%2A>方法。
  
```
ICollection<int> numbers = ...
numbers.Add(1);  
```
  
如果集合是只读的，则 `Add` 方法会抛出异常。在预期的方法调用经常失败的情况下，这可能是一个性能问题。优化此问题的方法之一是在尝试添加值之前测试集合是否可写。
  
```
ICollection<int> numbers = ...
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```
  
用于测试条件的成员（在我们的示例中是属性 `IsReadOnly` ）被称为 tester。用于执行潜在抛出操作的成员（在我们的示例中为 `Add` 方法）称为doer。
  
**✓ 考虑** 为可能在常见场景中抛出异常的成员使用 Tester-Doer 模式，以避免与异常相关的性能问题。
  
## <a name="try-parse-pattern"></a>Try-Parse 模式
对于性能极其敏感的 API，应使用比上一节中描述的 Tester-Doer 模式更快的模式。该模式要求调整成员名称，以使明确定义的测试用例成为成员语义的一部分。例如，<xref:System.DateTime> 定义了一个 <xref:System.DateTime.Parse%2A> 方法，如果解析字符串失败，则抛出异常。它还定义了一个相应的尝试解析的 <xref:System.DateTime.TryParse%2A> 方法，如果解析不成功则返回 false，并使用 `out` 参数返回成功解析的结果。
  
```
public struct DateTime {  
    public static DateTime Parse(string dateTime){
        ...
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```
  
使用此模式时，严格定义 try 功能非常重要。如果成员在很明确的尝试之外，因为其他原因而失败，则该成员仍必须抛出相应的异常。
  
**✓ 考虑** 为在常见场景中可能抛出异常的成员使用 Try-Parse 模式，以避免与异常相关的性能问题。
  
**✓ 务必** 为实现此模式的方法使用前缀 “Try” 和返回布尔值类型。
  
**✓ 务必** 为每个使用 Try-Parse 模式的成员提供一个异常抛出成员。
  
*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*
  
*经 Pearson Education, Inc 授权，转载自《框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版》(https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)
