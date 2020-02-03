---
title: 事件设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
ms.openlocfilehash: b44ee5933f8629b4dddbf3be1b79b2e77b0254f7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741686"
---
# <a name="event-design"></a>事件设计
事件是最常用的回叫（允许框架调用用户代码的结构）。 其他回调机制包括采用委托、虚拟成员和基于接口的插件的成员。可用性研究的数据表明，大多数开发人员比使用其他回调机制更喜欢使用事件. 事件能与 Visual Studio 和许多语言很好地集成。

 值得注意的是，有两组事件：在系统状态发生变化之前引发的事件，称为事前事件，以及状态更改后引发的事件，称为事后事件。 将 `Form.Closing`一个预先事件的示例，该事件在窗体关闭前引发。 后期事件的一个示例将 `Form.Closed`，该事件是在关闭窗体后引发的。

 ✔️对事件（而不是 "火灾" 或 "trigger"）使用术语 "引发"。

 ✔️使用 <xref:System.EventHandler%601?displayProperty=nameWithType> 而不是手动创建要用作事件处理程序的新委托。

 ✔️考虑使用 <xref:System.EventArgs> 的子类作为事件参数，除非你完全确信该事件从不需要将任何数据传递到事件处理方法，在这种情况下，你可以直接使用 `EventArgs` 类型。

 如果直接使用 `EventArgs` 交付 API，则永远不能添加与事件一起使用的任何数据，而不会破坏兼容性。 如果使用子类，即使最初完全为空，也可以在需要时向子类添加属性。

 ✔️使用受保护的虚拟方法引发每个事件。 这仅适用于非密封类的非静态事件，而不适用于结构、密封类或静态事件。

 该方法的目的是为派生类提供一种使用重写来处理事件的方法。 重写是一种更灵活、更快、更自然的方式来处理派生类中的基类事件。 按照惯例，方法的名称应以 “On” 开头，并跟随事件的名称。

 派生类可以选择在其重写中不调用方法的基本实现。 要做到这点，需要在方法中不包括使基类正常工作所需的任何处理过程。

 ✔️会对引发事件的受保护方法执行一个参数。

 应将参数命名为 `e`，并应将该参数类型化为事件参数类。

 引发非静态事件时，❌ 不会将 null 传递为发送方。

 ✔️在引发静态事件时将 null 作为发件人传递。

 引发事件时，❌ 不会传递 null 作为事件数据参数。

 如果不想将任何数据传递到事件处理方法，应传递 `EventArgs.Empty`。 开发人员希望此参数不为 null。

 ✔️考虑引发最终用户可以取消的事件。 这仅适用于事前事件。

 使用 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> 或其子类作为事件参数，以允许最终用户取消事件。

### <a name="custom-event-handler-design"></a>自定义事件处理程序设计
 有些情况下，不能使用 `EventHandler<T>`，例如框架需要使用早期版本的 CLR，而不支持泛型。 在这种情况下，可能需要设计和开发自定义事件处理程序委托。

 ✔️使用 void 的返回类型作为事件处理程序。

 事件处理程序可以调用多个事件处理方法（可能在多个对象上）。 如果允许事件处理方法返回值，则每个事件调用都有多个返回值。

 ✔️使用 `object` 作为事件处理程序的第一个参数的类型，并 `sender`调用它。

 ✔️使用 <xref:System.EventArgs?displayProperty=nameWithType> 或其子类作为事件处理程序的第二个参数的类型，并将其调用 `e`。

 ❌ 在事件处理程序上没有两个以上的参数。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
