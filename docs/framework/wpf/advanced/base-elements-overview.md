---
title: 基元素概述
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: 7d52d951d4fa4df83bbcca6b4cb479e18e532d2a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141623"
---
# <a name="base-elements-overview"></a>基元素概述
中[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]较高的类是从 SDK 文档中通常称为基元素类的四个类派生的。 这些类是<xref:System.Windows.UIElement> <xref:System.Windows.FrameworkElement>、<xref:System.Windows.ContentElement>和<xref:System.Windows.FrameworkContentElement>。 类<xref:System.Windows.DependencyObject>也是相关的，因为它是两个<xref:System.Windows.UIElement>和<xref:System.Windows.ContentElement>  

<a name="base_apis"></a>
## <a name="base-element-apis-in-wpf-classes"></a>WPF 类中的基元素 API  
 和<xref:System.Windows.UIElement><xref:System.Windows.ContentElement>都派生自<xref:System.Windows.DependencyObject>，通过稍有不同途径。 此级别的拆分涉及用户界面中的 使用<xref:System.Windows.UIElement>或<xref:System.Windows.ContentElement>，以及它们在应用程序中的作用。 <xref:System.Windows.UIElement>其类<xref:System.Windows.Media.Visual>层次结构中也有，该层次结构是公开底层较低级别的图形支持的类[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。 <xref:System.Windows.Media.Visual>通过定义独立的矩形屏幕区域提供渲染框架。 实际上，<xref:System.Windows.UIElement>对于支持较大对象模型的元素，用于渲染和布局到可描述为矩形屏幕区域的区域，以及内容模型有意更开放的区域，以允许不同的元素组合。 <xref:System.Windows.ContentElement>不派生自<xref:System.Windows.Media.Visual>。其模型是，将<xref:System.Windows.ContentElement>被其他的东西（如读取器或查看器）使用，然后解释元素并生成<xref:System.Windows.Media.Visual>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]要消耗的完整元素。 某些<xref:System.Windows.UIElement>类旨在成为内容主机：它们为一个或多个<xref:System.Windows.ContentElement>类提供宿主和呈现（<xref:System.Windows.Controls.DocumentViewer>是此类类的示例）。 <xref:System.Windows.ContentElement>用作对象模型稍小的元素的基类，用于更多内容，这些元素可能托管在<xref:System.Windows.UIElement>中。  
  
### <a name="framework-level-and-core-level"></a>框架级别和核心级别  
 <xref:System.Windows.UIElement>用作 的基类<xref:System.Windows.FrameworkElement>，<xref:System.Windows.ContentElement>并用作<xref:System.Windows.FrameworkContentElement>的基类。 下一级类的原因是支持独立于 WPF 框架级别的 WPF 核心级别，此划分还存在于如何在表示核心程序集和表示框架程序集之间划分 API 中。 WPF 框架级别表示一种更完整的解决方案，以满足基本应用程序需求，其中包括实现演示文稿的布局管理器。 WPF 核心级别可提供一种方法，使你能够充分利用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，而无需使用其他程序集的开销。 这些级别之间的区别很少对大多数典型的应用程序开发方案很重要，通常您应该将[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]API 视为一个整体，而不应关注 WPF 框架级别和 WPF 核心级别之间的区别。 如果应用程序设计选择替换大量 WPF 框架级别功能，建议了解级别差异，例如，整体解决方案是否已有其自己的 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 组合和布局的实现。  
  
<a name="subclassing_elements"></a>
## <a name="choosing-which-element-to-derive-from"></a>选择要从其中派生的元素  
 若要创建扩展 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的自定义类，最实用的方法是派生自 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 类之一，你可在其中通过现有类层次结构获得尽可能多的所需功能。 本节列出了以下三个最重要的元素类附带的功能，以帮助决定要从其中继承的类。  
  
 如果要实现控件（这确实是从类派生的更常见原因之一[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]），则可能需要从实际控件、控件族基类或至少从<xref:System.Windows.Controls.Control>基类派生的类。 有关指导和实际示例，请参阅[控件创作概述](../controls/control-authoring-overview.md)。  
  
 如果没有创建控件且需要派生自位于层次结构中较高层次的类，以下各节可用于指导在每个基元素类中定义哪些特征。  
  
 如果创建派生自<xref:System.Windows.DependencyObject>的类，则继承以下功能：  
  
- <xref:System.Windows.DependencyObject.GetValue%2A><xref:System.Windows.DependencyObject.SetValue%2A>和支持，以及一般财产系统支持。  
  
- 能够使用依赖属性和实现为依赖属性的附加属性。  
  
 如果创建的类派生自<xref:System.Windows.UIElement>， 除了 提供<xref:System.Windows.DependencyObject>的功能外，还继承了以下功能：  
  
- 对已动画处理的属性值的基本支持。 有关详细信息，请参阅 [动画概述](../graphics-multimedia/animation-overview.md)。  
  
- 基本输入事件支持以及命令支持。 有关详细信息，请参阅[输入概述](input-overview.md)和[命令概述](commanding-overview.md)。  
  
- 可进行替代以便介绍布局系统的虚拟方法。  
  
 如果创建的类派生自<xref:System.Windows.FrameworkElement>， 除了 提供<xref:System.Windows.UIElement>的功能外，还继承了以下功能：  
  
- 样式和情节提要支持。 有关详细信息，请参阅<xref:System.Windows.Style>和[情节提要概述](../graphics-multimedia/storyboards-overview.md)。  
  
- 数据绑定支持。 有关详细信息，请参阅 [数据绑定概述](../data/data-binding-overview.md)。  
  
- 动态资源引用支持。 有关详细信息，请参阅 [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。  
  
- 属性值继承支持，以及元数据中的其他标记，这些标记有助于报告关于框架服务属性的情况，例如数据绑定、样式或布局的框架实现。 有关详细信息，请参阅[框架属性元数据](framework-property-metadata.md)。  
  
- 逻辑树概念。 有关详细信息，请参见 [WPF 中的树](trees-in-wpf.md)。  
  
- 支持布局系统的实际 WPF 框架级实现，包括可以检测影响布局<xref:System.Windows.FrameworkElement.OnPropertyChanged%2A>的属性更改的重写。  
  
 如果创建的类派生自<xref:System.Windows.ContentElement>， 除了 提供<xref:System.Windows.DependencyObject>的功能外，还继承了以下功能：  
  
- 支持动画。 有关详细信息，请参阅 [动画概述](../graphics-multimedia/animation-overview.md)。  
  
- 基本输入事件支持以及命令支持。 有关详细信息，请参阅[输入概述](input-overview.md)和[命令概述](commanding-overview.md)。  
  
 如果创建的类派生自<xref:System.Windows.FrameworkContentElement>， 除了 提供<xref:System.Windows.ContentElement>的功能外，还获取以下功能：  
  
- 样式和情节提要支持。 有关详细信息，请参阅<xref:System.Windows.Style>和[动画概述](../graphics-multimedia/animation-overview.md)。  
  
- 数据绑定支持。 有关详细信息，请参阅 [数据绑定概述](../data/data-binding-overview.md)。  
  
- 动态资源引用支持。 有关详细信息，请参阅 [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。  
  
- 属性值继承支持，以及元数据中的其他标记，这些标记有助于报告关于框架服务属性的情况，例如数据绑定、样式或布局的框架实现。 有关详细信息，请参阅[框架属性元数据](framework-property-metadata.md)。  
  
- 不继承对布局系统修改（如<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>） 的访问。 布局系统实现仅在 上<xref:System.Windows.FrameworkElement>可用。 但是，您继承了一<xref:System.Windows.FrameworkElement.OnPropertyChanged%2A>个重写，该重写可以检测对影响布局的属性的更改，并将这些更改报告给任何内容主机。  
  
 针对各种类记录内容模型。 如果想要查找相应的类进行派生，类的内容模型是应该考虑的一个可能因素。 有关详细信息，请参阅 [WPF 内容模型](../controls/wpf-content-model.md)。  
  
<a name="other_base_classes"></a>
## <a name="other-base-classes"></a>其他基类  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject>支持[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]线程模型，并使为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序创建的所有对象都与 相关联。 <xref:System.Windows.Threading.Dispatcher> 即使您不<xref:System.Windows.UIElement>派生于 、<xref:System.Windows.DependencyObject>或<xref:System.Windows.Media.Visual>， 也应考虑派生，<xref:System.Windows.Threading.DispatcherObject>以便获得此线程模型支持。 有关详细信息，请参阅[线程模型](threading-model.md)。  
  
### <a name="visual"></a>视觉对象  
 <xref:System.Windows.Media.Visual>实现 2D 对象的概念，该对象通常需要在大致矩形区域中进行可视化表示。 实际<xref:System.Windows.Media.Visual>呈现发生在其他类中（它不是自包含的），但<xref:System.Windows.Media.Visual>该类提供了一个已知类型，该类型由不同级别的渲染过程使用。 <xref:System.Windows.Media.Visual>实现命中测试，但不会公开报告命中测试阳性的事件（这些事件在<xref:System.Windows.UIElement>中）。 有关详细信息，请参阅[可视化层编程](../graphics-multimedia/visual-layer-programming.md)。  
  
### <a name="freezable"></a>Freezable  
 <xref:System.Windows.Freezable>通过提供在性能原因需要或需要不可变对象时生成对象副本的方法，模拟可变对象中的不变性。 该<xref:System.Windows.Freezable>类型为某些图形元素（如几何和画笔以及动画）提供了通用基础。 值得注意的是，a<xref:System.Windows.Freezable>不是; <xref:System.Windows.Media.Visual>它可以保存在 应用 以填充另一<xref:System.Windows.Freezable>个对象的属性值时成为子属性的属性，并且这些子属性可能会影响渲染。 有关详细信息，请参阅 [Freezable 对象概述](freezable-objects-overview.md)。  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable>是一<xref:System.Windows.Freezable>个派生类，专门添加动画控制层和一些实用程序成员，以便当前动画属性可以区分为非动画属性。  
  
### <a name="control"></a>控制  
 <xref:System.Windows.Controls.Control>是各种称为控件或组件的对象类型的预期基类，具体取决于技术。 一般情况下，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件类可直接表示 UI 控件或积极参与控件组合。 <xref:System.Windows.Controls.Control>启用的主要功能是控制模板化。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Control>
- [依赖项属性概述](dependency-properties-overview.md)
- [控件创作概述](../controls/control-authoring-overview.md)
- [WPF 体系结构](wpf-architecture.md)
