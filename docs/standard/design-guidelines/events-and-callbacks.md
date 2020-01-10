---
title: 事件和回调
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
ms.openlocfilehash: 80c16e29f1d8a0653295ebc3cf25be6fb78b7dc9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709408"
---
# <a name="events-and-callbacks"></a>事件和回调
回调允许框架通过委托回调用户代码来实现可扩展性。 这些委托通常通过方法的参数传递给框架。  
  
 事件是回调的一种特殊情况，它支持通过便捷且一致的语法来提供委托（事件处理程序）。 此外，可以借助 Visual Studio 的语句完成和设计器功能来使用基于事件的 API。 (请参阅[事件设计](../../../docs/standard/design-guidelines/event.md)。)  
  
 **✓ 考虑** 使用回调来允许用户提供框架要执行的自定义代码。  
  
 **✓ 考虑** 使用事件允许用户自定义框架的行为，而无需理解面向对象的设计。  
  
 **✓ 务必** 更愿意使用事件而纯回调，因为它们是广泛的开发人员更熟悉，与 Visual Studio 语句完成集成。  
  
 **X 避免** 性能敏感的 Api 中使用回调。  
  
 **✓ DO** 使用新`Func<...>`， `Action<...>`，或`Expression<...>`而不是定义回调的 Api 时的自定义委托的类型。  
  
 `Func<...>` 和 `Action<...>` 表示泛型委托。 `Expression<...>` 表示可以编译并随后在运行时调用的函数定义，但也可以进行序列化并将其传递到远程进程。  
  
 **✓ 务必** 测量和了解使用性能影响的`Expression<...>`，而不是使用`Func<...>`和`Action<...>`委托。  
  
 在大多数情况下，`Expression<...>` 类型在逻辑上等同于 `Func<...>` 和 `Action<...>` 委托。 它们之间的主要区别在于委托旨在用于本地处理方案;表达式适用于在远程进程或计算机中计算表达式的好处。  
  
 **✓ DO** 了解，通过调用委托，正在执行任意代码，且无法具有安全、 正确性和兼容性影响。  
  
 *部分©2005，2009 Microsoft Corporation。保留所有权利。*  
  
 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。  
  
## <a name="see-also"></a>另请参阅

- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
