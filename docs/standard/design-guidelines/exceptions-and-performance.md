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
一个常见的问题与异常相关，如果使用异常来进行定期失败的代码，实现的性能都是不可接受。 这是关注点。 当成员引发了异常时，其性能可以是数量级。 但是，就可以实现良好性能，同时严格符合不允许使用错误代码的异常指导原则。 在本部分中所述的两种模式建议执行此操作的方法。  
  
 **X DO NOT** 由于异常可能会对性能产生负面影响的问题，因此使用错误代码。  
  
 若要提高性能，则可以使用 Tester-doer 模式或重分析模式，接下来的两部分中所述。  
  
## <a name="tester-doer-pattern"></a>Tester-doer 模式  
 有时可以通过拆分为两个成员改进了引发异常的成员的性能。 让我们看看<xref:System.Collections.Generic.ICollection%601.Add%2A>方法的<xref:System.Collections.Generic.ICollection%601>接口。  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 该方法`Add`集合为只读时引发。 这可能是在方法调用的地方通常失败的情况下性能问题。 若要缓解此问题的方法之一是测试是否集合然后再尝试添加一个值是可写。  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 用于测试条件，它在我们的示例中为该属性的成员`IsReadOnly`，称为测试人员。 用于执行可能引发的操作，该成员`Add`方法在本示例中，被称为 doer。  
  
 **✓ CONSIDER** 可能会引发异常的成员 Tester-doer 模式在常见方案以避免性能问题与异常相关。  
  
## <a name="try-parse-pattern"></a>尝试分析模式  
 对于极高性能 Api，应使用更快的运行模式比上一节中所述的 Tester-doer 模式。 该模式需要调整要明确定义测试案例的成员语义的一部分的成员名称。 例如，<xref:System.DateTime>定义<xref:System.DateTime.Parse%2A>字符串的分析失败时引发异常的方法。 它还定义了相应<xref:System.DateTime.TryParse%2A>，将尝试进行分析，但如果方法返回 false 分析失败并返回成功分析使用结果`out`参数。  
  
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
  
 使用此模式时，务必在严格的术语定义的重试功能。 如果成员以外定义完善的重试由于任何原因失败，该成员必须仍会引发相应异常。  
  
 **✓ CONSIDER** 可能会引发异常的成员尝试分析模式在常见方案以避免性能问题与异常相关。  
  
 **✓ DO** 方法实现此模式中使用前缀"Try"和布尔值返回的类型。  
  
 **✓ DO** 每个成员使用 Try 分析模式提供的异常引发的成员。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)
