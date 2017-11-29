---
title: "事件和回调"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 217e9eae3540e0a20afd0888d24803285d6352b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="events-and-callbacks"></a>事件和回调
回调是允许回调到通过委托的用户代码的框架的扩展点。 这些委托通常通过方法的参数传递到框架。  
  
 事件是一种特殊的回调情况提供委托 （事件处理程序） 支持方便且一致的语法。 此外，Visual Studio 的语句完成和设计器提供在使用基于事件的 Api 的帮助。 (请参阅[事件设计](../../../docs/standard/design-guidelines/event.md)。)  
  
 **请考虑 ✓**使用回调，以允许用户提供自定义代码来执行的框架。  
  
 **请考虑 ✓**使用事件以允许用户自定义一个框架，而无需了解面向对象的设计的行为。  
  
 **✓ 执行**更愿意使用事件而纯回调，因为它们是广泛的开发人员更熟悉，与 Visual Studio 语句完成集成。  
  
 **请避免 x**性能敏感的 Api 中使用回调。  
  
 **✓ 执行**使用新`Func<...>`， `Action<...>`，或`Expression<...>`而不是定义回调的 Api 时的自定义委托的类型。  
  
 `Func<...>`和`Action<...>`表示泛型委托。 `Expression<...>`表示函数定义，可以编译并随后在运行时调用但是也可序列化和传递到远程进程。  
  
 **✓ 执行**测量和了解使用性能影响的`Expression<...>`，而不是使用`Func<...>`和`Action<...>`委托。  
  
 `Expression<...>`类型是在逻辑上等效于大多数情况下`Func<...>`和`Action<...>`委托。 它们之间的主要区别是委托旨在用于本地进程方案;表达式用于其中是有益的和可能在远程进程或计算机中的表达式进行求值的情况。  
  
 **✓ 执行**了解，通过调用委托，正在执行任意代码，且无法具有安全、 正确性和兼容性影响。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>另请参阅  
 [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
