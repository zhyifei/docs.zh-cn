---
title: 事件设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b257da73d33fae54ef464e9dd69906316b87fd88
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353848"
---
# <a name="event-design"></a>事件设计
事件是最常使用的窗体的回叫 （允许框架在调用用户代码调用的构造）。 其他回调机制包括成员撰写委托、 虚拟成员，以及使用基于接口的插件。可用性研究中的数据表示大多数开发人员更熟练使用事件，它们使用与其他回调机制。 使用 Visual Studio 和许多语言可以很好地集成事件。  
  
 务必要注意，有两个组的事件： 事件的系统更改，名为事前事件和事件引发后状态发生变化，状态之前，将引发调用后的事件。 事件前的示例将`Form.Closing`，引发之前关闭窗体。 事件后的示例将`Form.Closed`，这引发后关闭窗体。  
  
 **✓ DO** 使用术语"引发"事件而不是"激发"或"触发"。  
  
 **✓ DO** 使用<xref:System.EventHandler%601?displayProperty=nameWithType>而不是手动创建要用作事件处理程序的新委托。  
  
 **✓ CONSIDER** 使用的一个子类<xref:System.EventArgs>作为事件自变量，除非您完全确定事件永远都不需要执行任何数据到的事件处理方法，在这种情况下你可以使用`EventArgs`直接键入。  
  
 如果 API 使用寄送`EventArgs`直接，您将永远无法添加任何数据，以执行与该事件，而不会破坏兼容性。 如果使用的子类，即使是如果最初完全为空，可以将属性添加到需要时的子类。  
  
 **✓ DO** 使用受保护的虚拟方法引发每个事件。 这是仅适用于未密封类，不适用于结构、 密封的类或静态事件上的非静态事件。  
  
 此方法的用途是提供派生类来处理使用替代的事件的方法。 重写是一种更灵活、 更快，且更自然的方式来处理在派生类中的基类事件。 按照约定，方法的名称应以"On"开头，并按照向事件的名称。  
  
 在派生的类可以选择不在其重写中调用该方法的基实现。 准备此基类才能正常工作所需的方法中不包括任何处理。  
  
 **✓ DO** 引发事件的受保护方法采用一个参数。  
  
 该参数应命名为`e`和的类型应为事件参数类。  
  
 **X DO NOT** 时引发的非静态事件传递 null 值作为发件人。  
  
 **✓ DO** 时引发的静态事件传递 null 值作为发件人。  
  
 **X DO NOT** 时引发事件传递 null 值作为事件数据参数。  
  
 应传递`EventArgs.Empty`如果不想将任何数据传递给事件处理方法。 开发人员看到此参数不为 null。  
  
 **✓ CONSIDER** 引发最终用户可以取消的事件。 这仅适用于预事件。  
  
 使用<xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>或要允许最终用户可取消事件的事件参数作为其子类。  
  
### <a name="custom-event-handler-design"></a>自定义事件处理程序设计  
 某些情况下，在其中`EventHandler<T>`不能使用，如框架需要与早期版本的 CLR 不支持泛型。 在这种情况下，可能需要设计和开发自定义事件处理程序委托。  
  
 **✓ DO** 对于事件处理程序使用返回类型为 void。  
  
 事件处理程序可以调用多个事件处理方法，可能在多个对象上。 如果允许事件处理方法返回一个值，则会为每个事件调用多个返回值。  
  
 **✓ DO** 使用`object`作为事件处理程序的第一个参数的类型和调用它`sender`。  
  
 **✓ DO** 使用<xref:System.EventArgs?displayProperty=nameWithType>或其子类作为事件处理程序中，第二个参数的类型和调用它`e`。  
  
 **X DO NOT** 对事件处理程序的两个以上参数。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
