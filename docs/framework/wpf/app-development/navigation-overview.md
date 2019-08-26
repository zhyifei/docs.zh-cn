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
ms.openlocfilehash: 574449f95ee9632d37f277d61806802457494df0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964593"
---
# <a name="navigation-overview"></a>导航概述

Windows Presentation Foundation (WPF) 支持可在两种类型的应用程序中使用的浏览器样式的导航: [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]独立应用程序和。 为了使导航的内容打包[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , <xref:System.Windows.Controls.Page>提供了类。 您可以通过<xref:System.Windows.Documents.Hyperlink>使用或<xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.NavigationService>以编程方式使用从一个导航到另一个。 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 使用日志记住从其导航和导航回它们的页。

<xref:System.Windows.Controls.Page>、 <xref:System.Windows.Documents.Hyperlink> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]、 <xref:System.Windows.Navigation.NavigationService>和日志构成提供的导航支持的核心。 本概述首先详细探讨这些功能, 然后介绍高级导航支持, 其中包括导航[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]到松散文件、HTML 文件和对象。

> [!NOTE]
> 在本主题中, 术语 "浏览器" 只引用可以托管[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]应用程序的浏览器, 当前包括 Microsoft Internet Explorer 和 Firefox。 仅特定[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]的浏览器支持特定功能的情况下, 浏览器版本被引用。

## <a name="navigation-in-wpf-applications"></a>WPF 应用程序中的导航

本主题概述了中[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]的关键导航功能。 这些功能适用于独立应用程序和[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], 尽管本主题在的上下文[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]中提供了这些功能。

> [!NOTE]
> 本主题不讨论如何生成和部署[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]。 有关的详细信息[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], 请参阅[WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)。

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

在[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]中, 您可以导航到多个内容类型, 其中包括 .NET Framework 对象、自定义对象、枚举值[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 、用户控件、文件和 HTML 文件。 不过, 你会发现打包内容最常见和最方便的方法是使用<xref:System.Windows.Controls.Page>。 此外, <xref:System.Windows.Controls.Page>还实现了特定于导航的功能, 以增强其外观并简化开发。

使用<xref:System.Windows.Controls.Page>, 可以通过使用如下所示的标记[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]以声明方式实现可导航的内容页。

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

在<xref:System.Windows.Controls.Page> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]中实现的将作为其根元素,需要命名空间声明。`Page` `Page`元素包含要导航并显示的内容。 可以通过设置`Page.Content`属性元素来添加内容, 如以下标记所示。

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content` 只能包含一个子元素，在前面的实例中，内容是一个单独的字符串“Hello, Page!”。 在实践中, 通常会使用布局控件作为子元素 (请参阅[布局](../advanced/layout.md)) 来包含内容并撰写内容。

`Page`元素的子元素被视为<xref:System.Windows.Controls.Page>和的内容, 因此, 不需要使用显式`Page.Content`声明。 以下标记和前面的示例在声明上是等效的。

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

在这种情况`Page.Content`下, 将自动设置为`Page`元素的子元素。 有关详细信息，请参阅 [WPF 内容模型](../controls/wpf-content-model.md)。

仅<xref:System.Windows.Controls.Page>标记可用于显示内容。 但是, <xref:System.Windows.Controls.Page>还可以显示允许用户与页面交互的控件, 并且它可以通过处理事件和调用应用程序逻辑来响应用户交互。 交互式<xref:System.Windows.Controls.Page>是通过结合使用标记和代码隐藏来实现的, 如下面的示例中所示。

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

要允许标记文件和代码隐藏文件协同工作，需要进行以下配置：

- 在标记中, `Page`元素必须`x:Class`包含属性。 生成应用程序`x:Class`后, 标记文件中存在会导致 Microsoft 生成引擎 (MSBuild) 创建一个`partial`派生自<xref:System.Windows.Controls.Page>的类, 并`x:Class`具有由特性指定的名称。 这要求[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]为架构 ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ) 添加命名空间声明。 生成`partial`的类实现`InitializeComponent`, 调用它来注册事件并设置标记中实现的属性。

- 在代码隐藏中, 类必须是`partial`由标记中的`x:Class`特性指定的同名类, 并且必须派生自<xref:System.Windows.Controls.Page>。 这允许在生成应用程序时将代码隐藏文件与`partial`为标记文件生成的类相关联 (请参阅[生成 WPF 应用程序](building-a-wpf-application-wpf.md))。

- 在代码隐藏中, <xref:System.Windows.Controls.Page>该类必须实现`InitializeComponent`调用方法的构造函数。 `InitializeComponent`由标记文件的生成`partial`类实现, 用于注册事件和设置在标记中定义的属性。

> [!NOTE]
> 使用<xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Page>将新添加到项目时, 将使用标记和代码隐藏来实现, 它包括创建标记和代码隐藏文件之间的关联所需的配置。 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]此处所述。

获得<xref:System.Windows.Controls.Page>之后, 可以导航到它。 若要指定应用<xref:System.Windows.Controls.Page>程序导航到的第一个, 需要配置启动。 <xref:System.Windows.Controls.Page>

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>配置起始页

[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 需要一定数量的应用程序结构以在浏览器中托管。 在[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]中<xref:System.Windows.Application> , 类是建立所需的应用程序基础结构的应用程序定义的一部分 (请参阅[应用程序管理概述](application-management-overview.md))。

通常使用标记和代码隐藏来实现应用程序定义, 并将标记文件配置为 MSBuild`ApplicationDefinition`项。 下面是的应用程序定义[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]。

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

可以使用其应用程序定义来指定开始<xref:System.Windows.Controls.Page>, <xref:System.Windows.Controls.Page>即启动时[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]自动加载的。 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 为此, 可将<xref:System.Windows.Application.StartupUri%2A>属性<xref:System.Windows.Controls.Page>设置为所需的。 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]

> [!NOTE]
> 在大多数情况下, <xref:System.Windows.Controls.Page>将编译到应用程序中或与应用程序一起部署。 在这些情况下, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] <xref:System.Windows.Controls.Page>标识的为[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], 这是符合*pack*方案的。 WPF [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]中的[pack uri](pack-uris-in-wpf.md)进一步讨论了 pack。 也可使用 http 方案导航到内容，这将在以下内容中讨论。

您可以在<xref:System.Windows.Application.StartupUri%2A>标记中以声明方式进行设置, 如下面的示例所示。

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

在此示例中, `StartupUri`属性设置为一个标识主页的[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]相对 pack。 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]启动后, 会自动导航到并显示主页。 下图对此进行了演示, 其中显示[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]了从 Web 服务器启动的。

![XBAP 页面](./media/navigation-overview/xbap-launched-from-a-web-server.png "这会显示从 Web 服务器启动的 XBAP。")

> [!NOTE]
> 有关开发和部署的[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]详细信息, 请参阅[wpf XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)和[部署 WPF 应用程序](deploying-a-wpf-application-wpf.md)。

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>配置主机窗口的标题、宽度和高度

您从上图中可以看到的一件事情是, 浏览器和选项卡面板的标题都是[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]的。 除了长，标题既没什么吸引力也没什么帮助。 出于此原因, <xref:System.Windows.Controls.Page>我们提供了一种方法, 用于通过<xref:System.Windows.Controls.Page.WindowTitle%2A>设置属性来更改标题。 此外, 您还可以通过分别设置<xref:System.Windows.Controls.Page.WindowWidth%2A>和<xref:System.Windows.Controls.Page.WindowHeight%2A>来配置浏览器窗口的宽度和高度。

<xref:System.Windows.Controls.Page.WindowTitle%2A>、 <xref:System.Windows.Controls.Page.WindowWidth%2A>和<xref:System.Windows.Controls.Page.WindowHeight%2A>可以在标记中以声明方式设置, 如下面的示例中所示。

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

结果如下图所示。

![窗口标题、高度、宽度](./media/navigation-overview/window-title-width-height.png "这会显示可以配置的窗口标题、高度和宽度。")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>超链接导航

典型[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]的包含多个页面。 若要从一页导航到另一页, 最简单的<xref:System.Windows.Documents.Hyperlink>方法是使用。 您可以使用<xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Controls.Page> 元素以`Hyperlink`声明方式向添加, 该元素显示在下面的标记中。

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

`Hyperlink`元素需要以下各项:

- 要导航[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]到的<xref:System.Windows.Controls.Page>包`NavigateUri` , 如特性所指定。

- 用户可以单击以启动导航的内容, 如文本和图像 (对于`Hyperlink`元素可包含的内容, 请参阅<xref:System.Windows.Documents.Hyperlink>)。

下图显示[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] <xref:System.Windows.Controls.Page>了具有的。 <xref:System.Windows.Documents.Hyperlink>

![包含超链接的页面](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "这会显示一个包含超链接的页的 XBAP。")

正如您所期望的那样<xref:System.Windows.Documents.Hyperlink> , 单击[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]将使导航到<xref:System.Windows.Controls.Page>由`NavigateUri`属性标识的。 此外, [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]将在 Internet Explorer 中的 " <xref:System.Windows.Controls.Page>最近使用的页" 列表中添加一个条目。 如下图所示。

![后退和前进按钮](./media/navigation-overview/back-and-forward-navigation.png "用 \"后退\" 和 \"前进\" 按钮导航。")

并且支持从一个<xref:System.Windows.Controls.Page>导航到另一个导航, <xref:System.Windows.Documents.Hyperlink>还支持片段导航。

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>片段导航

*片段导航*是在当前<xref:System.Windows.Controls.Page>或另一个<xref:System.Windows.Controls.Page>中导航到内容片段的内容。 在[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]中, 内容片段是命名元素包含的内容。 命名元素是设置了其`Name`属性的元素。 下面的标记显示了包含`TextBlock`内容片段的命名元素。

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

若要导航到内容片段, 该`NavigateUri`属性必须包括以下内容: <xref:System.Windows.Documents.Hyperlink>

- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 具有要导航到的<xref:System.Windows.Controls.Page>内容片段的的。

- “#”字符。

- 中包含内容片段的元素<xref:System.Windows.Controls.Page>的名称。

片段[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的格式如下。

*PageURI* `#` *ElementName*

下面显示了一个`Hyperlink`配置为导航到内容片段的的示例。

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> 本部分介绍中[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]的默认片段导航实现。 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]还允许实现自己的片段导航方案, 该方案在某种程度上需要处理<xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType>事件。

> [!IMPORTANT]
> 仅当可以通过 HTTP 浏览这些[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页面时, 才能导航[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]到松散`Page`页面 (仅限标记的文件, 并将其作为根元素)。
>
> 但松散[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页可以导航到其自己的片段。

<a name="NavigationService"></a>

### <a name="navigation-service"></a>导航服务

虽然<xref:System.Windows.Documents.Hyperlink>允许用户启动对特定<xref:System.Windows.Controls.Page>的导航, 但查找和下载<xref:System.Windows.Navigation.NavigationService>页面的工作由类执行。 实质上<xref:System.Windows.Navigation.NavigationService> , 提供代表客户端代码处理导航请求的能力, 例如。 <xref:System.Windows.Documents.Hyperlink> 此外, <xref:System.Windows.Navigation.NavigationService>还实现了对跟踪和影响导航请求的更高级别的支持。

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]单击时, 将调用以在指定的包中查找并下载<xref:System.Windows.Controls.Page>。 <xref:System.Windows.Documents.Hyperlink> 下载<xref:System.Windows.Controls.Page>的会转换为对象树, 这些对象的根对象是已下载<xref:System.Windows.Controls.Page>的实例。 对根<xref:System.Windows.Controls.Page>对象的引用存储<xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType>在属性中。 所导航[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]到的内容的 pack 存储<xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType>在属性中, 而<xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType>是存储导航到的最后一[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]页的 pack。

> [!NOTE]
> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]应用程序可以有多个当前处于活动状态<xref:System.Windows.Navigation.NavigationService>的应用程序。 有关详细信息, 请参阅本主题后面的[导航宿主](#Navigation_Hosts)。

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>使用导航服务以编程方式导航

您<xref:System.Windows.Navigation.NavigationService>无需知道是否使用<xref:System.Windows.Documents.Hyperlink>在标记中以声明方式实现导航, 因为<xref:System.Windows.Documents.Hyperlink>代表您<xref:System.Windows.Navigation.NavigationService>使用。 这意味着, 只要的<xref:System.Windows.Documents.Hyperlink>直接或间接父级是导航宿主 (请参阅[导航](#Navigation_Hosts)宿主), <xref:System.Windows.Documents.Hyperlink>就能找到并使用导航宿主的导航服务来处理导航请求。

但是, 在某些情况下, 你需要直接<xref:System.Windows.Navigation.NavigationService>使用, 其中包括:

- 需要<xref:System.Windows.Controls.Page>使用非参数构造函数实例化时。

- 当你需要在上设置属性, <xref:System.Windows.Controls.Page>然后再导航到它。

- 需要导航到的时,只能在运行时确定。<xref:System.Windows.Controls.Page>

在这些情况下, 需要编写代码, 以便通过调用<xref:System.Windows.Navigation.NavigationService.Navigate%2A> <xref:System.Windows.Navigation.NavigationService>对象的方法以编程方式启动导航。 这需要获取对的<xref:System.Windows.Navigation.NavigationService>引用。

#### <a name="getting-a-reference-to-the-navigationservice"></a>获取对 NavigationService 的引用

出于[导航宿主](#Navigation_Hosts)部分所述的原因, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]应用程序可以<xref:System.Windows.Navigation.NavigationService>有多个。 这意味着<xref:System.Windows.Navigation.NavigationService>, 你的代码需要一种方法来查找, 这<xref:System.Windows.Navigation.NavigationService>通常是导航到当前<xref:System.Windows.Controls.Page>的。 可以通过<xref:System.Windows.Navigation.NavigationService> `static` 调用方法获取<xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType>对的引用。 若要获取<xref:System.Windows.Navigation.NavigationService>导航到特定<xref:System.Windows.Controls.Page>的, 请将对的<xref:System.Windows.Controls.Page>引用作为<xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A>方法的参数传递。 下面的代码演示如何获取<xref:System.Windows.Navigation.NavigationService>当前<xref:System.Windows.Controls.Page>的。

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

作为<xref:System.Windows.Navigation.NavigationService>的查找<xref:System.Windows.Controls.Page>的快捷方式, <xref:System.Windows.Controls.Page>实现<xref:System.Windows.Controls.Page.NavigationService%2A>了属性。 这在下面的示例中显示。

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> 引发<xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.NavigationService> 事件时<xref:System.Windows.Controls.Page> , 只能获取对其的引用。 <xref:System.Windows.FrameworkElement.Loaded>

#### <a name="programmatic-navigation-to-a-page-object"></a>以编程方式导航到页对象

下面的示例演示如何使用<xref:System.Windows.Navigation.NavigationService>以编程方式导航<xref:System.Windows.Controls.Page>到。 需要编程式导航, 因为<xref:System.Windows.Controls.Page>要导航到的只能使用单个无参数的构造函数实例化。 以下<xref:System.Windows.Controls.Page>标记和代码中显示了具有非参数构造函数的。

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

以下标记和代码中<xref:System.Windows.Controls.Page>显示了导航到具有非参数构造函数的。 <xref:System.Windows.Controls.Page>

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

当单击<xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Controls.Page>上的时, 将通过实例化导航到使用非参数构造函数并调用<xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType>方法来启动导航。 <xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.NavigationService.Navigate%2A>接受对将导航到的<xref:System.Windows.Navigation.NavigationService>对象而不是包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的引用。

#### <a name="programmatic-navigation-with-a-pack-uri"></a>使用 Pack URI 以编程方式导航

如果需要以编程方式构造包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] (例如, 只能在运行时确定 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] ) <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> , 可以使用方法。 这在下面的示例中显示。

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>刷新当前页

如果与存储在[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 属性<xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType>中的包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]具有相同的包,则不会下载。<xref:System.Windows.Controls.Page> 若要[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]再次强制下载当前页, 可以<xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType>调用方法, 如以下示例中所示。

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>导航生存期

如你所见，有很多方法初始化导航。 当启动导航时, 导航正在进行时, 可以使用以下实现<xref:System.Windows.Navigation.NavigationService>的事件来跟踪和影响导航:

- <xref:System.Windows.Navigation.NavigationService.Navigating>。 请求新导航时发生。 可用于取消导航。

- <xref:System.Windows.Navigation.NavigationService.NavigationProgress>。 在下载过程中定期发生，用于提供定位进度信息。

- <xref:System.Windows.Navigation.NavigationService.Navigated>。 已定位并下载页时发生。

- <xref:System.Windows.Navigation.NavigationService.NavigationStopped>。 在导航停止 (通过调用<xref:System.Windows.Navigation.NavigationService.StopLoading%2A>) 时发生, 或在当前导航正在进行时请求新导航时发生。

- <xref:System.Windows.Navigation.NavigationService.NavigationFailed>。 在导航到所需内容的同时遇到错误时发生。

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted>。 导航到的内容已加载和分析，并开始呈现时发生。

- <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>。 导航到内容片段开始时发生，具体如何发生如下所述：

  - 立即，如果所需片段位于当前内容中。

  - 源内容加载之后，如果所需片段在不同内容中。

引发导航事件的顺序如下图所示。

![页面导航流程图](./media/navigation-overview/order-of-navigation-events.png "页面导航事件流程图")

一般情况下, <xref:System.Windows.Controls.Page>并不关心这些事件。 更有可能应用程序与应用程序相关, 因此, 这些事件也由<xref:System.Windows.Application>类引发:

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

每次<xref:System.Windows.Navigation.NavigationService>引发事件时, 类<xref:System.Windows.Application>将引发相应的事件。 <xref:System.Windows.Controls.Frame>和<xref:System.Windows.Navigation.NavigationWindow>提供相同的事件来检测其各自范围内的导航。

在某些情况下, <xref:System.Windows.Controls.Page>可能会对这些事件感兴趣。 例如, <xref:System.Windows.Controls.Page>可以<xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType>处理事件, 以确定是否取消导航。 这在下面的示例中显示。

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

如果你使用中<xref:System.Windows.Controls.Page>的导航事件注册处理程序, 如前面的示例所示, 你还必须取消注册事件处理程序。 如果不这样做, 可能会对导航如何[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]记住<xref:System.Windows.Controls.Page>使用日记的导航产生负面影响。

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>使用日志记住导航

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 使用两个堆栈来记住导航过的页：后退堆栈和前进堆栈。 当<xref:System.Windows.Controls.Page>你从当前导航到新<xref:System.Windows.Controls.Page>的或转发到现有<xref:System.Windows.Controls.Page>的时, 当前<xref:System.Windows.Controls.Page>将添加到*back 堆栈*中。 <xref:System.Windows.Controls.Page>当您从当前导航回之前<xref:System.Windows.Controls.Page>, 当前<xref:System.Windows.Controls.Page>将添加到*前进堆栈*中。 后退堆栈、前进堆栈和管理它们的功能统称为日志。 后退堆栈中的每一项和正向堆栈是<xref:System.Windows.Navigation.JournalEntry>类的实例, 并且称为*日记条目*。

#### <a name="navigating-the-journal-from-internet-explorer"></a>从 Internet Explorer 导航日志

从概念上讲, 日记的工作方式与 Internet Explorer 中的 "**后退**" 和 "**前进**" 按钮的操作方式相同。 这些在下图中显示。

![后退和前进按钮](./media/navigation-overview/back-and-forward-navigation.png "用 \"后退\" 和 \"前进\" 按钮导航。")

对于[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]由 internet explorer 承载的, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]将日记集成到 internet explorer 的[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]导航中。 这样, 用户便可以使用 Internet Explorer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]中的 "**后退**"、"**前进**" 和 "**最新页**" 按钮在中导航页面。

> [!IMPORTANT]
> 在 Internet Explorer 中, 当用户离开并返回到[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]时, 只有未保持活动状态的页的日记条目保留在日志中。 有关保持页处于活动状态的讨论, 请参阅本主题后面的[页生存期和日志](#PageLifetime)。

默认情况下, <xref:System.Windows.Controls.Page> [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Internet Explorer 的 "**最新页**" 列表中显示的每个文本<xref:System.Windows.Controls.Page>都是的。 很多情况下这对用户并没有什么特殊的意义。 幸运的是，可以使用以下选项更改文本：

1. 附加`JournalEntry.Name`的属性值。

2. `Page.Title`特性值。

3. [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]当前`Page.WindowTitle` 的<xref:System.Windows.Controls.Page>属性值和。

4. 当前 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 的 <xref:System.Windows.Controls.Page>。 (默认)

选项列出的顺序和查找文本的优先级顺序一致。 例如, 如果`JournalEntry.Name`设置了, 则忽略其他值。

下面的示例使用`Page.Title`特性更改为日记条目显示的文本。

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>使用 WPF 导航日志

尽管用户可以使用 Internet Explorer 中的 "**后退**"、"**前进**" 和 "**最新" 页**导航日记, 但你也可以使用提供的[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]声明性和编程机制导航日志。 这样做的一个原因是在页面中提供[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]自定义导航。

您可以使用公开<xref:System.Windows.Input.NavigationCommands>的导航命令以声明方式添加日记本导航支持。 下面的示例演示如何使用`BrowseBack`导航命令。

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

可以使用<xref:System.Windows.Navigation.NavigationService>类的以下成员之一以编程方式导航日记:

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

此日志还可以通过编程方式进行操作, 如本主题后面的将[内容状态保留为导航历史记录](#RetainingContentStateWithNavigationHistory)中所述。

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a>页生存期和日志

[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]假设有多个页面, 其中包含丰富的内容, 包括图形、动画和媒体。 这类页的内存占用量可能相当大，尤其是使用视频和音频媒体的时候。 假设日志 "记住" 已导航到的页面, 这种[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]情况很快就会消耗大量的内存量。

出于此原因, 日记的默认行为是在每个日记<xref:System.Windows.Controls.Page>条目中存储元数据, 而不是对<xref:System.Windows.Controls.Page>对象的引用。 导航到日记条目时, 其<xref:System.Windows.Controls.Page>元数据用于创建指定<xref:System.Windows.Controls.Page>的的新实例。 因此, 所导航的<xref:System.Windows.Controls.Page>每个都具有如下图所示的生存期。

![页生存期](./media/navigation-overview/navigated-page-lifetime.png "这会显示导航页面时的生存期。")

尽管使用默认日记行为可以节省内存消耗, 但每页呈现性能可能会降低;<xref:System.Windows.Controls.Page>呈现可能会很耗时, 尤其是在有大量内容时。 如果需要将<xref:System.Windows.Controls.Page>实例保留在日记中, 可以通过两种方法进行绘制。 首先, 可以通过<xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType>调用方法以编程方式导航到对象。

其次, 通过将[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.Windows.Controls.Page.KeepAlive%2A>属性设置为`true` (默认值为<xref:System.Windows.Controls.Page> `false`), 可以指定在日记中保留的实例。 如以下示例中所示, 可以在标记<xref:System.Windows.Controls.Page.KeepAlive%2A>中以声明方式设置。

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

保持活动状态的<xref:System.Windows.Controls.Page>生存期与不是相同。 第一次<xref:System.Windows.Controls.Page>将处于活动状态的状态导航到时, 它的实例化就<xref:System.Windows.Controls.Page>像是未保持活动状态的。 但是, 由于的<xref:System.Windows.Controls.Page>实例保留在日志中, 因此只要它保留在日志中, 就永远不会再对其进行实例化。 因此, 如果有<xref:System.Windows.Controls.Page>在每<xref:System.Windows.Controls.Page>次导航到时需要调用的初始化逻辑, 则应将其从构造函数移<xref:System.Windows.FrameworkElement.Loaded>到事件的处理程序中。 如下图所示, <xref:System.Windows.FrameworkElement.Loaded>每次<xref:System.Windows.Controls.Page>导航到<xref:System.Windows.FrameworkElement.Unloaded>和时, 都仍将引发和事件。

![当引发已加载和已卸载的事件时](./media/navigation-overview/loaded-and-unloaded-events.png "当导航到和中的某个页面时, 将引发已加载和已卸载的事件。")

<xref:System.Windows.Controls.Page>如果未保持活动状态, 则不应执行以下任一操作:

- 存储对它或它的任何部分的引用。

- 将事件处理程序注册到并非由其实现的事件。

执行上述任一操作都将创建强制<xref:System.Windows.Controls.Page>保留在内存中的引用, 即使已从日志中删除该引用。

通常, 您应该首选不<xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Page>保持活动状态的默认行为。 但是，这会存在将在下一节中讨论的状态影响。

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>保留导航历史记录的内容状态

如果未保持活动状态, 并且具有收集用户数据的控件, 则当用户离开并返回<xref:System.Windows.Controls.Page>到时, 数据会发生什么情况？ <xref:System.Windows.Controls.Page> 从用户体验角度，用户应该会希望看到他们以前输入的数据。 遗憾的<xref:System.Windows.Controls.Page>是, 由于每个导航都创建了一个新实例, 因此收集数据的控件将重新实例化, 数据会丢失。

幸运的是, 日记本提供对跨<xref:System.Windows.Controls.Page>导航的数据 (包括控制数据) 的支持。 具体而言, 每个的日记<xref:System.Windows.Controls.Page>条目都充当关联<xref:System.Windows.Controls.Page>状态的临时容器。 以下步骤概述了从导航时<xref:System.Windows.Controls.Page>使用此支持的方式:

1. 当前<xref:System.Windows.Controls.Page>的条目将添加到日志中。

2. 的状态<xref:System.Windows.Controls.Page>与该页的日记条目一起存储, 后者将添加到后面的堆栈中。

3. 导航到<xref:System.Windows.Controls.Page>新的。

当使用日记<xref:System.Windows.Controls.Page>向后导航到页面时, 将执行以下步骤:

1. 实例<xref:System.Windows.Controls.Page>化 (back 堆栈顶部的日记条目)。

2. 将用与的<xref:System.Windows.Controls.Page>日记条目一起存储的状态进行刷新。<xref:System.Windows.Controls.Page>

3. <xref:System.Windows.Controls.Page>向后导航到。

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]当在上使用以下控件时, 将<xref:System.Windows.Controls.Page>自动使用此支持:

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

如果使用这些控件 <xref:System.Windows.Controls.ListBox> , 则会在<xref:System.Windows.Controls.Page>导航中记住输入的数据, 如下图所示。 <xref:System.Windows.Controls.Page>

![具有记住状态的控件的页面](./media/navigation-overview/data-remembered-across-page-navigations.png "跨页面导航记住输入的数据。")

当除<xref:System.Windows.Controls.Page>前面的列表中的控件以外的其他控件时, 或者当状态存储在自定义对象中时, 需要编写代码以使日志记住跨<xref:System.Windows.Controls.Page>导航状态的状态。

如果需要记住跨<xref:System.Windows.Controls.Page>导航的小块状态, 可以使用配置了<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType>元数据标志的依赖<xref:System.Windows.DependencyProperty>属性 (请参见)。

如果<xref:System.Windows.Controls.Page>需要记住的跨导航的状态包含多个数据段, 则可能会发现, 将状态封装到单个类并<xref:System.Windows.Navigation.IProvideCustomContentState>实现接口所需的代码要少得多。

<xref:System.Windows.Controls.Page>如果需要在单个的各个状态之间导航, 而不是<xref:System.Windows.Controls.Page>从自身导航, 则可以使用<xref:System.Windows.Navigation.IProvideCustomContentState>和<xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>。

<a name="Cookies"></a>

### <a name="cookies"></a>Cookie

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]应用程序可以存储数据的另一种方法是使用<xref:System.Windows.Application.SetCookie%2A>和<xref:System.Windows.Application.GetCookie%2A>方法来创建、更新和删除 cookie。 可在中[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]创建的 cookie 与其他类型的 Web 应用程序使用的 cookie 相同; cookie 是应用程序在客户端计算机上或跨应用程序会话存储的任意数据块。 Cookie 数据通常采用以下格式的名称/值对的形式。

*Name* `=` *Value*

在将数据传递到时<xref:System.Windows.Application.SetCookie%2A>, <xref:System.Uri>如果将数据传递到应设置 cookie 的位置, 则会在内存中创建一个 cookie, 并且该 cookie 仅在当前应用程序会话的持续时间内可用。 这种类型的 cookie 称为*会话 cookie*。

要跨应用程序会话存储 cookie，必须使用以下格式将到期日期添加到 cookie。

*NAME* `=` *VALUE* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

在 cookie 过期之前, 具有到期日期的 cookie 存储在当前的 Windows 安装程序的临时 Internet Files 文件夹中。 此类 cookie 称为*永久性 cookie* , 因为它在应用程序会话之间保持不变。

可以通过调用<xref:System.Windows.Application.GetCookie%2A>方法来检索会话和持久 cookie, 同时<xref:System.Uri>传递使用<xref:System.Windows.Application.SetCookie%2A>方法设置 cookie 的位置的。

下面是中[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]支持 cookie 的一些方式:

- [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]独立的应用[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]程序, 可以创建和管理 cookie。

- 通过浏览器[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]可以访问由创建的 cookie。

- 来自相同域的 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 可以创建和共享 cookie。

- [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]同一个域中的 HTML 页面可以创建和共享 cookie。

- 当和松散[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]发出 Web 请求时, 会调度 cookie。

- Iframe 中的顶层[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]和[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]宿主都可以访问 cookie。

- 对于所有受[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]支持的浏览器, 中的 Cookie 支持都是相同的。

- 在 Internet Explorer 中, 与 cookie 相关的 P3P 策略将[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]遵循, 特别是对于第一方和第三方。 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>结构化导航

如果需要将数据从一个<xref:System.Windows.Controls.Page>传递到另一个, 则可以将数据作为参数传递给的<xref:System.Windows.Controls.Page>非参数构造函数。 请注意, 如果使用此方法<xref:System.Windows.Controls.Page> , 则必须保持活动状态; 否则, 下一次导航<xref:System.Windows.Controls.Page>到时, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]将使用无参数<xref:System.Windows.Controls.Page>构造函数重新实例化。

或者, 你<xref:System.Windows.Controls.Page>可以实现用需要传递的数据设置的属性。 不过, 当<xref:System.Windows.Controls.Page>需要将数据传递回<xref:System.Windows.Controls.Page>导航到该数据的时, 这会变得困难。 问题在于, 导航不会以本机方式支持用于确保在<xref:System.Windows.Controls.Page>从其导航后将返回到的机制。 实质上，导航不支持调用/返回语义。 为了解决此问题, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.Windows.Navigation.PageFunction%601>提供了可用于确保以可预测的结构化<xref:System.Windows.Controls.Page>方式返回到的类。 有关详细信息, 请参阅[结构化导航概述](structured-navigation-overview.md)。

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>NavigationWindow 类

到目前为止，你已全面了解最有可能用可导航内容生成应用程序的导航服务。 这些服务是在的上下文中讨论[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]的, 尽管它们并不[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]限于。 现代操作系统和 Windows 应用程序利用了新式用户的浏览器体验, 将浏览器样式的导航并入独立的应用程序。 常见示例包括：

- **Word 同义词库**:导航 word 选项。

- **文件资源管理器**:导航文件和文件夹。

- **向导**:将复杂任务分解到多个可在之间导航的页面。 例如, 处理添加和删除 Windows 功能的 Windows 组件向导。

若要将浏览器样式的导航并入独立应用程序, 可以使用<xref:System.Windows.Navigation.NavigationWindow>类。 <xref:System.Windows.Navigation.NavigationWindow>派生自<xref:System.Windows.Window> , 并对[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]提供的导航支持相同的扩展。 你可以将<xref:System.Windows.Navigation.NavigationWindow>作为独立应用程序的主窗口, 也可以用作辅助窗口 (如对话框)。

若要实现<xref:System.Windows.Navigation.NavigationWindow>, 与 (<xref:System.Windows.Window>、 <xref:System.Windows.Controls.Page>等中[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]的大多数顶级类一样, 你可以使用标记和代码隐藏的组合。 这在下面的示例中显示。

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

此代码将创建<xref:System.Windows.Navigation.NavigationWindow>一个, 它在打开<xref:System.Windows.Controls.Page>时会自动导航到 (主页 .xaml <xref:System.Windows.Navigation.NavigationWindow> )。 如果是主应用程序窗口, 则可以`StartupUri`使用属性来启动它。 <xref:System.Windows.Navigation.NavigationWindow> 这在以下标记中显示。

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

下图显示的<xref:System.Windows.Navigation.NavigationWindow>是独立应用程序的主窗口。

![主窗口](./media/navigation-overview/navigation-window-as-main-window.png "作为主窗口的导航窗口")

从图中可以看到<xref:System.Windows.Navigation.NavigationWindow> , 具有标题, 即使未<xref:System.Windows.Navigation.NavigationWindow>在前面示例的实现代码中进行设置也是如此。 而是使用<xref:System.Windows.Controls.Page.WindowTitle%2A>属性设置标题, 如以下代码所示。

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

<xref:System.Windows.Controls.Page.WindowWidth%2A>设置和<xref:System.Windows.Controls.Page.WindowHeight%2A>属性还会影响<xref:System.Windows.Navigation.NavigationWindow>。

通常, 当你需要自<xref:System.Windows.Navigation.NavigationWindow>定义其行为或外观时, 可以自行实现。 如果没有执行上述操作，则可以使用快捷方式。 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]如果<xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Page> 在独立<xref:System.Windows.Application>的应用程序中将的 pack 指定为,则会自动创建来承载的。<xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Application.StartupUri%2A> 以下标记显示如何实现此功能。

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

如果希望将辅助应用程序窗口 (如对话框<xref:System.Windows.Navigation.NavigationWindow>) 作为, 可以使用以下示例中的代码将其打开。

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

下图显示结果。

![一个对话框](./media/navigation-overview/navigation-window-as-dialog-box.png "作为对话框的导航窗口")

如您所见, <xref:System.Windows.Navigation.NavigationWindow>会显示允许用户导航日记的 Internet Explorer 样式的 "**后退**" 和 "**前进**" 按钮。 这些按钮提供相同的用户体验，如下图所示。

![System.windows.navigation.navigationwindow> 中的 "后退" 和 "前进" 按钮](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "导航窗口中的 \"后退\" 和 \"前进\" 按钮")

如果页面提供其自己的日记导航支持和 UI, 则<xref:System.Windows.Navigation.NavigationWindow>可以<xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A>通过将属性的值设置为来`false`隐藏显示的 "**后退**" 和 "**前进**" 按钮。

或者, 你可以使用中[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]的自定义支持来[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]替换<xref:System.Windows.Navigation.NavigationWindow>自身的。

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>框架类

浏览器和<xref:System.Windows.Navigation.NavigationWindow>都是托管可导航内容的窗口。 在某些情况下，应用程序具有无需整个窗口托管的内容。 相反，此类内容在其他内容中托管。 可以使用类将<xref:System.Windows.Controls.Frame>导向性内容插入到其他内容中。 <xref:System.Windows.Controls.Frame>提供与<xref:System.Windows.Navigation.NavigationWindow>和[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]相同的支持。

下面的示例演示如何使用<xref:System.Windows.Controls.Frame> `Frame`元素以<xref:System.Windows.Controls.Page>声明方式将添加到。

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

`Source`此标记设置<xref:System.Windows.Controls.Frame> <xref:System.Windows.Controls.Page> [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]元素的属性, 其中包含最初应导航到的的 pack。 `Frame` 下图显示[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] <xref:System.Windows.Controls.Page> 了具有在多个页面之间导航的的。<xref:System.Windows.Controls.Frame>

![在多个页面之间导航的帧](./media/navigation-overview/frame-navigation-between-multiple-pages.png "这会显示多个页面之间的帧导航。")

你不必在的内容<xref:System.Windows.Controls.Frame> <xref:System.Windows.Controls.Page>内使用。 在的内容<xref:System.Windows.Controls.Frame> <xref:System.Windows.Window>中托管。

默认情况下<xref:System.Windows.Controls.Frame> , 只有在没有其他日志时才使用自己的日记。 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame> [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] <xref:System.Windows.Navigation.NavigationWindow>如果是在或[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]中承载的内容的一部分, 则将使用属于或的日记。 <xref:System.Windows.Controls.Frame> 但是, 有时<xref:System.Windows.Controls.Frame>可能需要负责自己的日记。 这样做的一个原因是允许在承载<xref:System.Windows.Controls.Frame>的页面内进行日志导航。 这由下图说明。

![框架和页面图](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "这会在框架托管的页中显示日志导航。")

在这种情况下, 你可以<xref:System.Windows.Controls.Frame>通过<xref:System.Windows.Controls.Frame.JournalOwnership%2A>将的<xref:System.Windows.Controls.Frame>属性设置为<xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>来将配置为使用自己的日记。 这在以下标记中显示。

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

下图说明了在使用自己的日记的<xref:System.Windows.Controls.Frame>中导航的效果。

![使用自己的日记的帧](./media/navigation-overview/frame-uses-its-own-journal.png "这显示了在使用其自己的日记的帧中导航的效果。")

请注意[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] <xref:System.Windows.Controls.Frame>, 在中的导航 (而不是 Internet Explorer) 中显示日记条目。

> [!NOTE]
> 如果是在中承载的内容的[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]一部分<xref:System.Windows.Controls.Frame>,则使用其自己的日记, 因此会显示自己的导航。 <xref:System.Windows.Window> <xref:System.Windows.Controls.Frame>

如果你<xref:System.Windows.Controls.Frame>的用户体验需要提供自己的日记而不显示导航<xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 则可以通过将设置为[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]来<xref:System.Windows.Visibility.Hidden>隐藏导航。 这在以下标记中显示。

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>导航主机

<xref:System.Windows.Controls.Frame>和<xref:System.Windows.Navigation.NavigationWindow>是称为导航宿主的类。 *导航宿主*是可导航到并显示内容的类。 为实现此目的, 每个导航宿主都<xref:System.Windows.Navigation.NavigationService>使用其自己的和日志。 导航主机的基本构造在下图中显示。

![导航器关系图](./media/navigation-overview/navigation-host-construction.png "导航宿主的基本构造")

实质上, 这<xref:System.Windows.Navigation.NavigationWindow>允许<xref:System.Windows.Controls.Frame>和提供在浏览器中承载时[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]提供的相同导航支持。

除了使用<xref:System.Windows.Navigation.NavigationService>和日记, 导航宿主还实现实现相同的<xref:System.Windows.Navigation.NavigationService>成员。 这由下图说明。

![帧和 system.windows.navigation.navigationwindow> 中的日志](./media/navigation-overview/navigation-window-and-frame.png "导航窗口和框架")

这就允许直接对它们进行导航支持编程。 如果需要为中[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] <xref:System.Windows.Controls.Frame>托管的提供自定义导航, 则可以考虑此情况。 <xref:System.Windows.Window> 此外, 这两种类型都实现了与导航相关的`BackStack`附加成员, 其中包括<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>( <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType><xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>、 <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>) 和`ForwardStack` (,), 这使您能够枚举后端中的日记条目。分别为 stack 和 forward 堆栈。

如之前提及，应用程序中可以存在不止一个日志。 下图提供何时可能发生这种情况的示例。

![一个应用程序中的多个日志](./media/navigation-overview/multiple-journals-in-one-application.png "这是一个应用程序中多个日记的示例。")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>导航到非 XAML 页内容

本主题中<xref:System.Windows.Controls.Page>的和 pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]已用于演示的[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]各种导航功能。 但是, <xref:System.Windows.Controls.Page>编译到应用程序中的仅是可以导航到的内容类型, 而 pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]并不是标识内容的唯一方法。

如本部分所示, 你还可以导航到[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]松散文件、HTML 文件和对象。

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>导航到松散 XAML 文件

松散[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件是具有以下特征的文件:

- 仅[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]包含 (即, 不包含任何代码)。

- 具有适当的命名空间声明。

- 具有 .xaml 文件扩展名。

例如, 请考虑以下存储为松散[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件 "Person" 的内容。

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

双击该文件时，浏览器打开、导航到并显示内容。 如下图所示。

![显示人员 .xaml 文件中的内容](./media/navigation-overview/contents-of-person-xaml-file.png "显示 Person 文件的内容。")

可显示以下内容的[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]松散文件:

- 本地计算机上的网站、Intranet 或 Internet。

- [!INCLUDE[TLA#tla_unc](../../../../includes/tlasharptla-unc-md.md)]文件共享。

- 本地磁盘。

可以将[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]松散文件添加到浏览器的收藏夹, 或浏览器的主页。

> [!NOTE]
> 有关发布和启动松散[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页面的详细信息, 请参阅[部署 WPF 应用程序](deploying-a-wpf-application-wpf.md)。

松散[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]的一项限制是您只能承载安全地在部分信任环境中运行的内容。 例如, `Window`不能是松散[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件的根元素。 有关详细信息，请参阅 [WPF 部分信任安全性](../wpf-partial-trust-security.md)。

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>通过使用框架导航到 HTML 文件

正如您所料, 还可以导航到 HTML。 只需提供一个[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]使用 http 方案的。 例如, 下面[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]的示例演示一个<xref:System.Windows.Controls.Frame>导航到 HTML 页的。

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

导航到 HTML 需要特殊权限。 例如, 你不能从[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]在 Internet 区域部分信任安全沙箱中运行的中导航。 有关详细信息，请参阅 [WPF 部分信任安全性](../wpf-partial-trust-security.md)。

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>通过使用 WebBrowser 控件导航到 HTML 文件

<xref:System.Windows.Controls.WebBrowser>控件支持 HTML 文档托管、导航和脚本/托管代码互操作性。 有关<xref:System.Windows.Controls.WebBrowser>控件的详细信息, 请参阅<xref:System.Windows.Controls.WebBrowser>。

类似<xref:System.Windows.Controls.Frame>地, 使用导航到<xref:System.Windows.Controls.WebBrowser>使用的 HTML 需要特殊的权限。 例如, 在部分信任的应用程序中, 你只能导航到位于源站点的 HTML。 有关详细信息，请参阅 [WPF 部分信任安全性](../wpf-partial-trust-security.md)。

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>导航到自定义对象

如果你有存储为自定义对象的数据, 则显示该数据的一种方法是创建<xref:System.Windows.Controls.Page>一个具有绑定到这些对象的内容 (请参阅[数据绑定概述](../data/data-binding-overview.md))。 如果无需创建整个页面而只要显示对象，则可以直接导航到它们。

请考虑在以下代码中实现的类。`Person`

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

若要导航到该<xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType>方法, 请调用方法, 如以下代码所示。

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

下图显示结果。

![导航到类的页面](./media/navigation-overview/page-navigates-to-an-object.png "这是一个导航到对象的页面的示例。")

从此图可以看出，没有显示任何有用信息。 事实上, 显示的值是`ToString` **Person**对象的方法的返回值; 默认情况下, 这是唯一[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]可以用来表示您的对象的值。 您可以重写`ToString`方法以返回更有意义的信息, 尽管它仍只是一个字符串值。 使用的展示功能[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]的一种方法是使用数据模板。 可以实现[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]可以与特定类型的对象相关联的数据模板。 下面的代码演示了`Person`对象的数据模板。

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

此处, 使用`Person` `DataType`特性中的`x:Type`标记扩展将数据模板与类型相关联。 然后, 数据模板会`TextBlock`将元素 ( <xref:System.Windows.Controls.TextBlock>请参见) 绑定`Person`到类的属性。 下图显示了`Person`对象的更新外观。

![导航到具有数据模板的类](./media/navigation-overview/navigating-to-a-class.png "导航到具有数据模板的类。")

此技术的优势之一在于能够通过重复使用数据模板以在应用程序任意位置一致地显示对象而获得一致性。

有关数据模板的详细信息, 请参阅[数据模板化概述](../data/data-templating-overview.md)。

<a name="Security"></a>

## <a name="security"></a>安全性

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]导航支持允许[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]跨 Internet 导航到, 并允许应用程序托管第三方内容。 为了保护应用程序和用户免受有害行为的[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]影响, 提供了在[安全](../security-wpf.md)和[WPF 部分信任安全性](../wpf-partial-trust-security.md)中讨论的各种安全功能。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [应用程序管理概述](application-management-overview.md)
- [WPF 中的 Pack URI](pack-uris-in-wpf.md)
- [结构化导航概述](structured-navigation-overview.md)
- [导航拓扑概述](navigation-topologies-overview.md)
- [帮助主题](navigation-how-to-topics.md)
- [部署 WPF 应用程序](deploying-a-wpf-application-wpf.md)
