---
title: Trees
ms.date: 03/30/2017
helpviewer_keywords:
- logical tree [WPF]
- element tree [WPF]
- visual tree [WPF]
ms.assetid: e83f25e5-d66b-4fc7-92d2-50130c9a6649
ms.openlocfilehash: aed4350f1a7084b7894a70ac9d6d00cf25b39e34
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646201"
---
# <a name="trees-in-wpf"></a>WPF 中的树
在许多技术中，元素和组件都按树结构的形式组织。在这种结构中，开发人员可以直接操作树中的对象节点来影响应用程序的绘制或行为。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 也使用了若干树结构形式来定义程序元素之间的关系。 多数情况下，在概念层面考虑对象树形式时，WPF 开发人员会用代码创建应用程序，或用 XAML 定义应用程序的组成部分，但他们会调用具体的 API 或使用特定的标记来执行此操作，而不是像在 XML DOM 中那样，使用某些常规对象树操作 API。 WPF 公开两个提供树隐喻视图的帮助器类，<xref:System.Windows.LogicalTreeHelper>和<xref:System.Windows.Media.VisualTreeHelper>。 WPF 文档中还使用了“可视化树”和“逻辑树”两个术语，它们有助于理解某些关键 WPF 功能的行为。 本主题定义可视化树和逻辑树代表的内容，讨论此类树与整体对象树概念的关系，并介绍<xref:System.Windows.LogicalTreeHelper>和。 <xref:System.Windows.Media.VisualTreeHelper>  

<a name="element_tree"></a>
## <a name="trees-in-wpf"></a>WPF 中的树  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中，最完整的树结构是对象树。 如果在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中定义一个应用程序页，然后加载 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，将根据标记中元素之间的嵌套关系来创建树结构。 如果使用代码定义应用程序或应用程序的一部分，则将根据为属性（属性实现给定对象的内容模型）分配属性值的方式来创建树结构。 在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中，完整的对象树可通过两种方式进行概念化并报告给其公共 API：作为逻辑树和作为可视化树。 逻辑树与可视化树之间的区别不一定重要，但在某些 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 子系统中它们偶尔可能会导致问题，并影响你对标记或代码的选择。  
  
 尽管你并不会总是直接操作逻辑树或可视化树，但理解它们之间的关系有助于你从技术角度了解 WPF。 若要理解 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中属性继承和事件路由的工作原理，将 WPF 视为某种树形式也相当重要。  
  
> [!NOTE]
> 因为对象树更像是概念，而不像是实际 API，所以还可以将此概念视为对象图。 实际上，在运行时，对象之间的某些关系不能由树形式表示。 尽管如此，树形式的相关性还是很强，尤其是对于 XAML 定义的 UI。因此，大多数 WPF 文档在引用这个常见概念时，仍使用术语“对象树”。  
  
<a name="logical_tree"></a>
## <a name="the-logical-tree"></a>逻辑树  
 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中，通过为支持 UI 元素的对象设置属性，可以向这些 UI 元素添加内容。 例如，通过操作控件<xref:System.Windows.Controls.ListBox><xref:System.Windows.Controls.ItemsControl.Items%2A>的属性将项添加到控件。 通过执行此操作，您将项放入属性值<xref:System.Windows.Controls.ItemCollection>。 <xref:System.Windows.Controls.ItemsControl.Items%2A> 同样，要向 中添加<xref:System.Windows.Controls.DockPanel>对象，可以操作<xref:System.Windows.Controls.Panel.Children%2A>其属性值。 在这里，您将对象添加到 。 <xref:System.Windows.Controls.UIElementCollection> 有关代码示例，请参阅[如何：动态添加元素](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms752374(v=vs.100))。  
  
 在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]<xref:System.Windows.Controls.ListBox>中，在 或 控件或其他 UI 元素中<xref:System.Windows.Controls.DockPanel>放置列表项时，也会显式<xref:System.Windows.Controls.ItemsControl.Items%2A>或<xref:System.Windows.Controls.Panel.Children%2A>隐式使用 和 属性，如以下示例所示。  
  
 [!code-xaml[TreeOvwsSupport#AllCode](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeOvwsSupport/CS/page1.xaml#allcode)]  
  
 如果此 XAML 是作为文档对象模型下的 XML 进行处理，且已包含作为隐式项禁止注释的标记（可能是合法的），生成的 XML DOM 树已包含 `<ListBox.Items>` 的元素以及其他隐式项。 但是，读取标记和写入对象时，XAML 不会这样处理，生成的对象图不包含 `ListBox.Items`。 但是，它确实有一<xref:System.Windows.Controls.ListBox>个属性`Items`，该属性名为<xref:System.Windows.Controls.ItemCollection>，其中包含<xref:System.Windows.Controls.ItemCollection>， 并且在处理<xref:System.Windows.Controls.ListBox>XAML 时初始化但为空。 然后，作为 内容<xref:System.Windows.Controls.ListBox>存在的每个子对象元素将添加到<xref:System.Windows.Controls.ItemCollection>分析器调用`ItemCollection.Add`的 。 此示例将 XAML 处理成对象树，目前这似乎表明所创建的对象树基本上是逻辑树。  
  
 但是，逻辑树不是应用程序 UI 在运行时存在的整个对象图，即使不考虑 XAML 隐式语法项也是如此。主要原因是视觉对象和模板。 例如，请考虑 。 <xref:System.Windows.Controls.Button> 逻辑树报告<xref:System.Windows.Controls.Button>对象及其字符串`Content`。 但在运行时对象树中，此按钮还有更多内容。 特别是，该按钮仅以它的方式出现在屏幕上，因为应用了特定的<xref:System.Windows.Controls.Button>控件模板。 来自应用模板的可视化对象（如视觉按钮周围的深灰色模板定义<xref:System.Windows.Controls.Border>）不会在逻辑树中报告，即使您在运行时查看逻辑树（例如处理来自可见 UI 的输入事件，然后读取逻辑树）。 若要查找模板视觉对象，需要改为检查可视化树。  
  
 有关 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 语法如何映射到所创建的对象图，以及 XAML 中隐式语法的详细信息，请参阅 [XAML 语法详述](xaml-syntax-in-detail.md)或 [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)。  
  
<a name="tree_property_inheritance_event_routing"></a>
### <a name="the-purpose-of-the-logical-tree"></a>逻辑树用途  
 借助逻辑树，内容模型可以方便地循环访问其可能的子对象，从而实现扩展。 此外，逻辑树还为某些通知提供框架，例如在加载逻辑树中的所有对象时。 基本上，逻辑树是框架级别的近似运行时对象图（排除了视觉对象），但其足以用于对你自己的运行时应用程序组合执行多种查询操作。  
  
 此外，静态和动态资源引用都通过向上查看初始请求<xref:System.Windows.FrameworkElement.Resources%2A>对象集合的逻辑树来解决，然后继续逻辑树并检查每个<xref:System.Windows.FrameworkElement>（或<xref:System.Windows.FrameworkContentElement>） 另一`Resources`<xref:System.Windows.ResourceDictionary>个值，其中包含 可能包含该键。 当同时存在逻辑树和可视化树时，将使用逻辑树进行资源查找。 有关资源字典和查找的详细信息，请参见 [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。  
  
<a name="composition"></a>
### <a name="composition-of-the-logical-tree"></a>逻辑树的构成  
 逻辑树在 WPF 框架级别定义，这意味着与逻辑树操作最相关的 WPF 基元素是 或<xref:System.Windows.FrameworkElement><xref:System.Windows.FrameworkContentElement>。 但是，正如您所看到的是否实际使用 API<xref:System.Windows.LogicalTreeHelper>一样，逻辑树有时包含不是 或<xref:System.Windows.FrameworkElement><xref:System.Windows.FrameworkContentElement>的节点。 例如，逻辑树报告 的值<xref:System.Windows.Controls.TextBlock.Text%2A><xref:System.Windows.Controls.TextBlock>，该值是字符串。  
  
<a name="override_logical_tree"></a>
### <a name="overriding-the-logical-tree"></a>替代逻辑树  
 高级控件作者可以通过重写几个 API 来覆盖逻辑树，这些 API 定义常规对象或内容模型如何添加或删除逻辑树中的对象。 有关如何替代逻辑树的示例，请参阅[替代逻辑树](how-to-override-the-logical-tree.md)。  
  
<a name="pvi"></a>
### <a name="property-value-inheritance"></a>属性值继承  
 属性值继承通过混合树操作。 包含启用属性继承<xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>的属性的实际元数据是 WPF 框架级<xref:System.Windows.FrameworkPropertyMetadata>类。 因此，保存原始值的父项和继承该值的子对象都必须为<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>，并且它们都必须是某个逻辑树的一部分。 但是，对于支持属性继承的现有 WPF 属性，属性值的继承可通过逻辑树中没有的中介对象永久存在。 这主要适用于以下情况：让模板元素使用在应用了模板的实例上设置的任何继承属性值，或者使用在更高级别的页级构成（因此在逻辑树中也位于更高位置）中设置的任何继承属性值。 为了使属性值的继承在这两种情况下保持一致，继承属性必须注册为附加属性。如果要定义具有属性继承行为的自定义依赖属性，则应采用这种模式。 无法通过帮助器类实用工具方法完全预测属性继承确切使用的树，即使在运行时也是如此。 有关详细信息，请参阅[属性值继承](property-value-inheritance.md)。  
  
<a name="two_trees"></a>
## <a name="the-visual-tree"></a>可视化树  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中除了逻辑树的概念，还存在可视化树的概念。 可视化树描述可视对象的结构，如<xref:System.Windows.Media.Visual>基类表示。 为控件编写模板时，将定义或重新定义适用于该控件的可视化树。 对于出于性能和优化考虑需要对绘图进行较低级别控制的开发人员来说，他们也会对可视化树感兴趣。 在传统 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序编程中，可视化树的一个应用是：路由事件的事件路由大多遍历可视化树而非逻辑树。 路由事件行为的这种微妙之处可能不会很明显，除非你是控件作者。 通过可视化树对事件进行路由可使控件在可视化级别实现组合以处理事件或创建事件资源库。  
  
<a name="trees_content"></a>
## <a name="trees-content-elements-and-content-hosts"></a>树、内容元素和内容宿主  
 内容元素（派生自 的<xref:System.Windows.ContentElement>类）不是可视化树的一部分;因此，内容元素（派生自 的类）不是可视化树的一部分。它们不继承<xref:System.Windows.Media.Visual>，也没有可视表示形式。 为了在 UI 中显示 ，<xref:System.Windows.ContentElement>必须在 既是<xref:System.Windows.Media.Visual>逻辑树参与者的内容主机中托管的。 通常这样的对象是 。 <xref:System.Windows.FrameworkElement> 从概念上讲，内容宿主有些类似于内容的“浏览器”，它选择在该宿主控制的屏幕区域中显示内容的方式。 承载内容时，可以使内容成为通常与可视化树关联的某些树进程的参与者。 通常，<xref:System.Windows.FrameworkElement>主机类包括实现代码，该代码通过内容<xref:System.Windows.ContentElement>逻辑树的子节点将任何托管添加到事件路由，即使托管内容不是真正可视化树的一部分。 这是必要的，以便 可以<xref:System.Windows.ContentElement>源路由到任何元素（而不是其自身）的路由事件。  
  
<a name="tree_traversal"></a>
## <a name="tree-traversal"></a>树遍历  
 类<xref:System.Windows.LogicalTreeHelper>提供<xref:System.Windows.LogicalTreeHelper.GetChildren%2A><xref:System.Windows.LogicalTreeHelper.GetParent%2A>逻辑树遍历<xref:System.Windows.LogicalTreeHelper.FindLogicalNode%2A>的 和 方法。 在大多数情况下，不需要遍历现有控件的逻辑树，因为这些控件几乎总是将其逻辑子元素公开为一个专用集合属性，这种属性支持集合访问，如 `Add`、索引器等等。 树遍历主要是一种方案，由选择不从预期控制模式（如已定义集合属性）或<xref:System.Windows.Controls.ItemsControl><xref:System.Windows.Controls.Panel>已定义集合属性或打算提供自己的集合属性支持的控件作者使用的方案。  
  
 可视化树还支持可视化树遍历的帮助器类<xref:System.Windows.Media.VisualTreeHelper>。 可视化树不会通过特定于控件的属性轻易公开，因此，如果编程方案需要，<xref:System.Windows.Media.VisualTreeHelper>则建议使用该类遍历可视化树。 有关详细信息，请参阅 [WPF 图形呈现概述](../graphics-multimedia/wpf-graphics-rendering-overview.md)。  
  
> [!NOTE]
> 有时有必要检查所应用模板的可视化树。 执行此操作时应谨慎。 即使您正在遍历控件的可视化树，并且控件的使用者始终可以通过在实例上设置<xref:System.Windows.Controls.Control.Template%2A>该属性来更改模板，甚至最终用户也可以通过更改系统主题来影响应用的模板。  
  
<a name="routes"></a>
## <a name="routes-for-routed-events-as-a-tree"></a>“树”形式路由事件的路由  
 如前所述，对于任何给定的路由事件，其路由都沿着一条预定的树路径进行，这棵树是可视化树和逻辑树表示形式的混合体。 事件路由可在树中向上或向下进行，具体取决于该事件是隧道路由事件还是浮升路由事件。 事件路由概念没有直接支持的帮助器类（此类可用于独立于引发实际路由的事件，遍历事件）。 有一个类表示路由，<xref:System.Windows.EventRoute>但该类的方法通常仅供内部使用。  
  
<a name="resourcesandtrees"></a>
## <a name="resource-dictionaries-and-trees"></a>资源字典和树  
 对页中定义的所有 `Resources` 进行资源字典查找时，基本上遍历逻辑树。 逻辑树之外的对象可以引用键控资源，但资源查找顺序将从该对象与逻辑树的连接点开始。 在 WPF 中，只有逻辑树节点`Resources`可以具有包含 的属性<xref:System.Windows.ResourceDictionary>，因此遍历可视树以查找 抠资源没有好处<xref:System.Windows.ResourceDictionary>。  
  
 但是，资源查找也可以超出直接逻辑树。 对于应用程序标记，资源查找可向前继续进行到应用程序级资源字典，然后再到作为静态属性或键进行引用的主题支持和系统值。 如果资源引用是动态的，则主题本身也可以引用主题逻辑树之外的系统值。 有关资源字典和查找逻辑的详细信息，请参阅 [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。  
  
## <a name="see-also"></a>另请参阅

- [输入概述](input-overview.md)
- [WPF 图形呈现疑难解答](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [路由事件概述](routed-events-overview.md)
- [不在对象树中的对象元素的初始化](initialization-for-object-elements-not-in-an-object-tree.md)
- [WPF 体系结构](wpf-architecture.md)
