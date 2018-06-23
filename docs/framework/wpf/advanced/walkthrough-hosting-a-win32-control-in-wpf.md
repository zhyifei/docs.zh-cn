---
title: 演练：在 WPF 中承载 Win32 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: af8491a2887f4a35e2cd9926304948c12a67623a
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314973"
---
# <a name="walkthrough-hosting-a-win32-control-in-wpf"></a>演练：在 WPF 中承载 Win32 控件
Windows Presentation Foundation (WPF) 提供用于创建应用程序的丰富环境。 但是，当在 Win32 代码中有大量的投资，它可能更有效地至少某些重用的 WPF 应用程序中的代码而不是完全重写。 WPF 提供了用于承载 Win32 窗口中的，在 WPF 页上的简单机制。  
  
 本主题将指导你通过应用程序，[承载 WPF 示例中的 Win32 ListBox 控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)，主机 Win32 列表框控件。 此常规过程可以扩展为承载任何 Win32 窗口。  
  
  
<a name="requirements"></a>   
## <a name="requirements"></a>要求  
 本主题假定你基本熟悉 WPF 和 Win32 编程。 有关 WPF 编程的基本介绍，请参阅[入门](../../../../docs/framework/wpf/getting-started/index.md)。 有关 Win32 编程的介绍，你应引用的任何有关该主题的很多书籍尤其*编程 Windows* Charles Petzold 通过。  
  
 本主题附带的示例在 C# 中实现的因为它利用平台调用服务 (PInvoke) 来访问 Win32 API。 熟悉 PInvoke 是有用的但不是必需。  
  
> [!NOTE]
>  本主题包括来自相关示例的一些代码示例。 但是，出于可读性考虑，不包括完整的示例代码。 可以获取，也可以查看完整的代码从[承载 WPF 示例中的 Win32 ListBox 控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)。  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>基本过程  
 本部分概述了用于托管在 WPF 页上的 Win32 窗口的基本过程。 其余各节介绍了每个步骤的详细内容。  
  
 基本的承载步骤如下：  
  
1.  实现在 WPF 页来承载窗口。 一种方法是创建<xref:System.Windows.Controls.Border>要保留某一部分所承载的窗口的页元素。  
  
2.  实现类以承载继承自控件<xref:System.Windows.Interop.HwndHost>。  
  
3.  该类中重写<xref:System.Windows.Interop.HwndHost>类成员<xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>。  
  
4.  包含在 WPF 页的窗口的子级创建所承载的窗口。 尽管传统的 WPF 编程不需要显式提供使用情况下，宿主页是一个带有句柄 (HWND) 窗口。 接收页 HWND 通过`hwndParent`参数<xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>方法。 应将所承载的窗口创建为此 HWND 的子窗口。  
  
5.  在创建宿主窗口之后，返回所承载的窗口的 HWND。 如果你想要承载一个或多个 Win32 控件，您通常作为 HWND 的子级创建的宿主窗口并使该主机窗口的控件子级。 在宿主窗口包装控件提供一种简单的 WPF 页从控件接收通知用来处理一些特定的 Win32 问题通知跨 HWND 边界。  
  
6.  处理发送到宿主窗口的选定消息，例如，来自子控件的通知。 有两种方法可以实现此目的。  
  
    -   如果想要处理你的托管类中的消息，重写<xref:System.Windows.Interop.HwndHost.WndProc%2A>方法<xref:System.Windows.Interop.HwndHost>类。  
  
    -   如果倾向于 WPF 处理消息，处理<xref:System.Windows.Interop.HwndHost>类<xref:System.Windows.Interop.HwndHost.MessageHook>代码隐藏文件中的事件。 对于所承载的窗口收到的每条消息，都将发生此事件。 如果选择此选项，仍必须重写<xref:System.Windows.Interop.HwndHost.WndProc%2A>，但只需要一个最小实现。  
  
7.  重写<xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>和<xref:System.Windows.Interop.HwndHost.WndProc%2A>方法<xref:System.Windows.Interop.HwndHost>。 必须重写这些方法来满足<xref:System.Windows.Interop.HwndHost>协定，但你可能只需提供一个最小实现。  
  
8.  在代码隐藏文件中，创建控件的托管类的实例，并让其的子级<xref:System.Windows.Controls.Border>旨在承载窗口的元素。  
  
9. 通过将其发送与所承载的窗口进行通信[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]消息和来自其子窗口，如控件发送的通知的处理消息。  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>实现页面布局  
 承载 ListBox 控件在 WPF 页的布局包含两个区域。 页面左侧承载多个提供的 WPF 控件[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]，允许你操纵 Win32 控件。 页面右上角具有一个正方形区域，用于放置所承载的 ListBox 控件。  
  
 若要实现此布局的代码是非常简单。 根元素是<xref:System.Windows.Controls.DockPanel>具有两个子元素。 第一种是<xref:System.Windows.Controls.Border>承载 ListBox 控件的元素。 它在该页的右上角占据了一个大小为 200x200 的正方形。 第二个是<xref:System.Windows.Controls.StackPanel>元素包含一套 WPF 控件来显示信息以及使您可以通过设置操作 ListBox 控件公开互操作的属性。 为每个元素的子级的<xref:System.Windows.Controls.StackPanel>，查看有关这些元素是或它们执行的操作的详细信息使用的各种元素的参考材料，这些列在下面的示例代码，但不是会此处所述 (basic互操作模型不需要其中任何，它们可用于将一些交互功能添加到示例）。  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>实现类以承载 Microsoft Win32 控件  
 此示例的核心是实际承载控件的类，即 ControlHost.cs。 它继承自<xref:System.Windows.Interop.HwndHost>。 构造函数采用两个参数、 高度和宽度，它们分别对应于的高度和宽度<xref:System.Windows.Controls.Border>承载 ListBox 控件的元素。 更高版本使用这些值以确保控制匹配项的大小<xref:System.Windows.Controls.Border>元素。  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 还有一组常量。 这些常量很大程度上取自参见 Winuser.h，并允许你在调用 Win32 函数时使用传统的名称。  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>替代 BuildWindowCore 以创建 Microsoft Win32 窗口  
 你重写此方法以创建将托管的页面，并使窗口和页之间的连接的 Win32 窗口。 由于此示例涉及承载 ListBox 控件，因此将创建两个窗口。 第一个是由在 WPF 页实际承载的窗口。 ListBox 控件被创建为该窗口的子窗口。  
  
 采用此方法的原因是为了简化接收来自控件的通知的过程。 <xref:System.Windows.Interop.HwndHost>类可用于处理发送到它正在承载的窗口消息。 如果主机 Win32 直接控制，你将收到发送到控件的内部消息循环的消息。 你可以显示控件并向其发送消息，但不会收到该控件发送到其父窗口的通知。 这意味你没有办法检测用户何时与该控件进行交互，以及其他更多方面。 可改为创建一个宿主窗口，并使控件成为该窗口的子窗口。 这样，你便能够处理宿主窗口的消息，包括由该控件发送给它的通知。 由于宿主窗口只是控件的一个简单包装器而已，为了方便起见，以后将把该包称为 ListBox 控件。  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>创建宿主窗口和 ListBox 控件  
 你可以使用 PInvoke 通过创建和注册窗口类，创建控件的宿主窗口，依次类推。 但是，更简单的一种方法是使用预定义的“静态”窗口类创建窗口。 这将为你提供所需窗口步骤，以接收来自控件的通知，但需要完成最少的编码工作。  
  
 控件的 HWND 通过一个只读属性公开，以便宿主页面可使用它向控件发送消息。  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 ListBox 控件被创建为宿主窗口的子窗口。 两个窗口的高度和宽度被设置为传递给构造函数的值（前面已讨论）。 这可确保宿主窗口和控件的大小与页面上的保留区域相同。  在创建 windows 之后，则示例将返回<xref:System.Runtime.InteropServices.HandleRef>对象，其中包含主机窗口的 HWND。  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### <a name="implement-destroywindow-and-wndproc"></a>实现 DestroyWindow 和 WndProc  
 除了<xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>，还必须重写<xref:System.Windows.Interop.HwndHost.WndProc%2A>和<xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>方法<xref:System.Windows.Interop.HwndHost>。 在此示例中，该控件的消息都由处理<xref:System.Windows.Interop.HwndHost.MessageHook>处理程序，因此实现<xref:System.Windows.Interop.HwndHost.WndProc%2A>和<xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>很小。 情况下<xref:System.Windows.Interop.HwndHost.WndProc%2A>，将其设置`handled`到`false`以指示消息的处理了不并返回 0。 有关<xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>，只需销毁窗口。  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## <a name="host-the-control-on-the-page"></a>在页面上承载控件  
 若要托管页上的控件，你首先创建的新实例`ControlHost`类。 传递的高度和宽度的包含控件的边框元素 (`ControlHostElement`) 到`ControlHost`构造函数。 这可确保 ListBox 具有正确的大小。 然后通过分配托管页上的控件`ControlHost`对象传递给<xref:System.Windows.Controls.Decorator.Child%2A>宿主属性<xref:System.Windows.Controls.Border>。  
  
 此示例将附加的处理程序<xref:System.Windows.Interop.HwndHost.MessageHook>事件`ControlHost`从控件接收消息。 对于每条发送到宿主窗口的消息，都将引发此事件。 在这种情况下，这些消息是发送到包装实际 ListBox 控件的窗口的消息，其中包括来自控件的通知。 此示例将调用 SendMessage 以从控件获取信息并修改其内容。 下一节将详细介绍页面如何与控件通信。  
  
> [!NOTE]
>  请注意，有两个 SendMessage PInvoke 声明。 此操作，因为另一个使用`wParam`要传递一个字符串和其他参数使用它来将一个整数传递。 对于每个签名，都需要一个单独的声明，以确保正确封送数据。  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>在控件和页面之间的实现通信  
 通过将其发送 Windows 消息操作控件。 当用户与控件交互时，控件会通过向其宿主窗口发送通知来通知你。 [承载 WPF 中的 Win32 ListBox 控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)示例包含一个用户界面，提供了几个示例的原理：  
  
-   向列表中追加项。  
  
-   从列表中删除选定项  
  
-   显示当前选定项的文本。  
  
-   显示列表中的项数。  
  
 用户还可以选择某个项的列表框中通过单击它，就像常规的 Win32 应用程序。 每当用户通过选择、添加或追加项来更改列表框的状态时，都将更新所显示的数据。  
  
 要附加项，请发送列表框[`LB_ADDSTRING`消息](https://msdn.microsoft.com/library/windows/desktop/bb775181(v=vs.85).aspx)。 若要删除项，请将发送[ `LB_GETCURSEL` ](https://msdn.microsoft.com/library/windows/desktop/bb775197(v=vs.85).aspx)以获取当前所选内容的索引，然后[ `LB_DELETESTRING` ](https://msdn.microsoft.com/library/windows/desktop/bb775183(v=vs.85).aspx)删除项。 该示例还发送[ `LB_GETCOUNT` ](https://msdn.microsoft.com/library/windows/desktop/bb775195(v=vs.85).aspx)，并使用返回的值来更新显示来显示项的数目。 这两个这些实例[ `SendMessage` ](https://msdn.microsoft.com/library/windows/desktop/ms644950(v=vs.85).aspx)使用上一节中讨论的 PInvoke 声明之一。  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 当用户选择某一项或更改它们的选择时，控件通过将其发送通知宿主窗口[`WM_COMMAND`消息](https://msdn.microsoft.com/library/windows/desktop/ms647591(v=vs.85).aspx)，这会引发<xref:System.Windows.Interop.HwndHost.MessageHook>页的事件。 处理程序将接收到与宿主窗口的主窗口过程相同的信息。 它还将引用传递到一个布尔值， `handled`。 你设置`handled`到`true`以指示已处理消息并且需要不进行其他处理。  
  
 [`WM_COMMAND`](https://msdn.microsoft.com/library/windows/desktop/ms647591(v=vs.85).aspx) 各种不同的原因，以便你必须检查以确定它是否是你想要处理的事件的通知 ID 发送。 中的高位字包含 ID`wParam`参数。 此示例使用按位运算符来提取该 id。 如果用户已进行，或更改它们的选择，该 ID 将是[ `LBN_SELCHANGE` ](https://msdn.microsoft.com/library/windows/desktop/bb775161(v=vs.85).aspx)。  
  
 当[ `LBN_SELCHANGE` ](https://msdn.microsoft.com/library/windows/desktop/bb775161(v=vs.85).aspx)是收到，该示例通过发送控件中获取的选定项的索引[`LB_GETCURSEL`消息](https://msdn.microsoft.com/library/windows/desktop/bb775197(v=vs.85).aspx)。 若要获取文本，请先创建<xref:System.Text.StringBuilder>。 你之后要发送控件[`LB_GETTEXT`消息](https://msdn.microsoft.com/library/windows/desktop/bb761313(v=vs.85).aspx)。 传递空<xref:System.Text.StringBuilder>对象作为`wParam`参数。 当[ `SendMessage` ](https://msdn.microsoft.com/library/windows/desktop/ms644950(v=vs.85).aspx)返回时，<xref:System.Text.StringBuilder>将包含所选的项的文本。 这种用法[ `SendMessage` ](https://msdn.microsoft.com/library/windows/desktop/ms644950(v=vs.85).aspx)要求另一个 PInvoke 声明。  
  
 最后，设置`handled`到`true`以指示已处理该消息。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Interop.HwndHost>  
 [WPF 和 Win32 互操作](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [演练：我的第一个 WPF 桌面应用程序](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)
