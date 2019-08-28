---
title: WPF 和 Win32 互操作
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: c66003a692cd6d54e62491ed7c32970162452b3e
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041028"
---
# <a name="wpf-and-win32-interoperation"></a>WPF 和 Win32 互操作

本主题概述如何互操作 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 代码。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供了用于创建应用程序的丰富环境。 但是，如果对 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 代码投入很大，重复使用部分此代码可能更有效。

<a name="basics"></a>

## <a name="wpf-and-win32-interoperation-basics"></a>WPF 和 Win32 互操作基础知识

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 代码间的互操作存在两种基本方法。

- 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 窗口中承载 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 内容。 通过此方法，可在标准 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 窗口和应用程序的框架内使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的高级图形功能。

- 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容中承载 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 窗口。 通过此方法，可在其他 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的上下文中使用现有自定义 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 控件，并可跨边界传递数据。

本主题中对上述每种方法进行了概念性介绍。 有关在中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]承载的更多面向代码的说明, [请参阅演练:在 Win32](walkthrough-hosting-wpf-content-in-win32.md)中承载 WPF 内容。 有关在中[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]承载的更多面向代码的说明, [请参阅演练:在 WPF](walkthrough-hosting-a-win32-control-in-wpf.md)中承载 Win32 控件。

<a name="projects"></a>

## <a name="wpf-interoperation-projects"></a>WPF 互操作项目

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Api 是托管代码, 但大多数现有[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]程序都是以非C++托管的编写的。  不能从[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]真正的非托管程序调用 api。 但是, 通过将`/clr`选项[!INCLUDE[TLA#tla_visualcpp](../../../../includes/tlasharptla-visualcpp-md.md)]与编译器一起使用, 你可以创建混合托管的非托管程序, 你可以在其中无缝混合托管和非托管的 API 调用。

一个项目级别的难点在于, 您不能[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]将文件编译C++为项目。  可通过一些项目分离技术对此进行弥补。

- 创建一个C# DLL, 其中包含作为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]已编译程序集的所有页面, 然后让C++可执行文件将该 dll 作为引用包含在内。

- 为C# [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容创建一个可执行文件, 并使其引用C++包含[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]内容的 DLL。

- 使用<xref:System.Windows.Markup.XamlReader.Load%2A>在运行时[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]加载任何[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 而不编译。

- 不要使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , 而是编写[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]所有的代码, 并从<xref:System.Windows.Application>生成元素树。

请使用最适合你的方法。

> [!NOTE]
> 如果你之前未使用C++/cli, 你可能会注意到一些 "新建" 关键字 ( `gcnew`例如`nullptr`和) 在互操作代码示例中。 这些关键字将取代旧的双下划线语法 (`__gc`), 并为中C++的托管代码提供更自然的语法。  若要了解有关/Cli C++托管功能的详细信息, 请参阅[运行时平台的组件扩展](/cpp/windows/component-extensions-for-runtime-platforms)和[Hello, C++/cli](https://go.microsoft.com/fwlink/?LinkId=98739)。

<a name="hwnds"></a>

## <a name="how-wpf-uses-hwnds"></a>WPF 如何使用 Hwnd

若要充分利用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]“HWND 互操作”，需要了解 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 如何使用 HWND。 对于任何 HWND, 不能使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] DirectX 呈现或 gdi/gdi + 呈现来混合呈现。 这具有许多影响。 首先，若要混合这些绘制模型，必须创建互操作解决方案，并对选择使用的每个绘制模型使用互操作的指定段。 此外，绘制行为会为互操作解决方案可实现的操作创建一个“空域”限制。 有关“空域”概念的详细信息，请参见[技术区概述](technology-regions-overview.md)主题。

屏幕上的所有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素最终受 HWND 支持。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]当你创建<xref:System.Windows.Window>时, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]将创建一个<xref:System.Windows.Interop.HwndSource>顶级<xref:System.Windows.Window> HWND, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]并使用将及其内容放入 HWND。  应用程序中的其余 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容共享单个 HWND。 菜单、组合框下拉列表和其他弹出窗口例外。 这些元素会创建自己的顶层窗口，因此 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 菜单可能超出所在窗口 HWND 的边缘。 <xref:System.Windows.Interop.HwndHost>使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]在中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]放置 HWND 时, 将通知如何相对<xref:System.Windows.Window>于 HWND 定位新的子 hwnd。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]

与之相关的 HWND 概念是每个 HWND 内及其之间的透明度。 [技术区概述](technology-regions-overview.md)主题中对此也有相关介绍。

<a name="hosting_a_wpf_page"></a>

## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>在 Microsoft Win32 窗口中承载 WPF 内容

在窗口上承载的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]关键是<xref:System.Windows.Interop.HwndSource>类。 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 此类在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 窗口中包装 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容，以便 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容可作为子窗口并入 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。 以下方法在单个应用程序中合并 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。

1. 将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容（内容根元素）作为托管类实现。 通常, 类继承自一个可包含多个子元素和/或用作根元素 (例如<xref:System.Windows.Controls.DockPanel>或<xref:System.Windows.Controls.Page>) 的类。 后续步骤中，此类被称为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类，此类的实例被称为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象。

2. 使用C++/Cli 实现 Windows 应用程序 如果是从现有的非托管C++应用程序开始, 则通常可以通过更改项目设置以包括`/clr`编译器标志来使其调用托管代码 (可能需要支持`/clr`的所有内容的完整范围)本主题不介绍编译。

3. 将线程处理模型设置为单线程单元 (STA)。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 使用此线程模型。

4. 处理窗口过程中的 WM_CREATE 通知。

5. 在处理程序（或处理程序调用的函数）中，执行以下操作：

    1. 使用父窗口<xref:System.Windows.Interop.HwndSource> HWND 作为其`parent`参数创建一个新的对象。

    2. 创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类的一个实例。

    3. 将对[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容对象的引用分配<xref:System.Windows.Interop.HwndSource>给对象<xref:System.Windows.Interop.HwndSource.RootVisual%2A>属性。

    4. <xref:System.Windows.Interop.HwndSource> 对象<xref:System.Windows.Interop.HwndSource.Handle%2A>属性包含窗口句柄 (HWND)。 要获取可在应用程序的非托管部分中使用的 HWND，需将 `Handle.ToPointer()` 强制装换为 HWND。

6. 实现一个托管类，该类包含一个用于保存对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象的引用的静态字段。 此类允许你[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]从代码中获取对内容对象的引用, 但<xref:System.Windows.Interop.HwndSource>更重要的是, 它可以防止无意中对其进行垃圾回收。

7. 通过将处理程序附加到一个或多个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象事件，接收 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象的通知。

8. 通过使用存储在静态字段中的引用设置属性、调用方法等，与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象进行通信。

> [!NOTE]
> 如果生成一个单独的程序集然后对其进行引用，对于步骤 1，可使用内容类的默认分部类在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中完成部分或全部 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类定义。 尽管通常在<xref:System.Windows.Application>将对象[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]编译为程序集的过程中包含对象, 但最终<xref:System.Windows.Application>不会将其作为互操作的一部分使用, 只需将[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]一个或多个根类用于所引用的文件应用程序并引用其分部类。 该过程的其余部分基本与上述相似。
>
> 本主题[演练中的代码演示了其中的每个步骤:在 Win32](walkthrough-hosting-wpf-content-in-win32.md)中承载 WPF 内容。

<a name="hosting_an_hwnd"></a>

## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>在 WPF 中承载 Microsoft Win32 窗口

在其他[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容中承载窗口的关键是<xref:System.Windows.Interop.HwndHost>类。 该类在可添加到 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素树的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素中包装窗口。 <xref:System.Windows.Interop.HwndHost>还支持 Api, 这些 Api 允许您将此类任务作为托管窗口的进程消息执行。 基本过程：

1. 为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序创建一个元素树（可通过代码或标记）。 在元素树中查找可作为子元素添加的<xref:System.Windows.Interop.HwndHost>相应和允许的点。 剩余步骤中，此元素称为保留元素。

2. 派生自<xref:System.Windows.Interop.HwndHost>以创建[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]保存内容的对象。

3. 在该宿主类中, 重<xref:System.Windows.Interop.HwndHost>写<xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>方法。 返回承载窗口的 HWND。 可能需要将实际控件包装为返回窗口的子窗口；在承载窗口中包装控件为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容从控件接收通知提供了一种简单的方式。 此方法有助于更正一些有关主机控件边界处消息处理的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 问题。

4. 重写<xref:System.Windows.Interop.HwndHost>方法<xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>和<xref:System.Windows.Interop.HwndHost.WndProc%2A>。 这样做的目的是处理清除和删除对承载内容的引用，尤其是在已创建对非托管对象的引用的情况下。

5. 在代码隐藏文件中，创建控件承载类的一个实例，并使其成为保留元素的子元素。 通常<xref:System.Windows.FrameworkElement.Loaded>, 使用事件处理程序, 如, 或使用分部类构造函数。 但也可通过运行时行为添加互操作内容。

6. 处理选择的窗口消息，例如控件通知。 方法有两种。 两种方法提供对消息流的相同访问权限，因此你的选择很大程度上取决于编程简便性。

    - 对<xref:System.Windows.Interop.HwndHost> 方法<xref:System.Windows.Interop.HwndHost.WndProc%2A>的重写中的所有消息 (而不只是关闭消息) 实施消息处理。

    - 让宿主[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]元素通过<xref:System.Windows.Interop.HwndHost.MessageHook>处理事件来处理消息。 对发送到承载窗口的主窗口过程的每个消息都会引发该事件。

    - 不能使用<xref:System.Windows.Interop.HwndHost.WndProc%2A>在进程外的窗口处理消息。

7. 通过使用平台调用来调用非托管 `SendMessage` 函数，与承载窗口通信。

按照这些步骤，创建一个处理鼠标输入的应用程序。 通过实现<xref:System.Windows.Interop.IKeyboardInputSink>接口, 可以为您的托管窗口添加 tab 键支持。

本主题[演练中的代码演示了其中的每个步骤:在 WPF](walkthrough-hosting-a-win32-control-in-wpf.md)中承载 Win32 控件。

### <a name="hwnds-inside-wpf"></a>WPF 内部的 Hwnd

您可以将视为<xref:System.Windows.Interop.HwndHost>一种特殊的控件。 (从技术<xref:System.Windows.Interop.HwndHost>上讲<xref:System.Windows.FrameworkElement> , 是一个派生类<xref:System.Windows.Controls.Control> , 而不是一个派生类, 但可以将其视为用于互操作的控件。)抽象托管[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 内容[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的基础特性, 以便将承载的内容视为另一个类似控件的对象, 该对象应呈现并处理输入。 <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost>通常, 其行为与[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]任何其他<xref:System.Windows.FrameworkElement>行为相似, 不过, 在输出 (绘图和图形) 和输入 (鼠标和键盘) 方面有一些重要差异, 这取决于基础 hwnd 可支持的内容。

#### <a name="notable-differences-in-output-behavior"></a>输出行为的显著差异

- <xref:System.Windows.FrameworkElement>, 它是<xref:System.Windows.Interop.HwndHost>基类, 具有表示 UI 更改的几个属性。 其中包括诸如<xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>之类的属性, 这些属性将元素内元素的布局更改为父级。 但是，这些属性大多数未映射到可能的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 等效项（即使这类等效项可能存在）。 过多这些属性及其含义具有过高的绘制技术针对性，这使得映射并不可行。 因此, 设置等属性<xref:System.Windows.FrameworkElement.FlowDirection%2A> <xref:System.Windows.Interop.HwndHost>不起作用。

- <xref:System.Windows.Interop.HwndHost>不能旋转、缩放、倾斜或以其他方式受转换影响。

- <xref:System.Windows.Interop.HwndHost>不支持<xref:System.Windows.UIElement.Opacity%2A>属性 (alpha 混合)。 如果中的<xref:System.Windows.Interop.HwndHost>内容执行<xref:System.Drawing>包含 alpha 信息的操作, 则不会<xref:System.Windows.Interop.HwndHost>发生冲突, 但作为整体仅支持不透明度 = 1.0 (100%)。

- <xref:System.Windows.Interop.HwndHost>将显示在同一顶级窗口[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中的其他元素之上。 但是, <xref:System.Windows.Controls.ToolTip>或<xref:System.Windows.Controls.ContextMenu>生成的菜单是单独的顶级窗口, <xref:System.Windows.Interop.HwndHost>因此在中将正常运行。

- <xref:System.Windows.Interop.HwndHost>不遵守其父项<xref:System.Windows.UIElement>的剪辑区域。 如果尝试将某个<xref:System.Windows.Interop.HwndHost>类放置在滚动区域或<xref:System.Windows.Controls.Canvas>中, 这可能是一个问题。

#### <a name="notable-differences-in-input-behavior"></a>输入行为的显著差异

- 通常, 当输入设备在<xref:System.Windows.Interop.HwndHost>托管[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]区域内范围内时, 输入事件会直接移[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]到。

- 当鼠标悬停在<xref:System.Windows.Interop.HwndHost>上时, 应用程序不会接收[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]鼠标事件, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]并且属性<xref:System.Windows.UIElement.IsMouseOver%2A>的值将为`false`。

- `false` <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]当具有键盘焦点时, 应用程序不会接收键盘事件, 并且属性的值将为。 <xref:System.Windows.Interop.HwndHost>

- <xref:System.Windows.Interop.HwndHost>当焦点在内并且更改到中的<xref:System.Windows.Interop.HwndHost>另一个控件时, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序将不会接收<xref:System.Windows.UIElement.GotFocus>事件<xref:System.Windows.UIElement.LostFocus>或。

- 相关的触笔属性和事件类似, 当触笔悬停于上方<xref:System.Windows.Interop.HwndHost>时不报告信息。

<a name="tabbing_mnemonics_accelerators"></a>

## <a name="tabbing-mnemonics-and-accelerators"></a>Tab 键、助记键和加速键

和接口允许你为混合[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]应用程序创建无缝键盘体验: <xref:System.Windows.Interop.IKeyboardInputSite> <xref:System.Windows.Interop.IKeyboardInputSink>

- [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 组件之间的 Tab 键

- 焦点位于 Win32 组件内和 WPF 组件内时皆起作用的助记键和加速键。

和类都提供了的<xref:System.Windows.Interop.IKeyboardInputSink>实现, 但它们可能不会处理你需要用于更高级方案的所有输入消息。 <xref:System.Windows.Interop.HwndSource> <xref:System.Windows.Interop.HwndHost> 替换为适当方法，获取所需的键盘行为。

接口仅对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 区域间的转换过程中发生的事件提供支持。 在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 区域内，Tab 键行为完全受 Tab 键的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 实现逻辑（若有）控制。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Interop.HwndHost>
- <xref:System.Windows.Interop.HwndSource>
- <xref:System.Windows.Interop>
- [演练：在 WPF 中承载 Win32 控件](walkthrough-hosting-a-win32-control-in-wpf.md)
- [演练：在 Win32 中承载 WPF 内容](walkthrough-hosting-wpf-content-in-win32.md)
