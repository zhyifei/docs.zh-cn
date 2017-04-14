---
title: "处理和引发事件 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "应用程序开发 [.NET Framework], 事件"
  - "事件的委托模型"
  - "事件 [.NET Framework]"
ms.assetid: b6f65241-e0ad-4590-a99f-200ce741bb1f
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# 处理和引发事件
.NET Framework 中的事件是基于委托模型的。  委托模式遵守观察者设计模式使订阅者能够向提供程序注册并接收相关通知。  事件发送方推送通知事件发生，事件接收器接收该通知并定义给它的响应。  本文介绍委托模型的主要组件，如何在应用程序中使用事件和如何在您的代码中实现事件。  
  
 有关在[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用中处理时间的更多信息，请参见[事件和路由事件概述\(Windows store apps\)](http://go.microsoft.com/fwlink/p/?LinkId=261485)  
  
## 事件  
 事件是对象发送的消息，以发信号通知操作的发生。  事件可以由用户交互引起，例如单击按钮，也可能是由某些其他程序的逻辑引发，例如更改的属性值。  引发事件的对象称为*event sender* 事件发送方不知道哪个对象或方法将接收到（处理）它引发的事件。  事件通常是事件发送方，例如<xref:System.Web.UI.WebControls.Button.Click>事件是<xref:System.Web.UI.WebControls.Button>类的成员，<xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>事件是由<xref:System.ComponentModel.INotifyPropertyChanged>接口实现的成员。  
  
 使用 C\# 中的 `event`和 Visual Basic中的`Event` 关键字在事件类中签名并指定事件的委托来定义一个事件。  委托在下一节中介绍。  
  
 通常，为了引发事件，添加一个在C\#中标记为`protected`和`virtual`，在Visual Basic中标记为`Protected`和`Overridable`的方法。  命名次方法为`On`*EventName*，例如`OnDataReceived` 方法应带有指定事件数据对象的参数。  您提供此方法允许派生类重写引发事件的逻辑。  派生类必须始终调用基类的`On`*EventName*方法以确保注册的委托接收到事件。  
  
 下面的示例显示如何声明名叫`ThresholdReached` 的事件  事件与<xref:System.EventHandler>委托相关联并且被一个叫`OnThresholdReached`的方法引发。  
  
 [!code-csharp[EventsOverview#1](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#1)]
 [!code-vb[EventsOverview#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#1)]  
  
## 委托  
 委托是保存对方法的引用的类型。  委托声明与显示返回类型和参数的方法所引用的签名，并可以持有仅对与其签名匹配的方法。  这样，委托就等效于一个类型安全函数指针或一个回调。  一个委托声明足以定义一个委托类。  
  
 委托在 .NET Framework中有许多用途  在事件上下文中，委托是事件源和该的代码之间处理事件的媒介\(或类似指针的结构\)   如上一节的例子所示，可以通过在事件申明中包括委托类型来联系委托和事件。  有关委托的更多信息，请参见<xref:System.Delegate>类。  
  
 .NET Framework提供了<xref:System.EventHandler>和<xref:System.EventHandler%601>委托用来支持大多数的事件场景。  使用<xref:System.EventHandler>委托处理不包含事件数据的所有事件。  使用<xref:System.EventHandler%601>委托处理包含事件相关数据的事件。  这些委托没有返回类型值和并且带有两个参数 \(事件源的对象和事件数据中的对象\)。  
  
 事件委托是多路广播的，这意味着它们可以对多个事件处理方法进行引用  有关详细信息，请参见 <xref:System.Delegate>。相关页面  委托提供了事件处理中的灵活性和精确控制。  通过维护事件的已注册事件处理程序列表，委托为引发事件的类担当事件发送器的角色。  
  
 在<xref:System.EventHandler>和<xref:System.EventHandler%601>委托不可用的场景下，你可以定义一个委托。  要求您定义委托的场景非常少见的，例如，当您将无法识别泛型又必须操作代码时。  你在申明中给C\#使用`delegate`和给Visual Basic使用`Delegate`关键字来标记委托。  下面的示例说明如何申明名为 `ThresholdReachedEventHandler` 的委托。  
  
 [!code-csharp[EventsOverview#4](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#4)]
 [!code-vb[EventsOverview#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#4)]  
  
## 事件数据  
 与操作关联的数据可以通过事件数据的类提供。  .NET Framework 提供了许多事件数据类，你可以在你的应用程序中使用。  例如， <xref:System.IO.Ports.SerialDataReceivedEventArgs>类是<xref:System.IO.Ports.SerialPort.DataReceived?displayProperty=fullName>事件的事件数据类。  NET Framework遵循所有事件数据类以`EventArgs`结束的命名模式。  您通过查看委托事件确定哪个事件数据类与事件相关联。  例如，<xref:System.IO.Ports.SerialDataReceivedEventHandler>委托包含<xref:System.IO.Ports.SerialDataReceivedEventArgs>类作为他的一个参数。  
  
 <xref:System.EventArgs>是包含事件数据的类的基类。  当一个事件没有任何与他相关联的的数据<xref:System.EventArgs>也是你使用的类。  当你创建一个事件只是意味着你不需要通过任务数据通知其他类有事件要发送，包括<xref:System.EventArgs>类做为委托中的第二个参数。  当没有数据提供时，你可以越过<xref:System.EventArgs.Empty?displayProperty=fullName>值。  <xref:System.EventHandler>委托包括<xref:System.EventArgs>类并作为一个参数。  
  
 当你想创建一个自定义的事件数据类，创建的类要继承<xref:System.EventArgs>并且任何和事件相关的需要数据的成员。  通常，你需要遵循.NET Framework的命名模式并且你的事件数据类以以`EventArgs`结束。  
  
 下面的示例展示了一个名叫 `ThresholdReachedEventArgs`的事件数据类。  它包含引发事件的特定属性。  
  
 [!code-csharp[EventsOverview#3](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#3)]
 [!code-vb[EventsOverview#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#3)]  
  
## 事件处理程序  
 若要响应事件，你在事件接受者中定义一个事件处理方法。  此方法必须与你处理事件的委托签名匹配  在事件处理程序中，当事件引发时应执行必要的事件，例如在用户单击按钮之后收集用户输入  若要当事件发生时收到通知，你的事件处理方法必须被事件订阅。  
  
 下面的代码示例展示名为 `c_ThresholdReached` 的事件处理程序方法与<xref:System.EventHandler>委托的签名匹配。  方法被`ThresholdReached` 事件订阅。  
  
 [!code-csharp[EventsOverview#2](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#2)]
 [!code-vb[EventsOverview#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#2)]  
  
## 静态和动态事件处理程序  
 .NET Framework允许订户为获得事件通知而进行静态或动态注册。  静态事件处理程序在其所处理的事件所属类的整个生存期内有效。  动态事件处理程序在程序执行期间显式激活和停用，通常是为了响应某些条件程序逻辑。  例如，如果只在特定条件下才需要事件通知，或者如果应用程序提供了多个事件处理程序，并由运行时条件来确定要使用哪个事件处理程序，则可以使用动态事件处理程序。  上一节中的示例演示如何动态添加事件处理。  有关更多信息，请参见[事件](../Topic/Events%20\(Visual%20Basic\).md)和[事件](../Topic/Events%20\(C%23%20Programming%20Guide\).md)。  
  
## 引发多个事件  
 如果您的类引发多个事件，编译器会为每一个事件委托实例生产一个字段。  如果事件的数目很大，则一个委托一个字段的存储成本可能无法接受。  对于这些情况，.NET Framework 提供一个称为事件属性的构造（中的自定义事件），此构造可以和（您选择的）另一数据结构一起用于存储事件委托。  
  
 事件属性由带事件访问器的事件声明组成。  事件访问器是您定义的方法，用来从保存的数据结构中添加和移除事件委托实例  请注意，事件属性要比事件字段慢，因为必须先检索每个事件委托，然后才能调用它。  这是内存和速度之间的折中方案。  如果您的类定义了许多不常引发的事件，那么您可能要实现事件属性。  有关详细信息，请参阅[如何：使用事件属性处理多个事件](../../../docs/standard/events/how-to-handle-multiple-events-using-event-properties.md)。  
  
## 相关主题  
  
|标题|描述|  
|--------|--------|  
|[如何：引发和使用事件](../../../docs/standard/events/how-to-raise-and-consume-events.md)|包含引发和使用事件的示例。|  
|[如何：使用事件属性处理多个事件](../../../docs/standard/events/how-to-handle-multiple-events-using-event-properties.md)|展示如何使用事件属性处理多个事件。|  
|[观察程序设计模式](../../../docs/standard/events/observer-design-pattern.md)|描述允许订阅者注册和从提供者接受通知的设计模式。|  
|[如何：在 Web 窗体应用程序中使用事件](../../../docs/standard/events/how-to-consume-events-in-a-web-forms-application.md)|演示如何处理 Web窗体控件引发的事件。|  
  
## 请参阅  
 <xref:System.EventHandler>   
 <xref:System.EventHandler%601>   
 <xref:System.EventArgs>   
 <xref:System.Delegate>   
 [事件和路由事件概要 \(Windows store apps\)](http://go.microsoft.com/fwlink/?LinkId=261485)   
 [事件](../Topic/Events%20\(Visual%20Basic\).md)   
 [事件](../Topic/Events%20\(C%23%20Programming%20Guide\).md)