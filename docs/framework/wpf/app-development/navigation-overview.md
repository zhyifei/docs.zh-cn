---
title: 导航概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loose XAML files [WPF]
- windows [WPF]
- Start page [WPF]
- HTML files [WPF]
- structured navigation [WPF]
- fragment navigation [WPF]
- URIs (Uniform Resource Identifiers)
- custom objects [WPF]
- Uniform Resource Identifiers (URIs)
- pages [WPF]
- frames [WPF]
- navigation hosts [WPF]
- journals [WPF]
- lifetimes [WPF]
- retaining content state [WPF]
- content state [WPF]
- programmatic navigation [WPF]
- hyperlinks [WPF]
ms.assetid: 86ad2143-606a-4e34-bf7e-51a2594248b8
ms.openlocfilehash: 874bc0b1b0ac38210569632dc3d21ed727ae26e4
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291645"
---
# <a name="navigation-overview"></a>导航概述

Windows Presentation Foundation （WPF）支持可在两种类型的应用程序中使用的浏览器样式的导航：独立应用程序和 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]。 若要打包内容以便导航，@no__t 提供 @no__t 1 类。 您可以通过使用 @no__t 以声明方式从一个 <xref:System.Windows.Controls.Page> 导航到另一个，也可以使用 <xref:System.Windows.Navigation.NavigationService> 以编程方式导航。 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 使用日志记住从其导航和导航回它们的页。

<xref:System.Windows.Controls.Page>，<xref:System.Windows.Documents.Hyperlink>，<xref:System.Windows.Navigation.NavigationService>，而日记构成 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供的导航支持的核心。 本概述首先详细探讨这些功能，然后介绍高级导航支持，其中包括指向松散 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 文件、HTML 文件和对象的导航。

> [!NOTE]
> 在本主题中，术语 "浏览器" 只引用可以承载 @no__t 0 应用程序的浏览器，当前包括 Microsoft Internet Explorer 和 Firefox。 只有特定的浏览器支持特定 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 功能，浏览器版本被称为。

## <a name="navigation-in-wpf-applications"></a>WPF 应用程序中的导航

本主题概述了 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中的关键导航功能。 这些功能适用于独立应用程序和 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]，但本主题在 @no__t 的上下文中提供了这些功能。

> [!NOTE]
> 本主题不讨论如何生成和部署 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]。 有关 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 的详细信息，请参阅[WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)。

本节解释并演示导航的以下方面：

- [实现页](#CreatingAXAMLPage)

- [配置起始页](#Configuring_a_Start_Page)

- [配置主机窗口的标题、宽度和高度](#ConfiguringAXAMLPage)

- [超链接导航](#NavigatingBetweenXAMLPages)

- [片段导航](#FragmentNavigation)

- [导航服务](#NavigationService)

- [使用导航服务以编程方式导航](#Programmatic_Navigation_with_the_Navigation_Service)

- [导航生存期](#Navigation_Lifetime)

- [使用日志记住导航](#NavigationHistory)

- [页生存期和日志](#PageLifetime)

- [保留导航历史记录的内容状态](#RetainingContentStateWithNavigationHistory)

- [Cookie](#Cookies)

- [结构化导航](#Structured_Navigation)

<a name="CreatingAXAMLPage"></a>

### <a name="implementing-a-page"></a>实现页

在 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中，可以导航到多个内容类型，其中包括 .NET Framework 对象、自定义对象、枚举值、用户控件、@no__t 1 文件和 HTML 文件。 不过，你会发现打包内容最常见和最方便的方法是使用 <xref:System.Windows.Controls.Page>。 此外，@no__t 0 实现了特定于导航的功能，以增强其外观和简化开发。

使用 <xref:System.Windows.Controls.Page>，可以通过使用如下所示的标记以声明方式实现 @no__t 1 内容的可导航页面。

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

在 @no__t 的标记中实现的 @no__t 为 `Page` 作为其根元素，需要 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] @ no__t 命名空间声明。 @No__t-0 元素包含要导航并显示的内容。 可以通过设置 @no__t 的属性元素来添加内容，如以下标记所示。

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content` 只能包含一个子元素，在前面的实例中，内容是一个单独的字符串“Hello, Page!”。 在实践中，通常会使用布局控件作为子元素（请参阅[布局](../advanced/layout.md)）来包含内容并撰写内容。

@No__t-0 元素的子元素被视为 @no__t 的内容，因此，不需要使用显式的 `Page.Content` 声明。 以下标记和前面的示例在声明上是等效的。

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

在这种情况下，`Page.Content` 会自动设置为 @no__t 元素的子元素。 有关详细信息，请参阅 [WPF 内容模型](../controls/wpf-content-model.md)。

仅标记 <xref:System.Windows.Controls.Page> 可用于显示内容。 但是，@no__t 0 还可以显示允许用户与页面交互的控件，并且它可以通过处理事件和调用应用程序逻辑来响应用户交互。 交互式 <xref:System.Windows.Controls.Page> 通过结合使用标记和代码隐藏来实现，如以下示例中所示。

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

要允许标记文件和代码隐藏文件协同工作，需要进行以下配置：

- 在标记中，`Page` 元素必须包含 `x:Class` 属性。 在生成应用程序时，标记文件中 @no__t 的存在会导致 Microsoft 生成引擎（MSBuild）创建从 <xref:System.Windows.Controls.Page> 派生的 @no__t 1 类，并具有 `x:Class` 属性指定的名称。 这要求为 @no__t 架构（`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`）添加 @no__t 的命名空间声明。 生成的 @no__t 0 类实现 `InitializeComponent`，调用它来注册事件并设置在标记中实现的属性。

- 在代码隐藏中，类必须是一个 `partial` 类，其名称与标记中 `x:Class` 属性指定的名称相同，并且必须从 <xref:System.Windows.Controls.Page> 派生。 这样，代码隐藏文件就会与生成应用程序时为标记文件生成的 @no__t 0 类相关联（请参阅[生成 WPF 应用程序](building-a-wpf-application-wpf.md)）。

- 在代码隐藏中，@no__t 0 类必须实现调用 `InitializeComponent` 方法的构造函数。 `InitializeComponent` 由标记文件生成的 @no__t 1 类实现，用于注册事件和设置在标记中定义的属性。

> [!NOTE]
> 使用 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 将新的 @no__t 0 添加到你的项目时，将使用标记和代码隐藏来实现 <xref:System.Windows.Controls.Page>，并包括必要的配置以创建标记和代码隐藏文件之间的关联，如此处所述。

如果有 <xref:System.Windows.Controls.Page>，则可以导航到它。 若要指定应用程序导航到的第一个 <xref:System.Windows.Controls.Page>，需要将 start @no__t 配置为-1。

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>配置起始页

[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 需要一定数量的应用程序结构以在浏览器中托管。 在 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中，<xref:System.Windows.Application> 类是应用程序定义的一部分，该定义用于建立所需的应用程序基础结构（请参阅[应用程序管理概述](application-management-overview.md)）。

通常使用标记和代码隐藏来实现应用程序定义，并将标记文件配置为 MSBuild @ no__t-0 项。 下面是 @no__t 的应用程序定义。

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

@No__t-0 可以使用其应用程序定义来指定开始 <xref:System.Windows.Controls.Page>，这是在启动 @no__t 3 时自动加载的 @no__t。 为此，可将 <xref:System.Windows.Application.StartupUri%2A> 属性设置为所需 @no__t 的 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]。

> [!NOTE]
> 在大多数情况下，<xref:System.Windows.Controls.Page> 编译到应用程序中或与应用程序一起部署。 在这些情况下，标识 @no__t 的 @no__t 0 是一个 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]，这是符合*pack*方案的 @no__t 3。 在[WPF 的 Pack uri](pack-uris-in-wpf.md)中进一步讨论了 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]。 也可使用 http 方案导航到内容，这将在以下内容中讨论。

可以在标记中以声明方式设置 <xref:System.Windows.Application.StartupUri%2A>，如下面的示例中所示。

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

在此示例中，使用标识主页的相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 设置 `StartupUri` 属性。 如果 @no__t 为 "已启动"，则会自动导航并显示 "主页"。 下图对此进行了演示，其中显示了从 Web 服务器启动的 @no__t 0。

![Xbap 页面](./media/navigation-overview/xbap-launched-from-a-web-server.png "这会显示从 Web 服务器启动的 xbap。")

> [!NOTE]
> 有关开发和部署 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 的详细信息，请参阅[WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)和[部署 WPF 应用程序](deploying-a-wpf-application-wpf.md)。

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>配置主机窗口的标题、宽度和高度

您从上图中可以看到的一件事情是：浏览器和选项卡面板的标题都是 @no__t @no__t 为0。 除了长，标题既没什么吸引力也没什么帮助。 出于此原因，@no__t 为您提供了一种方法来通过设置 @no__t 属性来更改标题。 此外，还可以通过分别设置 @no__t 0 和 @no__t 来配置浏览器窗口的宽度和高度。

可以在标记中以声明方式设置 <xref:System.Windows.Controls.Page.WindowTitle%2A>、<xref:System.Windows.Controls.Page.WindowWidth%2A> 和 <xref:System.Windows.Controls.Page.WindowHeight%2A>，如下面的示例中所示。

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

结果如下图所示。

![窗口标题、高度、宽度](./media/navigation-overview/window-title-width-height.png "这将显示您可以配置的窗口标题、高度和宽度。")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>超链接导航

典型 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 包含多个页面。 若要从一页导航到另一页，最简单的方法是使用 <xref:System.Windows.Documents.Hyperlink>。 你可以使用以下标记中所示的 `Hyperlink` 元素以声明方式将 @no__t 0 添加到 @no__t。

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

@No__t 0 元素需要以下各项：

- 要导航到的 @no__t 的包 <xref:System.Windows.Controls.Page>，由 `NavigateUri` 特性指定。

- 用户可以单击以启动导航的内容（如文本和图像（对于 @no__t 0 元素可以包含的内容），请参阅 <xref:System.Windows.Documents.Hyperlink>）。

下图显示了一个 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]，其 @no__t 为 @no__t。

![包含超链接的页面](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "这会显示一个包含超链接的页的 XBAP。")

正如您所期望的那样，单击 <xref:System.Windows.Documents.Hyperlink> 会导致 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 导航到 `NavigateUri` 属性标识的 @no__t。 此外，[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 会将之前 @no__t 的条目添加到 Internet Explorer 中的 "最近使用的页" 列表。 如下图所示。

"![后退" 和 "前进" 按钮](./media/navigation-overview/back-and-forward-navigation.png "用 \"后退\" 和 \"前进\" 按钮导航。")

还支持从一个 <xref:System.Windows.Controls.Page> 到另一个的导航，<xref:System.Windows.Documents.Hyperlink> 还支持片段导航。

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>片段导航

*片段导航*是对当前 <xref:System.Windows.Controls.Page> 或其他 <xref:System.Windows.Controls.Page> 中的内容片段的导航。 在 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中，内容片段是已命名元素包含的内容。 命名元素是一个具有 `Name` 属性集的元素。 下面的标记显示了一个包含内容片段的命名 @no__t 0 元素。

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

对于 <xref:System.Windows.Documents.Hyperlink> 定位到内容片段，@no__t 属性必须包括以下内容：

- @No__t 的 @no__t 0，其中包含要导航到的内容片段。

- “#”字符。

- @No__t-0 上包含内容片段的元素的名称。

分段 @no__t 为以下格式。

*PageURI* `#` *ElementName*

下面显示了一个 `Hyperlink` 的示例，该示例配置为导航到内容片段。

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> 本部分介绍 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中的默认片段导航实现。 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 还允许实现自己的片段导航方案，该方案在某种程度上需要处理 @no__t 的事件。

> [!IMPORTANT]
> 仅当可以通过 HTTP 浏览这些页面时，才能导航到松散 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面（仅限标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件，带 `Page` 作为根元素）中的片段。
>
> 但是，松 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面可以导航到其自己的片段。

<a name="NavigationService"></a>

### <a name="navigation-service"></a>导航服务

虽然 @no__t 允许用户启动对特定 @no__t 的导航，但查找和下载页面的工作由 @no__t 2 类执行。 实质上，<xref:System.Windows.Navigation.NavigationService> 提供了代表客户端代码处理导航请求的功能，如 @no__t。 此外，@no__t 0 还实现了对跟踪和影响导航请求的更高级别的支持。

当单击 <xref:System.Windows.Documents.Hyperlink> 时，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 将调用 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> 来查找并下载指定 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 处的 @no__t 3。 下载的 <xref:System.Windows.Controls.Page> 会转换为对象树，该树的根对象是已下载 @no__t 的实例。 对根 @no__t 0 对象的引用存储在 @no__t 属性中。 所导航到的内容的 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 存储在 @no__t 属性中，而 <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> 将包 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 存储到导航到的最后一页。

> [!NOTE]
> @No__t 的应用程序可以有多个当前处于活动状态的 <xref:System.Windows.Navigation.NavigationService>。 有关详细信息，请参阅本主题后面的[导航宿主](#Navigation_Hosts)。

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>使用导航服务以编程方式导航

如果使用 @no__t 在标记中以声明方式实现了导航，则不需要了解 <xref:System.Windows.Navigation.NavigationService>，因为 <xref:System.Windows.Documents.Hyperlink> 代表你使用 @no__t。 这意味着，只要 @no__t 的直接或间接父级是导航宿主（请参阅[导航](#Navigation_Hosts)宿主），<xref:System.Windows.Documents.Hyperlink> 将能够查找和使用导航宿主的导航服务来处理导航请求。

但是，在某些情况下，你需要直接使用 <xref:System.Windows.Navigation.NavigationService>，其中包括：

- 需要使用非参数构造函数实例化 @no__t 0 时。

- 在导航到 @no__t 时，需要在其上设置属性。

- 需要导航到的 @no__t 0 时，只能在运行时确定。

在这些情况下，需要通过调用 @no__t 的对象的 @no__t 0 方法来编写代码，以编程方式启动导航。 这需要获取对 @no__t 的引用。

#### <a name="getting-a-reference-to-the-navigationservice"></a>获取对 NavigationService 的引用

出于[导航宿主](#Navigation_Hosts)部分所述的原因，@no__t 1 应用程序可以有多个 @no__t。 这意味着，你的代码需要一种方法来查找 <xref:System.Windows.Navigation.NavigationService>，这通常是导航到当前 <xref:System.Windows.Controls.Page> @no__t。 可以通过调用 `static` @ no__t 方法来获取对 @no__t 的引用。 若要获取导航到特定 <xref:System.Windows.Controls.Page> 的 @no__t，请将对 <xref:System.Windows.Controls.Page> 的引用作为 @no__t 方法的参数进行传递。 下面的代码演示如何获取当前 @no__t 的 @no__t 0。

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

若要快捷地查找 @no__t 的 @no__t 为-1，<xref:System.Windows.Controls.Page> 实现 @no__t 3 属性。 这在下面的示例中显示。

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> 当 <xref:System.Windows.Controls.Page> 引发 @no__t 3 事件时，@no__t 0 只能获取对其 @no__t 的引用。

#### <a name="programmatic-navigation-to-a-page-object"></a>以编程方式导航到页对象

下面的示例演示如何使用 <xref:System.Windows.Navigation.NavigationService> 以编程方式导航到 @no__t 1。 需要编程式导航，因为要导航到的 @no__t 0 只能使用单个无参数的构造函数实例化。 以下标记和代码中显示了具有非参数构造函数的 <xref:System.Windows.Controls.Page>。

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

以下标记和代码中显示了导航到具有非无参数的构造函数的 @no__t 的 @no__t 0。

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

如果单击此 @no__t 上的 <xref:System.Windows.Controls.Page>，则将通过实例化 <xref:System.Windows.Controls.Page> 来启动导航，以导航到使用非参数构造函数并调用 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> 方法。 <xref:System.Windows.Navigation.NavigationService.Navigate%2A> 接受对 <xref:System.Windows.Navigation.NavigationService> 将导航到的对象的引用，而不接受对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 的引用。

#### <a name="programmatic-navigation-with-a-pack-uri"></a>使用 Pack URI 以编程方式导航

如果需要以编程方式构造 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 的包（例如，只能在运行时确定 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]），则可以使用 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> 方法。 这在下面的示例中显示。

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>刷新当前页

如果 <xref:System.Windows.Controls.Page> 的包与存储在 @no__t 属性中的 pack @no__t @no__t 相同，则不会下载该。 若要强制 @no__t 为再次下载当前页，可以调用 <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> 方法，如以下示例中所示。

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>导航生存期

如你所见，有很多方法初始化导航。 当启动导航时，导航正在进行时，你可以使用 <xref:System.Windows.Navigation.NavigationService> 实现的以下事件跟踪和影响导航：

- <xref:System.Windows.Navigation.NavigationService.Navigating>。 请求新导航时发生。 可用于取消导航。

- <xref:System.Windows.Navigation.NavigationService.NavigationProgress>。 在下载过程中定期发生，用于提供定位进度信息。

- <xref:System.Windows.Navigation.NavigationService.Navigated>。 已定位并下载页时发生。

- <xref:System.Windows.Navigation.NavigationService.NavigationStopped>。 当导航停止时发生（通过调用 <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>），或在当前导航正在进行时请求新导航时发生。

- <xref:System.Windows.Navigation.NavigationService.NavigationFailed>。 在导航到所需内容的同时遇到错误时发生。

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted>。 导航到的内容已加载和分析，并开始呈现时发生。

- <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>。 导航到内容片段开始时发生，具体如何发生如下所述：

  - 立即，如果所需片段位于当前内容中。

  - 源内容加载之后，如果所需片段在不同内容中。

引发导航事件的顺序如下图所示。

![页面导航流程图](./media/navigation-overview/order-of-navigation-events.png "页面导航事件流程图")

通常情况下，@no__t 0 不关心这些事件。 更有可能应用程序与应用程序相关，出于此原因，这些事件也由 <xref:System.Windows.Application> 类引发：

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

每次 <xref:System.Windows.Navigation.NavigationService> 引发事件时，@no__t 1 类将引发相应的事件。 <xref:System.Windows.Controls.Frame> 和 <xref:System.Windows.Navigation.NavigationWindow> 提供相同的事件来检测其各自范围内的导航。

在某些情况下，@no__t 可能对这些事件感兴趣。 例如，<xref:System.Windows.Controls.Page> 可处理 @no__t 1 事件，以确定是否取消导航。 这在下面的示例中显示。

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

如果使用 @no__t 的导航事件注册处理程序，如前面的示例所示，还必须取消注册事件处理程序。 如果不这样做，可能会对 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 导航如何使用日记记住 @no__t 1 导航的相关副作用。

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>使用日志记住导航

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 使用两个堆栈来记住导航过的页：后退堆栈和前进堆栈。 当你从当前 <xref:System.Windows.Controls.Page> 导航到新的 <xref:System.Windows.Controls.Page> 或转发到现有 <xref:System.Windows.Controls.Page> 时，当前的 @no__t 将添加到*back 堆栈*中。 当你从当前 <xref:System.Windows.Controls.Page> 导航回到之前的 <xref:System.Windows.Controls.Page> 时，当前 @no__t 将添加到*前进堆栈*中。 后退堆栈、前进堆栈和管理它们的功能统称为日志。 Back stack 和 forward 堆栈中的每一项都是 <xref:System.Windows.Navigation.JournalEntry> 类的实例，称为*日记条目*。

#### <a name="navigating-the-journal-from-internet-explorer"></a>从 Internet Explorer 导航日志

从概念上讲，日记的工作方式与 Internet Explorer 中的 "**后退**" 和 "**前进**" 按钮的操作方式相同。 这些在下图中显示。

"![后退" 和 "前进" 按钮](./media/navigation-overview/back-and-forward-navigation.png "用 \"后退\" 和 \"前进\" 按钮导航。")

对于由 Internet Explorer 承载的 @no__t 0，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 将日记集成到 Internet Explorer 的导航 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 这允许用户使用 Internet Explorer 中的 "**后退**"、"**前进**" 和 "**最新页**" 按钮在 @no__t 中导航页面。

> [!IMPORTANT]
> 在 Internet Explorer 中，当用户离开并返回到 @no__t 时，只有未保持活动状态的页的日记条目保留在日志中。 有关保持页处于活动状态的讨论，请参阅本主题后面的[页生存期和日志](#PageLifetime)。

默认情况下，在 Internet Explorer 的 "**最新页**" 列表中显示的每个 <xref:System.Windows.Controls.Page> 的文本都是 @no__t 的 @no__t。 很多情况下这对用户并没有什么特殊的意义。 幸运的是，可以使用以下选项更改文本：

1. 附加的 `JournalEntry.Name` 特性值。

2. @No__t-0 特性值。

3. 当前 <xref:System.Windows.Controls.Page> 的 `Page.WindowTitle` 属性值和 @no__t。

4. 当前 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 的 <xref:System.Windows.Controls.Page>。 (默认)

选项列出的顺序和查找文本的优先级顺序一致。 例如，如果设置了 `JournalEntry.Name`，则忽略其他值。

下面的示例使用 `Page.Title` 特性来更改为日记本项显示的文本。

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>使用 WPF 导航日志

尽管用户可以使用 Internet Explorer 中的 "**后退**"、"**前进**" 和 "**最新" 页**导航日记，但你也可以使用 @no__t 提供的声明性和编程机制导航日志。 这样做的一个原因是在页面中提供自定义导航 Ui。

可以通过使用 <xref:System.Windows.Input.NavigationCommands> 公开的导航命令以声明方式添加日记本导航支持。 下面的示例演示如何使用 @no__t 的导航命令。

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

可以通过使用 <xref:System.Windows.Navigation.NavigationService> 类的以下成员之一以编程方式导航日记：

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

此日志还可以通过编程方式进行操作，如本主题后面的将[内容状态保留为导航历史记录](#RetainingContentStateWithNavigationHistory)中所述。

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a>页生存期和日志

请考虑一个 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]，其中包含多个包含丰富内容的页面，包括图形、动画和媒体。 这类页的内存占用量可能相当大，尤其是使用视频和音频媒体的时候。 假设日志 "记住" 已导航到的页面，此类 @no__t 会迅速消耗大量内存量。

出于此原因，日志的默认行为是在每个日记条目中存储 @no__t 的元数据，而不是对 @no__t 的对象的引用。 导航到某个日志条目时，其 @no__t 的元数据用于创建指定 @no__t 的新实例。 因此，所导航的每个 @no__t 0 都具有如下图所示的生存期。

![页面生存期](./media/navigation-overview/navigated-page-lifetime.png "：导航页面时显示生存期。")

尽管使用默认日记行为可以节省内存消耗，但每页呈现性能可能会降低;呈现 <xref:System.Windows.Controls.Page> 会很耗时，尤其是在有大量内容时。 如果需要在日记中保留 <xref:System.Windows.Controls.Page> 实例，可以通过两种方法进行绘制。 首先，可以通过调用 @no__t 的方法以编程方式导航到 <xref:System.Windows.Controls.Page> 对象。

其次，可以通过将 <xref:System.Windows.Controls.Page.KeepAlive%2A> 属性设置为 `true` （默认值为 `false`）来指定 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 在日志中保留 @no__t 的实例。 如以下示例中所示，可以在标记中以声明方式设置 <xref:System.Windows.Controls.Page.KeepAlive%2A>。

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

保持活动状态的 @no__t 的生存期与不是相同。 第一次导航到 <xref:System.Windows.Controls.Page> 时，将会将其实例化，就像 @no__t 不会保持活动状态一样。 但是，因为 <xref:System.Windows.Controls.Page> 的实例保留在日志中，因此只要它保留在日志中，就永远不会再对其进行实例化。 因此，如果 @no__t 的初始化逻辑需要在每次导航到 @no__t 时调用，则应将其从构造函数移到 @no__t 2 事件的处理程序中。 如下图所示，每次导航到和从 <xref:System.Windows.Controls.Page> 时，仍然会引发 <xref:System.Windows.FrameworkElement.Loaded> 和 @no__t 1 事件。

当向外和向外导航页面时，将![引发加载的和已卸载的事件](./media/navigation-overview/loaded-and-unloaded-events.png "，并引发已卸载的事件。")

如果 @no__t 0 未保持活动状态，则不应执行以下任一操作：

- 存储对它或它的任何部分的引用。

- 将事件处理程序注册到并非由其实现的事件。

执行上述任一操作都将创建强制在内存中保留 @no__t 的引用，即使已从日志中删除。

通常，您应该首选默认 <xref:System.Windows.Controls.Page> 行为，不会使 @no__t 保持活动状态。 但是，这会存在将在下一节中讨论的状态影响。

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>保留导航历史记录的内容状态

如果 @no__t 0 未保持活动状态，并且它具有收集用户数据的控件，则当用户离开并返回到 @no__t 时，数据会发生什么情况？ 从用户体验角度，用户应该会希望看到他们以前输入的数据。 遗憾的是，由于每个导航都创建了 <xref:System.Windows.Controls.Page> 的新实例，因此收集数据的控件重新实例化，数据会丢失。

幸运的是，日记本提供对在 <xref:System.Windows.Controls.Page> 导航（包括控制数据）之间记录数据的支持。 具体而言，每个 @no__t 的日记条目都充当关联的 <xref:System.Windows.Controls.Page> 状态的临时容器。 以下步骤概述了从导航 <xref:System.Windows.Controls.Page> 时如何使用此支持：

1. 当前 <xref:System.Windows.Controls.Page> 的条目将添加到日志中。

2. @No__t 的状态与该页面的日记条目一起存储，该条目将添加到后堆栈中。

3. 将导航到新 <xref:System.Windows.Controls.Page>。

当使用日记向后导航到 <xref:System.Windows.Controls.Page> 页面时，将执行以下步骤：

1. @No__t （back 堆栈顶部的日记条目）实例化。

2. 将用与 @no__t 的日记条目一起存储的状态来刷新 <xref:System.Windows.Controls.Page>。

3. 向后导航到 <xref:System.Windows.Controls.Page>。

在 @no__t 上使用以下控件时 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 自动使用此支持：

- <xref:System.Windows.Controls.CheckBox>

- <xref:System.Windows.Controls.ComboBox>

- <xref:System.Windows.Controls.Expander>

- <xref:System.Windows.Controls.Frame>

- <xref:System.Windows.Controls.ListBox>

- <xref:System.Windows.Controls.ListBoxItem>

- <xref:System.Windows.Controls.MenuItem>

- <xref:System.Windows.Controls.ProgressBar>

- <xref:System.Windows.Controls.RadioButton>

- <xref:System.Windows.Controls.Slider>

- <xref:System.Windows.Controls.TabControl>

- <xref:System.Windows.Controls.TabItem>

- <xref:System.Windows.Controls.TextBox>

如果 <xref:System.Windows.Controls.Page> 使用这些控件，则会在 @no__t 1 导航中记录输入的数据，如下图所**示 @no__t-** 3 中所示。

![包含控件的页面，这些控件可记住输入的状态](./media/navigation-overview/data-remembered-across-page-navigations.png "数据跨页面导航。")

如果 @no__t 为除前面列表中的控件以外的其他控件，或者当状态存储在自定义对象中时，则需要编写代码来使日志记住 @no__t 导航中的状态。

如果需要在 <xref:System.Windows.Controls.Page> 导航之间记录小部分的状态，可以使用配置了 <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> 元数据标志的依赖属性（请参阅 <xref:System.Windows.DependencyProperty>）。

如果 @no__t 0 需要记住的每个导航的状态包含多个数据片段，你可能会发现，将状态封装到单个类并实现 @no__t 1 接口所需的代码要少得多。

如果需要在单个 @no__t 的各个状态之间导航，而无需从 @no__t 中导航，则可以使用 <xref:System.Windows.Navigation.IProvideCustomContentState> 和 @no__t。

<a name="Cookies"></a>

### <a name="cookies"></a>Cookie

@No__t 0 应用程序可以存储数据的另一种方式是使用 cookie，这些 cookie 是使用 @no__t 1 和 @no__t 2 方法创建、更新和删除的。 可以在 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中创建的 cookie 与其他类型的 Web 应用程序使用的 cookie 相同;cookie 是由应用程序在客户端计算机上或跨应用程序会话存储的任意数据块。 Cookie 数据通常采用以下格式的名称/值对的形式。

*Name* `=` *Value*

如果将数据传递到 <xref:System.Windows.Application.SetCookie%2A>，以及应为其设置 cookie 的位置的 @no__t 1，则会在内存中创建一个 cookie，并且该 cookie 仅适用于当前应用程序会话的持续时间。 这种类型的 cookie 称为*会话 cookie*。

要跨应用程序会话存储 cookie，必须使用以下格式将到期日期添加到 cookie。

*NAME* `=` *VALUE* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

在 cookie 过期之前，具有到期日期的 cookie 存储在当前的 Windows 安装程序的临时 Internet Files 文件夹中。 此类 cookie 称为*永久性 cookie* ，因为它在应用程序会话之间保持不变。

可以通过调用 <xref:System.Windows.Application.GetCookie%2A> 方法来检索会话和永久性 cookie，同时传递使用 <xref:System.Windows.Application.SetCookie%2A> 方法设置 cookie 的位置的 @no__t 1。

下面是在 @no__t 中支持 cookie 的一些方式：

- @no__t 0 独立应用程序，[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 可创建和管理 cookie。

- 可以从浏览器访问 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 创建的 cookie。

- 来自相同域的 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 可以创建和共享 cookie。

- @no__t （0）和来自同一域的 HTML 页面可以创建和共享 cookie。

- 当 @no__t 0 和松散的 @no__t 1 页发出 Web 请求时，会调度 cookie。

- 在 IFRAME 中承载的顶级 @no__t （0）和 @no__t 1 均可访问 cookie。

- @No__t-0 中的 Cookie 支持对于所有受支持的浏览器都是相同的。

- 在 Internet Explorer 中，与 cookie 相关的 P3P 策略可通过 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 进行处理，特别是对于第一方和第三方 @no__t。

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>结构化导航

如果需要将数据从一个 <xref:System.Windows.Controls.Page> 传递到另一个，则可以将数据作为参数传递到 @no__t 的非参数构造函数。 请注意，如果使用此方法，则必须保持 <xref:System.Windows.Controls.Page> 活动状态;否则，下一次导航到 <xref:System.Windows.Controls.Page> 时，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 使用无参数构造函数重新实例化 @no__t。

或者，<xref:System.Windows.Controls.Page> 可以实现用需要传递的数据设置的属性。 不过，当 <xref:System.Windows.Controls.Page> 需要将数据传递回导航到它的 <xref:System.Windows.Controls.Page> 时，这会变得棘手。 问题在于，导航不会以本机方式支持用于确保在从其导航后将返回 <xref:System.Windows.Controls.Page> 的机制。 实质上，导航不支持调用/返回语义。 若要解决此问题，@no__t 提供 @no__t 1 类，可用于确保以可预测和结构化方式返回 @no__t。 有关详细信息，请参阅[结构化导航概述](structured-navigation-overview.md)。

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>NavigationWindow 类

到目前为止，你已全面了解最有可能用可导航内容生成应用程序的导航服务。 这些服务是在 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 的上下文中讨论的，不过它们并不限于 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]。 现代操作系统和 Windows 应用程序利用了新式用户的浏览器体验，将浏览器样式的导航并入独立的应用程序。 常见示例包括：

- **Word 同义词库**：导航 word 选项。

- **文件资源管理器**：导航文件和文件夹。

- **向导**：将复杂任务分解到多个可在之间导航的页面。 例如，处理添加和删除 Windows 功能的 Windows 组件向导。

若要将浏览器样式的导航并入独立应用程序，可以使用 <xref:System.Windows.Navigation.NavigationWindow> 类。 @no__t 派生自 <xref:System.Windows.Window>，并将其扩展为支持 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 提供的导航。 你可以使用 <xref:System.Windows.Navigation.NavigationWindow> 作为独立应用程序的主窗口，或者使用作为辅助窗口（如对话框）。

若要实现 <xref:System.Windows.Navigation.NavigationWindow>，与 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] （<xref:System.Windows.Window>、<xref:System.Windows.Controls.Page> 等）中的大多数顶级类一样，你可以使用标记和代码隐藏的组合。 这在下面的示例中显示。

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

此代码创建一个 <xref:System.Windows.Navigation.NavigationWindow>，在 <xref:System.Windows.Navigation.NavigationWindow> 打开时，它会自动导航到 @no__t （）。 如果 @no__t 为主应用程序窗口，则可以使用 `StartupUri` 属性启动它。 这在以下标记中显示。

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

下图显示了 <xref:System.Windows.Navigation.NavigationWindow> 作为独立应用程序的主窗口。

主窗口的![主]窗口(./media/navigation-overview/navigation-window-as-main-window.png "导航窗口")

从图中可以看到 <xref:System.Windows.Navigation.NavigationWindow> 具有标题，即使未在前面示例的 <xref:System.Windows.Navigation.NavigationWindow> 实现代码中进行设置。 而是使用 <xref:System.Windows.Controls.Page.WindowTitle%2A> 属性设置标题，如以下代码所示。

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

设置 <xref:System.Windows.Controls.Page.WindowWidth%2A> 和 @no__t 属性还会影响 @no__t。

通常，当需要自定义其行为或外观时，可以实现自己的 @no__t 0。 如果没有执行上述操作，则可以使用快捷方式。 如果在独立的应用程序中将 @no__t 的 pack <xref:System.Windows.Controls.Page> 指定为第 2 @no__t，则 <xref:System.Windows.Application> 会自动创建 @no__t 以托管 @no__t 5。 以下标记显示如何实现此功能。

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

如果要将辅助应用程序窗口（如对话框）作为 <xref:System.Windows.Navigation.NavigationWindow>，则可以使用以下示例中的代码将其打开。

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

下图显示结果。

![对话框](./media/navigation-overview/navigation-window-as-dialog-box.png "导航窗口作为对话框")

如您所见，<xref:System.Windows.Navigation.NavigationWindow> 显示允许用户浏览日记的 Internet Explorer 样式的 "**后退**" 和 "**前进**" 按钮。 这些按钮提供相同的用户体验，如下图所示。

(./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "导航窗口中 System.windows.navigation.navigationwindow> 后退和前进按钮")![中的后退和前进按钮]

如果页面提供其自己的日记导航支持和 UI，则可通过将 <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> 属性的值设置为 `false`，隐藏 @no__t 显示的 "**后退**" 和 "**前进**" 按钮。

另外，还可以使用 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中的自定义支持来替换 @no__t 的 @no__t。

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>框架类

浏览器和 @no__t 都是托管可导航内容的窗口。 在某些情况下，应用程序具有无需整个窗口托管的内容。 相反，此类内容在其他内容中托管。 可以通过使用 <xref:System.Windows.Controls.Frame> 类将导向性内容插入其他内容中。 @no__t 提供与 <xref:System.Windows.Navigation.NavigationWindow> 和 @no__t 2 相同的支持。

下面的示例演示如何使用第 2 @no__t 元素以声明方式将 @no__t 0 添加到 @no__t。

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

此标记设置 @no__t @no__t 为1的元素的 `Source` 属性，该属性的 pack @no__t 为第3步，@no__t 首先应导航到该类型。 下图显示了一个 @no__t 为 @no__t 的0，其中包含一个在多个页面之间导航的 @no__t。

![在多个页面之间导航的帧](./media/navigation-overview/frame-navigation-between-multiple-pages.png "显示多个页面之间的帧导航。")

你不必在 @no__t 的内容中使用 <xref:System.Windows.Controls.Frame>。 在 @no__t 的内容中托管 @no__t 的情况也很常见。

默认情况下，<xref:System.Windows.Controls.Frame> 只在没有其他日志时使用自己的日记。 如果 @no__t 0 是托管在 @no__t 1 或 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 内的内容的一部分，则 <xref:System.Windows.Controls.Frame> 将使用属于 @no__t 或 @no__t 的日志。 但有时，@no__t 0 可能需要负责自己的日记。 这样做的一个原因是允许在由 <xref:System.Windows.Controls.Frame> 承载的页面内进行日志导航。 这由下图说明。

![框架和页面图](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "这会在框架托管的页面内显示日志导航。")

在这种情况下，你可以通过将 <xref:System.Windows.Controls.Frame> 的 @no__t 属性设置为 <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>，将 @no__t 设置为使用自己的日记。 这在以下标记中显示。

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

下图说明了在使用自己的日记的 <xref:System.Windows.Controls.Frame> 中导航的效果。

![使用自己的日记的帧](./media/navigation-overview/frame-uses-its-own-journal.png "显示了在使用自己的日记的帧中进行导航的效果。")

请注意，日记条目显示在 <xref:System.Windows.Controls.Frame> 中的导航 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 而不是 Internet Explorer 中。

> [!NOTE]
> 如果 @no__t 为 <xref:System.Windows.Window> 中承载的内容的一部分，<xref:System.Windows.Controls.Frame> 将使用自己的日记，因此会显示其自己的导航 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。

如果你的用户体验需要 @no__t 0 来提供自己的日记，而不显示导航 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，则可以通过将 @no__t 设置为 <xref:System.Windows.Visibility.Hidden> 来隐藏导航 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 这在以下标记中显示。

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>导航主机

<xref:System.Windows.Controls.Frame> 和 <xref:System.Windows.Navigation.NavigationWindow> 是称为导航宿主的类。 *导航宿主*是可导航到并显示内容的类。 为实现此目的，每个导航宿主都使用其自己的 @no__t 0 和日记。 导航主机的基本构造在下图中显示。

导航![器关系图](./media/navigation-overview/navigation-host-construction.png "基本构造导航宿主")

实质上，这允许 <xref:System.Windows.Navigation.NavigationWindow> 和 <xref:System.Windows.Controls.Frame> 提供 @no__t 在浏览器中承载时提供的相同导航支持。

除了使用 @no__t 0 和日记，导航宿主还实现了 <xref:System.Windows.Navigation.NavigationService> 实现的相同成员。 这由下图说明。

![框架和 System.windows.navigation.navigationwindow>](./media/navigation-overview/navigation-window-and-frame.png "导航窗口和框架")中的日记

这就允许直接对它们进行导航支持编程。 如果需要为 <xref:System.Windows.Window> 中承载的 @no__t 提供自定义导航 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，则可以考虑此情况。 此外，这两种类型都实现了与导航相关的附加成员，包括 `BackStack` （<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>，<xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>）和 `ForwardStack` （<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>，<xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>），这使您可以分别枚举后端堆栈中的日记条目和向前堆栈。

如之前提及，应用程序中可以存在不止一个日志。 下图提供何时可能发生这种情况的示例。

![一个应用程序中有多个日志](./media/navigation-overview/multiple-journals-in-one-application.png "这是一个应用程序中多个日记的示例。")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>导航到非 XAML 页内容

在本主题中，<xref:System.Windows.Controls.Page> 和 pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 已用于演示 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 的各种导航功能。 但是，编译到应用程序中的 @no__t 0 不是唯一可以导航到的内容类型，包 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 不是标识内容的唯一方法。

如本部分所示，你还可以导航到松散 @no__t 的文件、HTML 文件和对象。

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>导航到松散 XAML 文件

松散 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件是具有以下特征的文件：

- 仅包含 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] （即没有代码）。

- 具有适当的命名空间声明。

- 具有 .xaml 文件扩展名。

例如，请考虑以下存储为松散 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件的内容。

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

双击该文件时，浏览器打开、导航到并显示内容。 如下图所示。

![显示 "person" 文件中的内容]将(./media/navigation-overview/contents-of-person-xaml-file.png "显示 \"person\" 文件的内容。")

可显示以下内容的松散 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件：

- 本地计算机上的网站、Intranet 或 Internet。

- 通用命名约定（UNC）文件共享。

- 本地磁盘。

松散 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件可以添加到浏览器的收藏夹中，也可以是浏览器的主页。

> [!NOTE]
> 有关发布和启动松散 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面的详细信息，请参阅[部署 WPF 应用程序](deploying-a-wpf-application-wpf.md)。

松 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 的一个限制是，只能托管在部分信任环境中可安全运行的内容。 例如，`Window` 不能是松散 @no__t 1 文件的根元素。 有关详细信息，请参阅 [WPF 部分信任安全性](../wpf-partial-trust-security.md)。

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>通过使用框架导航到 HTML 文件

正如您所料，还可以导航到 HTML。 只需提供使用 http 方案 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。 例如，下面的 @no__t 显示导航到 HTML 页的 @no__t 1。

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

导航到 HTML 需要特殊权限。 例如，你不能从在 Internet 区域部分信任安全沙箱中运行的 @no__t 中导航。 有关详细信息，请参阅 [WPF 部分信任安全性](../wpf-partial-trust-security.md)。

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>通过使用 WebBrowser 控件导航到 HTML 文件

@No__t-0 控件支持 HTML 文档托管、导航和脚本/托管代码互操作性。 有关 <xref:System.Windows.Controls.WebBrowser> 控件的详细信息，请参阅 @no__t。

与 <xref:System.Windows.Controls.Frame> 一样，使用 @no__t 导航到 HTML 需要特殊权限。 例如，在部分信任的应用程序中，你只能导航到位于源站点的 HTML。 有关详细信息，请参阅 [WPF 部分信任安全性](../wpf-partial-trust-security.md)。

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>导航到自定义对象

如果有存储为自定义对象的数据，则显示该数据的一种方法是创建一个 <xref:System.Windows.Controls.Page>，其中包含绑定到这些对象的内容（请参阅[数据绑定概述](../data/data-binding-overview.md)）。 如果无需创建整个页面而只要显示对象，则可以直接导航到它们。

请考虑在以下代码中实现的 @no__t 0 类。

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

若要导航到它，请调用 <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> 方法，如以下代码所示。

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

下图显示结果。

![导航到类的页面](./media/navigation-overview/page-navigates-to-an-object.png "这是导航到对象的页面的示例。")

从此图可以看出，没有显示任何有用信息。 事实上，显示的值是**Person**对象的 `ToString` 方法的返回值;默认情况下，这是 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 可用于表示对象的唯一值。 您可以重写 @no__t 0 方法以返回更有意义的信息，尽管它仍只是一个字符串值。 可以使用的一种方法，利用 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 的演示功能，使用数据模板。 可以实现 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 可以与特定类型的对象关联的数据模板。 下面的代码显示 `Person` 对象的数据模板。

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

在此处，通过在 `DataType` 属性中使用 @no__t 的标记扩展，将数据模板与 @no__t 类型相关联。 然后，数据模板将 `TextBlock` 元素（请参阅 <xref:System.Windows.Controls.TextBlock>）绑定到 @no__t 类的属性。 下图显示 `Person` 对象的更新外观。

![导航到具有数据模板的类]，该类(./media/navigation-overview/navigating-to-a-class.png "导航到具有数据模板的类。")

此技术的优势之一在于能够通过重复使用数据模板以在应用程序任意位置一致地显示对象而获得一致性。

有关数据模板的详细信息，请参阅[数据模板化概述](../data/data-templating-overview.md)。

<a name="Security"></a>

## <a name="security"></a>安全性

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 导航支持允许在 Internet 上导航到 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]，并允许应用程序托管第三方内容。 为了保护应用程序和用户免受有害行为的影响，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供了在[安全](../security-wpf.md)和[WPF 部分信任安全性](../wpf-partial-trust-security.md)中讨论的各种安全功能。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [应用程序管理概述](application-management-overview.md)
- [WPF 中的 Pack URI](pack-uris-in-wpf.md)
- [结构化导航概述](structured-navigation-overview.md)
- [导航拓扑概述](navigation-topologies-overview.md)
- [帮助主题](navigation-how-to-topics.md)
- [部署 WPF 应用程序](deploying-a-wpf-application-wpf.md)
