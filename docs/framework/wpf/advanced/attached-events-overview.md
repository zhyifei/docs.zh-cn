---
title: 附加事件概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling attached events [WPF]
- defining attached events as routed events [WPF]
- attached events [WPF], scenarios for
- attached events vs. routed events [WPF]
- backing attached events with routed events [WPF]
- attached events [WPF], definition
ms.assetid: 2c40eae3-80e4-4a45-ae09-df6c9ab4d91e
ms.openlocfilehash: 76ff60cfe26f9105d4504164802987115fc2a7e2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455471"
---
# <a name="attached-events-overview"></a>附加事件概述

Extensible Application Markup Language （XAML）定义称为*附加事件*的语言组件和事件类型。 通过附加事件的概念，你能够向任意元素（而不是实际定义或继承事件的元素）添加特定事件的处理程序。 在这种情况下，对象既不会引发事件，目标处理实例也不会定义或“拥有”事件。  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisites  
 本主题假定你已阅读[路由事件概述](routed-events-overview.md)和 [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)。  
  
<a name="Syntax"></a>   
## <a name="attached-event-syntax"></a>附加事件语法  
 附加事件具有 XAML 语法和编码模式，支持代码必须使用它才能支持附加的事件使用。  
  
 在 XAML 语法中，附加事件不只是通过其事件名称指定，而是由其所属类型和事件名称指定，用点（.）分隔。 因为事件名称是使用具有其所属类型的名称限定的，所以附加事件语法允许将任何附加事件附加到可以实例化的任何元素。  
  
 例如，下面是用于为自定义 `NeedsCleaning` 附加事件附加处理程序的 XAML 语法：  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 请注意 `aqua:` 前缀；该前缀在本例中是必需的，因为附加事件是来自自定义映射 xmlns 的自定义事件。  
  
<a name="WPFImplements"></a>   
## <a name="how-wpf-implements-attached-events"></a>WPF 如何实现附加事件

在 WPF 中，附加事件由 <xref:System.Windows.RoutedEvent> 字段支持，并在引发后通过树进行路由。 通常，附加事件的源（引发该事件的对象）是系统或服务源，所以运行引发该事件的代码的对象并不是元素树的直接组成部分。  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>附加事件的方案  
 在 WPF 中，附加事件存在于具有服务级别抽象的某些功能区域中，例如，对于由静态 <xref:System.Windows.Input.Mouse> 类或 <xref:System.Windows.Controls.Validation> 类启用的事件。 与该服务交互或使用该服务的类可以在附加事件语法中使用该事件，也可以选择将附加事件作为路由事件来呈现，这是类如何集成服务功能的一部分。  
  
 虽然 WPF 定义了大量附加事件，但使用或直接处理附加事件的方案非常有限。 通常情况下，附加事件为体系结构目的提供服务，但随后会转发到非附加（使用 CLR 事件 "包装"）路由事件。  
  
 例如，通过使用该 <xref:System.Windows.UIElement> 上 <xref:System.Windows.UIElement.MouseDown>，而不是在 XAML 或代码中处理附加事件语法，可以更轻松地在任何给定 <xref:System.Windows.UIElement> 上处理基础附加事件 <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType>。 附加事件用于体系结构，因为它允许进一部扩展输入设备。 假设的设备只需引发 <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> 来模拟鼠标输入，而无需从 <xref:System.Windows.Input.Mouse> 派生。 但是，此方案涉及事件的代码处理，附加事件的 XAML 处理与此方案无关。  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>在 WPF 中处理附加事件  
 处理附加事件的过程以及将要编写的处理程序代码与路由事件的基本相同。  
  
 通常，WPF 附加事件与 WPF 路由事件并不完全相同。 不同之处在于，事件的来源以及类作为成员公开的方式（这也会影响 XAML 处理程序语法）。  
  
 但正如前文所述，现有 WPF 附加事件并不是特别适用于 WPF 中的处理。 更多情况下，该事件用于在复合时，使复合元素能够向父元素报告状态，在这种情况下，事件通常用代码引发，同时依赖于相关父类中的类处理。 例如，<xref:System.Windows.Controls.Primitives.Selector> 中的项应引发附加的 <xref:System.Windows.Controls.Primitives.Selector.Selected> 事件，该事件随后由 <xref:System.Windows.Controls.Primitives.Selector> 类处理，然后 <xref:System.Windows.Controls.Primitives.Selector> 类可能会将其转换为不同的路由事件 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>。 有关路由事件和类处理的详细信息，请参阅[将路由事件标记为“已处理”和“类处理”](marking-routed-events-as-handled-and-class-handling.md)。  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>将自己的附加事件定义为路由事件  
 如果是从公共 WPF 基类派生的，则可以通过在类中包含某些模式方法，并使用基类中已经存在的实用工具方法来实现自己的附加事件。  
  
 模式如下：  
  
- 方法添加包含两个参数的 __*事件名称*处理程序__。 第一个参数是要向其添加事件处理程序的实例。 第二个参数是要添加的事件处理程序。 方法必须是 `public` 和 `static`，并且没有返回值。  
  
- 使用两个参数的方法__删除*事件名称*处理程序__。 第一个参数是从中删除事件处理程序的实例。 第二个参数是要删除的事件处理程序。 方法必须是 `public` 和 `static`，并且没有返回值。  
  
 当在元素上声明附加事件处理程序属性时， __Add*名称*程序处理程序__方法可简化 XAML 处理。 "__添加事件*名*处理程序__" 和 "__删除事件*名称*" 处理程序__方法还允许代码访问附加事件的事件处理程序存储区。  
  
 此常规模式尚未精确地用于框架中的实际实现，因为任何给定的 XAML 读取器实现可能都有不同的方案用于标识支持语言和体系结构中的基础事件。 这是 WPF 将附加事件作为路由事件实现的原因之一;要用于事件的标识符（<xref:System.Windows.RoutedEvent>）已由 WPF 事件系统定义。 此外，路由事件是对附加事件的 XAML 语言级概念的自然实现扩展。  
  
 WPF 附加事件的 "__添加*事件名称*" 处理程序__实现包括使用路由事件和处理程序作为参数调用 <xref:System.Windows.UIElement.AddHandler%2A>。  
  
 通常，此实现策略和路由事件系统会将附加事件的处理限制 <xref:System.Windows.UIElement> 派生类或 <xref:System.Windows.ContentElement> 派生类，因为只有这些类具有 <xref:System.Windows.UIElement.AddHandler%2A> 实现。  
  
 例如，下面的代码使用将附加事件声明为路由事件的 WPF 附加事件策略，来定义 owner 类 `Aquarium`上的 `NeedsCleaning` 附加事件。  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 请注意，用于建立附加事件标识符字段 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>的方法实际与用于注册非附加路由事件的方法相同。 附加事件和路由事件都已注册到集中式内部存储。 此事件存储实现能够考虑到[路由事件概述](routed-events-overview.md)中介绍的“事件即界面”概念。  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>引发 WPF 附加事件  
 通常不需要从代码中引发现有的 WPF 定义的附加事件。 这些事件遵循常规 "服务" 概念模型，服务类（如 <xref:System.Windows.Input.InputManager>）负责引发事件。  
  
 但是，如果要基于在 <xref:System.Windows.RoutedEvent>上建立附加事件的 WPF 模型来定义自定义附加事件，则可以使用 <xref:System.Windows.UIElement.RaiseEvent%2A> 从任何 <xref:System.Windows.UIElement> 或 <xref:System.Windows.ContentElement>引发附加事件。 如果引发路由事件（附加或不），则要求您将元素树中的特定元素声明为事件源;该源将报告为 <xref:System.Windows.UIElement.RaiseEvent%2A> 调用方。 服务负责确定将哪个元素报告为元素树中的事件源  
  
## <a name="see-also"></a>请参阅

- [路由事件概述](routed-events-overview.md)
- [XAML 语法详述](xaml-syntax-in-detail.md)
- [XAML 及 WPF 的自定义类](xaml-and-custom-classes-for-wpf.md)
