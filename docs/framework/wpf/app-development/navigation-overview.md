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
# <a name="navigation-overview"></a><span data-ttu-id="a24f6-102">导航概述</span><span class="sxs-lookup"><span data-stu-id="a24f6-102">Navigation Overview</span></span>

<span data-ttu-id="a24f6-103">Windows Presentation Foundation （WPF）支持可在两种类型的应用程序中使用的浏览器样式的导航：独立应用程序和 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a24f6-103">Windows Presentation Foundation (WPF) supports browser-style navigation that can be used in two types of applications: standalone applications and [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].</span></span> <span data-ttu-id="a24f6-104">若要打包内容以便导航，@no__t 提供 @no__t 1 类。</span><span class="sxs-lookup"><span data-stu-id="a24f6-104">To package content for navigation, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides the <xref:System.Windows.Controls.Page> class.</span></span> <span data-ttu-id="a24f6-105">您可以通过使用 @no__t 以声明方式从一个 <xref:System.Windows.Controls.Page> 导航到另一个，也可以使用 <xref:System.Windows.Navigation.NavigationService> 以编程方式导航。</span><span class="sxs-lookup"><span data-stu-id="a24f6-105">You can navigate from one <xref:System.Windows.Controls.Page> to another declaratively, by using a <xref:System.Windows.Documents.Hyperlink>, or programmatically, by using the <xref:System.Windows.Navigation.NavigationService>.</span></span> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="a24f6-106">使用日志记住从其导航和导航回它们的页。</span><span class="sxs-lookup"><span data-stu-id="a24f6-106">uses the journal to remember pages that have been navigated from and to navigate back to them.</span></span>

<span data-ttu-id="a24f6-107"><xref:System.Windows.Controls.Page>，<xref:System.Windows.Documents.Hyperlink>，<xref:System.Windows.Navigation.NavigationService>，而日记构成 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供的导航支持的核心。</span><span class="sxs-lookup"><span data-stu-id="a24f6-107"><xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Navigation.NavigationService>, and the journal form the core of the navigation support offered by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span> <span data-ttu-id="a24f6-108">本概述首先详细探讨这些功能，然后介绍高级导航支持，其中包括指向松散 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 文件、HTML 文件和对象的导航。</span><span class="sxs-lookup"><span data-stu-id="a24f6-108">This overview explores these features in detail before covering advanced navigation support that includes navigation to loose [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] files, HTML files, and objects.</span></span>

> [!NOTE]
> <span data-ttu-id="a24f6-109">在本主题中，术语 "浏览器" 只引用可以承载 @no__t 0 应用程序的浏览器，当前包括 Microsoft Internet Explorer 和 Firefox。</span><span class="sxs-lookup"><span data-stu-id="a24f6-109">In this topic, the term "browser" refers only to browsers that can host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications, which currently includes Microsoft Internet Explorer and Firefox.</span></span> <span data-ttu-id="a24f6-110">只有特定的浏览器支持特定 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 功能，浏览器版本被称为。</span><span class="sxs-lookup"><span data-stu-id="a24f6-110">Where specific [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] features are supported only by a particular browser, the browser version is referred to.</span></span>

## <a name="navigation-in-wpf-applications"></a><span data-ttu-id="a24f6-111">WPF 应用程序中的导航</span><span class="sxs-lookup"><span data-stu-id="a24f6-111">Navigation in WPF Applications</span></span>

<span data-ttu-id="a24f6-112">本主题概述了 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中的关键导航功能。</span><span class="sxs-lookup"><span data-stu-id="a24f6-112">This topic provides an overview of the key navigation capabilities in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span> <span data-ttu-id="a24f6-113">这些功能适用于独立应用程序和 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]，但本主题在 @no__t 的上下文中提供了这些功能。</span><span class="sxs-lookup"><span data-stu-id="a24f6-113">These capabilities are available to both standalone applications and [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], although this topic presents them within the context of an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].</span></span>

> [!NOTE]
> <span data-ttu-id="a24f6-114">本主题不讨论如何生成和部署 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a24f6-114">This topic doesn't discuss how to build and deploy [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].</span></span> <span data-ttu-id="a24f6-115">有关 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 的详细信息，请参阅[WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a24f6-115">For more information on [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], see [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).</span></span>

<span data-ttu-id="a24f6-116">本节解释并演示导航的以下方面：</span><span class="sxs-lookup"><span data-stu-id="a24f6-116">This section explains and demonstrates the following aspects of navigation:</span></span>

- [<span data-ttu-id="a24f6-117">实现页</span><span class="sxs-lookup"><span data-stu-id="a24f6-117">Implementing a Page</span></span>](#CreatingAXAMLPage)

- [<span data-ttu-id="a24f6-118">配置起始页</span><span class="sxs-lookup"><span data-stu-id="a24f6-118">Configuring a Start Page</span></span>](#Configuring_a_Start_Page)

- [<span data-ttu-id="a24f6-119">配置主机窗口的标题、宽度和高度</span><span class="sxs-lookup"><span data-stu-id="a24f6-119">Configuring the Host Window's Title, Width, and Height</span></span>](#ConfiguringAXAMLPage)

- [<span data-ttu-id="a24f6-120">超链接导航</span><span class="sxs-lookup"><span data-stu-id="a24f6-120">Hyperlink Navigation</span></span>](#NavigatingBetweenXAMLPages)

- [<span data-ttu-id="a24f6-121">片段导航</span><span class="sxs-lookup"><span data-stu-id="a24f6-121">Fragment Navigation</span></span>](#FragmentNavigation)

- [<span data-ttu-id="a24f6-122">导航服务</span><span class="sxs-lookup"><span data-stu-id="a24f6-122">Navigation Service</span></span>](#NavigationService)

- [<span data-ttu-id="a24f6-123">使用导航服务以编程方式导航</span><span class="sxs-lookup"><span data-stu-id="a24f6-123">Programmatic Navigation with the Navigation Service</span></span>](#Programmatic_Navigation_with_the_Navigation_Service)

- [<span data-ttu-id="a24f6-124">导航生存期</span><span class="sxs-lookup"><span data-stu-id="a24f6-124">Navigation Lifetime</span></span>](#Navigation_Lifetime)

- [<span data-ttu-id="a24f6-125">使用日志记住导航</span><span class="sxs-lookup"><span data-stu-id="a24f6-125">Remembering Navigation with the Journal</span></span>](#NavigationHistory)

- [<span data-ttu-id="a24f6-126">页生存期和日志</span><span class="sxs-lookup"><span data-stu-id="a24f6-126">Page Lifetime and the Journal</span></span>](#PageLifetime)

- [<span data-ttu-id="a24f6-127">保留导航历史记录的内容状态</span><span class="sxs-lookup"><span data-stu-id="a24f6-127">Retaining Content State with Navigation History</span></span>](#RetainingContentStateWithNavigationHistory)

- [<span data-ttu-id="a24f6-128">Cookie</span><span class="sxs-lookup"><span data-stu-id="a24f6-128">Cookies</span></span>](#Cookies)

- [<span data-ttu-id="a24f6-129">结构化导航</span><span class="sxs-lookup"><span data-stu-id="a24f6-129">Structured Navigation</span></span>](#Structured_Navigation)

<a name="CreatingAXAMLPage"></a>

### <a name="implementing-a-page"></a><span data-ttu-id="a24f6-130">实现页</span><span class="sxs-lookup"><span data-stu-id="a24f6-130">Implementing a Page</span></span>

<span data-ttu-id="a24f6-131">在 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中，可以导航到多个内容类型，其中包括 .NET Framework 对象、自定义对象、枚举值、用户控件、@no__t 1 文件和 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="a24f6-131">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], you can navigate to several content types that include .NET Framework objects, custom objects, enumeration values, user controls, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files, and HTML files.</span></span> <span data-ttu-id="a24f6-132">不过，你会发现打包内容最常见和最方便的方法是使用 <xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-132">However, you'll find that the most common and convenient way to package content is by using <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="a24f6-133">此外，@no__t 0 实现了特定于导航的功能，以增强其外观和简化开发。</span><span class="sxs-lookup"><span data-stu-id="a24f6-133">Furthermore, <xref:System.Windows.Controls.Page> implements navigation-specific features to enhance their appearance and simplify development.</span></span>

<span data-ttu-id="a24f6-134">使用 <xref:System.Windows.Controls.Page>，可以通过使用如下所示的标记以声明方式实现 @no__t 1 内容的可导航页面。</span><span class="sxs-lookup"><span data-stu-id="a24f6-134">Using <xref:System.Windows.Controls.Page>, you can declaratively implement a navigable page of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content by using markup like the following.</span></span>

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

<span data-ttu-id="a24f6-135">在 @no__t 的标记中实现的 @no__t 为 `Page` 作为其根元素，需要 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] @ no__t 命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="a24f6-135">A <xref:System.Windows.Controls.Page> that is implemented in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup has `Page` as its root element and requires the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)][!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] namespace declaration.</span></span> <span data-ttu-id="a24f6-136">@No__t-0 元素包含要导航并显示的内容。</span><span class="sxs-lookup"><span data-stu-id="a24f6-136">The `Page` element contains the content that you want to navigate to and display.</span></span> <span data-ttu-id="a24f6-137">可以通过设置 @no__t 的属性元素来添加内容，如以下标记所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-137">You add content by setting the `Page.Content` property element, as shown in the following markup.</span></span>

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

<span data-ttu-id="a24f6-138">`Page.Content` 只能包含一个子元素，在前面的实例中，内容是一个单独的字符串“Hello, Page!”。</span><span class="sxs-lookup"><span data-stu-id="a24f6-138">`Page.Content` can only contain one child element; in the preceding example, the content is a single string, "Hello, Page!"</span></span> <span data-ttu-id="a24f6-139">在实践中，通常会使用布局控件作为子元素（请参阅[布局](../advanced/layout.md)）来包含内容并撰写内容。</span><span class="sxs-lookup"><span data-stu-id="a24f6-139">In practice, you will usually use a layout control as the child element (see [Layout](../advanced/layout.md)) to contain and compose your content.</span></span>

<span data-ttu-id="a24f6-140">@No__t-0 元素的子元素被视为 @no__t 的内容，因此，不需要使用显式的 `Page.Content` 声明。</span><span class="sxs-lookup"><span data-stu-id="a24f6-140">The child elements of a `Page` element are considered to be the content of a <xref:System.Windows.Controls.Page> and, consequently, you don't need to use the explicit `Page.Content` declaration.</span></span> <span data-ttu-id="a24f6-141">以下标记和前面的示例在声明上是等效的。</span><span class="sxs-lookup"><span data-stu-id="a24f6-141">The following markup is the declarative equivalent to the preceding sample.</span></span>

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

<span data-ttu-id="a24f6-142">在这种情况下，`Page.Content` 会自动设置为 @no__t 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="a24f6-142">In this case, `Page.Content` is automatically set with the child elements of the `Page` element.</span></span> <span data-ttu-id="a24f6-143">有关详细信息，请参阅 [WPF 内容模型](../controls/wpf-content-model.md)。</span><span class="sxs-lookup"><span data-stu-id="a24f6-143">For more information, see [WPF Content Model](../controls/wpf-content-model.md).</span></span>

<span data-ttu-id="a24f6-144">仅标记 <xref:System.Windows.Controls.Page> 可用于显示内容。</span><span class="sxs-lookup"><span data-stu-id="a24f6-144">A markup-only <xref:System.Windows.Controls.Page> is useful for displaying content.</span></span> <span data-ttu-id="a24f6-145">但是，@no__t 0 还可以显示允许用户与页面交互的控件，并且它可以通过处理事件和调用应用程序逻辑来响应用户交互。</span><span class="sxs-lookup"><span data-stu-id="a24f6-145">However, a <xref:System.Windows.Controls.Page> can also display controls that allow users to interact with the page, and it can respond to user interaction by handling events and calling application logic.</span></span> <span data-ttu-id="a24f6-146">交互式 <xref:System.Windows.Controls.Page> 通过结合使用标记和代码隐藏来实现，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-146">An interactive <xref:System.Windows.Controls.Page> is implemented by using a combination of markup and code-behind, as shown in the following example.</span></span>

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

<span data-ttu-id="a24f6-147">要允许标记文件和代码隐藏文件协同工作，需要进行以下配置：</span><span class="sxs-lookup"><span data-stu-id="a24f6-147">To allow a markup file and code-behind file to work together, the following configuration is required:</span></span>

- <span data-ttu-id="a24f6-148">在标记中，`Page` 元素必须包含 `x:Class` 属性。</span><span class="sxs-lookup"><span data-stu-id="a24f6-148">In markup, the `Page` element must include the `x:Class` attribute.</span></span> <span data-ttu-id="a24f6-149">在生成应用程序时，标记文件中 @no__t 的存在会导致 Microsoft 生成引擎（MSBuild）创建从 <xref:System.Windows.Controls.Page> 派生的 @no__t 1 类，并具有 `x:Class` 属性指定的名称。</span><span class="sxs-lookup"><span data-stu-id="a24f6-149">When the application is built, the existence of `x:Class` in the markup file causes Microsoft build engine (MSBuild) to create a `partial` class that derives from <xref:System.Windows.Controls.Page> and has the name that is specified by the `x:Class` attribute.</span></span> <span data-ttu-id="a24f6-150">这要求为 @no__t 架构（`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`）添加 @no__t 的命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="a24f6-150">This requires the addition of an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace declaration for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).</span></span> <span data-ttu-id="a24f6-151">生成的 @no__t 0 类实现 `InitializeComponent`，调用它来注册事件并设置在标记中实现的属性。</span><span class="sxs-lookup"><span data-stu-id="a24f6-151">The generated `partial` class implements `InitializeComponent`, which is called to register the events and set the properties that are implemented in markup.</span></span>

- <span data-ttu-id="a24f6-152">在代码隐藏中，类必须是一个 `partial` 类，其名称与标记中 `x:Class` 属性指定的名称相同，并且必须从 <xref:System.Windows.Controls.Page> 派生。</span><span class="sxs-lookup"><span data-stu-id="a24f6-152">In code-behind, the class must be a `partial` class with the same name that is specified by the `x:Class` attribute in markup, and it must derive from <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="a24f6-153">这样，代码隐藏文件就会与生成应用程序时为标记文件生成的 @no__t 0 类相关联（请参阅[生成 WPF 应用程序](building-a-wpf-application-wpf.md)）。</span><span class="sxs-lookup"><span data-stu-id="a24f6-153">This allows the code-behind file to be associated with the `partial` class that is generated for the markup file when the application is built (see [Building a WPF Application](building-a-wpf-application-wpf.md)).</span></span>

- <span data-ttu-id="a24f6-154">在代码隐藏中，@no__t 0 类必须实现调用 `InitializeComponent` 方法的构造函数。</span><span class="sxs-lookup"><span data-stu-id="a24f6-154">In code-behind, the <xref:System.Windows.Controls.Page> class must implement a constructor that calls the `InitializeComponent` method.</span></span> <span data-ttu-id="a24f6-155">`InitializeComponent` 由标记文件生成的 @no__t 1 类实现，用于注册事件和设置在标记中定义的属性。</span><span class="sxs-lookup"><span data-stu-id="a24f6-155">`InitializeComponent` is implemented by the markup file's generated `partial` class to register events and set properties that are defined in markup.</span></span>

> [!NOTE]
> <span data-ttu-id="a24f6-156">使用 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 将新的 @no__t 0 添加到你的项目时，将使用标记和代码隐藏来实现 <xref:System.Windows.Controls.Page>，并包括必要的配置以创建标记和代码隐藏文件之间的关联，如此处所述。</span><span class="sxs-lookup"><span data-stu-id="a24f6-156">When you add a new <xref:System.Windows.Controls.Page> to your project using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], the <xref:System.Windows.Controls.Page> is implemented using both markup and code-behind, and it includes the necessary configuration to create the association between the markup and code-behind files as described here.</span></span>

<span data-ttu-id="a24f6-157">如果有 <xref:System.Windows.Controls.Page>，则可以导航到它。</span><span class="sxs-lookup"><span data-stu-id="a24f6-157">Once you have a <xref:System.Windows.Controls.Page>, you can navigate to it.</span></span> <span data-ttu-id="a24f6-158">若要指定应用程序导航到的第一个 <xref:System.Windows.Controls.Page>，需要将 start @no__t 配置为-1。</span><span class="sxs-lookup"><span data-stu-id="a24f6-158">To specify the first <xref:System.Windows.Controls.Page> that an application navigates to, you need to configure the start <xref:System.Windows.Controls.Page>.</span></span>

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a><span data-ttu-id="a24f6-159">配置起始页</span><span class="sxs-lookup"><span data-stu-id="a24f6-159">Configuring a Start Page</span></span>

[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] <span data-ttu-id="a24f6-160">需要一定数量的应用程序结构以在浏览器中托管。</span><span class="sxs-lookup"><span data-stu-id="a24f6-160">require a certain amount of application infrastructure to be hosted in a browser.</span></span> <span data-ttu-id="a24f6-161">在 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中，<xref:System.Windows.Application> 类是应用程序定义的一部分，该定义用于建立所需的应用程序基础结构（请参阅[应用程序管理概述](application-management-overview.md)）。</span><span class="sxs-lookup"><span data-stu-id="a24f6-161">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], the <xref:System.Windows.Application> class is part of an application definition that establishes the required application infrastructure (see [Application Management Overview](application-management-overview.md)).</span></span>

<span data-ttu-id="a24f6-162">通常使用标记和代码隐藏来实现应用程序定义，并将标记文件配置为 MSBuild @ no__t-0 项。</span><span class="sxs-lookup"><span data-stu-id="a24f6-162">An application definition is usually implemented using both markup and code-behind, with the markup file configured as an MSBuild`ApplicationDefinition` item.</span></span> <span data-ttu-id="a24f6-163">下面是 @no__t 的应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="a24f6-163">The following is an application definition for an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].</span></span>

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

<span data-ttu-id="a24f6-164">@No__t-0 可以使用其应用程序定义来指定开始 <xref:System.Windows.Controls.Page>，这是在启动 @no__t 3 时自动加载的 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-164">An [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] can use its application definition to specify a start <xref:System.Windows.Controls.Page>, which is the <xref:System.Windows.Controls.Page> that is automatically loaded when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is launched.</span></span> <span data-ttu-id="a24f6-165">为此，可将 <xref:System.Windows.Application.StartupUri%2A> 属性设置为所需 @no__t 的 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a24f6-165">You do this by setting the <xref:System.Windows.Application.StartupUri%2A> property with the [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] for the desired <xref:System.Windows.Controls.Page>.</span></span>

> [!NOTE]
> <span data-ttu-id="a24f6-166">在大多数情况下，<xref:System.Windows.Controls.Page> 编译到应用程序中或与应用程序一起部署。</span><span class="sxs-lookup"><span data-stu-id="a24f6-166">In most cases, the <xref:System.Windows.Controls.Page> is either compiled into or deployed with an application.</span></span> <span data-ttu-id="a24f6-167">在这些情况下，标识 @no__t 的 @no__t 0 是一个 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]，这是符合*pack*方案的 @no__t 3。</span><span class="sxs-lookup"><span data-stu-id="a24f6-167">In these cases, the [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that identifies a <xref:System.Windows.Controls.Page> is a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], which is a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that conforms to the *pack* scheme.</span></span> <span data-ttu-id="a24f6-168">在[WPF 的 Pack uri](pack-uris-in-wpf.md)中进一步讨论了 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a24f6-168">Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] are discussed further in     [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span> <span data-ttu-id="a24f6-169">也可使用 http 方案导航到内容，这将在以下内容中讨论。</span><span class="sxs-lookup"><span data-stu-id="a24f6-169">You can also navigate to content using the http scheme, which is discussed below.</span></span>

<span data-ttu-id="a24f6-170">可以在标记中以声明方式设置 <xref:System.Windows.Application.StartupUri%2A>，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-170">You can set <xref:System.Windows.Application.StartupUri%2A> declaratively in markup, as shown in the following example.</span></span>

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

<span data-ttu-id="a24f6-171">在此示例中，使用标识主页的相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 设置 `StartupUri` 属性。</span><span class="sxs-lookup"><span data-stu-id="a24f6-171">In this example, the `StartupUri` attribute is set with a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that identifies HomePage.xaml.</span></span> <span data-ttu-id="a24f6-172">如果 @no__t 为 "已启动"，则会自动导航并显示 "主页"。</span><span class="sxs-lookup"><span data-stu-id="a24f6-172">When the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is launched, HomePage.xaml is automatically navigated to and displayed.</span></span> <span data-ttu-id="a24f6-173">下图对此进行了演示，其中显示了从 Web 服务器启动的 @no__t 0。</span><span class="sxs-lookup"><span data-stu-id="a24f6-173">This is demonstrated by the following figure, which shows an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that was launched from a Web server.</span></span>

<span data-ttu-id="a24f6-174">![Xbap 页面](./media/navigation-overview/xbap-launched-from-a-web-server.png "这会显示从 Web 服务器启动的 xbap。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-174">![XBAP page](./media/navigation-overview/xbap-launched-from-a-web-server.png "This shows an XBAP launched from a Web server.")</span></span>

> [!NOTE]
> <span data-ttu-id="a24f6-175">有关开发和部署 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 的详细信息，请参阅[WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)和[部署 WPF 应用程序](deploying-a-wpf-application-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="a24f6-175">For more information regarding the development and deployment of [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], see [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md) and     [Deploying a WPF Application](deploying-a-wpf-application-wpf.md).</span></span>

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a><span data-ttu-id="a24f6-176">配置主机窗口的标题、宽度和高度</span><span class="sxs-lookup"><span data-stu-id="a24f6-176">Configuring the Host Window's Title, Width, and Height</span></span>

<span data-ttu-id="a24f6-177">您从上图中可以看到的一件事情是：浏览器和选项卡面板的标题都是 @no__t @no__t 为0。</span><span class="sxs-lookup"><span data-stu-id="a24f6-177">One thing you may have noticed from the previous figure is that the title of both the browser and the tab panel is the [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].</span></span> <span data-ttu-id="a24f6-178">除了长，标题既没什么吸引力也没什么帮助。</span><span class="sxs-lookup"><span data-stu-id="a24f6-178">Besides being long, the title is neither attractive nor informative.</span></span> <span data-ttu-id="a24f6-179">出于此原因，@no__t 为您提供了一种方法来通过设置 @no__t 属性来更改标题。</span><span class="sxs-lookup"><span data-stu-id="a24f6-179">For this reason, <xref:System.Windows.Controls.Page> offers a way for you to change the title by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property.</span></span> <span data-ttu-id="a24f6-180">此外，还可以通过分别设置 @no__t 0 和 @no__t 来配置浏览器窗口的宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="a24f6-180">Furthermore, you can configure the width and height of the browser window by setting <xref:System.Windows.Controls.Page.WindowWidth%2A> and <xref:System.Windows.Controls.Page.WindowHeight%2A>, respectively.</span></span>

<span data-ttu-id="a24f6-181">可以在标记中以声明方式设置 <xref:System.Windows.Controls.Page.WindowTitle%2A>、<xref:System.Windows.Controls.Page.WindowWidth%2A> 和 <xref:System.Windows.Controls.Page.WindowHeight%2A>，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-181"><xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A>, and <xref:System.Windows.Controls.Page.WindowHeight%2A> can be set declaratively in markup, as shown in the following example.</span></span>

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

<span data-ttu-id="a24f6-182">结果如下图所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-182">The result is shown in the following figure.</span></span>

<span data-ttu-id="a24f6-183">![窗口标题、高度、宽度](./media/navigation-overview/window-title-width-height.png "这将显示您可以配置的窗口标题、高度和宽度。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-183">![Window title, height, width](./media/navigation-overview/window-title-width-height.png "This shows the window title, height, and width you can configure.")</span></span>

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a><span data-ttu-id="a24f6-184">超链接导航</span><span class="sxs-lookup"><span data-stu-id="a24f6-184">Hyperlink Navigation</span></span>

<span data-ttu-id="a24f6-185">典型 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 包含多个页面。</span><span class="sxs-lookup"><span data-stu-id="a24f6-185">A typical [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] comprises several pages.</span></span> <span data-ttu-id="a24f6-186">若要从一页导航到另一页，最简单的方法是使用 <xref:System.Windows.Documents.Hyperlink>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-186">The simplest way to navigate from one page to another is to use a <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="a24f6-187">你可以使用以下标记中所示的 `Hyperlink` 元素以声明方式将 @no__t 0 添加到 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-187">You can declaratively add a <xref:System.Windows.Documents.Hyperlink> to a <xref:System.Windows.Controls.Page> by using the `Hyperlink` element, which is shown in the following markup.</span></span>

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

<span data-ttu-id="a24f6-188">@No__t 0 元素需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="a24f6-188">A `Hyperlink` element requires the following:</span></span>

- <span data-ttu-id="a24f6-189">要导航到的 @no__t 的包 <xref:System.Windows.Controls.Page>，由 `NavigateUri` 特性指定。</span><span class="sxs-lookup"><span data-stu-id="a24f6-189">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the <xref:System.Windows.Controls.Page> to navigate to, as specified by the `NavigateUri` attribute.</span></span>

- <span data-ttu-id="a24f6-190">用户可以单击以启动导航的内容（如文本和图像（对于 @no__t 0 元素可以包含的内容），请参阅 <xref:System.Windows.Documents.Hyperlink>）。</span><span class="sxs-lookup"><span data-stu-id="a24f6-190">Content that a user can click to initiate the navigation, such as text and images (for the content that the `Hyperlink` element can contain, see <xref:System.Windows.Documents.Hyperlink>).</span></span>

<span data-ttu-id="a24f6-191">下图显示了一个 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]，其 @no__t 为 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-191">The following figure shows an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] with a <xref:System.Windows.Controls.Page> that has a <xref:System.Windows.Documents.Hyperlink>.</span></span>

<span data-ttu-id="a24f6-192">![包含超链接的页面](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "这会显示一个包含超链接的页的 XBAP。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-192">![Page with Hyperlink](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "This shows an XBAP with a page with a hyperlink.")</span></span>

<span data-ttu-id="a24f6-193">正如您所期望的那样，单击 <xref:System.Windows.Documents.Hyperlink> 会导致 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 导航到 `NavigateUri` 属性标识的 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-193">As you would expect, clicking the <xref:System.Windows.Documents.Hyperlink> causes the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to navigate to the <xref:System.Windows.Controls.Page> that is identified by the `NavigateUri` attribute.</span></span> <span data-ttu-id="a24f6-194">此外，[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 会将之前 @no__t 的条目添加到 Internet Explorer 中的 "最近使用的页" 列表。</span><span class="sxs-lookup"><span data-stu-id="a24f6-194">Additionally, the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] adds an entry for the previous <xref:System.Windows.Controls.Page> to the Recent Pages list in Internet Explorer.</span></span> <span data-ttu-id="a24f6-195">如下图所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-195">This is shown in the following figure.</span></span>

<span data-ttu-id="a24f6-196">"![后退" 和 "前进" 按钮](./media/navigation-overview/back-and-forward-navigation.png "用 \"后退\" 和 \"前进\" 按钮导航。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-196">![Back and Forward buttons](./media/navigation-overview/back-and-forward-navigation.png "Navigate with the back and forward buttons.")</span></span>

<span data-ttu-id="a24f6-197">还支持从一个 <xref:System.Windows.Controls.Page> 到另一个的导航，<xref:System.Windows.Documents.Hyperlink> 还支持片段导航。</span><span class="sxs-lookup"><span data-stu-id="a24f6-197">As well as supporting navigation from one <xref:System.Windows.Controls.Page> to another, <xref:System.Windows.Documents.Hyperlink> also supports fragment navigation.</span></span>

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a><span data-ttu-id="a24f6-198">片段导航</span><span class="sxs-lookup"><span data-stu-id="a24f6-198">Fragment Navigation</span></span>

<span data-ttu-id="a24f6-199">*片段导航*是对当前 <xref:System.Windows.Controls.Page> 或其他 <xref:System.Windows.Controls.Page> 中的内容片段的导航。</span><span class="sxs-lookup"><span data-stu-id="a24f6-199">*Fragment navigation* is the navigation to a content fragment in either the current <xref:System.Windows.Controls.Page> or another <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="a24f6-200">在 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中，内容片段是已命名元素包含的内容。</span><span class="sxs-lookup"><span data-stu-id="a24f6-200">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], a content fragment is the content that is contained by a named element.</span></span> <span data-ttu-id="a24f6-201">命名元素是一个具有 `Name` 属性集的元素。</span><span class="sxs-lookup"><span data-stu-id="a24f6-201">A named element is an element that has its `Name` attribute set.</span></span> <span data-ttu-id="a24f6-202">下面的标记显示了一个包含内容片段的命名 @no__t 0 元素。</span><span class="sxs-lookup"><span data-stu-id="a24f6-202">The following markup shows a named `TextBlock` element that contains a content fragment.</span></span>

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

<span data-ttu-id="a24f6-203">对于 <xref:System.Windows.Documents.Hyperlink> 定位到内容片段，@no__t 属性必须包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="a24f6-203">For a <xref:System.Windows.Documents.Hyperlink> to navigate to a content fragment, the `NavigateUri` attribute must include the following:</span></span>

- <span data-ttu-id="a24f6-204">@No__t 的 @no__t 0，其中包含要导航到的内容片段。</span><span class="sxs-lookup"><span data-stu-id="a24f6-204">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the <xref:System.Windows.Controls.Page> with the content fragment to navigate to.</span></span>

- <span data-ttu-id="a24f6-205">“#”字符。</span><span class="sxs-lookup"><span data-stu-id="a24f6-205">A "#" character.</span></span>

- <span data-ttu-id="a24f6-206">@No__t-0 上包含内容片段的元素的名称。</span><span class="sxs-lookup"><span data-stu-id="a24f6-206">The name of the element on the <xref:System.Windows.Controls.Page> that contains the content fragment.</span></span>

<span data-ttu-id="a24f6-207">分段 @no__t 为以下格式。</span><span class="sxs-lookup"><span data-stu-id="a24f6-207">A fragment [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] has the following format.</span></span>

<span data-ttu-id="a24f6-208">*PageURI* `#` *ElementName*</span><span class="sxs-lookup"><span data-stu-id="a24f6-208">*PageURI* `#` *ElementName*</span></span>

<span data-ttu-id="a24f6-209">下面显示了一个 `Hyperlink` 的示例，该示例配置为导航到内容片段。</span><span class="sxs-lookup"><span data-stu-id="a24f6-209">The following shows an example of a `Hyperlink` that is configured to navigate to a content fragment.</span></span>

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> <span data-ttu-id="a24f6-210">本部分介绍 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中的默认片段导航实现。</span><span class="sxs-lookup"><span data-stu-id="a24f6-210">This section describes the default fragment navigation implementation in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="a24f6-211">还允许实现自己的片段导航方案，该方案在某种程度上需要处理 @no__t 的事件。</span><span class="sxs-lookup"><span data-stu-id="a24f6-211">also allows you to implement your own fragment navigation scheme which, in part, requires handling the <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> event.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a24f6-212">仅当可以通过 HTTP 浏览这些页面时，才能导航到松散 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面（仅限标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件，带 `Page` 作为根元素）中的片段。</span><span class="sxs-lookup"><span data-stu-id="a24f6-212">You can navigate to fragments in loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages (markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files with `Page` as the root element) only if the pages can be browsed via HTTP.</span></span>
>
> <span data-ttu-id="a24f6-213">但是，松 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面可以导航到其自己的片段。</span><span class="sxs-lookup"><span data-stu-id="a24f6-213">However, a loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page can navigate to its own fragments.</span></span>

<a name="NavigationService"></a>

### <a name="navigation-service"></a><span data-ttu-id="a24f6-214">导航服务</span><span class="sxs-lookup"><span data-stu-id="a24f6-214">Navigation Service</span></span>

<span data-ttu-id="a24f6-215">虽然 @no__t 允许用户启动对特定 @no__t 的导航，但查找和下载页面的工作由 @no__t 2 类执行。</span><span class="sxs-lookup"><span data-stu-id="a24f6-215">While <xref:System.Windows.Documents.Hyperlink> allows a user to initiate navigation to a particular <xref:System.Windows.Controls.Page>, the work of locating and downloading the page is performed by the <xref:System.Windows.Navigation.NavigationService> class.</span></span> <span data-ttu-id="a24f6-216">实质上，<xref:System.Windows.Navigation.NavigationService> 提供了代表客户端代码处理导航请求的功能，如 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-216">Essentially, <xref:System.Windows.Navigation.NavigationService> provides the ability to process a navigation request on behalf of client code, such as the <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="a24f6-217">此外，@no__t 0 还实现了对跟踪和影响导航请求的更高级别的支持。</span><span class="sxs-lookup"><span data-stu-id="a24f6-217">Additionally, <xref:System.Windows.Navigation.NavigationService> implements higher-level support for tracking and influencing a navigation request.</span></span>

<span data-ttu-id="a24f6-218">当单击 <xref:System.Windows.Documents.Hyperlink> 时，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 将调用 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> 来查找并下载指定 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 处的 @no__t 3。</span><span class="sxs-lookup"><span data-stu-id="a24f6-218">When a <xref:System.Windows.Documents.Hyperlink> is clicked, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] calls <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> to locate and download the <xref:System.Windows.Controls.Page> at the specified pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="a24f6-219">下载的 <xref:System.Windows.Controls.Page> 会转换为对象树，该树的根对象是已下载 @no__t 的实例。</span><span class="sxs-lookup"><span data-stu-id="a24f6-219">The downloaded <xref:System.Windows.Controls.Page> is converted to a tree of objects whose root object is an instance of the downloaded <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="a24f6-220">对根 @no__t 0 对象的引用存储在 @no__t 属性中。</span><span class="sxs-lookup"><span data-stu-id="a24f6-220">A reference to the root <xref:System.Windows.Controls.Page> object is stored in the <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a24f6-221">所导航到的内容的 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 存储在 @no__t 属性中，而 <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> 将包 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 存储到导航到的最后一页。</span><span class="sxs-lookup"><span data-stu-id="a24f6-221">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the content that was navigated to is stored in the <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> property, while the <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> stores the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the last page that was navigated to.</span></span>

> [!NOTE]
> <span data-ttu-id="a24f6-222">@No__t 的应用程序可以有多个当前处于活动状态的 <xref:System.Windows.Navigation.NavigationService>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-222">It is possible for a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application to have more than one currently active <xref:System.Windows.Navigation.NavigationService>.</span></span> <span data-ttu-id="a24f6-223">有关详细信息，请参阅本主题后面的[导航宿主](#Navigation_Hosts)。</span><span class="sxs-lookup"><span data-stu-id="a24f6-223">For more information, see [Navigation Hosts](#Navigation_Hosts) later in this topic.</span></span>

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a><span data-ttu-id="a24f6-224">使用导航服务以编程方式导航</span><span class="sxs-lookup"><span data-stu-id="a24f6-224">Programmatic Navigation with the Navigation Service</span></span>

<span data-ttu-id="a24f6-225">如果使用 @no__t 在标记中以声明方式实现了导航，则不需要了解 <xref:System.Windows.Navigation.NavigationService>，因为 <xref:System.Windows.Documents.Hyperlink> 代表你使用 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-225">You don't need to know about <xref:System.Windows.Navigation.NavigationService> if navigation is implemented declaratively in markup using <xref:System.Windows.Documents.Hyperlink>, because <xref:System.Windows.Documents.Hyperlink> uses the <xref:System.Windows.Navigation.NavigationService> on your behalf.</span></span> <span data-ttu-id="a24f6-226">这意味着，只要 @no__t 的直接或间接父级是导航宿主（请参阅[导航](#Navigation_Hosts)宿主），<xref:System.Windows.Documents.Hyperlink> 将能够查找和使用导航宿主的导航服务来处理导航请求。</span><span class="sxs-lookup"><span data-stu-id="a24f6-226">This means that, as long as either the direct or indirect parent of a <xref:System.Windows.Documents.Hyperlink> is a navigation host (see [Navigation Hosts](#Navigation_Hosts)), <xref:System.Windows.Documents.Hyperlink> will be able to find and use the navigation host's navigation service to process a navigation request.</span></span>

<span data-ttu-id="a24f6-227">但是，在某些情况下，你需要直接使用 <xref:System.Windows.Navigation.NavigationService>，其中包括：</span><span class="sxs-lookup"><span data-stu-id="a24f6-227">However, there are situations when you need to use <xref:System.Windows.Navigation.NavigationService> directly, including the following:</span></span>

- <span data-ttu-id="a24f6-228">需要使用非参数构造函数实例化 @no__t 0 时。</span><span class="sxs-lookup"><span data-stu-id="a24f6-228">When you need to instantiate a <xref:System.Windows.Controls.Page> using a non-parameterless constructor.</span></span>

- <span data-ttu-id="a24f6-229">在导航到 @no__t 时，需要在其上设置属性。</span><span class="sxs-lookup"><span data-stu-id="a24f6-229">When you need to set properties on the <xref:System.Windows.Controls.Page> before you navigate to it.</span></span>

- <span data-ttu-id="a24f6-230">需要导航到的 @no__t 0 时，只能在运行时确定。</span><span class="sxs-lookup"><span data-stu-id="a24f6-230">When the <xref:System.Windows.Controls.Page> that needs to be navigated to can only be determined at run time.</span></span>

<span data-ttu-id="a24f6-231">在这些情况下，需要通过调用 @no__t 的对象的 @no__t 0 方法来编写代码，以编程方式启动导航。</span><span class="sxs-lookup"><span data-stu-id="a24f6-231">In these situations, you need to write code to programmatically initiate navigation by calling the <xref:System.Windows.Navigation.NavigationService.Navigate%2A> method of the <xref:System.Windows.Navigation.NavigationService> object.</span></span> <span data-ttu-id="a24f6-232">这需要获取对 @no__t 的引用。</span><span class="sxs-lookup"><span data-stu-id="a24f6-232">That requires getting a reference to a <xref:System.Windows.Navigation.NavigationService>.</span></span>

#### <a name="getting-a-reference-to-the-navigationservice"></a><span data-ttu-id="a24f6-233">获取对 NavigationService 的引用</span><span class="sxs-lookup"><span data-stu-id="a24f6-233">Getting a Reference to the NavigationService</span></span>

<span data-ttu-id="a24f6-234">出于[导航宿主](#Navigation_Hosts)部分所述的原因，@no__t 1 应用程序可以有多个 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-234">For reasons that are covered in the [Navigation Hosts](#Navigation_Hosts) section, a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application can have more than one <xref:System.Windows.Navigation.NavigationService>.</span></span> <span data-ttu-id="a24f6-235">这意味着，你的代码需要一种方法来查找 <xref:System.Windows.Navigation.NavigationService>，这通常是导航到当前 <xref:System.Windows.Controls.Page> @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-235">This means that your code needs a way to find a <xref:System.Windows.Navigation.NavigationService>, which is usually the <xref:System.Windows.Navigation.NavigationService> that navigated to the current <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="a24f6-236">可以通过调用 `static` @ no__t 方法来获取对 @no__t 的引用。</span><span class="sxs-lookup"><span data-stu-id="a24f6-236">You can get a reference to a <xref:System.Windows.Navigation.NavigationService> by calling the `static`<xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a24f6-237">若要获取导航到特定 <xref:System.Windows.Controls.Page> 的 @no__t，请将对 <xref:System.Windows.Controls.Page> 的引用作为 @no__t 方法的参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="a24f6-237">To get the <xref:System.Windows.Navigation.NavigationService> that navigated to a particular <xref:System.Windows.Controls.Page>, you pass a reference to the <xref:System.Windows.Controls.Page> as the argument of the <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> method.</span></span> <span data-ttu-id="a24f6-238">下面的代码演示如何获取当前 @no__t 的 @no__t 0。</span><span class="sxs-lookup"><span data-stu-id="a24f6-238">The following code shows how to get the <xref:System.Windows.Navigation.NavigationService> for the current <xref:System.Windows.Controls.Page>.</span></span>

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

<span data-ttu-id="a24f6-239">若要快捷地查找 @no__t 的 @no__t 为-1，<xref:System.Windows.Controls.Page> 实现 @no__t 3 属性。</span><span class="sxs-lookup"><span data-stu-id="a24f6-239">As a shortcut for finding the <xref:System.Windows.Navigation.NavigationService> for a <xref:System.Windows.Controls.Page>, <xref:System.Windows.Controls.Page> implements the <xref:System.Windows.Controls.Page.NavigationService%2A> property.</span></span> <span data-ttu-id="a24f6-240">这在下面的示例中显示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-240">This is shown in the following example.</span></span>

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> <span data-ttu-id="a24f6-241">当 <xref:System.Windows.Controls.Page> 引发 @no__t 3 事件时，@no__t 0 只能获取对其 @no__t 的引用。</span><span class="sxs-lookup"><span data-stu-id="a24f6-241">A <xref:System.Windows.Controls.Page> can only get a reference to its <xref:System.Windows.Navigation.NavigationService> when <xref:System.Windows.Controls.Page> raises the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

#### <a name="programmatic-navigation-to-a-page-object"></a><span data-ttu-id="a24f6-242">以编程方式导航到页对象</span><span class="sxs-lookup"><span data-stu-id="a24f6-242">Programmatic Navigation to a Page Object</span></span>

<span data-ttu-id="a24f6-243">下面的示例演示如何使用 <xref:System.Windows.Navigation.NavigationService> 以编程方式导航到 @no__t 1。</span><span class="sxs-lookup"><span data-stu-id="a24f6-243">The following example shows how to use the <xref:System.Windows.Navigation.NavigationService> to programmatically navigate to a <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="a24f6-244">需要编程式导航，因为要导航到的 @no__t 0 只能使用单个无参数的构造函数实例化。</span><span class="sxs-lookup"><span data-stu-id="a24f6-244">Programmatic navigation is required because the <xref:System.Windows.Controls.Page> that is being navigated to can only be instantiated using a single, non-parameterless constructor.</span></span> <span data-ttu-id="a24f6-245">以下标记和代码中显示了具有非参数构造函数的 <xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-245">The <xref:System.Windows.Controls.Page> with the non-parameterless constructor is shown in the following markup and code.</span></span>

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

<span data-ttu-id="a24f6-246">以下标记和代码中显示了导航到具有非无参数的构造函数的 @no__t 的 @no__t 0。</span><span class="sxs-lookup"><span data-stu-id="a24f6-246">The <xref:System.Windows.Controls.Page> that navigates to the <xref:System.Windows.Controls.Page> with the non-parameterless constructor is shown in the following markup and code.</span></span>

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

<span data-ttu-id="a24f6-247">如果单击此 @no__t 上的 <xref:System.Windows.Controls.Page>，则将通过实例化 <xref:System.Windows.Controls.Page> 来启动导航，以导航到使用非参数构造函数并调用 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="a24f6-247">When the <xref:System.Windows.Documents.Hyperlink> on this <xref:System.Windows.Controls.Page> is clicked, navigation is initiated by instantiating the <xref:System.Windows.Controls.Page> to navigate to using the non-parameterless constructor and calling the <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a24f6-248"><xref:System.Windows.Navigation.NavigationService.Navigate%2A> 接受对 <xref:System.Windows.Navigation.NavigationService> 将导航到的对象的引用，而不接受对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 的引用。</span><span class="sxs-lookup"><span data-stu-id="a24f6-248"><xref:System.Windows.Navigation.NavigationService.Navigate%2A> accepts a reference to the object that the <xref:System.Windows.Navigation.NavigationService> will navigate to, rather than a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>

#### <a name="programmatic-navigation-with-a-pack-uri"></a><span data-ttu-id="a24f6-249">使用 Pack URI 以编程方式导航</span><span class="sxs-lookup"><span data-stu-id="a24f6-249">Programmatic Navigation with a Pack URI</span></span>

<span data-ttu-id="a24f6-250">如果需要以编程方式构造 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 的包（例如，只能在运行时确定 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]），则可以使用 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="a24f6-250">If you need to construct a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] programmatically (when you can only determine the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] at run time, for example), you can use the <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a24f6-251">这在下面的示例中显示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-251">This is shown in the following example.</span></span>

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a><span data-ttu-id="a24f6-252">刷新当前页</span><span class="sxs-lookup"><span data-stu-id="a24f6-252">Refreshing the Current Page</span></span>

<span data-ttu-id="a24f6-253">如果 <xref:System.Windows.Controls.Page> 的包与存储在 @no__t 属性中的 pack @no__t @no__t 相同，则不会下载该。</span><span class="sxs-lookup"><span data-stu-id="a24f6-253">A <xref:System.Windows.Controls.Page> is not downloaded if it has the same pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] as the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that is stored in the <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a24f6-254">若要强制 @no__t 为再次下载当前页，可以调用 <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> 方法，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-254">To force [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] to download the current page again, you can call the <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> method, as shown in the following example.</span></span>

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a><span data-ttu-id="a24f6-255">导航生存期</span><span class="sxs-lookup"><span data-stu-id="a24f6-255">Navigation Lifetime</span></span>

<span data-ttu-id="a24f6-256">如你所见，有很多方法初始化导航。</span><span class="sxs-lookup"><span data-stu-id="a24f6-256">There are many ways to initiate navigation, as you've seen.</span></span> <span data-ttu-id="a24f6-257">当启动导航时，导航正在进行时，你可以使用 <xref:System.Windows.Navigation.NavigationService> 实现的以下事件跟踪和影响导航：</span><span class="sxs-lookup"><span data-stu-id="a24f6-257">When navigation is initiated, and while navigation is in progress, you can track and influence the navigation using the following events that are implemented by <xref:System.Windows.Navigation.NavigationService>:</span></span>

- <span data-ttu-id="a24f6-258"><xref:System.Windows.Navigation.NavigationService.Navigating>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-258"><xref:System.Windows.Navigation.NavigationService.Navigating>.</span></span> <span data-ttu-id="a24f6-259">请求新导航时发生。</span><span class="sxs-lookup"><span data-stu-id="a24f6-259">Occurs when a new navigation is requested.</span></span> <span data-ttu-id="a24f6-260">可用于取消导航。</span><span class="sxs-lookup"><span data-stu-id="a24f6-260">Can be used to cancel the navigation.</span></span>

- <span data-ttu-id="a24f6-261"><xref:System.Windows.Navigation.NavigationService.NavigationProgress>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-261"><xref:System.Windows.Navigation.NavigationService.NavigationProgress>.</span></span> <span data-ttu-id="a24f6-262">在下载过程中定期发生，用于提供定位进度信息。</span><span class="sxs-lookup"><span data-stu-id="a24f6-262">Occurs periodically during a download to provide navigation progress information.</span></span>

- <span data-ttu-id="a24f6-263"><xref:System.Windows.Navigation.NavigationService.Navigated>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-263"><xref:System.Windows.Navigation.NavigationService.Navigated>.</span></span> <span data-ttu-id="a24f6-264">已定位并下载页时发生。</span><span class="sxs-lookup"><span data-stu-id="a24f6-264">Occurs when the page has been located and downloaded.</span></span>

- <span data-ttu-id="a24f6-265"><xref:System.Windows.Navigation.NavigationService.NavigationStopped>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-265"><xref:System.Windows.Navigation.NavigationService.NavigationStopped>.</span></span> <span data-ttu-id="a24f6-266">当导航停止时发生（通过调用 <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>），或在当前导航正在进行时请求新导航时发生。</span><span class="sxs-lookup"><span data-stu-id="a24f6-266">Occurs when the navigation is stopped (by calling <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>), or when a new navigation is requested while a current navigation is in progress.</span></span>

- <span data-ttu-id="a24f6-267"><xref:System.Windows.Navigation.NavigationService.NavigationFailed>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-267"><xref:System.Windows.Navigation.NavigationService.NavigationFailed>.</span></span> <span data-ttu-id="a24f6-268">在导航到所需内容的同时遇到错误时发生。</span><span class="sxs-lookup"><span data-stu-id="a24f6-268">Occurs when an error is raised while navigating to the requested content.</span></span>

- <span data-ttu-id="a24f6-269"><xref:System.Windows.Navigation.NavigationService.LoadCompleted>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-269"><xref:System.Windows.Navigation.NavigationService.LoadCompleted>.</span></span> <span data-ttu-id="a24f6-270">导航到的内容已加载和分析，并开始呈现时发生。</span><span class="sxs-lookup"><span data-stu-id="a24f6-270">Occurs when content that was navigated to is loaded and parsed, and has begun rendering.</span></span>

- <span data-ttu-id="a24f6-271"><xref:System.Windows.Navigation.NavigationService.FragmentNavigation>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-271"><xref:System.Windows.Navigation.NavigationService.FragmentNavigation>.</span></span> <span data-ttu-id="a24f6-272">导航到内容片段开始时发生，具体如何发生如下所述：</span><span class="sxs-lookup"><span data-stu-id="a24f6-272">Occurs when navigation to a content fragment begins, which happens:</span></span>

  - <span data-ttu-id="a24f6-273">立即，如果所需片段位于当前内容中。</span><span class="sxs-lookup"><span data-stu-id="a24f6-273">Immediately, if the desired fragment is in the current content.</span></span>

  - <span data-ttu-id="a24f6-274">源内容加载之后，如果所需片段在不同内容中。</span><span class="sxs-lookup"><span data-stu-id="a24f6-274">After the source content has been loaded, if the desired fragment is in different content.</span></span>

<span data-ttu-id="a24f6-275">引发导航事件的顺序如下图所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-275">The navigation events are raised in the order that is illustrated by the following figure.</span></span>

<span data-ttu-id="a24f6-276">![页面导航流程图](./media/navigation-overview/order-of-navigation-events.png "页面导航事件流程图")</span><span class="sxs-lookup"><span data-stu-id="a24f6-276">![Page navigation flow chart](./media/navigation-overview/order-of-navigation-events.png "Page navigation event flow chart")</span></span>

<span data-ttu-id="a24f6-277">通常情况下，@no__t 0 不关心这些事件。</span><span class="sxs-lookup"><span data-stu-id="a24f6-277">In general, a <xref:System.Windows.Controls.Page> isn't concerned about these events.</span></span> <span data-ttu-id="a24f6-278">更有可能应用程序与应用程序相关，出于此原因，这些事件也由 <xref:System.Windows.Application> 类引发：</span><span class="sxs-lookup"><span data-stu-id="a24f6-278">It is more likely that an application is concerned with them and, for that reason, these events are also raised by the <xref:System.Windows.Application> class:</span></span>

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

<span data-ttu-id="a24f6-279">每次 <xref:System.Windows.Navigation.NavigationService> 引发事件时，@no__t 1 类将引发相应的事件。</span><span class="sxs-lookup"><span data-stu-id="a24f6-279">Every time <xref:System.Windows.Navigation.NavigationService> raises an event, the <xref:System.Windows.Application> class raises the corresponding event.</span></span> <span data-ttu-id="a24f6-280"><xref:System.Windows.Controls.Frame> 和 <xref:System.Windows.Navigation.NavigationWindow> 提供相同的事件来检测其各自范围内的导航。</span><span class="sxs-lookup"><span data-stu-id="a24f6-280"><xref:System.Windows.Controls.Frame> and <xref:System.Windows.Navigation.NavigationWindow> offer the same events to detect navigation within their respective scopes.</span></span>

<span data-ttu-id="a24f6-281">在某些情况下，@no__t 可能对这些事件感兴趣。</span><span class="sxs-lookup"><span data-stu-id="a24f6-281">In some cases, a <xref:System.Windows.Controls.Page> might be interested in these events.</span></span> <span data-ttu-id="a24f6-282">例如，<xref:System.Windows.Controls.Page> 可处理 @no__t 1 事件，以确定是否取消导航。</span><span class="sxs-lookup"><span data-stu-id="a24f6-282">For example, a <xref:System.Windows.Controls.Page> might handle the <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> event to determine whether or not to cancel navigation away from itself.</span></span> <span data-ttu-id="a24f6-283">这在下面的示例中显示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-283">This is shown in the following example.</span></span>

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

<span data-ttu-id="a24f6-284">如果使用 @no__t 的导航事件注册处理程序，如前面的示例所示，还必须取消注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a24f6-284">If you register a handler with a navigation event from a <xref:System.Windows.Controls.Page>, as the preceding example does, you must also unregister the event handler.</span></span> <span data-ttu-id="a24f6-285">如果不这样做，可能会对 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 导航如何使用日记记住 @no__t 1 导航的相关副作用。</span><span class="sxs-lookup"><span data-stu-id="a24f6-285">If you don't, there may be side effects with respect to how [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] navigation remembers <xref:System.Windows.Controls.Page> navigation using the journal.</span></span>

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a><span data-ttu-id="a24f6-286">使用日志记住导航</span><span class="sxs-lookup"><span data-stu-id="a24f6-286">Remembering Navigation with the Journal</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="a24f6-287">使用两个堆栈来记住导航过的页：后退堆栈和前进堆栈。</span><span class="sxs-lookup"><span data-stu-id="a24f6-287">uses two stacks to remember the pages that you have navigated from: a back stack and a forward stack.</span></span> <span data-ttu-id="a24f6-288">当你从当前 <xref:System.Windows.Controls.Page> 导航到新的 <xref:System.Windows.Controls.Page> 或转发到现有 <xref:System.Windows.Controls.Page> 时，当前的 @no__t 将添加到*back 堆栈*中。</span><span class="sxs-lookup"><span data-stu-id="a24f6-288">When you navigate from the current <xref:System.Windows.Controls.Page> to a new <xref:System.Windows.Controls.Page> or forward to an existing <xref:System.Windows.Controls.Page>, the current <xref:System.Windows.Controls.Page> is added to the *back stack*.</span></span> <span data-ttu-id="a24f6-289">当你从当前 <xref:System.Windows.Controls.Page> 导航回到之前的 <xref:System.Windows.Controls.Page> 时，当前 @no__t 将添加到*前进堆栈*中。</span><span class="sxs-lookup"><span data-stu-id="a24f6-289">When you navigate from the current <xref:System.Windows.Controls.Page> back to the previous <xref:System.Windows.Controls.Page>, the current <xref:System.Windows.Controls.Page> is added to the *forward stack*.</span></span> <span data-ttu-id="a24f6-290">后退堆栈、前进堆栈和管理它们的功能统称为日志。</span><span class="sxs-lookup"><span data-stu-id="a24f6-290">The back stack, the forward stack, and the functionality to manage them, are collectively referred to as the journal.</span></span> <span data-ttu-id="a24f6-291">Back stack 和 forward 堆栈中的每一项都是 <xref:System.Windows.Navigation.JournalEntry> 类的实例，称为*日记条目*。</span><span class="sxs-lookup"><span data-stu-id="a24f6-291">Each item in the back stack and the forward stack is an instance of the <xref:System.Windows.Navigation.JournalEntry> class, and is referred to as a *journal entry*.</span></span>

#### <a name="navigating-the-journal-from-internet-explorer"></a><span data-ttu-id="a24f6-292">从 Internet Explorer 导航日志</span><span class="sxs-lookup"><span data-stu-id="a24f6-292">Navigating the Journal from Internet Explorer</span></span>

<span data-ttu-id="a24f6-293">从概念上讲，日记的工作方式与 Internet Explorer 中的 "**后退**" 和 "**前进**" 按钮的操作方式相同。</span><span class="sxs-lookup"><span data-stu-id="a24f6-293">Conceptually, the journal operates the same way that the **Back** and **Forward** buttons in Internet Explorer do.</span></span> <span data-ttu-id="a24f6-294">这些在下图中显示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-294">These are shown in the following figure.</span></span>

<span data-ttu-id="a24f6-295">"![后退" 和 "前进" 按钮](./media/navigation-overview/back-and-forward-navigation.png "用 \"后退\" 和 \"前进\" 按钮导航。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-295">![Back and Forward buttons](./media/navigation-overview/back-and-forward-navigation.png "Navigate with the back and forward buttons.")</span></span>

<span data-ttu-id="a24f6-296">对于由 Internet Explorer 承载的 @no__t 0，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 将日记集成到 Internet Explorer 的导航 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a24f6-296">For [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] that are hosted by Internet Explorer, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integrates the journal into the navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] of Internet Explorer.</span></span> <span data-ttu-id="a24f6-297">这允许用户使用 Internet Explorer 中的 "**后退**"、"**前进**" 和 "**最新页**" 按钮在 @no__t 中导航页面。</span><span class="sxs-lookup"><span data-stu-id="a24f6-297">This allows users to navigate pages in an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] by using the **Back**, **Forward**, and **Recent Pages** buttons in Internet Explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a24f6-298">在 Internet Explorer 中，当用户离开并返回到 @no__t 时，只有未保持活动状态的页的日记条目保留在日志中。</span><span class="sxs-lookup"><span data-stu-id="a24f6-298">In Internet Explorer, when a user navigates away from and back to an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], only the journal entries for pages that were not kept alive are retained in the journal.</span></span> <span data-ttu-id="a24f6-299">有关保持页处于活动状态的讨论，请参阅本主题后面的[页生存期和日志](#PageLifetime)。</span><span class="sxs-lookup"><span data-stu-id="a24f6-299">For discussion on keeping pages alive, see [Page Lifetime and the Journal](#PageLifetime) later in this topic.</span></span>

<span data-ttu-id="a24f6-300">默认情况下，在 Internet Explorer 的 "**最新页**" 列表中显示的每个 <xref:System.Windows.Controls.Page> 的文本都是 @no__t 的 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-300">By default, the text for each <xref:System.Windows.Controls.Page> that appears in the **Recent Pages** list of Internet Explorer is the [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="a24f6-301">很多情况下这对用户并没有什么特殊的意义。</span><span class="sxs-lookup"><span data-stu-id="a24f6-301">In many cases, this is not particularly meaningful to the user.</span></span> <span data-ttu-id="a24f6-302">幸运的是，可以使用以下选项更改文本：</span><span class="sxs-lookup"><span data-stu-id="a24f6-302">Fortunately, you can change the text using one the following options:</span></span>

1. <span data-ttu-id="a24f6-303">附加的 `JournalEntry.Name` 特性值。</span><span class="sxs-lookup"><span data-stu-id="a24f6-303">The attached `JournalEntry.Name` attribute value.</span></span>

2. <span data-ttu-id="a24f6-304">@No__t-0 特性值。</span><span class="sxs-lookup"><span data-stu-id="a24f6-304">The `Page.Title` attribute value.</span></span>

3. <span data-ttu-id="a24f6-305">当前 <xref:System.Windows.Controls.Page> 的 `Page.WindowTitle` 属性值和 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-305">The `Page.WindowTitle` attribute value and the [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the current <xref:System.Windows.Controls.Page>.</span></span>

4. <span data-ttu-id="a24f6-306">当前 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 的 <xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-306">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the current <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="a24f6-307">(默认)</span><span class="sxs-lookup"><span data-stu-id="a24f6-307">(Default)</span></span>

<span data-ttu-id="a24f6-308">选项列出的顺序和查找文本的优先级顺序一致。</span><span class="sxs-lookup"><span data-stu-id="a24f6-308">The order in which the options are listed matches the order of precedence for finding the text.</span></span> <span data-ttu-id="a24f6-309">例如，如果设置了 `JournalEntry.Name`，则忽略其他值。</span><span class="sxs-lookup"><span data-stu-id="a24f6-309">For example, if `JournalEntry.Name` is set, the other values are ignored.</span></span>

<span data-ttu-id="a24f6-310">下面的示例使用 `Page.Title` 特性来更改为日记本项显示的文本。</span><span class="sxs-lookup"><span data-stu-id="a24f6-310">The following example uses the `Page.Title` attribute to change the text that appears for a journal entry.</span></span>

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a><span data-ttu-id="a24f6-311">使用 WPF 导航日志</span><span class="sxs-lookup"><span data-stu-id="a24f6-311">Navigating the Journal Using WPF</span></span>

<span data-ttu-id="a24f6-312">尽管用户可以使用 Internet Explorer 中的 "**后退**"、"**前进**" 和 "**最新" 页**导航日记，但你也可以使用 @no__t 提供的声明性和编程机制导航日志。</span><span class="sxs-lookup"><span data-stu-id="a24f6-312">Although a user can navigate the journal by using the **Back**, **Forward**, and **Recent Pages** in Internet Explorer, you can also navigate the journal using both declarative and programmatic mechanisms provided by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span> <span data-ttu-id="a24f6-313">这样做的一个原因是在页面中提供自定义导航 Ui。</span><span class="sxs-lookup"><span data-stu-id="a24f6-313">One reason to do this is to provide custom navigation UIs in your pages.</span></span>

<span data-ttu-id="a24f6-314">可以通过使用 <xref:System.Windows.Input.NavigationCommands> 公开的导航命令以声明方式添加日记本导航支持。</span><span class="sxs-lookup"><span data-stu-id="a24f6-314">You can declaratively add journal navigation support by using the navigation commands exposed by <xref:System.Windows.Input.NavigationCommands>.</span></span> <span data-ttu-id="a24f6-315">下面的示例演示如何使用 @no__t 的导航命令。</span><span class="sxs-lookup"><span data-stu-id="a24f6-315">The following example demonstrates how to use the `BrowseBack` navigation command.</span></span>

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

<span data-ttu-id="a24f6-316">可以通过使用 <xref:System.Windows.Navigation.NavigationService> 类的以下成员之一以编程方式导航日记：</span><span class="sxs-lookup"><span data-stu-id="a24f6-316">You can programmatically navigate the journal by using one of the following members of the <xref:System.Windows.Navigation.NavigationService> class:</span></span>

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

<span data-ttu-id="a24f6-317">此日志还可以通过编程方式进行操作，如本主题后面的将[内容状态保留为导航历史记录](#RetainingContentStateWithNavigationHistory)中所述。</span><span class="sxs-lookup"><span data-stu-id="a24f6-317">The journal can also be manipulated programmatically, as discussed in [Retaining Content State with Navigation History](#RetainingContentStateWithNavigationHistory) later in this topic.</span></span>

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a><span data-ttu-id="a24f6-318">页生存期和日志</span><span class="sxs-lookup"><span data-stu-id="a24f6-318">Page Lifetime and the Journal</span></span>

<span data-ttu-id="a24f6-319">请考虑一个 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]，其中包含多个包含丰富内容的页面，包括图形、动画和媒体。</span><span class="sxs-lookup"><span data-stu-id="a24f6-319">Consider an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] with several pages that contain rich content, including graphics, animations, and media.</span></span> <span data-ttu-id="a24f6-320">这类页的内存占用量可能相当大，尤其是使用视频和音频媒体的时候。</span><span class="sxs-lookup"><span data-stu-id="a24f6-320">The memory footprint for pages like these could be quite large, particularly if video and audio media are used.</span></span> <span data-ttu-id="a24f6-321">假设日志 "记住" 已导航到的页面，此类 @no__t 会迅速消耗大量内存量。</span><span class="sxs-lookup"><span data-stu-id="a24f6-321">Given that the journal "remembers" pages that have been navigated to, such an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] could quickly consume a large and noticeable amount of memory.</span></span>

<span data-ttu-id="a24f6-322">出于此原因，日志的默认行为是在每个日记条目中存储 @no__t 的元数据，而不是对 @no__t 的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="a24f6-322">For this reason, the default behavior of the journal is to store <xref:System.Windows.Controls.Page> metadata in each journal entry rather than a reference to a <xref:System.Windows.Controls.Page> object.</span></span> <span data-ttu-id="a24f6-323">导航到某个日志条目时，其 @no__t 的元数据用于创建指定 @no__t 的新实例。</span><span class="sxs-lookup"><span data-stu-id="a24f6-323">When a journal entry is navigated to, its <xref:System.Windows.Controls.Page> metadata is used to create a new instance of the specified <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="a24f6-324">因此，所导航的每个 @no__t 0 都具有如下图所示的生存期。</span><span class="sxs-lookup"><span data-stu-id="a24f6-324">As a consequence, each <xref:System.Windows.Controls.Page> that is navigated has the lifetime that is illustrated by the following figure.</span></span>

<span data-ttu-id="a24f6-325">![页面生存期](./media/navigation-overview/navigated-page-lifetime.png "：导航页面时显示生存期。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-325">![Page lifetime](./media/navigation-overview/navigated-page-lifetime.png "This shows the lifetime when a page is navigated.")</span></span>

<span data-ttu-id="a24f6-326">尽管使用默认日记行为可以节省内存消耗，但每页呈现性能可能会降低;呈现 <xref:System.Windows.Controls.Page> 会很耗时，尤其是在有大量内容时。</span><span class="sxs-lookup"><span data-stu-id="a24f6-326">Although using the default journaling behavior can save on memory consumption, per-page rendering performance might be reduced; reinstantiating a <xref:System.Windows.Controls.Page> can be time-intensive, particularly if it has a lot of content.</span></span> <span data-ttu-id="a24f6-327">如果需要在日记中保留 <xref:System.Windows.Controls.Page> 实例，可以通过两种方法进行绘制。</span><span class="sxs-lookup"><span data-stu-id="a24f6-327">If you need to retain a <xref:System.Windows.Controls.Page> instance in the journal, you can draw on two techniques for doing so.</span></span> <span data-ttu-id="a24f6-328">首先，可以通过调用 @no__t 的方法以编程方式导航到 <xref:System.Windows.Controls.Page> 对象。</span><span class="sxs-lookup"><span data-stu-id="a24f6-328">First, you can programmatically navigate to a <xref:System.Windows.Controls.Page> object by calling the <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="a24f6-329">其次，可以通过将 <xref:System.Windows.Controls.Page.KeepAlive%2A> 属性设置为 `true` （默认值为 `false`）来指定 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 在日志中保留 @no__t 的实例。</span><span class="sxs-lookup"><span data-stu-id="a24f6-329">Second, you can specify that [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] retain an instance of a <xref:System.Windows.Controls.Page> in the journal by setting the <xref:System.Windows.Controls.Page.KeepAlive%2A> property to `true` (the default is `false`).</span></span> <span data-ttu-id="a24f6-330">如以下示例中所示，可以在标记中以声明方式设置 <xref:System.Windows.Controls.Page.KeepAlive%2A>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-330">As shown in the following example, you can set <xref:System.Windows.Controls.Page.KeepAlive%2A> declaratively in markup.</span></span>

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

<span data-ttu-id="a24f6-331">保持活动状态的 @no__t 的生存期与不是相同。</span><span class="sxs-lookup"><span data-stu-id="a24f6-331">The lifetime of a <xref:System.Windows.Controls.Page> that is kept alive is subtly different from one that is not.</span></span> <span data-ttu-id="a24f6-332">第一次导航到 <xref:System.Windows.Controls.Page> 时，将会将其实例化，就像 @no__t 不会保持活动状态一样。</span><span class="sxs-lookup"><span data-stu-id="a24f6-332">The first time a <xref:System.Windows.Controls.Page> that is kept alive is navigated to, it is instantiated just like a <xref:System.Windows.Controls.Page> that is not kept alive.</span></span> <span data-ttu-id="a24f6-333">但是，因为 <xref:System.Windows.Controls.Page> 的实例保留在日志中，因此只要它保留在日志中，就永远不会再对其进行实例化。</span><span class="sxs-lookup"><span data-stu-id="a24f6-333">However, because an instance of the <xref:System.Windows.Controls.Page> is retained in the journal, it is never instantiated again for as long as it remains in the journal.</span></span> <span data-ttu-id="a24f6-334">因此，如果 @no__t 的初始化逻辑需要在每次导航到 @no__t 时调用，则应将其从构造函数移到 @no__t 2 事件的处理程序中。</span><span class="sxs-lookup"><span data-stu-id="a24f6-334">Consequently, if a <xref:System.Windows.Controls.Page> has initialization logic that needs to be called every time the <xref:System.Windows.Controls.Page> is navigated to, you should move it from the constructor into a handler for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="a24f6-335">如下图所示，每次导航到和从 <xref:System.Windows.Controls.Page> 时，仍然会引发 <xref:System.Windows.FrameworkElement.Loaded> 和 @no__t 1 事件。</span><span class="sxs-lookup"><span data-stu-id="a24f6-335">As shown in the following figure, the <xref:System.Windows.FrameworkElement.Loaded> and <xref:System.Windows.FrameworkElement.Unloaded> events are still raised each time a <xref:System.Windows.Controls.Page> is navigated to and from, respectively.</span></span>

<span data-ttu-id="a24f6-336">当向外和向外导航页面时，将![引发加载的和已卸载的事件](./media/navigation-overview/loaded-and-unloaded-events.png "，并引发已卸载的事件。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-336">![When the Loaded and Unloaded events are raised](./media/navigation-overview/loaded-and-unloaded-events.png "Loaded and unloaded events are raised when a page is navigated to and from.")</span></span>

<span data-ttu-id="a24f6-337">如果 @no__t 0 未保持活动状态，则不应执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="a24f6-337">When a <xref:System.Windows.Controls.Page> is not kept alive, you should not do either of the following:</span></span>

- <span data-ttu-id="a24f6-338">存储对它或它的任何部分的引用。</span><span class="sxs-lookup"><span data-stu-id="a24f6-338">Store a reference to it, or any part of it.</span></span>

- <span data-ttu-id="a24f6-339">将事件处理程序注册到并非由其实现的事件。</span><span class="sxs-lookup"><span data-stu-id="a24f6-339">Register event handlers with events that are not implemented by it.</span></span>

<span data-ttu-id="a24f6-340">执行上述任一操作都将创建强制在内存中保留 @no__t 的引用，即使已从日志中删除。</span><span class="sxs-lookup"><span data-stu-id="a24f6-340">Doing either of these will create references that force the <xref:System.Windows.Controls.Page> to be retained in memory, even after it has been removed from the journal.</span></span>

<span data-ttu-id="a24f6-341">通常，您应该首选默认 <xref:System.Windows.Controls.Page> 行为，不会使 @no__t 保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="a24f6-341">In general, you should prefer the default <xref:System.Windows.Controls.Page> behavior of not keeping a <xref:System.Windows.Controls.Page> alive.</span></span> <span data-ttu-id="a24f6-342">但是，这会存在将在下一节中讨论的状态影响。</span><span class="sxs-lookup"><span data-stu-id="a24f6-342">However, this has state implications that are discussed in the next section.</span></span>

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a><span data-ttu-id="a24f6-343">保留导航历史记录的内容状态</span><span class="sxs-lookup"><span data-stu-id="a24f6-343">Retaining Content State with Navigation History</span></span>

<span data-ttu-id="a24f6-344">如果 @no__t 0 未保持活动状态，并且它具有收集用户数据的控件，则当用户离开并返回到 @no__t 时，数据会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="a24f6-344">If a <xref:System.Windows.Controls.Page> is not kept alive, and it has controls that collect data from the user, what happens to the data if a user navigates away from and back to the <xref:System.Windows.Controls.Page>?</span></span> <span data-ttu-id="a24f6-345">从用户体验角度，用户应该会希望看到他们以前输入的数据。</span><span class="sxs-lookup"><span data-stu-id="a24f6-345">From a user experience perspective, the user should expect to see the data they entered previously.</span></span> <span data-ttu-id="a24f6-346">遗憾的是，由于每个导航都创建了 <xref:System.Windows.Controls.Page> 的新实例，因此收集数据的控件重新实例化，数据会丢失。</span><span class="sxs-lookup"><span data-stu-id="a24f6-346">Unfortunately, because a new instance of the <xref:System.Windows.Controls.Page> is created with each navigation, the controls that collected the data are reinstantiated and the data is lost.</span></span>

<span data-ttu-id="a24f6-347">幸运的是，日记本提供对在 <xref:System.Windows.Controls.Page> 导航（包括控制数据）之间记录数据的支持。</span><span class="sxs-lookup"><span data-stu-id="a24f6-347">Fortunately, the journal provides support for remembering data across <xref:System.Windows.Controls.Page> navigations, including control data.</span></span> <span data-ttu-id="a24f6-348">具体而言，每个 @no__t 的日记条目都充当关联的 <xref:System.Windows.Controls.Page> 状态的临时容器。</span><span class="sxs-lookup"><span data-stu-id="a24f6-348">Specifically, the journal entry for each <xref:System.Windows.Controls.Page> acts as a temporary container for the associated <xref:System.Windows.Controls.Page> state.</span></span> <span data-ttu-id="a24f6-349">以下步骤概述了从导航 <xref:System.Windows.Controls.Page> 时如何使用此支持：</span><span class="sxs-lookup"><span data-stu-id="a24f6-349">The following steps outline how this support is used when a <xref:System.Windows.Controls.Page> is navigated from:</span></span>

1. <span data-ttu-id="a24f6-350">当前 <xref:System.Windows.Controls.Page> 的条目将添加到日志中。</span><span class="sxs-lookup"><span data-stu-id="a24f6-350">An entry for the current <xref:System.Windows.Controls.Page> is added to the journal.</span></span>

2. <span data-ttu-id="a24f6-351">@No__t 的状态与该页面的日记条目一起存储，该条目将添加到后堆栈中。</span><span class="sxs-lookup"><span data-stu-id="a24f6-351">The state of the <xref:System.Windows.Controls.Page> is stored with the journal entry for that page, which is added to the back stack.</span></span>

3. <span data-ttu-id="a24f6-352">将导航到新 <xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-352">The new <xref:System.Windows.Controls.Page> is navigated to.</span></span>

<span data-ttu-id="a24f6-353">当使用日记向后导航到 <xref:System.Windows.Controls.Page> 页面时，将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a24f6-353">When the page <xref:System.Windows.Controls.Page> is navigated back to, using the journal, the following steps take place:</span></span>

1. <span data-ttu-id="a24f6-354">@No__t （back 堆栈顶部的日记条目）实例化。</span><span class="sxs-lookup"><span data-stu-id="a24f6-354">The <xref:System.Windows.Controls.Page> (the top journal entry on the back stack) is instantiated.</span></span>

2. <span data-ttu-id="a24f6-355">将用与 @no__t 的日记条目一起存储的状态来刷新 <xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-355">The <xref:System.Windows.Controls.Page> is refreshed with the state that was stored with the journal entry for the <xref:System.Windows.Controls.Page>.</span></span>

3. <span data-ttu-id="a24f6-356">向后导航到 <xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-356">The <xref:System.Windows.Controls.Page> is navigated back to.</span></span>

<span data-ttu-id="a24f6-357">在 @no__t 上使用以下控件时 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 自动使用此支持：</span><span class="sxs-lookup"><span data-stu-id="a24f6-357">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] automatically uses this support when the following controls are used on a <xref:System.Windows.Controls.Page>:</span></span>

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

<span data-ttu-id="a24f6-358">如果 <xref:System.Windows.Controls.Page> 使用这些控件，则会在 @no__t 1 导航中记录输入的数据，如下图所**示 @no__t-** 3 中所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-358">If a <xref:System.Windows.Controls.Page> uses these controls, data entered into them is remembered across <xref:System.Windows.Controls.Page> navigations, as demonstrated by the **Favorite Color**<xref:System.Windows.Controls.ListBox> in the following figure.</span></span>

<span data-ttu-id="a24f6-359">![包含控件的页面，这些控件可记住输入的状态](./media/navigation-overview/data-remembered-across-page-navigations.png "数据跨页面导航。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-359">![Page with controls that remember state](./media/navigation-overview/data-remembered-across-page-navigations.png "Data entered is remembered across page navigations.")</span></span>

<span data-ttu-id="a24f6-360">如果 @no__t 为除前面列表中的控件以外的其他控件，或者当状态存储在自定义对象中时，则需要编写代码来使日志记住 @no__t 导航中的状态。</span><span class="sxs-lookup"><span data-stu-id="a24f6-360">When a <xref:System.Windows.Controls.Page> has controls other than those in the preceding list, or when state is stored in custom objects, you need to write code to cause the journal to remember state across <xref:System.Windows.Controls.Page> navigations.</span></span>

<span data-ttu-id="a24f6-361">如果需要在 <xref:System.Windows.Controls.Page> 导航之间记录小部分的状态，可以使用配置了 <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> 元数据标志的依赖属性（请参阅 <xref:System.Windows.DependencyProperty>）。</span><span class="sxs-lookup"><span data-stu-id="a24f6-361">If you need to remember small pieces of state across <xref:System.Windows.Controls.Page> navigations, you can use dependency properties (see <xref:System.Windows.DependencyProperty>) that are configured with the <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> metadata flag.</span></span>

<span data-ttu-id="a24f6-362">如果 @no__t 0 需要记住的每个导航的状态包含多个数据片段，你可能会发现，将状态封装到单个类并实现 @no__t 1 接口所需的代码要少得多。</span><span class="sxs-lookup"><span data-stu-id="a24f6-362">If the state that your <xref:System.Windows.Controls.Page> needs to remember across navigations comprises multiple pieces of data, you may find it less code intensive to encapsulate your state in a single class and implement the <xref:System.Windows.Navigation.IProvideCustomContentState> interface.</span></span>

<span data-ttu-id="a24f6-363">如果需要在单个 @no__t 的各个状态之间导航，而无需从 @no__t 中导航，则可以使用 <xref:System.Windows.Navigation.IProvideCustomContentState> 和 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-363">If you need to navigate through various states of a single <xref:System.Windows.Controls.Page>, without navigating from the <xref:System.Windows.Controls.Page> itself, you can use <xref:System.Windows.Navigation.IProvideCustomContentState> and <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>.</span></span>

<a name="Cookies"></a>

### <a name="cookies"></a><span data-ttu-id="a24f6-364">Cookie</span><span class="sxs-lookup"><span data-stu-id="a24f6-364">Cookies</span></span>

<span data-ttu-id="a24f6-365">@No__t 0 应用程序可以存储数据的另一种方式是使用 cookie，这些 cookie 是使用 @no__t 1 和 @no__t 2 方法创建、更新和删除的。</span><span class="sxs-lookup"><span data-stu-id="a24f6-365">Another way that [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications can store data is with cookies, which are created, updated, and deleted by using the <xref:System.Windows.Application.SetCookie%2A> and <xref:System.Windows.Application.GetCookie%2A> methods.</span></span> <span data-ttu-id="a24f6-366">可以在 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中创建的 cookie 与其他类型的 Web 应用程序使用的 cookie 相同;cookie 是由应用程序在客户端计算机上或跨应用程序会话存储的任意数据块。</span><span class="sxs-lookup"><span data-stu-id="a24f6-366">The cookies that you can create in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] are the same cookies that other types of Web applications use; cookies are arbitrary pieces of data that are stored by an application on a client machine either during or across application sessions.</span></span> <span data-ttu-id="a24f6-367">Cookie 数据通常采用以下格式的名称/值对的形式。</span><span class="sxs-lookup"><span data-stu-id="a24f6-367">Cookie data typically takes the form of a name/value pair in the following format.</span></span>

<span data-ttu-id="a24f6-368">*Name* `=` *Value*</span><span class="sxs-lookup"><span data-stu-id="a24f6-368">*Name* `=` *Value*</span></span>

<span data-ttu-id="a24f6-369">如果将数据传递到 <xref:System.Windows.Application.SetCookie%2A>，以及应为其设置 cookie 的位置的 @no__t 1，则会在内存中创建一个 cookie，并且该 cookie 仅适用于当前应用程序会话的持续时间。</span><span class="sxs-lookup"><span data-stu-id="a24f6-369">When the data is passed to <xref:System.Windows.Application.SetCookie%2A>, along with the <xref:System.Uri> of the location for which the cookie should be set, a cookie is created in-memory, and it is only available for the duration of the current application session.</span></span> <span data-ttu-id="a24f6-370">这种类型的 cookie 称为*会话 cookie*。</span><span class="sxs-lookup"><span data-stu-id="a24f6-370">This type of cookie is referred to as a *session cookie*.</span></span>

<span data-ttu-id="a24f6-371">要跨应用程序会话存储 cookie，必须使用以下格式将到期日期添加到 cookie。</span><span class="sxs-lookup"><span data-stu-id="a24f6-371">To store a cookie across application sessions, an expiration date must be added to the cookie, using the following format.</span></span>

<span data-ttu-id="a24f6-372">*NAME* `=` *VALUE* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`</span><span class="sxs-lookup"><span data-stu-id="a24f6-372">*NAME* `=` *VALUE* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`</span></span>

<span data-ttu-id="a24f6-373">在 cookie 过期之前，具有到期日期的 cookie 存储在当前的 Windows 安装程序的临时 Internet Files 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a24f6-373">A cookie with an expiration date is stored in the current Windows installation's Temporary Internet Files folder until the cookie expires.</span></span> <span data-ttu-id="a24f6-374">此类 cookie 称为*永久性 cookie* ，因为它在应用程序会话之间保持不变。</span><span class="sxs-lookup"><span data-stu-id="a24f6-374">Such a cookie is known as a *persistent cookie* because it persists across application sessions.</span></span>

<span data-ttu-id="a24f6-375">可以通过调用 <xref:System.Windows.Application.GetCookie%2A> 方法来检索会话和永久性 cookie，同时传递使用 <xref:System.Windows.Application.SetCookie%2A> 方法设置 cookie 的位置的 @no__t 1。</span><span class="sxs-lookup"><span data-stu-id="a24f6-375">You retrieve both session and persistent cookies by calling the <xref:System.Windows.Application.GetCookie%2A> method, passing the <xref:System.Uri> of the location where the cookie was set with the <xref:System.Windows.Application.SetCookie%2A> method.</span></span>

<span data-ttu-id="a24f6-376">下面是在 @no__t 中支持 cookie 的一些方式：</span><span class="sxs-lookup"><span data-stu-id="a24f6-376">The following are some of the ways that cookies are supported in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]:</span></span>

- <span data-ttu-id="a24f6-377">@no__t 0 独立应用程序，[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 可创建和管理 cookie。</span><span class="sxs-lookup"><span data-stu-id="a24f6-377">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone applications and [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] can both create and manage cookies.</span></span>

- <span data-ttu-id="a24f6-378">可以从浏览器访问 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 创建的 cookie。</span><span class="sxs-lookup"><span data-stu-id="a24f6-378">Cookies that are created by an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] can be accessed from the browser.</span></span>

- <span data-ttu-id="a24f6-379">来自相同域的 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 可以创建和共享 cookie。</span><span class="sxs-lookup"><span data-stu-id="a24f6-379">[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] from the same domain can create and share cookies.</span></span>

- <span data-ttu-id="a24f6-380">@no__t （0）和来自同一域的 HTML 页面可以创建和共享 cookie。</span><span class="sxs-lookup"><span data-stu-id="a24f6-380">[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] and HTML pages from the same domain can create and share cookies.</span></span>

- <span data-ttu-id="a24f6-381">当 @no__t 0 和松散的 @no__t 1 页发出 Web 请求时，会调度 cookie。</span><span class="sxs-lookup"><span data-stu-id="a24f6-381">Cookies are dispatched when [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] and loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages make Web requests.</span></span>

- <span data-ttu-id="a24f6-382">在 IFRAME 中承载的顶级 @no__t （0）和 @no__t 1 均可访问 cookie。</span><span class="sxs-lookup"><span data-stu-id="a24f6-382">Both top-level [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] and [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] hosted in IFRAMES can access cookies.</span></span>

- <span data-ttu-id="a24f6-383">@No__t-0 中的 Cookie 支持对于所有受支持的浏览器都是相同的。</span><span class="sxs-lookup"><span data-stu-id="a24f6-383">Cookie support in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] is the same for all supported browsers.</span></span>

- <span data-ttu-id="a24f6-384">在 Internet Explorer 中，与 cookie 相关的 P3P 策略可通过 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 进行处理，特别是对于第一方和第三方 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-384">In Internet Explorer, P3P policy that pertains to cookies is honored by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], particularly with respect to first-party and third-party [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].</span></span>

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a><span data-ttu-id="a24f6-385">结构化导航</span><span class="sxs-lookup"><span data-stu-id="a24f6-385">Structured Navigation</span></span>

<span data-ttu-id="a24f6-386">如果需要将数据从一个 <xref:System.Windows.Controls.Page> 传递到另一个，则可以将数据作为参数传递到 @no__t 的非参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="a24f6-386">If you need to pass data from one <xref:System.Windows.Controls.Page> to another, you can pass the data as arguments to a non-parameterless constructor of the <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="a24f6-387">请注意，如果使用此方法，则必须保持 <xref:System.Windows.Controls.Page> 活动状态;否则，下一次导航到 <xref:System.Windows.Controls.Page> 时，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 使用无参数构造函数重新实例化 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-387">Note that if you use this technique, you must keep the <xref:System.Windows.Controls.Page> alive; if not, the next time you navigate to the <xref:System.Windows.Controls.Page>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] reinstantiates the <xref:System.Windows.Controls.Page> by using the parameterless constructor.</span></span>

<span data-ttu-id="a24f6-388">或者，<xref:System.Windows.Controls.Page> 可以实现用需要传递的数据设置的属性。</span><span class="sxs-lookup"><span data-stu-id="a24f6-388">Alternatively, your <xref:System.Windows.Controls.Page> can implement properties that are set with the data that needs to be passed.</span></span> <span data-ttu-id="a24f6-389">不过，当 <xref:System.Windows.Controls.Page> 需要将数据传递回导航到它的 <xref:System.Windows.Controls.Page> 时，这会变得棘手。</span><span class="sxs-lookup"><span data-stu-id="a24f6-389">Things become tricky, however, when a <xref:System.Windows.Controls.Page> needs to pass data back to the <xref:System.Windows.Controls.Page> that navigated to it.</span></span> <span data-ttu-id="a24f6-390">问题在于，导航不会以本机方式支持用于确保在从其导航后将返回 <xref:System.Windows.Controls.Page> 的机制。</span><span class="sxs-lookup"><span data-stu-id="a24f6-390">The problem is that navigation doesn't natively support mechanisms for guaranteeing that a <xref:System.Windows.Controls.Page> will be returned to after it is navigated from.</span></span> <span data-ttu-id="a24f6-391">实质上，导航不支持调用/返回语义。</span><span class="sxs-lookup"><span data-stu-id="a24f6-391">Essentially, navigation doesn't support call/return semantics.</span></span> <span data-ttu-id="a24f6-392">若要解决此问题，@no__t 提供 @no__t 1 类，可用于确保以可预测和结构化方式返回 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-392">To solve this problem, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides the <xref:System.Windows.Navigation.PageFunction%601> class that you can use to ensure that a <xref:System.Windows.Controls.Page> is returned to in a predictable and structured fashion.</span></span> <span data-ttu-id="a24f6-393">有关详细信息，请参阅[结构化导航概述](structured-navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a24f6-393">For more information, see [Structured Navigation Overview](structured-navigation-overview.md).</span></span>

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a><span data-ttu-id="a24f6-394">NavigationWindow 类</span><span class="sxs-lookup"><span data-stu-id="a24f6-394">The NavigationWindow Class</span></span>

<span data-ttu-id="a24f6-395">到目前为止，你已全面了解最有可能用可导航内容生成应用程序的导航服务。</span><span class="sxs-lookup"><span data-stu-id="a24f6-395">To this point, you've seen the gamut of navigation services that you are most likely to use to build applications with navigable content.</span></span> <span data-ttu-id="a24f6-396">这些服务是在 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 的上下文中讨论的，不过它们并不限于 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a24f6-396">These services were discussed in the context of [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], although they are not limited to [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].</span></span> <span data-ttu-id="a24f6-397">现代操作系统和 Windows 应用程序利用了新式用户的浏览器体验，将浏览器样式的导航并入独立的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a24f6-397">Modern operating systems and Windows applications take advantage of the browser experience of modern users to incorporate browser-style navigation into standalone applications.</span></span> <span data-ttu-id="a24f6-398">常见示例包括：</span><span class="sxs-lookup"><span data-stu-id="a24f6-398">Common examples include:</span></span>

- <span data-ttu-id="a24f6-399">**Word 同义词库**：导航 word 选项。</span><span class="sxs-lookup"><span data-stu-id="a24f6-399">**Word Thesaurus**: Navigate word choices.</span></span>

- <span data-ttu-id="a24f6-400">**文件资源管理器**：导航文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="a24f6-400">**File Explorer**: Navigate files and folders.</span></span>

- <span data-ttu-id="a24f6-401">**向导**：将复杂任务分解到多个可在之间导航的页面。</span><span class="sxs-lookup"><span data-stu-id="a24f6-401">**Wizards**: Breaking down a complex task into multiple pages that can be navigated between.</span></span> <span data-ttu-id="a24f6-402">例如，处理添加和删除 Windows 功能的 Windows 组件向导。</span><span class="sxs-lookup"><span data-stu-id="a24f6-402">An example is the Windows Components Wizard that handles adding and removing Windows features.</span></span>

<span data-ttu-id="a24f6-403">若要将浏览器样式的导航并入独立应用程序，可以使用 <xref:System.Windows.Navigation.NavigationWindow> 类。</span><span class="sxs-lookup"><span data-stu-id="a24f6-403">To incorporate browser-style navigation into your standalone applications, you can use the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="a24f6-404">@no__t 派生自 <xref:System.Windows.Window>，并将其扩展为支持 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 提供的导航。</span><span class="sxs-lookup"><span data-stu-id="a24f6-404"><xref:System.Windows.Navigation.NavigationWindow> derives from <xref:System.Windows.Window> and extends it with the same support for navigation that [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] provide.</span></span> <span data-ttu-id="a24f6-405">你可以使用 <xref:System.Windows.Navigation.NavigationWindow> 作为独立应用程序的主窗口，或者使用作为辅助窗口（如对话框）。</span><span class="sxs-lookup"><span data-stu-id="a24f6-405">You can use <xref:System.Windows.Navigation.NavigationWindow> as either the main window of your standalone application or as a secondary window such as a dialog box.</span></span>

<span data-ttu-id="a24f6-406">若要实现 <xref:System.Windows.Navigation.NavigationWindow>，与 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] （<xref:System.Windows.Window>、<xref:System.Windows.Controls.Page> 等）中的大多数顶级类一样，你可以使用标记和代码隐藏的组合。</span><span class="sxs-lookup"><span data-stu-id="a24f6-406">To implement a <xref:System.Windows.Navigation.NavigationWindow>, as with most top-level classes in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] (<xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, and so on), you use a combination of markup and code-behind.</span></span> <span data-ttu-id="a24f6-407">这在下面的示例中显示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-407">This is shown in the following example.</span></span>

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

<span data-ttu-id="a24f6-408">此代码创建一个 <xref:System.Windows.Navigation.NavigationWindow>，在 <xref:System.Windows.Navigation.NavigationWindow> 打开时，它会自动导航到 @no__t （）。</span><span class="sxs-lookup"><span data-stu-id="a24f6-408">This code creates a <xref:System.Windows.Navigation.NavigationWindow> that automatically navigates to a <xref:System.Windows.Controls.Page> (HomePage.xaml) when the <xref:System.Windows.Navigation.NavigationWindow> is opened.</span></span> <span data-ttu-id="a24f6-409">如果 @no__t 为主应用程序窗口，则可以使用 `StartupUri` 属性启动它。</span><span class="sxs-lookup"><span data-stu-id="a24f6-409">If the <xref:System.Windows.Navigation.NavigationWindow> is the main application window, you can use the `StartupUri` attribute to launch it.</span></span> <span data-ttu-id="a24f6-410">这在以下标记中显示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-410">This is shown in the following markup.</span></span>

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

<span data-ttu-id="a24f6-411">下图显示了 <xref:System.Windows.Navigation.NavigationWindow> 作为独立应用程序的主窗口。</span><span class="sxs-lookup"><span data-stu-id="a24f6-411">The following figure shows the <xref:System.Windows.Navigation.NavigationWindow> as the main window of a standalone application.</span></span>

<span data-ttu-id="a24f6-412">主窗口的![主]窗口(./media/navigation-overview/navigation-window-as-main-window.png "导航窗口")</span><span class="sxs-lookup"><span data-stu-id="a24f6-412">![A main window](./media/navigation-overview/navigation-window-as-main-window.png "Navigation window as the main window")</span></span>

<span data-ttu-id="a24f6-413">从图中可以看到 <xref:System.Windows.Navigation.NavigationWindow> 具有标题，即使未在前面示例的 <xref:System.Windows.Navigation.NavigationWindow> 实现代码中进行设置。</span><span class="sxs-lookup"><span data-stu-id="a24f6-413">From the figure, you can see that the <xref:System.Windows.Navigation.NavigationWindow> has a title, even though it wasn't set in the <xref:System.Windows.Navigation.NavigationWindow> implementation code from the preceding example.</span></span> <span data-ttu-id="a24f6-414">而是使用 <xref:System.Windows.Controls.Page.WindowTitle%2A> 属性设置标题，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-414">Instead, the title is set using the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, which is shown in the following code.</span></span>

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

<span data-ttu-id="a24f6-415">设置 <xref:System.Windows.Controls.Page.WindowWidth%2A> 和 @no__t 属性还会影响 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-415">Setting the <xref:System.Windows.Controls.Page.WindowWidth%2A> and <xref:System.Windows.Controls.Page.WindowHeight%2A> properties also affects the <xref:System.Windows.Navigation.NavigationWindow>.</span></span>

<span data-ttu-id="a24f6-416">通常，当需要自定义其行为或外观时，可以实现自己的 @no__t 0。</span><span class="sxs-lookup"><span data-stu-id="a24f6-416">Usually, you implement your own <xref:System.Windows.Navigation.NavigationWindow> when you need to customize either its behavior or its appearance.</span></span> <span data-ttu-id="a24f6-417">如果没有执行上述操作，则可以使用快捷方式。</span><span class="sxs-lookup"><span data-stu-id="a24f6-417">If you do neither, you can use a shortcut.</span></span> <span data-ttu-id="a24f6-418">如果在独立的应用程序中将 @no__t 的 pack <xref:System.Windows.Controls.Page> 指定为第 2 @no__t，则 <xref:System.Windows.Application> 会自动创建 @no__t 以托管 @no__t 5。</span><span class="sxs-lookup"><span data-stu-id="a24f6-418">If you specify the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of a <xref:System.Windows.Controls.Page> as the <xref:System.Windows.Application.StartupUri%2A> in a standalone application, <xref:System.Windows.Application> automatically creates a <xref:System.Windows.Navigation.NavigationWindow> to host the <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="a24f6-419">以下标记显示如何实现此功能。</span><span class="sxs-lookup"><span data-stu-id="a24f6-419">The following markup shows how to enable this.</span></span>

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

<span data-ttu-id="a24f6-420">如果要将辅助应用程序窗口（如对话框）作为 <xref:System.Windows.Navigation.NavigationWindow>，则可以使用以下示例中的代码将其打开。</span><span class="sxs-lookup"><span data-stu-id="a24f6-420">If you want a secondary application window such as a dialog box to be a <xref:System.Windows.Navigation.NavigationWindow>, you can use the code in the following example to open it.</span></span>

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

<span data-ttu-id="a24f6-421">下图显示结果。</span><span class="sxs-lookup"><span data-stu-id="a24f6-421">The following figure shows the result.</span></span>

<span data-ttu-id="a24f6-422">![对话框](./media/navigation-overview/navigation-window-as-dialog-box.png "导航窗口作为对话框")</span><span class="sxs-lookup"><span data-stu-id="a24f6-422">![A dialog box](./media/navigation-overview/navigation-window-as-dialog-box.png "Navigation window as a dialog box")</span></span>

<span data-ttu-id="a24f6-423">如您所见，<xref:System.Windows.Navigation.NavigationWindow> 显示允许用户浏览日记的 Internet Explorer 样式的 "**后退**" 和 "**前进**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a24f6-423">As you can see, <xref:System.Windows.Navigation.NavigationWindow> displays Internet Explorer-style **Back** and **Forward** buttons that allow users to navigate the journal.</span></span> <span data-ttu-id="a24f6-424">这些按钮提供相同的用户体验，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-424">These buttons provide the same user experience, as shown in the following figure.</span></span>

<span data-ttu-id="a24f6-425">(./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "导航窗口中 System.windows.navigation.navigationwindow> 后退和前进按钮")![中的后退和前进按钮]</span><span class="sxs-lookup"><span data-stu-id="a24f6-425">![Back and Forward buttons in a NavigationWindow](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "Back and Forward buttons in a Navigation window")</span></span>

<span data-ttu-id="a24f6-426">如果页面提供其自己的日记导航支持和 UI，则可通过将 <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> 属性的值设置为 `false`，隐藏 @no__t 显示的 "**后退**" 和 "**前进**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a24f6-426">If your pages provide their own journal navigation support and UI, you can hide the **Back** and **Forward** buttons displayed by <xref:System.Windows.Navigation.NavigationWindow> by setting the value of the <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> property to `false`.</span></span>

<span data-ttu-id="a24f6-427">另外，还可以使用 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中的自定义支持来替换 @no__t 的 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-427">Alternatively, you can use customization support in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] to replace the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] of the <xref:System.Windows.Navigation.NavigationWindow> itself.</span></span>

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a><span data-ttu-id="a24f6-428">框架类</span><span class="sxs-lookup"><span data-stu-id="a24f6-428">The Frame Class</span></span>

<span data-ttu-id="a24f6-429">浏览器和 @no__t 都是托管可导航内容的窗口。</span><span class="sxs-lookup"><span data-stu-id="a24f6-429">Both the browser and <xref:System.Windows.Navigation.NavigationWindow> are windows that host navigable content.</span></span> <span data-ttu-id="a24f6-430">在某些情况下，应用程序具有无需整个窗口托管的内容。</span><span class="sxs-lookup"><span data-stu-id="a24f6-430">In some cases, applications have content that does not need to be hosted by an entire window.</span></span> <span data-ttu-id="a24f6-431">相反，此类内容在其他内容中托管。</span><span class="sxs-lookup"><span data-stu-id="a24f6-431">Instead, such content be hosted inside other content.</span></span> <span data-ttu-id="a24f6-432">可以通过使用 <xref:System.Windows.Controls.Frame> 类将导向性内容插入其他内容中。</span><span class="sxs-lookup"><span data-stu-id="a24f6-432">You can insert navigable content into other content by using the <xref:System.Windows.Controls.Frame> class.</span></span> <span data-ttu-id="a24f6-433">@no__t 提供与 <xref:System.Windows.Navigation.NavigationWindow> 和 @no__t 2 相同的支持。</span><span class="sxs-lookup"><span data-stu-id="a24f6-433"><xref:System.Windows.Controls.Frame> provides the same support as <xref:System.Windows.Navigation.NavigationWindow> and [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].</span></span>

<span data-ttu-id="a24f6-434">下面的示例演示如何使用第 2 @no__t 元素以声明方式将 @no__t 0 添加到 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-434">The following example shows how to add a <xref:System.Windows.Controls.Frame> to a <xref:System.Windows.Controls.Page> declaratively by using the `Frame` element.</span></span>

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

<span data-ttu-id="a24f6-435">此标记设置 @no__t @no__t 为1的元素的 `Source` 属性，该属性的 pack @no__t 为第3步，@no__t 首先应导航到该类型。</span><span class="sxs-lookup"><span data-stu-id="a24f6-435">This markup sets the `Source` attribute of the `Frame` element with a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the <xref:System.Windows.Controls.Page> that the <xref:System.Windows.Controls.Frame> should initially navigate to.</span></span> <span data-ttu-id="a24f6-436">下图显示了一个 @no__t 为 @no__t 的0，其中包含一个在多个页面之间导航的 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-436">The following figure shows an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] with a <xref:System.Windows.Controls.Page> that has a <xref:System.Windows.Controls.Frame> that has navigated between several pages.</span></span>

<span data-ttu-id="a24f6-437">![在多个页面之间导航的帧](./media/navigation-overview/frame-navigation-between-multiple-pages.png "显示多个页面之间的帧导航。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-437">![A frame that has navigated between multiple pages](./media/navigation-overview/frame-navigation-between-multiple-pages.png "This shows a frame navigation between multiple pages.")</span></span>

<span data-ttu-id="a24f6-438">你不必在 @no__t 的内容中使用 <xref:System.Windows.Controls.Frame>。</span><span class="sxs-lookup"><span data-stu-id="a24f6-438">You don't only have to use <xref:System.Windows.Controls.Frame> inside the content of a <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="a24f6-439">在 @no__t 的内容中托管 @no__t 的情况也很常见。</span><span class="sxs-lookup"><span data-stu-id="a24f6-439">It is also common to host a <xref:System.Windows.Controls.Frame> inside the content of a <xref:System.Windows.Window>.</span></span>

<span data-ttu-id="a24f6-440">默认情况下，<xref:System.Windows.Controls.Frame> 只在没有其他日志时使用自己的日记。</span><span class="sxs-lookup"><span data-stu-id="a24f6-440">By default, <xref:System.Windows.Controls.Frame> only uses its own journal in the absence of another journal.</span></span> <span data-ttu-id="a24f6-441">如果 @no__t 0 是托管在 @no__t 1 或 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 内的内容的一部分，则 <xref:System.Windows.Controls.Frame> 将使用属于 @no__t 或 @no__t 的日志。</span><span class="sxs-lookup"><span data-stu-id="a24f6-441">If a <xref:System.Windows.Controls.Frame> is part of content that is hosted inside either a <xref:System.Windows.Navigation.NavigationWindow> or an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], <xref:System.Windows.Controls.Frame> uses the journal that belongs to the <xref:System.Windows.Navigation.NavigationWindow> or [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].</span></span> <span data-ttu-id="a24f6-442">但有时，@no__t 0 可能需要负责自己的日记。</span><span class="sxs-lookup"><span data-stu-id="a24f6-442">Sometimes, though, a <xref:System.Windows.Controls.Frame> might need to be responsible for its own journal.</span></span> <span data-ttu-id="a24f6-443">这样做的一个原因是允许在由 <xref:System.Windows.Controls.Frame> 承载的页面内进行日志导航。</span><span class="sxs-lookup"><span data-stu-id="a24f6-443">One reason to do so is to allow journal navigation within the pages that are hosted by a <xref:System.Windows.Controls.Frame>.</span></span> <span data-ttu-id="a24f6-444">这由下图说明。</span><span class="sxs-lookup"><span data-stu-id="a24f6-444">This is illustrated by the following figure.</span></span>

<span data-ttu-id="a24f6-445">![框架和页面图](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "这会在框架托管的页面内显示日志导航。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-445">![Frame and Page diagram](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "This shows journal navigation within pages hosted by a frame.")</span></span>

<span data-ttu-id="a24f6-446">在这种情况下，你可以通过将 <xref:System.Windows.Controls.Frame> 的 @no__t 属性设置为 <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>，将 @no__t 设置为使用自己的日记。</span><span class="sxs-lookup"><span data-stu-id="a24f6-446">In this case, you can configure the <xref:System.Windows.Controls.Frame> to use its own journal by setting the <xref:System.Windows.Controls.Frame.JournalOwnership%2A> property of the <xref:System.Windows.Controls.Frame> to <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>.</span></span> <span data-ttu-id="a24f6-447">这在以下标记中显示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-447">This is shown in the following markup.</span></span>

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

<span data-ttu-id="a24f6-448">下图说明了在使用自己的日记的 <xref:System.Windows.Controls.Frame> 中导航的效果。</span><span class="sxs-lookup"><span data-stu-id="a24f6-448">The following figure illustrates the effect of navigating within a <xref:System.Windows.Controls.Frame> that uses its own journal.</span></span>

<span data-ttu-id="a24f6-449">![使用自己的日记的帧](./media/navigation-overview/frame-uses-its-own-journal.png "显示了在使用自己的日记的帧中进行导航的效果。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-449">![A frame that uses its own journal](./media/navigation-overview/frame-uses-its-own-journal.png "This shows the effect of navigating within a frame that uses its own journal.")</span></span>

<span data-ttu-id="a24f6-450">请注意，日记条目显示在 <xref:System.Windows.Controls.Frame> 中的导航 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 而不是 Internet Explorer 中。</span><span class="sxs-lookup"><span data-stu-id="a24f6-450">Notice that the journal entries are shown by the navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in the <xref:System.Windows.Controls.Frame>, rather than by Internet Explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="a24f6-451">如果 @no__t 为 <xref:System.Windows.Window> 中承载的内容的一部分，<xref:System.Windows.Controls.Frame> 将使用自己的日记，因此会显示其自己的导航 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a24f6-451">If a <xref:System.Windows.Controls.Frame> is part of content that is hosted in a <xref:System.Windows.Window>, <xref:System.Windows.Controls.Frame> uses its own journal and, consequently, displays its own navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span>

<span data-ttu-id="a24f6-452">如果你的用户体验需要 @no__t 0 来提供自己的日记，而不显示导航 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，则可以通过将 @no__t 设置为 <xref:System.Windows.Visibility.Hidden> 来隐藏导航 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a24f6-452">If your user experience requires a <xref:System.Windows.Controls.Frame> to provide its own journal without showing the navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], you can hide the navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] by setting the <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> to <xref:System.Windows.Visibility.Hidden>.</span></span> <span data-ttu-id="a24f6-453">这在以下标记中显示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-453">This is shown in the following markup.</span></span>

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a><span data-ttu-id="a24f6-454">导航主机</span><span class="sxs-lookup"><span data-stu-id="a24f6-454">Navigation Hosts</span></span>

<span data-ttu-id="a24f6-455"><xref:System.Windows.Controls.Frame> 和 <xref:System.Windows.Navigation.NavigationWindow> 是称为导航宿主的类。</span><span class="sxs-lookup"><span data-stu-id="a24f6-455"><xref:System.Windows.Controls.Frame> and <xref:System.Windows.Navigation.NavigationWindow> are classes that are known as navigation hosts.</span></span> <span data-ttu-id="a24f6-456">*导航宿主*是可导航到并显示内容的类。</span><span class="sxs-lookup"><span data-stu-id="a24f6-456">A *navigation host* is a class that can navigate to and display content.</span></span> <span data-ttu-id="a24f6-457">为实现此目的，每个导航宿主都使用其自己的 @no__t 0 和日记。</span><span class="sxs-lookup"><span data-stu-id="a24f6-457">To accomplish this, each navigation host uses its own <xref:System.Windows.Navigation.NavigationService> and journal.</span></span> <span data-ttu-id="a24f6-458">导航主机的基本构造在下图中显示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-458">The basic construction of a navigation host is shown in the following figure.</span></span>

<span data-ttu-id="a24f6-459">导航![器关系图](./media/navigation-overview/navigation-host-construction.png "基本构造导航宿主")</span><span class="sxs-lookup"><span data-stu-id="a24f6-459">![Navigator diagrams](./media/navigation-overview/navigation-host-construction.png "Basic construction of a navigation host")</span></span>

<span data-ttu-id="a24f6-460">实质上，这允许 <xref:System.Windows.Navigation.NavigationWindow> 和 <xref:System.Windows.Controls.Frame> 提供 @no__t 在浏览器中承载时提供的相同导航支持。</span><span class="sxs-lookup"><span data-stu-id="a24f6-460">Essentially, this allows <xref:System.Windows.Navigation.NavigationWindow> and <xref:System.Windows.Controls.Frame> to provide the same navigation support that an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] provides when hosted in the browser.</span></span>

<span data-ttu-id="a24f6-461">除了使用 @no__t 0 和日记，导航宿主还实现了 <xref:System.Windows.Navigation.NavigationService> 实现的相同成员。</span><span class="sxs-lookup"><span data-stu-id="a24f6-461">Besides using <xref:System.Windows.Navigation.NavigationService> and a journal, navigation hosts implement the same members that <xref:System.Windows.Navigation.NavigationService> implements.</span></span> <span data-ttu-id="a24f6-462">这由下图说明。</span><span class="sxs-lookup"><span data-stu-id="a24f6-462">This is illustrated by the following figure.</span></span>

<span data-ttu-id="a24f6-463">![框架和 System.windows.navigation.navigationwindow>](./media/navigation-overview/navigation-window-and-frame.png "导航窗口和框架")中的日记</span><span class="sxs-lookup"><span data-stu-id="a24f6-463">![A journal in a Frame and in a NavigationWindow](./media/navigation-overview/navigation-window-and-frame.png "Navigation Window and Frame")</span></span>

<span data-ttu-id="a24f6-464">这就允许直接对它们进行导航支持编程。</span><span class="sxs-lookup"><span data-stu-id="a24f6-464">This allows you to program navigation support directly against them.</span></span> <span data-ttu-id="a24f6-465">如果需要为 <xref:System.Windows.Window> 中承载的 @no__t 提供自定义导航 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，则可以考虑此情况。</span><span class="sxs-lookup"><span data-stu-id="a24f6-465">You may consider this if you need to provide a custom navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] for a <xref:System.Windows.Controls.Frame> that is hosted in a <xref:System.Windows.Window>.</span></span> <span data-ttu-id="a24f6-466">此外，这两种类型都实现了与导航相关的附加成员，包括 `BackStack` （<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>，<xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>）和 `ForwardStack` （<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>，<xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>），这使您可以分别枚举后端堆栈中的日记条目和向前堆栈。</span><span class="sxs-lookup"><span data-stu-id="a24f6-466">Furthermore, both types implement additional, navigation-related members, including `BackStack` (<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>) and `ForwardStack` (<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>), which allow you to enumerate the journal entries in the back stack and forward stack, respectively.</span></span>

<span data-ttu-id="a24f6-467">如之前提及，应用程序中可以存在不止一个日志。</span><span class="sxs-lookup"><span data-stu-id="a24f6-467">As mentioned earlier, more than one journal can exist within an application.</span></span> <span data-ttu-id="a24f6-468">下图提供何时可能发生这种情况的示例。</span><span class="sxs-lookup"><span data-stu-id="a24f6-468">The following figure provides an example of when this can happen.</span></span>

<span data-ttu-id="a24f6-469">![一个应用程序中有多个日志](./media/navigation-overview/multiple-journals-in-one-application.png "这是一个应用程序中多个日记的示例。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-469">![Multiple journals within one application](./media/navigation-overview/multiple-journals-in-one-application.png "This is an example of more than one journal in an application.")</span></span>

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a><span data-ttu-id="a24f6-470">导航到非 XAML 页内容</span><span class="sxs-lookup"><span data-stu-id="a24f6-470">Navigating to Content Other than XAML Pages</span></span>

<span data-ttu-id="a24f6-471">在本主题中，<xref:System.Windows.Controls.Page> 和 pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 已用于演示 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 的各种导航功能。</span><span class="sxs-lookup"><span data-stu-id="a24f6-471">Throughout this topic, <xref:System.Windows.Controls.Page> and pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] have been used to demonstrate the various navigation capabilities of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span> <span data-ttu-id="a24f6-472">但是，编译到应用程序中的 @no__t 0 不是唯一可以导航到的内容类型，包 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 不是标识内容的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="a24f6-472">However, a <xref:System.Windows.Controls.Page> that is compiled into an application is not the only type of content that can be navigated to, and pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] aren't the only way to identify content.</span></span>

<span data-ttu-id="a24f6-473">如本部分所示，你还可以导航到松散 @no__t 的文件、HTML 文件和对象。</span><span class="sxs-lookup"><span data-stu-id="a24f6-473">As this section demonstrates, you can also navigate to loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files, HTML files, and objects.</span></span>

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a><span data-ttu-id="a24f6-474">导航到松散 XAML 文件</span><span class="sxs-lookup"><span data-stu-id="a24f6-474">Navigating to Loose XAML Files</span></span>

<span data-ttu-id="a24f6-475">松散 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件是具有以下特征的文件：</span><span class="sxs-lookup"><span data-stu-id="a24f6-475">A loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is a file with the following characteristics:</span></span>

- <span data-ttu-id="a24f6-476">仅包含 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] （即没有代码）。</span><span class="sxs-lookup"><span data-stu-id="a24f6-476">Contains only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (that is, no code).</span></span>

- <span data-ttu-id="a24f6-477">具有适当的命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="a24f6-477">Has an appropriate namespace declaration.</span></span>

- <span data-ttu-id="a24f6-478">具有 .xaml 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="a24f6-478">Has the .xaml file name extension.</span></span>

<span data-ttu-id="a24f6-479">例如，请考虑以下存储为松散 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="a24f6-479">For example, consider the following content that is stored as a loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file, Person.xaml.</span></span>

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

<span data-ttu-id="a24f6-480">双击该文件时，浏览器打开、导航到并显示内容。</span><span class="sxs-lookup"><span data-stu-id="a24f6-480">When you double-click the file, the browser opens and navigates to and displays the content.</span></span> <span data-ttu-id="a24f6-481">如下图所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-481">This is shown in the following figure.</span></span>

<span data-ttu-id="a24f6-482">![显示 "person" 文件中的内容]将(./media/navigation-overview/contents-of-person-xaml-file.png "显示 \"person\" 文件的内容。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-482">![Display of the content in the Person.XAML file](./media/navigation-overview/contents-of-person-xaml-file.png "Shows the contents of the Person.XAML file.")</span></span>

<span data-ttu-id="a24f6-483">可显示以下内容的松散 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件：</span><span class="sxs-lookup"><span data-stu-id="a24f6-483">You can display a loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file from the following:</span></span>

- <span data-ttu-id="a24f6-484">本地计算机上的网站、Intranet 或 Internet。</span><span class="sxs-lookup"><span data-stu-id="a24f6-484">A Web site on the local machine, the intranet, or the Internet.</span></span>

- <span data-ttu-id="a24f6-485">通用命名约定（UNC）文件共享。</span><span class="sxs-lookup"><span data-stu-id="a24f6-485">A Universal Naming Convention (UNC) file share.</span></span>

- <span data-ttu-id="a24f6-486">本地磁盘。</span><span class="sxs-lookup"><span data-stu-id="a24f6-486">The local disk.</span></span>

<span data-ttu-id="a24f6-487">松散 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件可以添加到浏览器的收藏夹中，也可以是浏览器的主页。</span><span class="sxs-lookup"><span data-stu-id="a24f6-487">A loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file can be added to the browser's favorites, or be the browser's home page.</span></span>

> [!NOTE]
> <span data-ttu-id="a24f6-488">有关发布和启动松散 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面的详细信息，请参阅[部署 WPF 应用程序](deploying-a-wpf-application-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="a24f6-488">For more information about publishing and launching loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages, see [Deploying a WPF Application](deploying-a-wpf-application-wpf.md).</span></span>

<span data-ttu-id="a24f6-489">松 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 的一个限制是，只能托管在部分信任环境中可安全运行的内容。</span><span class="sxs-lookup"><span data-stu-id="a24f6-489">One limitation with respect to loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is that you can only host content that is safe to run in partial trust.</span></span> <span data-ttu-id="a24f6-490">例如，`Window` 不能是松散 @no__t 1 文件的根元素。</span><span class="sxs-lookup"><span data-stu-id="a24f6-490">For example, `Window` cannot be the root element of a loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="a24f6-491">有关详细信息，请参阅 [WPF 部分信任安全性](../wpf-partial-trust-security.md)。</span><span class="sxs-lookup"><span data-stu-id="a24f6-491">For more information, see [WPF Partial Trust Security](../wpf-partial-trust-security.md).</span></span>

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a><span data-ttu-id="a24f6-492">通过使用框架导航到 HTML 文件</span><span class="sxs-lookup"><span data-stu-id="a24f6-492">Navigating to HTML Files by Using Frame</span></span>

<span data-ttu-id="a24f6-493">正如您所料，还可以导航到 HTML。</span><span class="sxs-lookup"><span data-stu-id="a24f6-493">As you might expect, you can also navigate to HTML.</span></span> <span data-ttu-id="a24f6-494">只需提供使用 http 方案 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a24f6-494">You simply need to provide a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that uses the http scheme.</span></span> <span data-ttu-id="a24f6-495">例如，下面的 @no__t 显示导航到 HTML 页的 @no__t 1。</span><span class="sxs-lookup"><span data-stu-id="a24f6-495">For example, the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] shows a <xref:System.Windows.Controls.Frame> that navigates to an HTML page.</span></span>

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

<span data-ttu-id="a24f6-496">导航到 HTML 需要特殊权限。</span><span class="sxs-lookup"><span data-stu-id="a24f6-496">Navigating to HTML requires special permissions.</span></span> <span data-ttu-id="a24f6-497">例如，你不能从在 Internet 区域部分信任安全沙箱中运行的 @no__t 中导航。</span><span class="sxs-lookup"><span data-stu-id="a24f6-497">For example, you can't navigate from an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that is running in the Internet zone partial trust security sandbox.</span></span> <span data-ttu-id="a24f6-498">有关详细信息，请参阅 [WPF 部分信任安全性](../wpf-partial-trust-security.md)。</span><span class="sxs-lookup"><span data-stu-id="a24f6-498">For more information, see [WPF Partial Trust Security](../wpf-partial-trust-security.md).</span></span>

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a><span data-ttu-id="a24f6-499">通过使用 WebBrowser 控件导航到 HTML 文件</span><span class="sxs-lookup"><span data-stu-id="a24f6-499">Navigating to HTML Files by Using the WebBrowser Control</span></span>

<span data-ttu-id="a24f6-500">@No__t-0 控件支持 HTML 文档托管、导航和脚本/托管代码互操作性。</span><span class="sxs-lookup"><span data-stu-id="a24f6-500">The <xref:System.Windows.Controls.WebBrowser> control supports HTML document hosting, navigation and script/managed code interoperability.</span></span> <span data-ttu-id="a24f6-501">有关 <xref:System.Windows.Controls.WebBrowser> 控件的详细信息，请参阅 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a24f6-501">For detailed information regarding the <xref:System.Windows.Controls.WebBrowser> control, see <xref:System.Windows.Controls.WebBrowser>.</span></span>

<span data-ttu-id="a24f6-502">与 <xref:System.Windows.Controls.Frame> 一样，使用 @no__t 导航到 HTML 需要特殊权限。</span><span class="sxs-lookup"><span data-stu-id="a24f6-502">Like <xref:System.Windows.Controls.Frame>, navigating to HTML using <xref:System.Windows.Controls.WebBrowser> requires special permissions.</span></span> <span data-ttu-id="a24f6-503">例如，在部分信任的应用程序中，你只能导航到位于源站点的 HTML。</span><span class="sxs-lookup"><span data-stu-id="a24f6-503">For example, from a partial-trust application, you can navigate only to HTML located at the site of origin.</span></span> <span data-ttu-id="a24f6-504">有关详细信息，请参阅 [WPF 部分信任安全性](../wpf-partial-trust-security.md)。</span><span class="sxs-lookup"><span data-stu-id="a24f6-504">For more information, see [WPF Partial Trust Security](../wpf-partial-trust-security.md).</span></span>

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a><span data-ttu-id="a24f6-505">导航到自定义对象</span><span class="sxs-lookup"><span data-stu-id="a24f6-505">Navigating to Custom Objects</span></span>

<span data-ttu-id="a24f6-506">如果有存储为自定义对象的数据，则显示该数据的一种方法是创建一个 <xref:System.Windows.Controls.Page>，其中包含绑定到这些对象的内容（请参阅[数据绑定概述](../data/data-binding-overview.md)）。</span><span class="sxs-lookup"><span data-stu-id="a24f6-506">If you have data that is stored as custom objects, one way to display that data is to create a <xref:System.Windows.Controls.Page> with content that is bound to those objects (see [Data Binding Overview](../data/data-binding-overview.md)).</span></span> <span data-ttu-id="a24f6-507">如果无需创建整个页面而只要显示对象，则可以直接导航到它们。</span><span class="sxs-lookup"><span data-stu-id="a24f6-507">If you don't need the overhead of creating an entire page just to display the objects, you can navigate directly to them instead.</span></span>

<span data-ttu-id="a24f6-508">请考虑在以下代码中实现的 @no__t 0 类。</span><span class="sxs-lookup"><span data-stu-id="a24f6-508">Consider the `Person` class that is implemented in the following code.</span></span>

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

<span data-ttu-id="a24f6-509">若要导航到它，请调用 <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> 方法，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="a24f6-509">To navigate to it, you call the <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> method, as demonstrated by the following code.</span></span>

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

<span data-ttu-id="a24f6-510">下图显示结果。</span><span class="sxs-lookup"><span data-stu-id="a24f6-510">The following figure shows the result.</span></span>

<span data-ttu-id="a24f6-511">![导航到类的页面](./media/navigation-overview/page-navigates-to-an-object.png "这是导航到对象的页面的示例。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-511">![A page that navigates to a class](./media/navigation-overview/page-navigates-to-an-object.png "This is an example of a page that navigates to an object.")</span></span>

<span data-ttu-id="a24f6-512">从此图可以看出，没有显示任何有用信息。</span><span class="sxs-lookup"><span data-stu-id="a24f6-512">From this figure, you can see that nothing useful is displayed.</span></span> <span data-ttu-id="a24f6-513">事实上，显示的值是**Person**对象的 `ToString` 方法的返回值;默认情况下，这是 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 可用于表示对象的唯一值。</span><span class="sxs-lookup"><span data-stu-id="a24f6-513">In fact, the value that is displayed is the return value of the `ToString` method for the **Person** object; by default, this is the only value that [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] can use to represent your object.</span></span> <span data-ttu-id="a24f6-514">您可以重写 @no__t 0 方法以返回更有意义的信息，尽管它仍只是一个字符串值。</span><span class="sxs-lookup"><span data-stu-id="a24f6-514">You could override the `ToString` method to return more meaningful information, although it will still only be a string value.</span></span> <span data-ttu-id="a24f6-515">可以使用的一种方法，利用 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 的演示功能，使用数据模板。</span><span class="sxs-lookup"><span data-stu-id="a24f6-515">One technique you can use that takes advantage of the presentation capabilities of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] is to use a data template.</span></span> <span data-ttu-id="a24f6-516">可以实现 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 可以与特定类型的对象关联的数据模板。</span><span class="sxs-lookup"><span data-stu-id="a24f6-516">You can implement a data template that [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] can associate with an object of a particular type.</span></span> <span data-ttu-id="a24f6-517">下面的代码显示 `Person` 对象的数据模板。</span><span class="sxs-lookup"><span data-stu-id="a24f6-517">The following code shows a data template for the `Person` object.</span></span>

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

<span data-ttu-id="a24f6-518">在此处，通过在 `DataType` 属性中使用 @no__t 的标记扩展，将数据模板与 @no__t 类型相关联。</span><span class="sxs-lookup"><span data-stu-id="a24f6-518">Here, the data template is associated with the `Person` type by using the `x:Type` markup extension in the `DataType` attribute.</span></span> <span data-ttu-id="a24f6-519">然后，数据模板将 `TextBlock` 元素（请参阅 <xref:System.Windows.Controls.TextBlock>）绑定到 @no__t 类的属性。</span><span class="sxs-lookup"><span data-stu-id="a24f6-519">The data template then binds `TextBlock` elements (see <xref:System.Windows.Controls.TextBlock>) to the properties of the `Person` class.</span></span> <span data-ttu-id="a24f6-520">下图显示 `Person` 对象的更新外观。</span><span class="sxs-lookup"><span data-stu-id="a24f6-520">The following figure shows the updated appearance of the `Person` object.</span></span>

<span data-ttu-id="a24f6-521">![导航到具有数据模板的类]，该类(./media/navigation-overview/navigating-to-a-class.png "导航到具有数据模板的类。")</span><span class="sxs-lookup"><span data-stu-id="a24f6-521">![Navigating to a class that has a data template](./media/navigation-overview/navigating-to-a-class.png "Navigating to a class that has a data template.")</span></span>

<span data-ttu-id="a24f6-522">此技术的优势之一在于能够通过重复使用数据模板以在应用程序任意位置一致地显示对象而获得一致性。</span><span class="sxs-lookup"><span data-stu-id="a24f6-522">An advantage of this technique is the consistency you gain by being able to reuse the data template to display your objects consistently anywhere in your application.</span></span>

<span data-ttu-id="a24f6-523">有关数据模板的详细信息，请参阅[数据模板化概述](../data/data-templating-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a24f6-523">For more information on data templates, see [Data Templating Overview](../data/data-templating-overview.md).</span></span>

<a name="Security"></a>

## <a name="security"></a><span data-ttu-id="a24f6-524">安全性</span><span class="sxs-lookup"><span data-stu-id="a24f6-524">Security</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="a24f6-525">导航支持允许在 Internet 上导航到 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]，并允许应用程序托管第三方内容。</span><span class="sxs-lookup"><span data-stu-id="a24f6-525">navigation support allows [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] to be navigated to across the Internet, and it allows applications to host third-party content.</span></span> <span data-ttu-id="a24f6-526">为了保护应用程序和用户免受有害行为的影响，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供了在[安全](../security-wpf.md)和[WPF 部分信任安全性](../wpf-partial-trust-security.md)中讨论的各种安全功能。</span><span class="sxs-lookup"><span data-stu-id="a24f6-526">To protect both applications and users from harmful behavior, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides a variety of security features that are discussed in [Security](../security-wpf.md) and [WPF Partial Trust Security](../wpf-partial-trust-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a24f6-527">请参阅</span><span class="sxs-lookup"><span data-stu-id="a24f6-527">See also</span></span>

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [<span data-ttu-id="a24f6-528">应用程序管理概述</span><span class="sxs-lookup"><span data-stu-id="a24f6-528">Application Management Overview</span></span>](application-management-overview.md)
- [<span data-ttu-id="a24f6-529">WPF 中的 Pack URI</span><span class="sxs-lookup"><span data-stu-id="a24f6-529">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
- [<span data-ttu-id="a24f6-530">结构化导航概述</span><span class="sxs-lookup"><span data-stu-id="a24f6-530">Structured Navigation Overview</span></span>](structured-navigation-overview.md)
- [<span data-ttu-id="a24f6-531">导航拓扑概述</span><span class="sxs-lookup"><span data-stu-id="a24f6-531">Navigation Topologies Overview</span></span>](navigation-topologies-overview.md)
- [<span data-ttu-id="a24f6-532">帮助主题</span><span class="sxs-lookup"><span data-stu-id="a24f6-532">How-to Topics</span></span>](navigation-how-to-topics.md)
- [<span data-ttu-id="a24f6-533">部署 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="a24f6-533">Deploying a WPF Application</span></span>](deploying-a-wpf-application-wpf.md)
