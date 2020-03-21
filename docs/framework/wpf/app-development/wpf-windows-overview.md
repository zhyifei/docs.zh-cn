---
title: 窗口概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], displaying content via
- XAML pages [WPF], displaying
- content [WPF], displaying via XAML
- window objects [WPF]
- hosting [WPF], applications
- managing windows [WPF]
- dialog boxes [WPF]
- Page object [WPF]
- NavigationWindow objects [WPF]
- applications [WPF], hosting
- content [WPF], displaying
- events [WPF]
- content [WPF], displaying via procedural code
- modal windows [WPF]
- procedural code [WPF], displaying content via
- displaying content via procedural code [WPF]
- window management [WPF]
- displaying content [WPF]
- window events [WPF]
- windows [WPF]
- modal dialog boxes [WPF]
- displaying XAML pages [WPF]
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
ms.openlocfilehash: b06afb56f43a874815cf9f679f1f7fefbdfd4565
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145535"
---
# <a name="wpf-windows-overview"></a>WPF Windows 概述
用户通过窗口与 Windows 演示基础 （WPF） 独立应用程序进行交互。 窗口的主要用途是托管使数据可视化并使用户能够与数据交互的内容。 独立 WPF 应用程序通过使用<xref:System.Windows.Window>类提供自己的窗口。 本主题在<xref:System.Windows.Window>介绍在独立应用程序中创建和管理窗口的基础知识之前介绍。  
  
> [!NOTE]
> 浏览器托管的 WPF 应用程序（包括 XAML 浏览器应用程序 （XBAP） 和松散[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]页面）不提供自己的窗口。 相反，它们托管在 Windows Internet 资源管理器提供的窗口中。 请参阅[WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)。  

<a name="TheWindowClass"></a>
## <a name="the-window-class"></a>窗口类  
 下图说明了窗口的组成部分：  
  
 ![显示窗口元素的屏幕截图。](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 窗口分为两个区域：非工作区和工作区。  
  
 窗口*的非工作区*由 WPF 实现，包括大多数窗口共有的窗口部分，包括以下内容：  
  
- 边框。  
  
- 标题栏。  
  
- 图标。  
  
- “最小化”、“最大化”和“还原”按钮。  
  
- “关闭”按钮。  
  
- “系统”菜单，其中包含允许用户最小化、最大化、还原、移动和关闭窗口以及重设窗口大小的菜单项。  
  
 窗口的*工作区*是窗口非工作区中的区域，开发人员使用 它添加特定于应用程序的内容，如菜单栏、工具栏和控件。  
  
 在 WPF 中，窗口由用于执行<xref:System.Windows.Window>以下操作的类封装：  
  
- 显示窗口。  
  
- 配置窗口的大小、位置和外观。  
  
- 托管特定于应用程序的内容。  
  
- 管理窗口的生存期。  
  
<a name="DefiningAWindow"></a>
## <a name="implementing-a-window"></a>实现窗口  
 典型窗口的实现包括外观和行为，其中*外观*定义窗口对用户的外观，*行为*定义窗口在用户与其交互时的工作方式。 在 WPF 中，可以使用代码或[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记实现窗口的外观和行为。  
  
 但是，通常情况下，窗口的外观使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记实现，并且其行为使用代码后面实现，如下例所示。  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 要使[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记文件和代码后面文件协同工作，需要：  
  
- 在标记中，`Window`元素必须包括属性。 `x:Class` 生成应用程序`x:Class`时，标记文件中的存在会导致 Microsoft 生成引擎 （MSBuild） 创建派生`partial`自<xref:System.Windows.Window>并具有`x:Class`属性指定的名称的类。 这需要为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]架构添加 XML 命名空间声明 （ `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` 。 生成的`partial`类实现方法`InitializeComponent`，该方法被调用以注册事件并设置在标记中实现的属性。  
  
- 在代码后面，类必须是具有标记中属性`partial`指定的相同名称的`x:Class`类，并且必须派生自<xref:System.Windows.Window>。 这允许代码背后的文件与生成应用程序时为标记文件生成的`partial`类相关联（请参阅[构建 WPF 应用程序](building-a-wpf-application-wpf.md)）。  
  
- 在代码后面，<xref:System.Windows.Window>类必须实现调用方法的`InitializeComponent`构造函数。 `InitializeComponent`由标记文件的生成`partial`类实现，以注册事件并设置在标记中定义的属性。  
  
> [!NOTE]
> 使用 Visual Studio<xref:System.Windows.Window>向项目添加新项目时，<xref:System.Windows.Window>将使用标记和代码后面实现 ，并包括创建标记和代码后面文件之间的关联的必要配置，如此处所述。  
  
 有了此配置，您可以专注于在标记中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]定义窗口的外观，并在代码后面实现其行为。 下面的示例显示了一个窗口，其中带有一个按钮[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，在标记中实现，并且在代码后面实现该<xref:System.Windows.Controls.Primitives.ButtonBase.Click>按钮事件的事件处理程序。  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>
## <a name="configuring-a-window-definition-for-msbuild"></a>为 MSBuild 配置窗口定义  
 如何实现窗口决定了如何为 MSBuild 配置窗口。 对于使用标记[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]和代码后面定义的窗口：  
  
- XAML 标记文件配置为 MSBuild`Page`项。  
  
- 代码背后的文件配置为 MSBuild`Compile`项。  
  
 这显示在以下 MSBuild 项目文件中。  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 有关构建 WPF 应用程序的信息，请参阅[构建 WPF 应用程序](building-a-wpf-application-wpf.md)。  
  
<a name="WindowLifetime"></a>
## <a name="window-lifetime"></a>窗口生存期  
 与所有类一样，窗口也有生存期，开始于首次实例化窗口，在这之后将打开、激活、停用直至最终关闭窗口。  

<a name="Opening_a_Window"></a>
### <a name="opening-a-window"></a>打开窗口  
 若要打开窗口，首先要创建窗口实例，下面的示例演示此操作。  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 在此示例中，应用程序启动时`MarkupAndCodeBehindWindow`实例化，在引发<xref:System.Windows.Application.Startup>事件时发生实例化。  
  
 实例化窗口时，对窗口的引用将自动添加到由<xref:System.Windows.Application>对象管理的窗口列表中（请参阅<xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>）。 此外，默认情况下，要实例化的第一个窗口<xref:System.Windows.Application>设置为主应用程序窗口（请参阅<xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>）。  
  
 最后通过调用<xref:System.Windows.Window.Show%2A>方法打开窗口;结果如下图所示。  
  
 ![通过调用窗口打开的窗口。](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 通过调用<xref:System.Windows.Window.Show%2A>打开的窗口是一个无模式窗口，这意味着应用程序以允许用户在同一应用程序中激活其他窗口的模式运行。  
  
> [!NOTE]
> <xref:System.Windows.Window.ShowDialog%2A>调用 以以模式方式打开窗口，如对话框。 有关详细信息，请参阅[对话框概述](dialog-boxes-overview.md)。  
  
 调用<xref:System.Windows.Window.Show%2A>时，窗口在显示建立基础结构以允许其接收用户输入之前执行初始化工作。 初始化窗口时，<xref:System.Windows.Window.SourceInitialized>将引发事件并显示窗口。  
  
 作为快捷方式，<xref:System.Windows.Application.StartupUri%2A>可以设置为指定应用程序启动时自动打开的第一个窗口。  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 应用程序启动时，由 的值<xref:System.Windows.Application.StartupUri%2A>指定的窗口将无模式打开;在内部，窗口通过调用其<xref:System.Windows.Window.Show%2A>方法打开。  
  
<a name="Ownership"></a>
#### <a name="window-ownership"></a>窗口所有权  
 使用<xref:System.Windows.Window.Show%2A>方法打开的窗口与创建它的窗口没有隐式关系;因此，使用 方法打开的窗口与创建它的窗口没有隐式关系。用户可以独立于另一个窗口与任一窗口进行交互，这意味着任一窗口都可以执行以下操作：  
  
- 盖住另一个窗口（除非其中一个窗口<xref:System.Windows.Window.Topmost%2A>的属性设置为`true`）。  
  
- 在不影响另一个窗口的情况下最小化、最大化和还原。  
  
 某些窗口要求与打开它们的窗口保持某种关系。 例如，集成开发环境 （IDE） 应用程序可能会打开属性窗口和工具窗口，其典型行为是覆盖创建它们的窗口。 此外，此类窗口应始终与创建它们的窗口一起关闭、最小化、最大化和还原。 这种关系可以通过使一个窗口*拥有*另一个窗口来建立，并且通过使用所有者<xref:System.Windows.Window.Owner%2A>*窗口*来设置*拥有的窗口*的属性来实现。 下面的示例说明了这一点。  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 建立所有权后：  
  
- 拥有的窗口可以通过检查其属性的值来引用其<xref:System.Windows.Window.Owner%2A>所有者窗口。  
  
- 所有者窗口可以通过检查其<xref:System.Windows.Window.OwnedWindows%2A>属性的值来发现它拥有的所有窗口。  
  
<a name="Preventing"></a>
#### <a name="preventing-window-activation"></a>防止窗口激活  
 在某些情况下，在显示时不应激活窗口，例如 Internet 信使式应用程序的对话窗口或电子邮件应用程序的通知窗口。  
  
 如果应用程序的窗口在显示时不应激活，则可以在首次调用<xref:System.Windows.Window.ShowActivated%2A>`false`<xref:System.Windows.Window.Show%2A>该方法之前将其属性设置为 。 结果是：  
  
- 不会激活窗口。  
  
- 不会引发窗口的事件<xref:System.Windows.Window.Activated>。  
  
- 当前激活的窗口保持激活状态。  
  
 但是，只要用户通过单击工作区或非工作区激活了窗口，窗口就会变为激活状态。 在这种情况下：  
  
- 已激活窗口。  
  
- 引发窗口的事件<xref:System.Windows.Window.Activated>。  
  
- 停用之前激活的窗口。  
  
- 窗口<xref:System.Windows.Window.Deactivated>和<xref:System.Windows.Window.Activated>事件随后按预期引发，以响应用户操作。  
  
<a name="Window_Activation"></a>
### <a name="window-activation"></a>窗口激活  
 首次打开窗口时，它将成为活动窗口（除非将其显示为<xref:System.Windows.Window.ShowActivated%2A>）。 `false` *活动窗口*是当前捕获用户输入的窗口，例如击键和鼠标单击。 当窗口变为活动状态时，它会引发<xref:System.Windows.Window.Activated>事件。  
  
> [!NOTE]
> 首次打开窗口时，仅在引发<xref:System.Windows.FrameworkElement.Loaded><xref:System.Windows.Window.ContentRendered><xref:System.Windows.Window.Activated>事件后引发 和 事件。 考虑到这一点，在提出时<xref:System.Windows.Window.ContentRendered>，可以有效地考虑打开一个窗口。  
  
 某个窗口成为活动窗口后，用户可以在同一应用程序内激活其他窗口，或者激活其他应用程序。 发生这种情况时，当前活动窗口将停用并引发事件<xref:System.Windows.Window.Deactivated>。 同样，当用户选择当前停用的窗口时，该窗口将再次变为活动状态并<xref:System.Windows.Window.Activated>引发。  
  
 处理<xref:System.Windows.Window.Activated><xref:System.Windows.Window.Deactivated>的一个常见原因是启用和禁用只能在窗口处于活动状态时运行的功能。 例如，一些窗口显示需要用户持续输入或关注的交互式内容，这些内容包括游戏和视频播放器。 下面的示例是一个简化的视频播放器，演示如何处理<xref:System.Windows.Window.Activated>和<xref:System.Windows.Window.Deactivated>实现此行为。  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 停用某个窗口后，其他类型的应用程序可能仍会在后台运行代码。 例如，在用户使用其他应用程序时，邮件客户端可能会继续轮询邮件服务器。 类似的应用程序在主窗口停用时，通常将提供不同或其他的行为。 对于邮件程序，这可能意味着将新邮件项添加到收件箱和将通知图标添加到系统任务栏。 仅当邮件窗口不处于活动状态时，才需要显示通知图标，可以通过检查<xref:System.Windows.Window.IsActive%2A>属性来确定该图标。  
  
 如果后台任务完成，窗口可能需要通过调用<xref:System.Windows.Window.Activate%2A>方法更紧急地通知用户。 如果用户正在与调用时<xref:System.Windows.Window.Activate%2A>激活的另一个应用程序交互，则窗口的任务栏按钮将闪烁。 如果用户正在与当前应用程序交互，则调用<xref:System.Windows.Window.Activate%2A>会将窗口带到前台。  
  
> [!NOTE]
> 您可以使用 和<xref:System.Windows.Application.Activated?displayProperty=nameWithType><xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>事件处理应用程序范围激活。  
  
<a name="Closing_a_Window"></a>
### <a name="closing-a-window"></a>关闭窗口  
 窗口的生存期在用户关闭它时终止。 可以使用非工作区中的元素关闭窗口，这些元素包括：  
  
- **"关闭"菜单**的 **"关闭**"项。  
  
- 按 ALT+F4。  
  
- 按 **"关闭"** 按钮。  
  
 可以向工作区提供其他关闭窗口的机制，较为常见的机制包括：  
  
- **"文件**"菜单中的**退出**项，通常用于主应用程序窗口。  
  
- **"文件**"菜单中的**Close**项，通常在辅助应用程序窗口中。  
  
- **取消**按钮，通常在模式对话框上。  
  
- **关闭**按钮，通常在无模式对话框上。  
  
 要关闭窗口以响应这些自定义机制之一，您需要调用 方法<xref:System.Windows.Window.Close%2A>。 以下示例通过选择 **"文件**"菜单上的 **"退出**"来实现关闭窗口的能力。  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 当窗口关闭时，它将引发两个事件： <xref:System.Windows.Window.Closing> <xref:System.Windows.Window.Closed>和 。  
  
 <xref:System.Windows.Window.Closing>在窗口关闭之前引发，它提供了一种机制，可以阻止窗口关闭。 阻止窗口关闭的一个常见原因是窗口内容包含修改的数据。 在此情况下，<xref:System.Windows.Window.Closing>可以处理事件以确定数据是否脏，如果是，则询问用户是继续关闭窗口而不保存数据，还是取消窗口关闭。 下面的示例显示了处理<xref:System.Windows.Window.Closing>的关键方面。  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 事件<xref:System.Windows.Window.Closing>处理程序传递 一个<xref:System.ComponentModel.CancelEventArgs>，它实现`Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>设置为`true`防止窗口关闭的属性。  
  
 如果未<xref:System.Windows.Window.Closing>处理，或者处理但未取消，窗口将关闭。 就在窗口实际关闭之前，<xref:System.Windows.Window.Closed>正在引发。 此时，无法阻止窗口关闭。  
  
> [!NOTE]
> 可以将应用程序配置为在主应用程序窗口关闭（请参阅<xref:System.Windows.Application.MainWindow%2A>）或最后一个窗口关闭时自动关闭。 有关详细信息，请参阅<xref:System.Windows.Application.ShutdownMode%2A>。  
  
 虽然可以通过非客户端和工作区中提供的机制显式关闭窗口，但窗口也可以由于应用程序或 Windows 的其他部分的行为而隐式关闭，包括：  
  
- 用户注销或关闭 Windows。  
  
- 窗口的所有者关闭（请参阅<xref:System.Windows.Window.Owner%2A>）。  
  
- 主应用程序窗口已关闭，并且<xref:System.Windows.Application.ShutdownMode%2A>为<xref:System.Windows.ShutdownMode.OnMainWindowClose>。  
  
- 调用 <xref:System.Windows.Application.Shutdown%2A>。  
  
> [!NOTE]
> 窗口在关闭后无法重新打开。  
  
<a name="Window_Lifetime_Events"></a>
### <a name="window-lifetime-events"></a>窗口生存期事件  
 下图显示了窗口生存期内主体事件的顺序：  
  
 ![显示窗口生存期内的事件的图表。](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 下图显示了不激活的情况下显示的窗口生存期内主体事件的顺序（<xref:System.Windows.Window.ShowActivated%2A>设置为`false`在显示窗口之前）：  
  
 ![显示窗口生存期内的事件而不激活的图表。](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>
## <a name="window-location"></a>窗口位置  
 当窗口打开时，它在相对于桌面的 x 和 y 维度中有一个位置。 此位置可以通过分别检查 和<xref:System.Windows.Window.Left%2A><xref:System.Windows.Window.Top%2A>属性来确定。 设置这些属性可以更改窗口的位置。  
  
 还可以通过使用以下<xref:System.Windows.Window><xref:System.Windows.Window.WindowStartupLocation%2A><xref:System.Windows.WindowStartupLocation>枚举值之一设置属性来指定首次出现 时的初始位置：  
  
- <xref:System.Windows.WindowStartupLocation.CenterOwner>（默认值）  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 如果启动位置<xref:System.Windows.WindowStartupLocation.Manual>指定为 ，并且 尚未<xref:System.Windows.Window.Left%2A>设置<xref:System.Windows.Window.Top%2A>和 属性，<xref:System.Windows.Window>则请求 Windows 显示位置。  
  
<a name="Topmost_Windows_and_Z_Order"></a>
### <a name="topmost-windows-and-z-order"></a>最顶层窗口和 Z 顺序  
 除了有 x 和 y 位置外，窗口还在 z 维度中有一个位置，该位置确定窗口相对于其他窗口的垂直位置。 它称为窗口的 z 顺序，并且有两种类型：正常 z 顺序和最顶层 z 顺序。 窗口在正常*z 顺序*中的位置由窗口当前是否处于活动状态决定。 默认情况下，窗口位于正常 z 顺序中。 窗口在*最顶层 z 顺序*中的位置也取决于窗口当前是否处于活动状态。 此外，最顶层 z 顺序中的窗口始终位于正常 z 顺序中的窗口之上。 窗口通过将属性<xref:System.Windows.Window.Topmost%2A>设置为`true`位于最上面的 z 顺序中。  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 在每个 z 顺序中，当前的活动窗口显示在同一 z 顺序中所有其他窗口之上。  
  
<a name="WindowSize"></a>
## <a name="window-size"></a>窗口大小  
 除了具有桌面位置外，窗口的大小由多个属性确定，包括各种宽度和高度属性和<xref:System.Windows.Window.SizeToContent%2A>。  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A><xref:System.Windows.FrameworkElement.Width%2A>，<xref:System.Windows.FrameworkElement.MaxWidth%2A>用于管理窗口在其生存期内可以具有的宽度范围，并配置如下示例所示。  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 窗口高度由<xref:System.Windows.FrameworkElement.MinHeight%2A><xref:System.Windows.FrameworkElement.Height%2A>和 和<xref:System.Windows.FrameworkElement.MaxHeight%2A>进行管理，并配置如下示例所示。  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 由于各种宽度值和高度值各自指定了一个范围，所以大小可调整大小的窗口的宽度和高度可以是相应维度中指定范围内的任何值。 要检测其当前宽度和高度，分别<xref:System.Windows.FrameworkElement.ActualWidth%2A>检查<xref:System.Windows.FrameworkElement.ActualHeight%2A>和 。  
  
 如果希望窗口的宽度和高度具有适合窗口内容大小的大小，则可以使用 具有以下值<xref:System.Windows.Window.SizeToContent%2A>的属性：  
  
- <xref:System.Windows.SizeToContent.Manual>. 不起作用（默认值）。  
  
- <xref:System.Windows.SizeToContent.Width>. 适合内容宽度，其效果与设置内容<xref:System.Windows.FrameworkElement.MinWidth%2A>和<xref:System.Windows.FrameworkElement.MaxWidth%2A>内容宽度的效果相同。  
  
- <xref:System.Windows.SizeToContent.Height>. 适合内容高度，这与设置内容<xref:System.Windows.FrameworkElement.MinHeight%2A>的高度和<xref:System.Windows.FrameworkElement.MaxHeight%2A>内容的高度具有相同的效果。  
  
- <xref:System.Windows.SizeToContent.WidthAndHeight>. 适合内容<xref:System.Windows.FrameworkElement.MinHeight%2A>宽度和高度，其效果与设置内容的高度以及<xref:System.Windows.FrameworkElement.MaxHeight%2A>设置内容<xref:System.Windows.FrameworkElement.MinWidth%2A>的宽度和<xref:System.Windows.FrameworkElement.MaxWidth%2A>宽度的效果相同。  
  
 以下示例显示了一个窗口，它在第一次显示时即自动调整垂直方向和水平方向上的大小以适应内容。  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 下面的示例演示如何在代码中设置<xref:System.Windows.Window.SizeToContent%2A>属性以指定窗口如何调整大小以适合其内容。
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>
## <a name="order-of-precedence-for-sizing-properties"></a>大小调整属性的优先级顺序  
 从根本上说，窗口的各种大小属性可以结合使用，以定义可调整大小的窗口的宽度和高度范围。 为确保保持有效范围，<xref:System.Windows.Window>请使用以下优先级顺序计算大小属性的值。  
  
 **对于高度属性：**  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 **对于宽度属性：**  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 优先级顺序还可以确定窗口在最大化时的大小，该窗口使用<xref:System.Windows.Window.WindowState%2A>属性进行管理。  
  
<a name="WindowState"></a>
## <a name="window-state"></a>窗口状态  
 可调整大小的窗口在生存期中拥有三种状态：正常、最小化和最大化。 具有*正常*状态的窗口是窗口的默认状态。 这种状态下的窗口允许用户使用重设大小手柄或边框移动窗口和重设其大小（前提是大小可以重设）。  
  
 具有*最小化*状态的窗口将折叠到其任务栏按钮（如果<xref:System.Windows.Window.ShowInTaskbar%2A>设置为`true`;否则，它会折叠到尽可能小的大小，并重新定位到桌面的左下角。 虽然不在任务栏显示的最小化窗口可以在桌面上四处拖动，但这两种类型的最小化窗口都不可以使用边框或重设大小手柄重设窗口大小。  
  
 具有*最大化*状态的窗口将扩展到其可以的最大大小，该大小将仅与其<xref:System.Windows.FrameworkElement.MaxWidth%2A>、<xref:System.Windows.FrameworkElement.MaxHeight%2A>和<xref:System.Windows.Window.SizeToContent%2A>属性规定的大小一样大。 与最小化窗口一样，最大化窗口无法使用重设大小手柄或通过拖动边框来重设大小。  
  
> [!NOTE]
> <xref:System.Windows.Window.Top%2A>窗口的值<xref:System.Windows.Window.Left%2A><xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性始终表示正常状态的值，即使窗口当前正在最大化或最小化也是如此。  
  
 可以通过设置其<xref:System.Windows.Window.WindowState%2A>属性来配置窗口的状态，该属性可以具有以下<xref:System.Windows.WindowState>枚举值之一：  
  
- <xref:System.Windows.WindowState.Normal>（默认值）  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 以下示例显示如何创建在打开时最大化显示的窗口。  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 通常，应设置为<xref:System.Windows.Window.WindowState%2A>配置窗口的初始状态。 显示可调整大小的窗口后，用户可以按窗口标题栏上的“最小化”、“最大化”和“还原”按钮来更改窗口状态。  
  
<a name="WindowAppearance"></a>
## <a name="window-appearance"></a>窗口外观  
 通过将特定于窗口的内容（例如按钮、标签和文本框）添加到窗口的工作区可以更改它的外观。 要配置非工作区，<xref:System.Windows.Window>请提供多个属性，其中包括<xref:System.Windows.Window.Icon%2A>设置窗口的图标并<xref:System.Windows.Window.Title%2A>设置其标题。  
  
 还可以通过配置窗口的重设大小模式、窗口样式，以及窗口是否显示为桌面任务栏中的按钮，更改非工作区边框的外观和行为。  

<a name="Resize_Mode"></a>
### <a name="resize-mode"></a>重设大小模式  
 根据属性，<xref:System.Windows.Window.WindowStyle%2A>您可以控制用户调整窗口大小的方式（以及是否）大小。 窗口样式的选择会影响用户是否可以通过拖动窗口与鼠标的边框来调整窗口的大小，是否在非工作区上显示 **"最小化**"、**最大化**和**调整大小**按钮，如果确实出现，则是否启用了这些按钮。  
  
 您可以通过设置窗口<xref:System.Windows.Window.ResizeMode%2A>的属性（可以是以下<xref:System.Windows.ResizeMode>枚举值之一）来配置窗口的大小大小：  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <xref:System.Windows.ResizeMode.CanResize>（默认值）  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 与<xref:System.Windows.Window.WindowStyle%2A>，窗口的调整大小模式在其生存期内不太可能更改，这意味着您很可能从[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记中设置它。  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 请注意，您可以通过检查<xref:System.Windows.Window.WindowState%2A>属性来检测窗口是最大化、最小化还是还原。  
  
<a name="Window_Style"></a>
### <a name="window-style"></a>窗口样式  
 从窗口非工作区公开的边框适用于大多数应用程序。 但是，有时候会需要不同类型的边框，或者根本不需要边框，具体取决于窗口类型。  
  
 要控制窗口获取的边框类型，您需要使用枚<xref:System.Windows.Window.WindowStyle%2A><xref:System.Windows.WindowStyle>举的以下值之一设置其属性：  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <xref:System.Windows.WindowStyle.SingleBorderWindow>（默认值）  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 下图说明了这些窗口样式的效果：  
  
 ![窗口边框样式的插图。](./media/wpf-windows-overview/window-border-styles.png)  
  
 您可以使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记或<xref:System.Windows.Window.WindowStyle%2A>代码进行设置;因为它不太可能在窗口的生存期内更改，因此您很可能使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记来配置它。  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>非矩形窗口样式  
 还在某些情况下，<xref:System.Windows.Window.WindowStyle%2A>允许您拥有的边界样式是不够的。 例如，您可能希望创建具有非矩形边框的应用程序，如 Microsoft Windows 媒体播放器使用。  
  
 例如，请考虑下图中显示的语音气泡窗口：  
  
 ![一个语音气泡窗口，上面写着"拖动我"。](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 可以通过将<xref:System.Windows.Window.WindowStyle%2A>属性设置为<xref:System.Windows.WindowStyle.None>和 使用<xref:System.Windows.Window>具有透明度的特殊支持来创建这种类型的窗口。  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 多个值组合起来可以指示窗口呈现完全透明的效果。 在这种状态下，无法使用窗口的非工作区修饰（“关闭”菜单，“最小化”、“最大化”和“还原”按钮等）。 因此，需要提供自己的修饰。  
  
<a name="Task_Bar_Presence"></a>
### <a name="task-bar-presence"></a>任务栏显示  

窗口的默认外观包括任务栏按钮，如图所示：

 ![显示带有任务栏按钮的窗口的屏幕截图。](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 某些类型的窗口没有任务栏按钮，如消息框和对话框（请参阅[对话框概述](dialog-boxes-overview.md)）。 您可以通过设置<xref:System.Windows.Window.ShowInTaskbar%2A>属性（默认情况下）`true`来控制窗口的任务栏按钮是否显示。  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations"></a>安全注意事项  
 <xref:System.Windows.Window>需要`UnmanagedCode`实例化安全权限。 对于从本地计算机安装并启动的应用程序，此权限在授予应用程序的权限集中。  
  
 但是，这不属于使用 ClickOnce 从 Internet 或本地 Intranet 区域启动的应用程序授予的权限集。 因此，用户将收到 ClickOnce 安全警告，并且需要将应用程序的权限集提升为完全信任。  
  
 此外，默认情况下，XBAP 不能显示窗口或对话框。 有关独立应用程序安全注意事项的讨论，请参阅[WPF 安全策略 - 平台安全](../wpf-security-strategy-platform-security.md)。  
  
<a name="Other_Types_of_Windows"></a>
## <a name="other-types-of-windows"></a>其他类型的窗口  
 <xref:System.Windows.Navigation.NavigationWindow>是一个窗口，旨在承载可导航内容。 有关详细信息，请参阅[导航概述](navigation-overview.md)。  
  
 对话框是通常用来收集用户信息以完成某项功能的窗口。 例如，当用户想要打开文件时，"**打开文件"** 对话框通常由应用程序显示，以便从用户获取文件名。 有关详细信息，请参阅[对话框概述](dialog-boxes-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [对话框概述](dialog-boxes-overview.md)
- [生成 WPF 应用程序](building-a-wpf-application-wpf.md)
