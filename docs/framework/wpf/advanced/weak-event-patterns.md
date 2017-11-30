---
title: "弱事件模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a27e17e4940ff68f34d1e7e4accfb9e112bc412b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="weak-event-patterns"></a>弱事件模式
在应用程序，很可能不会被附加到事件源的处理程序破坏与附加到源的处理程序的侦听器对象结合使用。 这种情况下可能会导致内存泄漏。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]引入了一种设计模式，可以用于解决此问题，通过专用管理器类的特定事件并在该事件的侦听器上实现接口。 此设计模式中被称为*弱事件模式*。  
  
## <a name="why-implement-the-weak-event-pattern"></a>为什么实现弱事件模式？  
 侦听事件可能导致内存泄漏。 为侦听事件的典型方法是使用将处理程序附加到源上的事件的特定于语言的语法。 例如，在[!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]，语法是： `source.SomeEvent += new SomeEventHandler(MyEventHandler)`。  
  
 此方法创建的强引用从事件源移到的事件侦听器。 通常，为侦听器附加事件处理程序会导致侦听器具有上 （除非显式删除事件处理程序） 受源的对象生存期对象生存期。 但在某些情况下，你可能想，侦听器可以由其他因素控制的对象生存期，如是否它当前所属的应用程序，而不是源的生存期的可视化树。 只要源对象生存期扩展的侦听器对象生存期结束后，正常事件模式会导致内存泄漏： 侦听器保持活动状态时间超过预期。  
  
 弱事件模式设计用于解决此内存泄漏问题。 只要侦听器需要注册一个事件，但该侦听器不明确了解何时注销时，会使用弱事件模式。 只要源的对象生存期超过了侦听器的有用的对象生存期，还会使用弱事件模式。 (在这种情况下，*有用*由你决定。)弱事件模式，侦听器可以注册和而不会影响以任何方式侦听器的对象生存期特征对事件进行接收。 实际上，从源隐式的引用不能决定侦听器是否是符合垃圾回收的条件。 引用为弱引用，因此的命名弱事件模式和相关[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]。 侦听器可以进行垃圾回收或销毁，且源可以继续而不保留对现在销毁对象的非可收集处理程序引用。  
  
## <a name="who-should-implement-the-weak-event-pattern"></a>人员应实现弱事件模式？  
 主要用于控制作者有趣的是实现弱事件模式。 控件的作者，你有很大程度上责任的行为和包含的控件和对其插入到的应用程序的影响。 这包括控件对象生存期行为，特别是描述的内存泄漏问题的处理。  
  
 某些情况下本质上是有助于使自身弱事件模式的应用程序。 其中一种方案是数据绑定。 在数据绑定中，很常见的源对象，可以完全独立于的侦听器对象，它是绑定的目标。 许多方面[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]数据绑定已具有应用于事件的实现方式弱事件模式。  
  
## <a name="how-to-implement-the-weak-event-pattern"></a>如何实现弱事件模式  
 有三种方法实现弱事件模式。 下表列出的三种方法，并提供一些指导应何时使用每个。  
  
|方法|何时实现|  
|--------------|-----------------------|  
|使用现有弱事件 manager 类|如果你想要订阅的事件具有对应<xref:System.Windows.WeakEventManager>，使用现有弱事件管理器。 弱事件管理器所包含的 WPF 的列表，请参阅中的继承层次结构<xref:System.Windows.WeakEventManager>类。 但是，请注意，有相对较少弱事件管理器将包含在 WPF 中，这样你将可能需要选择其他方法之一。|  
|使用泛型弱事件管理器类|使用通用<xref:System.Windows.WeakEventManager%602>如果现有<xref:System.Windows.WeakEventManager>不可用，你想轻松实现，并且你不关心效率。 泛型<xref:System.Windows.WeakEventManager%602>效率低于现有或自定义的弱事件管理器。 例如，泛型类执行详细的反射来发现给定名称的事件的事件。 此外，通过使用泛型注册事件的代码<xref:System.Windows.WeakEventManager%602>为更详细比使用的现有或自定义<xref:System.Windows.WeakEventManager>。|  
|创建自定义弱事件管理器类|创建自定义<xref:System.Windows.WeakEventManager>时你的现有<xref:System.Windows.WeakEventManager>不可用，并且你希望最高的效率。 使用自定义<xref:System.Windows.WeakEventManager>璹綷事件将会更高效，但你执行会产生编写更多代码开头的成本。|  
  
 下列各节描述如何实现弱事件模式。  出于本文的讨论，订阅的事件具有以下特征。  
  
-   事件名称不`SomeEvent`。  
  
-   事件由引发`EventSource`类。  
  
-   事件处理程序类型： `SomeEventEventHandler` (或`EventHandler<SomeEventEventArgs>`)。  
  
-   该事件传递的参数类型`SomeEventEventArgs`到事件处理程序。  
  
### <a name="using-an-existing-weak-event-manager-class"></a>使用现有弱事件管理器类  
  
1.  管理器中找到的现有弱事件。  
  
     弱事件管理器所包含的 WPF 的列表，请参阅中的继承层次结构<xref:System.Windows.WeakEventManager>类。  
  
2.  使用新的弱事件管理器，而不是正常事件挂钩。  
  
     例如，如果你的代码使用以下模式来订阅事件：  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     将其更改为以下模式：  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     同样，如果你的代码使用以下模式来取消订阅事件：  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     将其更改为以下模式：  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a>使用泛型的弱事件管理器类  
  
1.  使用泛型<xref:System.Windows.WeakEventManager%602>类而不是正常事件挂钩。  
  
     当你使用<xref:System.Windows.WeakEventManager%602>要注册事件侦听器，必须提供事件源和<xref:System.EventArgs>用作类和调用类型参数的类型<xref:System.Windows.WeakEventManager%602.AddHandler%2A>中下面的代码所示：  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a>创建自定义的弱事件管理器类  
  
1.  将以下类模板复制到你的项目。  
  
     此类继承自<xref:System.Windows.WeakEventManager>类。  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  替换`SomeEventWeakEventManager`名称与你自己的名称。  
  
3.  将与你的事件的相应名称的前面所述的三个名称。 (`SomeEvent`， `EventSource`，和`SomeEventEventArgs`)  
  
4.  设置为与它所管理的事件相同的可见性弱事件管理器类的可见性 （公共 / 内部 / 私有）。  
  
5.  使用新的弱事件管理器，而不是正常事件挂钩。  
  
     例如，如果你的代码使用以下模式来订阅事件：  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     将其更改为以下模式：  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     同样，如果你的代码使用以下模式来取消订阅事件：  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     将其更改为以下模式：  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.WeakEventManager>  
 <xref:System.Windows.IWeakEventListener>  
 [路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)
