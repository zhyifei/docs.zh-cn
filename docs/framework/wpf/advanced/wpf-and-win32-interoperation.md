---
title: WPF 和 Win32 互操作
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: 7248b0e5abcf2c6357dc7ce7c708eaa85358061a
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846795"
---
# <a name="wpf-and-win32-interoperation"></a>WPF 和 Win32 互操作

本主题概述如何互操作 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 代码。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供了用于创建应用程序的丰富环境。 但是，如果对 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 代码投入很大，重复使用部分此代码可能更有效。

<a name="basics"></a>

## <a name="wpf-and-win32-interoperation-basics"></a>WPF 和 Win32 互操作基础知识

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 代码间的互操作存在两种基本方法。

- 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 窗口中承载 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 内容。 通过此方法，可在标准 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 窗口和应用程序的框架内使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的高级图形功能。

- 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容中承载 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 窗口。 通过此方法，可在其他 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的上下文中使用现有自定义 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 控件，并可跨边界传递数据。

本主题中对上述每种方法进行了概念性介绍。 有关在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 中承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的更具有代码针对性的说明，请参阅[演练：在 Win32 中承载 WPF 内容](walkthrough-hosting-wpf-content-in-win32.md)。 有关在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中承载 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 的更具代码针对性的说明，请参阅[演练：在 WPF 中承载 Win32 控件](walkthrough-hosting-a-win32-control-in-wpf.md)。

<a name="projects"></a>

## <a name="wpf-interoperation-projects"></a>WPF 互操作项目

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Api 是托管代码，但大多数现有 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 程序都是用非C++托管的。  不能从真正的非托管程序调用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Api。 但是，通过将 `/clr` 选项与 Microsoft Visual C++编译器一起使用，你可以创建混合托管的非托管程序，你可以在其中无缝混合托管和非托管的 API 调用。

一个项目级别的难点在于，您不能将 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 文件编译C++为项目。  可通过一些项目分离技术对此进行弥补。

- 创建一个C# DLL，其中包含作为编译程序集的所有 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页面，然后让C++可执行文件将该 dll 作为引用包含在内。

- 为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]C#内容创建一个可执行文件，并让其引用C++包含[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]内容的 DLL。

- 使用 <xref:System.Windows.Markup.XamlReader.Load%2A> 在运行时加载任何 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，而不是编译您的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。

- 请勿使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，并在代码中编写所有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，并从 <xref:System.Windows.Application>生成元素树。

请使用最适合你的方法。

> [!NOTE]
> 如果你之前未使用C++/cli，你可能会注意到一些 "新" 关键字，如互操作代码示例中的`gcnew`和`nullptr`。 这些关键字将取代旧的双下划线语法（`__gc`），并为中C++的托管代码提供更自然的语法。  若要了解有关/Cli C++托管功能的详细信息，请参阅[运行时平台的组件扩展](/cpp/windows/component-extensions-for-runtime-platforms)。

<a name="hwnds"></a>

## <a name="how-wpf-uses-hwnds"></a>WPF 如何使用 Hwnd

若要充分利用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]“HWND 互操作”，需要了解 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 如何使用 HWND。 对于任何 HWND，不能将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 呈现与 DirectX 呈现或 GDI/GDI + 呈现混合使用。 这具有许多影响。 首先，若要混合这些绘制模型，必须创建互操作解决方案，并对选择使用的每个绘制模型使用互操作的指定段。 此外，绘制行为会为互操作解决方案可实现的操作创建一个“空域”限制。 有关“空域”概念的详细信息，请参见[技术区概述](technology-regions-overview.md)主题。

屏幕上的所有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素最终受 HWND 支持。 当你创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window>时，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 会创建一个顶级 HWND，并使用 <xref:System.Windows.Interop.HwndSource> 将 <xref:System.Windows.Window> 及其 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容放入 HWND。  应用程序中的其余 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容共享单个 HWND。 菜单、组合框下拉列表和其他弹出窗口例外。 这些元素会创建自己的顶层窗口，因此 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 菜单可能超出所在窗口 HWND 的边缘。 当你使用 <xref:System.Windows.Interop.HwndHost> 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中放置 HWND 时，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 将通知 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 如何相对于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND 定位新的子 HWND。

与之相关的 HWND 概念是每个 HWND 内及其之间的透明度。 [技术区概述](technology-regions-overview.md)主题中对此也有相关介绍。

<a name="hosting_a_wpf_page"></a>

## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>在 Microsoft Win32 窗口中承载 WPF 内容

在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 窗口中承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的关键是 <xref:System.Windows.Interop.HwndSource> 类。 此类在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 窗口中包装 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容，以便 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容可作为子窗口并入 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。 以下方法在单个应用程序中合并 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。

1. 将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容（内容根元素）作为托管类实现。 通常，类继承自其中一个类，这些类可包含多个子元素和/或用作根元素，例如 <xref:System.Windows.Controls.DockPanel> 或 <xref:System.Windows.Controls.Page>。 后续步骤中，此类被称为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类，此类的实例被称为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象。

2. 使用C++/Cli 实现 Windows 应用程序 如果是从现有的非托管C++应用程序开始，则通常可以通过更改项目设置来使其调用托管代码，使其包含`/clr`编译器标志（支持`/clr`编译所需的内容的完整范围未在本主题中介绍）。

3. 将线程处理模型设置为单线程单元 (STA)。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 使用此线程模型。

4. 处理窗口过程中的 WM_CREATE 通知。

5. 在处理程序（或处理程序调用的函数）中，执行以下操作：

    1. 使用父窗口 HWND 作为其 `parent` 参数创建新的 <xref:System.Windows.Interop.HwndSource> 对象。

    2. 创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类的一个实例。

    3. 向 <xref:System.Windows.Interop.HwndSource> 对象 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 属性分配对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象的引用。

    4. <xref:System.Windows.Interop.HwndSource> 对象 <xref:System.Windows.Interop.HwndSource.Handle%2A> 属性包含窗口句柄（HWND）。 要获取可在应用程序的非托管部分中使用的 HWND，需将 `Handle.ToPointer()` 强制装换为 HWND。

6. 实现一个托管类，该类包含一个用于保存对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象的引用的静态字段。 此类允许你从你的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 代码中获取对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象的引用，但更重要的是，它会阻止你的 <xref:System.Windows.Interop.HwndSource> 无意间被垃圾回收。

7. 通过将处理程序附加到一个或多个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象事件，接收 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象的通知。

8. 通过使用存储在静态字段中的引用设置属性、调用方法等，与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象进行通信。

> [!NOTE]
> 如果生成一个单独的程序集然后对其进行引用，对于步骤 1，可使用内容类的默认分部类在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中完成部分或全部 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类定义。 虽然在将 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 编译到程序集中时通常包含一个 <xref:System.Windows.Application> 对象，但最终不会使用该 <xref:System.Windows.Application> 作为互操作的一部分，只需将一个或多个根类用于应用程序所引用的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件即可和引用它们的分部类。 该过程的其余部分基本与上述相似。
>
> [演练：在 Win32 中承载 WPF 内容](walkthrough-hosting-wpf-content-in-win32.md)主题中对这些每个步骤通过代码进行了说明。

<a name="hosting_an_hwnd"></a>

## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>在 WPF 中承载 Microsoft Win32 窗口

在其他 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容内承载 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 窗口的关键是 <xref:System.Windows.Interop.HwndHost> 类。 该类在可添加到 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素树的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素中包装窗口。 <xref:System.Windows.Interop.HwndHost> 还支持 Api，这些 Api 允许你为承载的窗口的进程消息执行此类任务。 基本过程：

1. 为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序创建一个元素树（可通过代码或标记）。 在元素树中查找适当且允许的点，可在其中将 <xref:System.Windows.Interop.HwndHost> 实现添加为子元素。 剩余步骤中，此元素称为保留元素。

2. 从 <xref:System.Windows.Interop.HwndHost> 派生，以创建保存 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 内容的对象。

3. 在该宿主类中，重写 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>的 <xref:System.Windows.Interop.HwndHost> 方法。 返回承载窗口的 HWND。 可能需要将实际控件包装为返回窗口的子窗口；在承载窗口中包装控件为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容从控件接收通知提供了一种简单的方式。 此方法有助于更正一些有关主机控件边界处消息处理的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 问题。

4. 重写 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 和 <xref:System.Windows.Interop.HwndHost.WndProc%2A>的 <xref:System.Windows.Interop.HwndHost> 方法。 这样做的目的是处理清除和删除对承载内容的引用，尤其是在已创建对非托管对象的引用的情况下。

5. 在代码隐藏文件中，创建控件承载类的一个实例，并使其成为保留元素的子元素。 通常会使用事件处理程序（如 <xref:System.Windows.FrameworkElement.Loaded>）或使用分部类构造函数。 但也可通过运行时行为添加互操作内容。

6. 处理选择的窗口消息，例如控件通知。 方法有两种。 两种方法提供对消息流的相同访问权限，因此你的选择很大程度上取决于编程简便性。

    - 在 <xref:System.Windows.Interop.HwndHost> 方法 <xref:System.Windows.Interop.HwndHost.WndProc%2A>的重写中，为所有消息（而不只是关闭消息）实现消息处理。

    - 让宿主 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素通过处理 <xref:System.Windows.Interop.HwndHost.MessageHook> 事件来处理这些消息。 对发送到承载窗口的主窗口过程的每个消息都会引发该事件。

    - 不能使用 <xref:System.Windows.Interop.HwndHost.WndProc%2A>处理不在进程中的消息。

7. 通过使用平台调用来调用非托管 `SendMessage` 函数，与承载窗口通信。

按照这些步骤，创建一个处理鼠标输入的应用程序。 可以通过实现 <xref:System.Windows.Interop.IKeyboardInputSink> 接口，为承载的窗口添加 tab 键支持。

[演练：在 WPF 中承载 Win32 控件](walkthrough-hosting-a-win32-control-in-wpf.md)主题中对这些每个步骤通过代码进行了说明。

### <a name="hwnds-inside-wpf"></a>WPF 内部的 Hwnd

您可以将 <xref:System.Windows.Interop.HwndHost> 视为一种特殊的控件。 （从技术上讲，<xref:System.Windows.Interop.HwndHost> 是 <xref:System.Windows.FrameworkElement> 派生类，而不是 <xref:System.Windows.Controls.Control> 派生类，但可以将其视为用于互操作的控件。）<xref:System.Windows.Interop.HwndHost> 抽象所承载内容的基础 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 性质，使 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的其余部分将托管内容视为另一个类似控件的对象，该对象应呈现并处理输入。 <xref:System.Windows.Interop.HwndHost> 的行为与任何其他 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>的行为相同，但根据基础 Hwnd 可支持的限制，与输出（绘图和图形）和输入（鼠标和键盘）之间存在一些重要的差异。

#### <a name="notable-differences-in-output-behavior"></a>输出行为的显著差异

- <xref:System.Windows.FrameworkElement>（<xref:System.Windows.Interop.HwndHost> 基类）具有相当多的属性，这些属性表示 UI 的更改。 其中包括诸如 <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>之类的属性，这些属性将元素内元素的布局更改为父级。 但是，这些属性大多数未映射到可能的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 等效项（即使这类等效项可能存在）。 过多这些属性及其含义具有过高的绘制技术针对性，这使得映射并不可行。 因此，在 <xref:System.Windows.Interop.HwndHost> 上设置属性（如 <xref:System.Windows.FrameworkElement.FlowDirection%2A>）不起作用。

- 不能对 <xref:System.Windows.Interop.HwndHost> 进行旋转、缩放、倾斜或以其他方式受转换的影响。

- <xref:System.Windows.Interop.HwndHost> 不支持 <xref:System.Windows.UIElement.Opacity%2A> 属性（alpha 混合）。 如果 <xref:System.Windows.Interop.HwndHost> 中的内容执行包含 alpha 信息 <xref:System.Drawing> 操作，则不会发生冲突，但 <xref:System.Windows.Interop.HwndHost> 为整体仅支持不透明度 = 1.0 （100%）。

- <xref:System.Windows.Interop.HwndHost> 将显示在同一顶级窗口中的其他 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素之上。 但是，"<xref:System.Windows.Controls.ToolTip>" 或 "<xref:System.Windows.Controls.ContextMenu> 生成" 菜单是一个单独的顶级窗口，因此在 <xref:System.Windows.Interop.HwndHost>中的行为会正确。

- <xref:System.Windows.Interop.HwndHost> 不遵守其父 <xref:System.Windows.UIElement>的剪辑区域。 如果尝试将 <xref:System.Windows.Interop.HwndHost> 类放置在滚动区域或 <xref:System.Windows.Controls.Canvas>中，这可能是一个问题。

#### <a name="notable-differences-in-input-behavior"></a>输入行为的显著差异

- 通常，当输入设备在 <xref:System.Windows.Interop.HwndHost> 托管 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 区域内的范围内时，输入事件会直接 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]。

- 当鼠标悬停在 <xref:System.Windows.Interop.HwndHost>上时，应用程序不会收到 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的鼠标事件，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性 <xref:System.Windows.UIElement.IsMouseOver%2A> 的值将为 `false`。

- 当 <xref:System.Windows.Interop.HwndHost> 具有键盘焦点时，应用程序将不会收到 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的键盘事件，并且 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> 属性的值将 `false`。

- 当焦点位于 <xref:System.Windows.Interop.HwndHost> 中，并更改 <xref:System.Windows.Interop.HwndHost>中的另一个控件时，应用程序将不会接收 <xref:System.Windows.UIElement.GotFocus> 或 <xref:System.Windows.UIElement.LostFocus>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 事件。

- 相关的触笔属性和事件类似，当触笔位于 <xref:System.Windows.Interop.HwndHost>上时不报告信息。

<a name="tabbing_mnemonics_accelerators"></a>

## <a name="tabbing-mnemonics-and-accelerators"></a>Tab 键、助记键和加速键

<xref:System.Windows.Interop.IKeyboardInputSink> 和 <xref:System.Windows.Interop.IKeyboardInputSite> 接口允许您为混合 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 应用程序创建无缝键盘体验：

- [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 组件之间的 Tab 键

- 焦点位于 Win32 组件内和 WPF 组件内时皆起作用的助记键和加速键。

<xref:System.Windows.Interop.HwndHost> 和 <xref:System.Windows.Interop.HwndSource> 类均提供 <xref:System.Windows.Interop.IKeyboardInputSink>的实现，但它们可能不会处理更高级方案所需的所有输入消息。 替换为适当方法，获取所需的键盘行为。

接口仅对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 区域间的转换过程中发生的事件提供支持。 在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 区域内，Tab 键行为完全受 Tab 键的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 实现逻辑（若有）控制。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Interop.HwndHost>
- <xref:System.Windows.Interop.HwndSource>
- <xref:System.Windows.Interop>
- [演练：在 WPF 中托管 Win32 控件](walkthrough-hosting-a-win32-control-in-wpf.md)
- [演练：在 Win32 中承载 WPF 内容](walkthrough-hosting-wpf-content-in-win32.md)
