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
ms.openlocfilehash: a3a2f711840ad7f6e28443dac3c18501cd4400e0
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401402"
---
# <a name="attached-events-overview"></a>附加事件概述
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 定义了一个语言组件和称为附加事件的事件类型。 通过附加事件的概念，你能够向任意元素（而不是实际定义或继承事件的元素）添加特定事件的处理程序。 在这种情况下，对象既不会引发事件，目标处理实例也不会定义或“拥有”事件。  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>系统必备  
 本主题假定你已阅读[路由事件概述](routed-events-overview.md)和 [XAML 概述 (WPF)](xaml-overview-wpf.md)。  
  
<a name="Syntax"></a>   
## <a name="attached-event-syntax"></a>附加事件语法  
 附加事件具有一种 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 语法和编码模式，后备代码必须使用该语法和编码模式才能支持使用附加事件。  
  
 在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 语法中，不仅可以通过事件名称来指定附加事件，还可以通过事件所属类型和事件名称来指定，中间以句点 (.) 分隔。 因为事件名称是使用具有其所属类型的名称限定的，所以附加事件语法允许将任何附加事件附加到可以实例化的任何元素。  
  
 例如，下面是 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 语法，用于附加自定义 `NeedsCleaning` 附加事件的处理程序：  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 请注意 `aqua:` 前缀；该前缀在本例中是必需的，因为附加事件是来自自定义映射 xmlns 的自定义事件。  
  
<a name="WPFImplements"></a>   
## <a name="how-wpf-implements-attached-events"></a>WPF 如何实现附加事件  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中, 附加事件<xref:System.Windows.RoutedEvent>由字段支持, 并在引发后通过树进行路由。 通常，附加事件的源（引发该事件的对象）是系统或服务源，所以运行引发该事件的代码的对象并不是元素树的直接组成部分。  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>附加事件的方案  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中, 附加事件存在于具有服务级别抽象的某些功能区域中, 例如, 对于由静态<xref:System.Windows.Input.Mouse>类或<xref:System.Windows.Controls.Validation>类启用的事件。 与该服务交互或使用该服务的类可以在附加事件语法中使用该事件，也可以选择将附加事件作为路由事件来呈现，这是类如何集成服务功能的一部分。  
  
 尽管 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 定义了许多附加事件，但直接使用或处理附加事件的情形却很少。 通常情况下, 附加事件为体系结构目的提供服务, 但随后会转发到非附加 (使用 CLR 事件 "包装") 路由事件。  
  
 <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType>例如, 可以<xref:System.Windows.UIElement>通过使用<xref:System.Windows.UIElement.MouseDown> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]来<xref:System.Windows.UIElement>更轻松地处理基础附加事件, 而不是在或代码中处理附加事件语法。 附加事件用于体系结构，因为它允许进一部扩展输入设备。 假设的设备只需引发<xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType>才能模拟鼠标输入, 而无需从<xref:System.Windows.Input.Mouse>派生。 但是，此方案会涉及事件的代码处理，而附加事件的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理则与此方案无关。  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>在 WPF 中处理附加事件  
 处理附加事件的过程以及将要编写的处理程序代码与路由事件的基本相同。  
  
 一般情况下，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 附加事件与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 路由事件并没有太大的区别。 不同之处在于如何确定事件的源，以及如何通过类将事件作为成员进行公开（这还将影响 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理程序语法）。  
  
 但是，正如前文所述，现有的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 附加事件并不是专门用于在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中进行处理。 更多情况下，该事件用于在复合时，使复合元素能够向父元素报告状态，在这种情况下，事件通常用代码引发，同时依赖于相关父类中的类处理。 例如, 中的<xref:System.Windows.Controls.Primitives.Selector>项应引发附加<xref:System.Windows.Controls.Primitives.Selector.Selected>事件, 该类<xref:System.Windows.Controls.Primitives.Selector>随后由类进行处理, 并可能由<xref:System.Windows.Controls.Primitives.Selector>类转换为其他路由事件, <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>. 有关路由事件和类处理的详细信息，请参阅[将路由事件标记为“已处理”和“类处理”](marking-routed-events-as-handled-and-class-handling.md)。  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>将自己的附加事件定义为路由事件  
 如果从通用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 基类派生，则可以通过在类中包括某些模式方法并使用基类中已经存在的实用工具方法来实现自己的附加事件。  
  
 模式如下：  
  
- 方法添加包含两个参数的 ***事件名称*处理程序**。 第一个参数是要向其添加事件处理程序的实例。 第二个参数是要添加的事件处理程序。 方法必须是`public`和, `static`并且没有返回值。  
  
- 使用两个参数的方法**删除*事件名称*处理程序**。 第一个参数是从中删除事件处理程序的实例。 第二个参数是要删除的事件处理程序。 方法必须是`public`和, `static`并且没有返回值。  
  
 当在元素上声明附加事件处理[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]程序特性时, **Add*名称*程序处理程序**方法可简化处理。 "**添加事件*名*处理程序**" 和 "**删除事件*名称*" 处理程序**方法还允许代码访问附加事件的事件处理程序存储区。  
  
 此常规模式对于框架中的实际实现还不够精确，因为任何给定的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 读取器实现都可能采用不同的方案在支持语言和体系结构中标识基础事件。 这是将附加事件作为路由[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]事件实现的原因之一; 事件系统已定义[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]用于事件的标识符 (<xref:System.Windows.RoutedEvent>)。 另外，路由一个事件也是对附加事件的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 语言级概念的自然实现扩展。  
  
 附加事件的 "**添加*事件名称*" 处理程序**实现包括使用路由事件和处理程序作为参数调用。<xref:System.Windows.UIElement.AddHandler%2A> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
 通常, 此实现策略和路由事件系统会将附加事件的处理限制为<xref:System.Windows.UIElement>派生类或<xref:System.Windows.ContentElement>派生类, 因为只有这些类具有<xref:System.Windows.UIElement.AddHandler%2A>实现。  
  
 例如，以下代码通过将附加事件声明为路由事件的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 附加事件策略，在所有者类 `Aquarium` 中定义 `NeedsCleaning` 附加事件。  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 请注意, 用于建立附加事件标识符字段<xref:System.Windows.EventManager.RegisterRoutedEvent%2A>的方法实际上与用于注册非附加路由事件的方法相同。 附加事件和路由事件都已注册到集中式内部存储。 此事件存储实现能够考虑到[路由事件概述](routed-events-overview.md)中介绍的“事件即界面”概念。  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>引发 WPF 附加事件  
 通常不需要从代码中引发 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 定义的现有附加事件。 这些事件遵循常规 "服务" 概念模型, 服务类 (如<xref:System.Windows.Input.InputManager> ) 负责引发事件。  
  
 但是, 如果要基于[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]在上<xref:System.Windows.RoutedEvent>建立附加事件的模型来定义自定义附加事件, 则可以使用<xref:System.Windows.UIElement.RaiseEvent%2A>从任何<xref:System.Windows.UIElement>或<xref:System.Windows.ContentElement>引发附加事件。 如果引发路由事件 (附加或不), 则要求您将元素树中的特定元素声明为事件源;该源将报告为<xref:System.Windows.UIElement.RaiseEvent%2A>调用方。 服务负责确定将哪个元素报告为元素树中的事件源  
  
## <a name="see-also"></a>请参阅

- [路由事件概述](routed-events-overview.md)
- [XAML 语法详述](xaml-syntax-in-detail.md)
- [XAML 及 WPF 的自定义类](xaml-and-custom-classes-for-wpf.md)
