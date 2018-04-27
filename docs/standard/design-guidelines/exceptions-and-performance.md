---
title: 异常和性能
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7972cf7d63ee22e791d46046f30c9be467cc758e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="exceptions-and-performance"></a>异常和性能
与异常相关的一个常见问题是，如果使用异常来进行例行失败的代码，实现的性能将无法接受。 这是一个有效的问题。 在成员引发了异常，其性能可能会极大地速度较慢。 但是，很可能来实现良好性能时严格符合禁止使用错误代码的异常指导原则。 本节中所述的两种模式建议执行此操作的方法。  
  
 **X 不**由于异常可能会对性能产生负面影响的问题，因此使用错误代码。  
  
 若要提高性能，它是可以使用 Tester-doer 模式或尝试分析模式，接下来的两部分中所述。  
  
## <a name="tester-doer-pattern"></a>Tester-doer 模式  
 有时可通过成员拆分为两个改善性能的异常引发的成员。 让我们看一下<xref:System.Collections.Generic.ICollection%601.Add%2A>方法<xref:System.Collections.Generic.ICollection%601>接口。  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 该方法`Add`引发如果该集合为只读的。 这可能会在方法调用的地方通常失败的情况下造成性能问题。 一种以缓解问题的是测试集合是否是可写之前尝试添加一个值。  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 用于测试条件，它在我们的示例中为该属性的成员`IsReadOnly`，简称为测试人员。 用于执行可能引发的操作，该成员`Add`方法在本示例中，称为 doer。  
  
 **请考虑 ✓**可能会引发异常的成员 Tester-doer 模式在常见方案以避免性能问题与异常相关。  
  
## <a name="try-parse-pattern"></a>尝试分析模式  
 对于极性能敏感的 Api，应使用一种更快的运行模式，比上一节中所述的 Tester-doer 模式。 模式需要调整定义完善的测试案例成员语义的一部分的成员名称。 例如，<xref:System.DateTime>定义<xref:System.DateTime.Parse%2A>字符串的分析失败时引发异常的方法。 它还定义相应<xref:System.DateTime.TryParse%2A>，尝试进行分析，但如果方法返回 false 分析失败并返回成功分析使用结果`out`参数。  
  
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
  
 在使用此模式时，务必在术语中严格定义的重试功能。 如果成员的定义完善的重试任何原因失败，该成员必须仍会引发相应异常。  
  
 **请考虑 ✓**可能会引发异常的成员尝试分析模式在常见方案以避免性能问题与异常相关。  
  
 **✓ 执行**方法实现此模式中使用前缀"Try"和布尔值返回的类型。  
  
 **✓ 执行**每个成员使用 Try 分析模式提供的异常引发的成员。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)
