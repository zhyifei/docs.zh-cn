---
title: 事件和回调
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 390c12af7107bb78fc261c55ea15390cf9eaa5b7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43862944"
---
# <a name="events-and-callbacks"></a>事件和回调
回调允许框架通过委托回调用户代码来实现可扩展性。这些委托通常通过方法的参数传递给框架。
  
事件是回调的一种特殊情况，它支持便捷且一致的语法来提供委托（事件处理程序）。此外，Visual Studio 的语句完成和设计器为使用基于事件的 API 提供了帮助。（请参阅[事件设计](../../../docs/standard/design-guidelines/event.md)。）
  
**✓ 考虑** 使用回调来允许用户提供框架要执行的自定义代码。

**✓ 考虑** 使用事件允许用户自定义框架的行为，而无需理解面向对象的设计。

**✓ 务必** 倾向使用事件而非普通回调，因为一般开发人员更熟悉事件，而且事件能与Visual Studio 的语句完成功能集成在一起。

**X 避免** 在性能敏感的 API 中使用回调。  

**✓ 务必** 在定义带回调的 API 时，使用新的 `Func<...>`，`Action<...>`，`Expression<...>`，而不是自定义委托。  

`Func<...>` 和 `Action<...>` 表示泛型委托。`Expression<...>` 表示函数定义，可在运行时编译并随后调用，但也可以进行序列化并传递给远程进程。

**✓ 务必** 估量和了解使用 `Expression<...>` 的性能影响，而不是使用 `Func<...>`和 `Action<...>` 委托。  

在大多数情况下，`Expression<...>` 类型在逻辑上等同于 `Func<...>` 和`Action<...>` 委托。它们之间的主要区别是，委托适用于本地进程场景;表达式适用于在远进程或计算机中评估表达式有利且可能的情况。

**✓ 务必** 要了解通过调用委托，您正在执行任意代码，可能会对安全性、正确性和兼容性产生影响。

*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
