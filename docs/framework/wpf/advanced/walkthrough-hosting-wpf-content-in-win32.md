---
title: Win32 中的主机 WPF 内容
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
ms.openlocfilehash: 8a5d556abf49c9c1f49e7853e752ebc5248d1101
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186070"
---
# <a name="walkthrough-hosting-wpf-content-in-win32"></a>演练：在 Win32 中承载 WPF 内容
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供了用于创建应用程序的丰富环境。 但是，当您对 Win32 代码进行大量投资时，向应用程序添加[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]功能而不是重写原始代码可能更有效。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供了在 Win32[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]窗口中托管内容的简单机制。  
  
 本教程介绍如何编写示例应用程序，[在 Win32 窗口示例中托管 WPF 内容](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32HostingWPFPage)，该示例[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]在 Win32 窗口中托管内容。 您可以扩展此示例以承载任何 Win32 窗口。 因为它涉及混合托管和非托管代码，所以应用程序以C++/CLI编写。  

<a name="requirements"></a>
## <a name="requirements"></a>要求  
 本教程假定对 Win32[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]编程和 Win32 编程基本熟悉。 有关[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]编程的基本介绍，请参阅[入门](../getting-started/index.md)。 有关 Win32 编程的介绍，您应该参考有关该主题的众多书籍，特别是查尔斯·佩佐德的*编程 Windows。*  
  
 由于本教程附带的示例在 C++/CLI 中实现，本教程假定熟悉使用 C++对 Windows API 进行编程，并了解托管代码编程。 熟悉C++/CLI是有帮助的，但不是必须的。  
  
> [!NOTE]
> 本教程包括来自相关示例的一些代码示例。 但是，出于可读性考虑，不包括完整的示例代码。 有关完整的示例代码，请参阅[在 Win32 窗口示例中托管 WPF 内容](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32HostingWPFPage)。  
  
<a name="basic_procedure"></a>
## <a name="the-basic-procedure"></a>基本过程  
 本节概述了用于在 Win32 窗口中托管[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容的基本过程。 其余章节说明每个步骤的详细内容。  
  
 在 Win32 窗口中托管[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容的关键是<xref:System.Windows.Interop.HwndSource>类。 此类将[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容包装在 Win32 窗口中，允许将其作为子窗口合并到您的[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]窗口中。 以下方法将 Win32 和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]单个应用程序相结合。  
  
1. 将[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容作为托管类实现。  
  
2. 使用C++/CLI实现 Windows 应用程序。 如果要从现有应用程序和非托管C++代码开始，通常可以通过更改项目设置来包括`/clr`编译器标志来启用它调用托管代码。  
  
3. 将线程处理模型设置为单线程单元 (STA)。  
  
4. 在窗口过程中处理[WM_CREATE](/windows/desktop/winmsg/wm-create)通知，并执行以下操作：  
  
    1. 创建一个新的 <xref:System.Windows.Interop.HwndSource> 对象，将父窗口用作其 `parent` 参数。  
  
    2. 创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类的一个实例。  
  
    3. 将对[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容对象的引用分配给<xref:System.Windows.Interop.HwndSource.RootVisual%2A>的属性。 <xref:System.Windows.Interop.HwndSource>  
  
    4. 获取该内容的 HWND。 <xref:System.Windows.Interop.HwndSource.Handle%2A> 对象的 <xref:System.Windows.Interop.HwndSource> 属性包含窗口句柄 (HWND)。 要获取可在应用程序的非托管部分中使用的 HWND，需将 `Handle.ToPointer()` 强制装换为 HWND。  
  
5. 实现一个托管类，该类包含一个用于保存对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的引用的静态字段。 此类允许您从 Win32 代码中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]获取对内容的引用。  
  
6. 向静态字段分配 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容。  
  
7. 通过将处理程序附加到一[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]个或多个[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]事件来接收来自内容的通知。  
  
8. 通过使用存储在静态字段中用于设置属性等的引用来与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容通信。  
  
> [!NOTE]
> 您还可以使用 来实现[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]内容[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 但是，您必须将其单独编译为动态链接库 （DLL） 并从 Win32 应用程序中引用该 DLL。 该过程的其余部分与上述相似。

<a name="implementing_the_application"></a>
## <a name="implementing-the-host-application"></a>实现主机应用程序
 本节介绍如何在基本的 Win32 应用程序中托管[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容。 内容本身在C++/CLI 中作为托管类实现。 大多数情况下，它是简单的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 编程。 [在实施WPF内容](#implementing_the_wpf_page)时讨论了内容实现的关键方面。

- [基本应用程序](#the_basic_application)

- [承载 WPF 内容](#hosting_the_wpf_page)

- [保存对 WPF 内容的引用](#holding_a_reference)

- [与 WPF 内容通信](#communicating_with_the_page)

<a name="the_basic_application"></a>
### <a name="the-basic-application"></a>基本应用程序
 主机应用程序的出发点是创建 Visual Studio 2005 模板。

1. 打开 Visual Studio 2005，并从 **"文件**"菜单中选择 **"新项目**"。

2. 从可视化C++项目类型列表中选择**Win32。** 如果您的默认语言不C++，您将在 **"其他语言"** 下找到这些项目类型。

3. 选择**Win32 项目**模板，为项目指定名称，然后单击 **"确定"** 以启动**Win32 应用程序向导**。

4. 接受向导的默认设置，然后单击 **"完成"** 以启动项目。

 该模板创建基本 Win32 应用程序，包括：

- 应用程序的入口点。

- 一个窗口和关联的窗口过程 (WndProc)。

- 包含 **"文件**"和"**帮助**"标题的菜单。 "**文件**"菜单具有关闭应用程序的**退出**项。 "**帮助"** 菜单具有启动简单对话框**的"关于**"项。

 在开始编写代码以承载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容之前，需要对基本模板进行两项修改。

 第一项是将项目作为托管代码进行编译。 默认情况下，项目将作为非托管代码进行编译。 但是，由于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 是在托管代码中实现的，因此必须将项目进行相应编译。

1. 右键单击**解决方案资源管理器**中的项目名称，并从上下文菜单中选择 **"属性**"以启动 **"属性页"** 对话框。

2. 从左侧窗格中的树视图中选择 **"配置属性**"。

3. 从右侧窗格中的 **"项目默认值"** 列表中选择 **"通用语言运行时**支持"。

4. 从下拉列表框中选择**通用语言运行时支持 （/clr）。**

> [!NOTE]
> 此编译器标志使你能够在应用程序中使用托管代码，但非托管代码将仍将像以前一样进行编译。

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 使用单线程单元 (STA) 线程处理模型。 为了正确处理[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容代码，必须通过将属性应用于入口点，将应用程序的线程模型设置为 STA。

 [!code-cpp[Win32HostingWPFPage#WinMain](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]

<a name="hosting_the_wpf_page"></a>
### <a name="hosting-the-wpf-content"></a>承载 WPF 内容
 内容是[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]一个简单的地址输入应用程序。 它包含若干个 <xref:System.Windows.Controls.TextBox> 控件，这些控件用于获得用户名称、地址等。 还有两个<xref:System.Windows.Controls.Button>控件，**确定**和**取消**。 当用户单击 **"确定"** 时，按钮<xref:System.Windows.Controls.Primitives.ButtonBase.Click>的事件处理程序会从<xref:System.Windows.Controls.TextBox>控件收集数据，将其分配给相应的属性，并引发自定义事件 。 `OnButtonClicked` 当用户单击 **"取消"** 时，处理程序将仅引发`OnButtonClicked`。 `OnButtonClicked` 的事件参数对象包含布尔型字段，用于指示被单击的按钮。

 承载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容的代码在主机窗口中[WM_CREATE](/windows/desktop/winmsg/wm-create)通知的处理程序中实现。

 [!code-cpp[Win32HostingWPFPage#WMCreate](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]

 该方法`GetHwnd`采用大小和位置信息加上父窗口句柄，并返回托管[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容的窗口句柄。

> [!NOTE]
> 无法对 `#using` 命名空间使用 `System::Windows::Interop` 指令。 如果进行此操作，将造成该命名空间中的 <xref:System.Windows.Interop.MSG> 结构和在 winuser.h 中声明的 MSG 结构之间的名称冲突。 必须使用完全限定名来访问该命名空间的内容。

 [!code-cpp[Win32HostingWPFPage#GetHwnd](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]

 您不能直接在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序窗口中托管内容。 从而，首先创建 <xref:System.Windows.Interop.HwndSource> 对象以包装 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容。 此对象基本上是一个旨在承载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容的窗口。 通过将<xref:System.Windows.Interop.HwndSource>对象创建为作为应用程序的一部分的 Win32 窗口的子窗口，在父窗口中托管该对象。 <xref:System.Windows.Interop.HwndSource>构造函数参数包含与创建 Win32 子窗口时传递给 CreateWindow 的信息大致相同。

 接下来创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容对象的实例。 在这种情况下，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容作为单独的类实现，`WPFPage`使用C++/CLI。 还可以使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 实现 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 内容。 但是，要执行此操作，您需要设置一个单独的项目，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]并将内容构建为 DLL。 您可以将对该 DLL 的引用添加到项目中，并使用该引用创建内容的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]实例。

 通过将对[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容<xref:System.Windows.Interop.HwndSource.RootVisual%2A>的引用分配给 的属性<xref:System.Windows.Interop.HwndSource>，在子窗口中显示内容。

 代码的下一行将一个事件处理程序 `WPFButtonClicked` 附加到 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容 `OnButtonClicked` 事件。 当用户单击 **"确定"** 或 **"取消"** 按钮时，将调用此处理程序。 有关此事件处理程序的进一步讨论[，请参阅communicating_with_the_WPF内容](#communicating_with_the_page)。

 代码显示的最后一行返回与 <xref:System.Windows.Interop.HwndSource> 对象关联的窗口句柄 (HWND)。 您可以使用 Win32 代码中的此句柄将消息发送到托管窗口，尽管示例不这样做。 每当 <xref:System.Windows.Interop.HwndSource> 对象收到一条消息时就会引发一个事件。 若要处理消息，请调用 <xref:System.Windows.Interop.HwndSource.AddHook%2A> 方法来附加消息处理程序，然后在此处理程序中处理消息。

<a name="holding_a_reference"></a>
### <a name="holding-a-reference-to-the-wpf-content"></a>保存对 WPF 内容的引用
 对于许多应用程序，你将需要稍后与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容进行通信。 例如，可能需要修改 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容属性，或可能让 <xref:System.Windows.Interop.HwndSource> 对象托管不同的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容。 执行此操作需要对 <xref:System.Windows.Interop.HwndSource> 对象或 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的引用。 <xref:System.Windows.Interop.HwndSource> 对象及其关联 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容保留在内存中，直到销毁窗口句柄。 但是，一旦从窗口过程返回，分配给 <xref:System.Windows.Interop.HwndSource> 对象的变量就将超出范围。 使用 Win32 应用程序处理此问题的惯常方法是使用静态变量或全局变量。 遗憾的是，你无法向这些类型的变量分配托管对象。 可以向全局或静态变量分配与 <xref:System.Windows.Interop.HwndSource> 对象关联的窗口句柄，但这一操作不会提供对对象本身的访问。

 针对这一问题最简单的解决方案是实现一个托管类，该类包含一组静态字段，这些字段保存对需要访问的任何托管对象的引用。 此示例使用 `WPFPageHost` 类来保存对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的引用，以及对该内容某些属性的初始值的引用（用户以后可能会对这些属性进行更改）。 这在标头中进行定义。

 [!code-cpp[Win32HostingWPFPage#WPFPageHost](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]

 `GetHwnd` 函数的后半部分将值分配给这些字段以供以后使用（在 `myPage` 仍处于范围内时）。

<a name="communicating_with_the_page"></a>
### <a name="communicating-with-the-wpf-content"></a>与 WPF 内容通信
 与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的通信有两种类型。 当用户单击[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]**"确定"** 或 **"取消"** 按钮时，应用程序将从内容接收信息。 该应用程序还具有 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，使用户可以更改各种 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容属性，例如背景色或默认字体大小。

 如上所述，用户单击任一按钮时，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容将引发 `OnButtonClicked` 事件。 该应用程序将一个处理程序附加到此事件以接收这些通知。 如果单击了 **"确定"** 按钮，处理程序将从[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容中获取用户信息，并将其显示在一组静态控件中。

 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]

 该处理程序从 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容接收到一个自定义事件参数对象 `MyPageEventArgs`。 `true`如果单击了 **"确定"** 按钮，并且`false`单击了 **"取消"** 按钮，则对象的属性`IsOK`将设置为"取消" 按钮。

 如果单击了 **"确定"** 按钮，处理程序将从容器类中获取对[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容的引用。 然后它会收集由关联的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容属性保存的用户信息，并使用静态控件在父窗口上显示该信息。 由于[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容数据以托管字符串的形式出现，因此必须将其封送供 Win32 控件使用。 如果单击"**取消"** 按钮，处理程序将清除静态控件中的数据。

 应用程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 提供一组单选按钮，允许用户修改 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的背景色和若干与字体相关的属性。 下面的示例是应用程序的窗口过程 (WndProc) 的一段摘录及其消息处理功能，通过该功能可设置不同消息上的各种属性，包括背景色。 其他内容与此类似，将不进行展示。 请查看完整示例了解详细信息和上下文。

 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]

 若要设置背景色，请从 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 获取对 `hostedPage` 内容 (`WPFPageHost`) 的引用并将背景色属性设置为适当的颜色。 此示例使用三种颜色选项：原始颜色、浅绿色或浅橙红色。 原始背景色作为静态字段存储在 `WPFPageHost` 类中。 若要设置其他两种颜色，请创建一个新的 <xref:System.Windows.Media.SolidColorBrush> 对象，并从 <xref:System.Windows.Media.Colors> 对象向构造函数传递一个静态颜色值。

<a name="implementing_the_wpf_page"></a>
## <a name="implementing-the-wpf-page"></a>实现 WPF 页
 您可以托管和使用内容，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]而不了解实际实现。 如果[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容已打包在单独的 DLL 中，则内容可以以任何通用语言运行时 （CLR） 语言构建。 以下是示例中使用的C++/CLI 实现的简短演练。 本节包含下列子节。

- [布局](#page_layout)

- [将数据返回到主机窗口](#returning_data_to_window)

- [设置 WPF 属性](#set_page_properties)

<a name="page_layout"></a>
### <a name="layout"></a>布局
 内容中[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]的元素由五个<xref:System.Windows.Controls.TextBox>控件组成，并具有关联的<xref:System.Windows.Controls.Label>控件：名称、地址、城市、州和 Zip。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 还有两个<xref:System.Windows.Controls.Button>控件，**确定**和**取消**

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容在 `WPFPage` 类中实现。 布局通过 <xref:System.Windows.Controls.Grid> 布局元素进行处理。 该类继承自实际使其成为 <xref:System.Windows.Controls.Grid> 内容根元素的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。

 内容[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]构造函数采用所需的宽度和高度，并<xref:System.Windows.Controls.Grid>相应地调整大小。 然后<xref:System.Windows.Controls.ColumnDefinition>，它通过创建一组 和<xref:System.Windows.Controls.RowDefinition>对象并分别将它们添加到<xref:System.Windows.Controls.Grid>对象库<xref:System.Windows.Controls.Grid.ColumnDefinitions%2A>和<xref:System.Windows.Controls.Grid.RowDefinitions%2A>集合来定义基本布局。 这将定义具有 5 行和 7 列的网格，该网格具有单元内容定义的维度。

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]

 接下来，此构造函数将 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 元素添加到 <xref:System.Windows.Controls.Grid>。 第一个元素是标题文本，这是一个在网格首行居中的 <xref:System.Windows.Controls.Label> 控件。

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]

 下一行包含名称 <xref:System.Windows.Controls.Label> 控制及其关联的 <xref:System.Windows.Controls.TextBox> 控件。 由于对每个标签/文本框对使用同一代码，因而该代码被置于一对专用方法内并用于所有五个标签/文本框对。 该方法创建相应的控件，并调用 <xref:System.Windows.Controls.Grid> 类静态 <xref:System.Windows.Controls.Grid.SetColumn%2A> 和 <xref:System.Windows.Controls.Grid.SetRow%2A> 方法，以将控件置于相应单元格内。 创建控件后，该示例对 <xref:System.Windows.Controls.UIElementCollection.Add%2A> 的 <xref:System.Windows.Controls.Panel.Children%2A> 属性调用 <xref:System.Windows.Controls.Grid> 方法，以便将控件添加到网格。 用于添加剩余标签/文本框对的代码相似。 请参阅示例代码了解详细信息。

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]

 这两种方法的实现如下所示：

 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]

 最后，该示例添加 **"确定****"和"取消"** 按钮，并将事件处理程序附加到<xref:System.Windows.Controls.Primitives.ButtonBase.Click>其事件。

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]

<a name="returning_data_to_window"></a>
### <a name="returning-the-data-to-the-host-window"></a>将数据返回到主机窗口
 单击任一按钮后，将引发其 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件。 主机窗口只需将处理程序附加到这些事件，然后直接从 <xref:System.Windows.Controls.TextBox> 控件获取数据。 此示例使用的是不太直接的方法。 它处理内容<xref:System.Windows.Controls.Primitives.ButtonBase.Click>内的内容[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，然后引发自定义事件`OnButtonClicked`，以通知[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容。 这允许内容在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]通知主机之前执行一些参数验证。 该处理程序从 <xref:System.Windows.Controls.TextBox> 控件获取文本，然后将其分配给公共属性（主机可从其中检索信息）。

 WPFPage.h 中的事件声明：

 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]

 WPFPage.cpp 中的 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件处理程序：

 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]

<a name="set_page_properties"></a>
### <a name="setting-the-wpf-properties"></a>设置 WPF 属性
 Win32 主机允许用户更改多个[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容属性。 从 Win32 方面来说，这只是更改属性的问题。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类中的实现从某种意义上来说更加复杂，因为不存在控制所有控件的字体的单个全局属性。 相反，每个控件的相应属性均是在属性的 set 访问器中进行更改的。 下面的示例显示了属性的代码`DefaultFontFamily`。 设置属性将调用专用方法，该方法依次又将为各控件设置 <xref:System.Windows.Controls.Control.FontFamily%2A> 属性。

 从 WPFPage.h：

 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]

 从 WPFPage.cpp：

 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Interop.HwndSource>
- [WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)
