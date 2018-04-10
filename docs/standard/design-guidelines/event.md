---
title: 事件设计
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a07392ba805b5f2a3913b01a15dd0e1668f0ccf7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="event-design"></a>事件设计
事件是回调 （允许框架，以调入用户代码的构造） 的最常用的形式。 其他回调机制包括采用委托、 虚拟成员和基于接口的插件的成员。从可用性研究的数据指示的大部分开发人员更喜欢使用事件，与它们使用的其他回调机制。 事件可以很好地与 Visual Studio 和许多语言集成。  
  
 务必请注意，有两个组的事件： 事件在系统更改，调用预事件，以及后状态更改时，引发的事件的状态之前引发调用后的事件。 预事件的示例将`Form.Closing`，引发之前关闭窗体。 事件后的示例将`Form.Closed`，引发后关闭窗体。  
  
 **✓ 执行**使用术语"引发"事件而不是"激发"或"触发"。  
  
 **✓ 执行**使用<xref:System.EventHandler%601?displayProperty=nameWithType>而不是手动创建要用作事件处理程序的新委托。  
  
 **请考虑 ✓**使用的一个子类<xref:System.EventArgs>作为事件自变量，除非您完全确定事件永远都不需要执行任何数据到的事件处理方法，在这种情况下你可以使用`EventArgs`直接键入。  
  
 如果你提供 API 使用`EventArgs`直接，你永远不会将能够添加任何数据，以执行与该事件，而不会破坏兼容性。 如果你使用的子类，即使是如果最初完全为空，你将能够将属性添加到需要时的子类。  
  
 **✓ 执行**使用受保护的虚拟方法引发每个事件。 这是仅适用于未密封类，不适用于结构、 密封的类或静态事件上的非静态事件。  
  
 该方法旨在提供一种方法的派生类使用替代对事件进行处理。 重写是更灵活、 更快，且更自然的方式来处理在派生类中的基类事件。 按照约定，方法的名称应以"On"开头，并按照向事件的名称。  
  
 派生的类可以选择不在其重写中调用基实现的方法。 为准备此的方法所需的正常工作的基类中不包括任何处理。  
  
 **✓ 执行**引发事件的受保护方法采用一个参数。  
  
 该参数应命名为`e`和类型应为事件参数类。  
  
 **X 不**时引发的非静态事件传递 null 值作为发件人。  
  
 **✓ 执行**时引发的静态事件传递 null 值作为发件人。  
  
 **X 不**时引发事件传递 null 值作为事件数据参数。  
  
 应传递`EventArgs.Empty`如果不想将任何数据传递给事件处理方法。 开发人员希望此参数不为 null。  
  
 **请考虑 ✓**引发最终用户可以取消的事件。 这仅适用于预事件。  
  
 使用<xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>或要允许最终用户若要取消事件的事件参数作为其子类。  
  
### <a name="custom-event-handler-design"></a>自定义事件处理程序设计  
 在其中的情况下`EventHandler<T>`无法使用，如框架需要使用早期版本的 CLR，不支持泛型。 在这种情况下，你可能需要设计和开发自定义事件处理程序委托。  
  
 **✓ 执行**对于事件处理程序使用返回类型为 void。  
  
 事件处理程序可以调用多个事件处理方法，可能是对多个对象。 如果允许事件处理方法返回一个值，则不存在的每个事件调用多个返回值。  
  
 **✓ 执行**使用`object`作为事件处理程序的第一个参数的类型和调用它`sender`。  
  
 **✓ 执行**使用<xref:System.EventArgs?displayProperty=nameWithType>或其子类作为事件处理程序中，第二个参数的类型和调用它`e`。  
  
 **X 不**对事件处理程序的两个以上参数。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
