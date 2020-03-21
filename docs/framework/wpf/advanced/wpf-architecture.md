---
title: 体系结构
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], attached
- attached properties [WPF]
- architecture [WPF]
- unmanaged components [WPF]
- affinity thread [WPF]
- Storyboards [WPF]
- milcore [WPF]
- components [WPF], unmanaged
- painter's algorithm
- interfaces [WPF], INotifyPropertyChange
- CommandBindings [WPF]
- data templates [WPF]
- thread [WPF], affinity
ms.assetid: 8579c10b-76ab-4c52-9691-195ce02333c8
ms.openlocfilehash: b16be8470a47f3e8e362feb0b13e10aa901baacb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187124"
---
# <a name="wpf-architecture"></a>WPF 体系结构
本主题提供 Windows 演示基础 （WPF） 类层次结构的导览。 它涵盖了 WPF 的大多数主要子系统，并描述了它们如何交互。 它还详细介绍了 WPF 架构师所做的一些选择。  

<a name="System_Object"></a>
## <a name="systemobject"></a>System.Object  
 主 WPF 编程模型通过托管代码公开。 在 WPF 设计阶段的早期，就系统托管组件和非托管组件之间的划分位置进行了多次辩论。 CLR 提供了许多功能，使开发更高效、更可靠（包括内存管理、错误处理、通用类型系统等），但它们是有代价的。  
  
 下图说明了世界森林论坛的主要组成部分。 关系图的红色部分（演示框架、演示核心和 milcore）是 WPF 的主要代码部分。 在这些组件中，只有一个是非托管组件 - milcore。 Milcore 编写于非托管代码中，以便与 DirectX 紧密集成。 WPF 中的所有显示都通过 DirectX 引擎完成，从而可实现高效的硬件和软件呈现。 WPF 还需要对内存和执行进行精细控制。 milcore 中的组合引擎对性能非常敏感，需要放弃 CLR 的许多优势才能获得性能。  
  
 ![WPF 在 .NET Framework 中的位置。](./media/wpf-architect1.PNG "wpf_architect1")  
  
 本主题稍后将讨论 WPF 的托管和非托管部分之间的通信。 下面介绍托管编程模型的其余部分。  
  
<a name="System_Threading_DispatcherObject"></a>
## <a name="systemthreadingdispatcherobject"></a>System.Threading.DispatcherObject  
 WPF 中的大多数对象派生<xref:System.Windows.Threading.DispatcherObject>自，它提供了处理并发和线程的基本构造。 WPF 基于调度程序实现的消息传递系统。 这的工作原理很像熟悉的Win32消息泵;事实上，WPF 调度程序使用 User32 消息执行交叉线程调用。  
  
 在 WPF 中讨论并发性时，实际上需要了解两个核心概念 - 调度器和线程相关性。  
  
 在 WPF 的设计阶段，目标是移动到单个执行线程，但采用非线程"关联化"模型。 当一个组件使用执行线程的标识来存储某种类型的状态时，将发生线程关联。 最常见的形式是使用线程本地存储 (TLS) 来存储状态。 线程关联要求执行的每个逻辑线程仅由操作系统中的一个物理线程所拥有，这将占用大量内存。 最后，WPF 的线程处理模型通过线程关联与单一线程执行的现有 User32 线程处理模型保持同步。 这样做的主要原因是互操作性 – OLE 2.0、剪贴板和 Internet 资源管理器等系统都需要单线程关联 （STA） 执行。  
  
 假设你具有带有 STA 线程的对象，则需要在线程之间通信并验证你是否位于正确的线程上的一种方法。 调度程序的作用就在于此。 调度程序是一个基本的消息调度系统，具有多个按优先顺序排列的队列。 消息的示例包括原始输入通知（鼠标移动）、框架函数（布局）或用户命令（执行此方法）。 通过派生从<xref:System.Windows.Threading.DispatcherObject>，您将创建具有 STA 行为的 CLR 对象，并在创建时为调度程序提供指向调度程序的指针。  
  
<a name="System_Windows_DependencyObject"></a>
## <a name="systemwindowsdependencyobject"></a>System.Windows.DependencyObject  
 构建 WPF 时使用的主要体系结构哲学之一是首选属性而不是方法或事件。 属性具有声明性，可更方便地指定用途而不是操作。 它还支持模型驱动或数据驱动的系统，以显示用户界面内容。 这种理念的预期效果是创建更多可以绑定到的属性，从而更好地控制应用程序的行为。  
  
 为了使更多的系统由属性驱动，需要比 CLR 提供的更丰富的属性系统。 这种丰富性的一个简单示例是更改通知。 若要实现双向绑定，需要绑定的双方支持更改通知。 若要使行为与属性值相关联，需要在属性值更改时收到通知。 微软 .NET 框架有一个接口 **，NotifyPropertyChange**，它允许对象发布更改通知，但它是可选的。  
  
 WPF 提供了一个更丰富的属性系统，派生<xref:System.Windows.DependencyObject>自类型。 该属性系统实际是一个“依赖”属性系统，因为它会跟踪属性表达式之间的依赖关系，并在依赖关系更改时自动重新验证属性值。 例如，如果属性继承 （如<xref:System.Windows.Controls.Control.FontSize%2A>），则如果属性在继承该值的元素的父项上发生更改，则系统将自动更新。  
  
 WPF 属性系统的基础是属性表达式的概念。 在 WPF 的第一个版本中，属性表达式系统已关闭，并且表达式都作为框架的一部分提供。 表达式致使属性系统不具有数据绑定、样式调整或继承硬编码，而是由框架内后面的层来提供这些功能。  
  
 属性系统还提供属性值的稀疏存储。 因为对象可能有数十个（如果达不到上百个）属性，并且大部分值处于其默认状态（被继承、由样式设置等），所以并非对象的每个实例都需要具有在其上定义的每个属性的完全权重。  
  
 属性系统的最后一个新功能是附加属性的概念。 WPF 元素基于组合和组件重用原则构建。 通常的情况是，某些包含元素（如<xref:System.Windows.Controls.Grid>布局元素）需要子元素上的其他数据来控制其行为（如行/列信息）。 任何对象都可以为任何其他对象提供属性定义，而不是将所有这些属性与每个元素相关联。 这与 JavaScript 中的“expando”功能相似。  
  
<a name="System_Windows_Media_Visual"></a>
## <a name="systemwindowsmediavisual"></a>System.Windows.Media.Visual  
 定义一个系统后，下一步是将像素绘制到屏幕上。 该<xref:System.Windows.Media.Visual>类用于构建一个可视对象树，每个对象都可选地包含有关如何呈现这些指令（剪切、转换等）的绘图说明和元数据。 <xref:System.Windows.Media.Visual>设计为极其轻巧和灵活，因此大多数功能没有公共 API 公开，并且严重依赖受保护的回调功能。  
  
 <xref:System.Windows.Media.Visual>实际上是 WPF 组合系统的切入点。 <xref:System.Windows.Media.Visual>是这两个子系统（托管 API 和非托管 milcore）之间的连接点。  
  
 WPF 通过遍历 milcore 管理的非托管数据结构来显示数据。 这些结构（称为组合节点）代表层次结构显示树，其中每个节点都有呈现指令。 只能通过消息传递协议来访问此树（如下图右侧所示）。  
  
 编程 WPF 时，您将<xref:System.Windows.Media.Visual>创建元素和派生类型，这些元素和派生类型通过此消息传递协议在内部与组合树通信。 WPF<xref:System.Windows.Media.Visual>中的每个节点可以创建一个、无或多个合成节点。  
  
 ![Windows Presentation Foundation 可视化树。](./media/wpf-architecture2.PNG "wpf_architecture2")  
  
 请注意一个非常重要的体系结构细节 - 会缓存整个可视化树和绘制指令。 在图形方面，WPF 使用保留的渲染系统。 这可以实现以高刷新率重绘系统，并且组合系统不会阻止对用户代码的回调。 这有助于防止出现应用程序无响应的情况。  
  
 关系图中容易忽略的另一个重要细节是系统实际执行组合的方式。  
  
 在 User32 和 GDI 中，系统可立即使用模式剪切系统。 当需要绘制一个组件时，系统会建立一个剪裁边界，在此边界外，不允许组件接触像素，然后会要求组件在该框中绘制像素。 此系统在内存受限的系统上工作良好，因为当某些内容更改时，只需处理受影响的组件即可 - 不会由两个组件同时处理一个像素的颜色。  
  
 WPF使用"画家算法"绘画模型。 要求每个组件从显示内容的背面绘制到正面，而不是剪裁每个组件。 这允许每个组件在先前组件的显示内容上绘制。 此模型的优点是可以生成部分透明的复杂形状。 在当今的现代图形硬件中，此型号相对较快（创建 User32/GDI 时情况并非如此）。  
  
 如前所述，WPF 的核心理念是转向更具声明性的"以属性为中心的"编程模型。 在可视化系统中，这体现在有意思的几个方面。  
  
 首先，对于保留的模式图形系统，这实际上是从命令性 DrawLine/DrawLine 类型模型移动到面向数据的模型 new Line()/new Line()。 通过这种向数据驱动的绘制的移动，可以使用属性表达绘制指令上的复杂操作。 派生的类型<xref:System.Windows.Media.Drawing>实际上是用于渲染的对象模型。  
  
 第二，如果评估动画系统，你会发现它几乎是完全声明性的。 可以将动画表示为动画对象上的一组属性，无需要求开发人员计算下一个位置或下一个颜色。 这些动画可以表达开发人员或设计人员的意图（在 5 秒内将此按钮从一个位置移动到另一个位置），系统可以确定完成此任务的最高效方式。  
  
<a name="System_Windows_UIElement"></a>
## <a name="systemwindowsuielement"></a>System.Windows.UIElement  
 <xref:System.Windows.UIElement>定义核心子系统，包括布局、输入和事件。  
  
 布局是 WPF 的核心概念。 在许多系统中，可能有一组固定的布局模型（HTML 支持三种布局模型：流、绝对和表），也可能没有布局模型（User32 实际仅支持绝对定位）。 WPF 首先假定开发人员和设计人员需要一个灵活、可扩展的布局模型，该模型可以由属性值而不是命令逻辑驱动。 在级别<xref:System.Windows.UIElement>上，引入了布局的基本协定 - 具有<xref:System.Windows.UIElement.Measure%2A>和<xref:System.Windows.UIElement.Arrange%2A>传递的两相模型。  
  
 <xref:System.Windows.UIElement.Measure%2A>允许组件确定它要采用的大小。 这是一个单独的阶段，<xref:System.Windows.UIElement.Arrange%2A>因为在许多情况下，父元素将要求子元素多次测量以确定其最佳位置和大小。 父元素要求子元素进行度量这一事实演示了 WPF 的另一个关键理念 - 内容大小。 WPF 中的所有控件都支持调整其内容的自然大小。 这使本地化更加容易，并可实现调整内容大小时进行动态元素布局。 该<xref:System.Windows.UIElement.Arrange%2A>阶段允许父级定位并确定每个子级的最终大小。  
  
 经常花费大量时间讨论 WPF 的输出端和相关<xref:System.Windows.Media.Visual>对象。 然而，在输入端也有许多创新。 WPF 输入模型中最根本的更改可能是通过系统路由输入事件的一致模型。  
  
 输入是作为内核模式设备驱动程序上的信号发出的，并通过涉及 Windows 内核和 User32 的复杂过程路由到正确的进程和线程。 将与输入对应的 User32 消息路由到 WPF 后，该消息将转换为 WPF 原始输入消息并发送到调度程序。 WPF 允许将原始输入事件转换为多个实际事件，使"MouseEnter"等功能能够在系统的较低级别实现，并保证交付。  
  
 每个输入事件至少会转换为两个事件 -“预览”事件和实际事件。 WPF 中的所有事件都有通过元素树路由的概念。 如果事件从目标向上穿过树到根，则表示为"气泡"，如果事件从根开始并向下遍历到目标，则表示为"隧道"。 输入预览事件隧道，使树中的任何元素都有机会筛选事件或对事件采取操作。 然后，常规（非预览）事件将从目标向上浮升到根。  
  
 隧道和浮升阶段之间的划分使键盘快捷键等功能的实现在复合环境中采用一致的方式。 在 User32 中，可以通过使用一个全局表来实现键盘快捷键，该表中包含你希望支持的所有快捷键（Ctrl+N 映射到“新建”）。 在应用程序的调度程序中，可以调用 **TranslateAccelerator**，它会探查 User32 中的输入消息，并确定是否有任何消息与已注册的快捷键匹配。 在 WPF 中，这不起作用，因为系统是完全"可组合的" - 任何元素都可以处理和使用任何键盘快捷键。 将此两阶段模型用于输入，可允许组件实现其自己的“TranslateAccelerator”。  
  
 为了更进一步，<xref:System.Windows.UIElement>还介绍了命令绑定的概念。 WPF 命令系统允许开发人员根据命令终结点（实现<xref:System.Windows.Input.ICommand>的）定义功能。 命令绑定使元素可以定义输入笔势 (Ctrl+N) 和命令（“新建”）之间的映射。 输入笔势和命令定义都是可扩展的，并且可以在使用时联系到一起。 这使得一些操作（例如，允许最终用户自定义其要在应用程序内使用的键绑定）显得无关紧要。  
  
 在这一主题中，WPF 的"核心"功能（在演示核心程序集中实现的功能）一直是焦点。 构建 WPF 时，基础部分（如使用**度量**和**排列**的布局合同）和框架部分（如特定布局（如<xref:System.Windows.Controls.Grid>等布局的实现）之间的干净分离是预期的结果。 目标是提供在堆栈中处于较低位置的可扩展性点，这将允许外部开发人员在需要时创建自己的框架。  
  
<a name="System_Windows_FrameworkElement"></a>
## <a name="systemwindowsframeworkelement"></a>System.Windows.FrameworkElement  
 <xref:System.Windows.FrameworkElement>可以从两种不同的方式看待。 它引入了一组策略和自定义，这些子系统位于 WPF 的下层中。 它还引入了一组新的子系统。  
  
 引入<xref:System.Windows.FrameworkElement>的主要策略是围绕应用程序布局。 <xref:System.Windows.FrameworkElement>基于由引入<xref:System.Windows.UIElement>的基本布局协定构建，并添加了布局"槽"的概念，使布局作者更容易具有一组一致的属性驱动的布局语义。 属性（<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>例如<xref:System.Windows.FrameworkElement.VerticalAlignment%2A> <xref:System.Windows.FrameworkElement.MinWidth%2A>，<xref:System.Windows.FrameworkElement.Margin%2A>和 （仅举几例） 提供从<xref:System.Windows.FrameworkElement>布局容器内的一致行为派生的所有组件。  
  
 <xref:System.Windows.FrameworkElement>还提供了更容易的 API 暴露到 WPF 核心层中的许多功能。 例如，<xref:System.Windows.FrameworkElement>通过 方法提供对动画的直接<xref:System.Windows.FrameworkElement.BeginStoryboard%2A>访问。 提供了<xref:System.Windows.Media.Animation.Storyboard>一种针对一组属性编写多个动画的脚本的方法。  
  
 <xref:System.Windows.FrameworkElement>引入的两个最关键的事情是数据绑定和样式。  
  
 WPF 中的数据绑定子系统对于使用 Windows 窗体或ASP.NET创建应用程序[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]的人应相对熟悉。 在上述每个系统中，可通过一种简单的方式来表达希望将给定元素中的一个或多个属性绑定到一个数据片段。 WPF 完全支持属性绑定、转换和列表绑定。  
  
 WPF 中数据绑定最有趣的功能之一是引入数据模板。 利用数据模板，可以通过声明方式指定某个数据片断的可视化方式。 无需创建可绑定到数据的自定义用户界面，而是转而让数据来确定要创建的显示内容。  
  
 样式实际上是轻量型的数据绑定。 使用样式，可以将共享定义的一组属性绑定到元素的一个或多个实例。 样式通过显式引用（通过设置<xref:System.Windows.FrameworkElement.Style%2A>属性）或通过将样式与元素的 CLR 类型关联而隐式应用于元素。  
  
<a name="System_Windows_Controls_Control"></a>
## <a name="systemwindowscontrolscontrol"></a>System.Windows.Controls.Control  
 控件的最重要功能是模板化。 如果将 WPF 的组合系统视为一个保留模式绘制系统，则控件可通过模板化以一种参数化的声明性方式描述其绘制。 实际上<xref:System.Windows.Controls.ControlTemplate>，A 只不过是一个脚本来创建一组子元素，该元素具有控件提供的属性的绑定。  
  
 <xref:System.Windows.Controls.Control>提供了一组股票属性<xref:System.Windows.Controls.Control.Foreground%2A>，<xref:System.Windows.Controls.Control.Background%2A><xref:System.Windows.Controls.Control.Padding%2A>仅举几例，模板作者随后可以使用这些属性自定义控件的显示。 控件的实现提供了数据模型和交互模型。 交互模型定义了一组命令（如窗口的“关闭”），以及到输入笔势的绑定（如单击窗口右上角的红叉）。 数据模型提供了一组属性，用于自定义交互模型或自定义显示内容（由模板确定）。  
  
 数据模型（属性）、交互模型（命令和事件）及显示模型（模板）之间的划分，可实现对控件的外观和行为的完全自定义。  
  
 最常见的控件数据模型是内容模型。 如果查看控件（如<xref:System.Windows.Controls.Button>），您将看到其具有名为"内容"的类型<xref:System.Object>属性。 在 Windows 窗体和ASP.NET中，此属性通常是字符串，但是这限制了可以放入按钮的内容类型。 按钮的内容可以是简单的字符串、复杂的数据对象或整个元素树。 如果是数据对象，可以使用数据模板构造显示内容。  
  
<a name="Summary"></a>
## <a name="summary"></a>总结  
 WPF 旨在允许您创建动态数据驱动的演示系统。 系统的每一部分均可通过驱动行为的属性集来创建对象。 数据绑定是系统的基础部分，在每一层中均进行了集成。  
  
 传统的应用程序创建一个显示内容，然后绑定到某些数据。 在 WPF 中，有关控件的所有内容（显示的各个方面）都由某种类型的数据绑定生成。 通过在按钮内部创建复合控件并将其显示内容绑定到按钮的内容属性，会显示按钮中的文本。  
  
 当您开始开发基于 WPF 的应用程序时，它应该感觉非常熟悉。 您可以设置属性、使用对象和数据绑定的方式与使用 Windows 窗体或ASP.NET大致相同。 通过对 WPF 体系结构的更深入调查，您会发现存在创建更丰富的应用程序的可能性，这些应用程序从根本上将数据视为应用程序的核心驱动因素。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Threading.DispatcherObject>
- <xref:System.Windows.Input.CommandBinding>
- <xref:System.Windows.Controls.Control>
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [布局](layout.md)
- [动画概述](../graphics-multimedia/animation-overview.md)
