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
ms.openlocfilehash: e125c9a57090049f4319da96c7004f06606d0147
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141557"
---
# <a name="attached-events-overview"></a>附加事件概述

可扩展应用程序标记语言 （XAML） 定义称为*附加事件*的语言组件和事件类型。 通过附加事件的概念，你能够向任意元素（而不是实际定义或继承事件的元素）添加特定事件的处理程序。 在这种情况下，对象既不会引发事件，目标处理实例也不会定义或“拥有”事件。  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>系统必备  
 本主题假定你已阅读[路由事件概述](routed-events-overview.md)和 [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)。  
  
<a name="Syntax"></a>
## <a name="attached-event-syntax"></a>附加事件语法  
 附加的事件具有 XAML 语法和编码模式，备份代码必须使用该模式才能支持附加的事件使用。  
  
 在 XAML 语法中，附加的事件不仅由其事件名称指定，还由其所属类型加上事件名称指定，由点 （.） 分隔。 因为事件名称是使用具有其所属类型的名称限定的，所以附加事件语法允许将任何附加事件附加到可以实例化的任何元素。  
  
 例如，以下是用于附加自定义`NeedsCleaning`附加事件的处理程序的 XAML 语法：  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 请注意 `aqua:` 前缀；该前缀在本例中是必需的，因为附加事件是来自自定义映射 xmlns 的自定义事件。  
  
<a name="WPFImplements"></a>
## <a name="how-wpf-implements-attached-events"></a>WPF 如何实现附加事件

在 WPF 中，附加的事件由<xref:System.Windows.RoutedEvent>字段备份，并在引发后通过树路由它们。 通常，附加事件的源（引发该事件的对象）是系统或服务源，所以运行引发该事件的代码的对象并不是元素树的直接组成部分。  
  
<a name="Scenarios"></a>
## <a name="scenarios-for-attached-events"></a>附加事件的方案  
 在 WPF 中，附加事件存在于存在服务级别抽象的某些功能区域，例如对于静态<xref:System.Windows.Input.Mouse>类或<xref:System.Windows.Controls.Validation>类启用的事件。 与该服务交互或使用该服务的类可以在附加事件语法中使用该事件，也可以选择将附加事件作为路由事件来呈现，这是类如何集成服务功能的一部分。  
  
 尽管 WPF 定义了许多附加事件，但直接使用或处理附加事件的情况非常有限。 通常，附加事件具有体系结构目的，但随后将转发到未附加（带有 CLR 事件"包装器"的路由事件）。  
  
 <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType>例如，通过在给定的<xref:System.Windows.UIElement>上面使用<xref:System.Windows.UIElement.MouseDown>，而不是在 XAML 或代码中处理附加<xref:System.Windows.UIElement>的事件语法，可以更轻松地处理基础附加事件。 附加事件用于体系结构，因为它允许进一部扩展输入设备。 假设设备只需要提高<xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType>，以模拟鼠标输入，并且不需要派生<xref:System.Windows.Input.Mouse>来执行此操作。 但是，此方案涉及事件的代码处理，并且附加事件的 XAML 处理与此方案无关。  
  
<a name="Handling"></a>
## <a name="handling-an-attached-event-in-wpf"></a>在 WPF 中处理附加事件  
 处理附加事件的过程以及将要编写的处理程序代码与路由事件的基本相同。  
  
 通常，WPF 附加事件与 WPF 路由事件没有很大区别。 差异是事件的来源方式以及类作为成员如何公开事件（这也会影响 XAML 处理程序语法）。  
  
 但是，如前所述，现有的 WPF 附加事件并非特别适用于在 WPF 中处理。 更多情况下，该事件用于在复合时，使复合元素能够向父元素报告状态，在这种情况下，事件通常用代码引发，同时依赖于相关父类中的类处理。 例如，应引发<xref:System.Windows.Controls.Primitives.Selector>附加<xref:System.Windows.Controls.Primitives.Selector.Selected>事件，然后<xref:System.Windows.Controls.Primitives.Selector>由类处理该事件，然后由<xref:System.Windows.Controls.Primitives.Selector>类可能将其转换为其他路由事件 。 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 有关路由事件和类处理的详细信息，请参阅[将路由事件标记为“已处理”和“类处理”](marking-routed-events-as-handled-and-class-handling.md)。  
  
<a name="Custom"></a>
## <a name="defining-your-own-attached-events-as-routed-events"></a>将自己的附加事件定义为路由事件  
 如果要从常见的 WPF 基类派生，则可以通过在类中包括某些模式方法并使用基类上已经存在的实用程序方法来实现您自己的附加事件。  
  
 模式如下：  
  
- 方法添加具有两个参数__*的事件名称*处理程序__。 第一个参数是向其添加事件处理程序的实例。 第二个参数是要添加的事件处理程序。 方法必须为`public`和`static`，没有返回值。  
  
- 方法删除具有两个参数__*的事件名称*处理程序__。 第一个参数是从中删除事件处理程序的实例。 第二个参数是要删除的事件处理程序。 方法必须为`public`和`static`，没有返回值。  
  
 在元素上声明附加的事件处理程序属性时，__添加*事件名称*处理程序__访问器方法有助于 XAML 处理。 __添加*事件名称*处理程序__和__删除*事件名称*处理程序__方法还允许对附加事件的事件处理程序存储进行代码访问。  
  
 此常规模式还不足以在框架中实际实现，因为任何给定的 XAML 读取器实现可能具有不同的方案来标识支持语言和体系结构中的基础事件。 这是 WPF 将附加事件作为路由事件实现的原因之一;用于事件 （<xref:System.Windows.RoutedEvent>） 的标识符已由 WPF 事件系统定义。 此外，路由事件是附加事件的 XAML 语言级别概念的自然实现扩展。  
  
 WPF 附加事件的__添加*事件名称*处理程序__实现包括将<xref:System.Windows.UIElement.AddHandler%2A>路由事件和处理程序调用作为参数。  
  
 此实现策略和路由事件系统通常将附加事件的处理限制为<xref:System.Windows.UIElement>派生类或<xref:System.Windows.ContentElement>派生类，因为只有这些类具有<xref:System.Windows.UIElement.AddHandler%2A>实现。  
  
 例如，以下代码定义所有者类`NeedsCleaning``Aquarium`上的附加事件，使用 WPF 附加的事件策略将附加事件声明为路由事件。  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 请注意，用于建立附加事件标识符字段<xref:System.Windows.EventManager.RegisterRoutedEvent%2A>的方法 实际上是用于注册非附加路由事件的方法。 附加事件和路由事件都已注册到集中式内部存储。 此事件存储实现能够考虑到[路由事件概述](routed-events-overview.md)中介绍的“事件即界面”概念。  
  
<a name="Raising"></a>
## <a name="raising-a-wpf-attached-event"></a>引发 WPF 附加事件  
 您通常不需要从代码中引发现有的 WPF 定义的附加事件。 这些事件遵循一般"服务"概念模型，服务类（如<xref:System.Windows.Input.InputManager>负责引发事件）。  
  
 但是，如果您正在基于基于 附加事件的 WPF 模型定义<xref:System.Windows.RoutedEvent>自定义附加事件，则可以使用<xref:System.Windows.UIElement.RaiseEvent%2A>从 任何<xref:System.Windows.UIElement>或<xref:System.Windows.ContentElement>引发附加事件。 引发路由事件（附加或不附加）要求您将元素树中的特定元素声明为事件源;否则，将元素声明为事件源。该源报告为<xref:System.Windows.UIElement.RaiseEvent%2A>调用方。 服务负责确定将哪个元素报告为元素树中的事件源  
  
## <a name="see-also"></a>另请参阅

- [路由事件概述](routed-events-overview.md)
- [XAML 语法详述](xaml-syntax-in-detail.md)
- [XAML 及 WPF 的自定义类](xaml-and-custom-classes-for-wpf.md)
