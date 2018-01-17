---
title: "附加事件概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fcfe0d97b86a27859d79685e035d8f3f765a965b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="attached-events-overview"></a>附加事件概述
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 定义了一个语言组件和称为附加事件的事件类型。 通过附加事件的概念，你能够向任意元素（而不是实际定义或继承事件的元素）添加特定事件的处理程序。 在这种情况下，对象既不会引发事件，目标处理实例也不会定义或“拥有”事件。  
  
 
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>系统必备  
 本主题假定你已阅读[路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)和 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)。  
  
<a name="Syntax"></a>   
## <a name="attached-event-syntax"></a>附加事件语法  
 附加事件具有一种 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 语法和编码模式，后备代码必须使用该语法和编码模式才能支持使用附加事件。  
  
 在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 语法中，不仅可以通过事件名称来指定附加事件，还可以通过事件所属类型和事件名称来指定，中间以句点 (.) 分隔。 因为事件名称是使用具有其所属类型的名称限定的，所以附加事件语法允许将任何附加事件附加到可以实例化的任何元素。  
  
 例如，下面是 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 语法，用于附加自定义 `NeedsCleaning` 附加事件的处理程序：  
  
 [!code-xaml[WPFAquariumSln#AE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 请注意 `aqua:` 前缀；该前缀在本例中是必需的，因为附加事件是来自自定义映射 xmlns 的自定义事件。  
  
<a name="WPFImplements"></a>   
## <a name="how-wpf-implements-attached-events"></a>WPF 如何实现附加事件  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]、 附加事件由<xref:System.Windows.RoutedEvent>字段和后引发它们时通过树路由。 通常，附加事件的源（引发该事件的对象）是系统或服务源，所以运行引发该事件的代码的对象并不是元素树的直接组成部分。  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>附加事件的方案  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]、 附加事件都位于特定功能区域没有服务级别抽象，如启用由静态事件<xref:System.Windows.Input.Mouse>类或<xref:System.Windows.Controls.Validation>类。 与该服务交互或使用该服务的类可以在附加事件语法中使用该事件，也可以选择将附加事件作为路由事件来呈现，这是类如何集成服务功能的一部分。  
  
 尽管 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 定义了许多附加事件，但直接使用或处理附加事件的情形却很少。 一般情况下，附加事件用于体系结构，但随后即被转发给非附加（使用 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 事件“包装器”提供支持）路由事件。  
  
 例如，基础附加事件<xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType>可以更方便地处理针对任何给定<xref:System.Windows.UIElement>使用<xref:System.Windows.UIElement.MouseDown>上<xref:System.Windows.UIElement>而不是可以处理附加的事件语法中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]或代码。 附加事件用于体系结构，因为它允许进一部扩展输入设备。 假设设备只需引发<xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType>在订购模拟鼠标输入并不需要派生自<xref:System.Windows.Input.Mouse>若要这样做。 但是，此方案会涉及事件的代码处理，而附加事件的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理则与此方案无关。  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>在 WPF 中处理附加事件  
 处理附加事件的过程以及将要编写的处理程序代码与路由事件的基本相同。  
  
 一般情况下，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 附加事件与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 路由事件并没有太大的区别。 不同之处在于如何确定事件的源，以及如何通过类将事件作为成员进行公开（这还将影响 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理程序语法）。  
  
 但是，正如前文所述，现有的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 附加事件并不是专门用于在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中进行处理。 更多情况下，该事件用于在复合时，使复合元素能够向父元素报告状态，在这种情况下，事件通常用代码引发，同时依赖于相关父类中的类处理。 例如内的项<xref:System.Windows.Controls.Primitives.Selector>应引发附加<xref:System.Windows.Controls.Primitives.Selector.Selected>事件，然后是类由处理<xref:System.Windows.Controls.Primitives.Selector>类，然后可能通过转换<xref:System.Windows.Controls.Primitives.Selector>到不同的路由事件的类<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>. 有关路由事件和类处理的详细信息，请参阅[将路由事件标记为“已处理”和“类处理”](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)。  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>将自己的附加事件定义为路由事件  
 如果从通用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 基类派生，则可以通过在类中包括某些模式方法并使用基类中已经存在的实用工具方法来实现自己的附加事件。  
  
 模式如下：  
  
-   含两个参数的方法 `Add*Handler`。 第一个参数必须标识事件，而标识的事件必须与方法名称中带有 * 的名称相匹配。 第二个参数是要添加的处理程序。 该方法必须是公共且静态的，没有任何返回值。  
  
-   含两个参数的方法 `Remove*Handler`。 第一个参数必须标识事件，而标识的事件必须与方法名称中带有 * 的名称相匹配。 第二个参数是要删除的处理程序。 该方法必须是公共且静态的，没有任何返回值。  
  
 当在某个元素中声明附加事件处理程序属性时，`Add*Handler` 访问器方法可以加快 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理。 `Add*Handler` 和 `Remove*Handler` 方法还可实现对附加事件的事件处理程序存储的代码访问。  
  
 此常规模式对于框架中的实际实现还不够精确，因为任何给定的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 读取器实现都可能采用不同的方案在支持语言和体系结构中标识基础事件。 这是由于原因之一，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]实现附加作为路由事件的事件; 要使用的事件的标识符 (<xref:System.Windows.RoutedEvent>) 已由定义[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]事件系统。 另外，路由一个事件也是对附加事件的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 语言级概念的自然实现扩展。  
  
 `Add*Handler`实现[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]附加的事件包含调用<xref:System.Windows.UIElement.AddHandler%2A>与路由的事件和作为自变量的处理程序。  
  
 此实现策略和路由的事件系统通常将附加事件的处理限制为<xref:System.Windows.UIElement>派生类或<xref:System.Windows.ContentElement>派生类中，因为只有这些类具有<xref:System.Windows.UIElement.AddHandler%2A>实现。  
  
 例如，以下代码通过将附加事件声明为路由事件的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 附加事件策略，在所有者类 `Aquarium` 中定义 `NeedsCleaning` 附加事件。  
  
 [!code-csharp[WPFAquariumSln#AECode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 请注意，该方法用于建立附加的事件标识符字段， <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>，是实际的用于注册非附加路由的事件的相同的方法。 附加事件和路由事件都已注册到集中式内部存储。 此事件存储实现能够考虑到[路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)中介绍的“事件即界面”概念。  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>引发 WPF 附加事件  
 通常不需要从代码中引发 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 定义的现有附加事件。 这些事件遵循常规"服务"概念模型中，并如服务类<xref:System.Windows.Input.InputManager>负责引发事件。  
  
 但是，如果要定义基于自定义的附加的事件[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]模型的基础上附加事件<xref:System.Windows.RoutedEvent>，你可以使用<xref:System.Windows.UIElement.RaiseEvent%2A>以引发从任何一个附加的事件<xref:System.Windows.UIElement>或<xref:System.Windows.ContentElement>。 引发路由的事件 （不管附加） 要求先声明作为事件源中; 在元素树中的特定元素该源将报告为<xref:System.Windows.UIElement.RaiseEvent%2A>调用方。 服务负责确定将哪个元素报告为元素树中的事件源  
  
## <a name="see-also"></a>请参阅  
 [路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [XAML 语法详述](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)  
 [XAML 及 WPF 的自定义类](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
