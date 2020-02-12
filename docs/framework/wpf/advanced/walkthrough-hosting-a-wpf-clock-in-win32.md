---
title: 演练：在 Win32 中承载 WPF 时钟
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 0aecde96d182e12ab72b1a6cba129ab1d8a28391
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123774"
---
# <a name="walkthrough-host-a-wpf-clock-in-win32"></a>演练：在 Win32 中承载 WPF 时钟

若要将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 放入 Win32 应用程序中，请使用 <xref:System.Windows.Interop.HwndSource>，它提供包含 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的 HWND。 首先创建 <xref:System.Windows.Interop.HwndSource>，并为其提供类似于 CreateWindow 的参数。 然后，告诉 <xref:System.Windows.Interop.HwndSource> 所需的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容。 最后，获取 <xref:System.Windows.Interop.HwndSource>中的 HWND。 本演练演示如何在重新实现 "操作系统**日期和时间属性**" 对话框的 Win32 应用程序中创建混合 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。

## <a name="prerequisites"></a>先决条件

请参阅[WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)。

## <a name="how-to-use-this-tutorial"></a>如何使用本教程

本教程重点介绍生成互操作应用程序的重要步骤。 本教程通过示例[Win32 时钟互操作示例](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)进行了支持，但该示例反射了最终产品。 本教程介绍的步骤如下所示：从自己的现有 Win32 项目开始（可能是预先存在的项目），并向应用程序添加托管的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 可以将最终产品与[Win32 时钟互操作示例](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)进行比较。

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Win32 中的 Windows Presentation Framework 的演练 (HwndSource)

下图显示了本教程的预期最终产品：

![显示 "日期和时间属性" 对话框的屏幕截图。](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

可以通过在 Visual Studio 中创建C++ Win32 项目，并使用对话框编辑器创建以下内容来重新创建此对话框：

!["重新创建日期和时间属性" 对话框](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

（您无需使用 Visual Studio 就 <xref:System.Windows.Interop.HwndSource>，也不需要使用C++编写 Win32 程序，但这是执行此操作的一种相当典型的方法，并且非常适合逐步教程说明）。

需要完成五个特定的子步骤，才能将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟添加到对话框中：

1. 通过在 Visual Studio 中更改项目设置，使 Win32 项目可以调用托管代码（ **/clr**）。

2. 在单独的 DLL 中创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>。

3. 将该 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> 置于 <xref:System.Windows.Interop.HwndSource>内。

4. 使用 <xref:System.Windows.Interop.HwndSource.Handle%2A> 属性获取该 <xref:System.Windows.Controls.Page> 的 HWND。

5. 使用 Win32 确定在较大的 Win32 应用程序中放置 HWND 的位置

## <a name="clr"></a>/clr

第一步是将此非托管 Win32 项目转换为可以调用托管代码的项目。 使用/clr 编译器选项，它将链接到要使用的必要 Dll，并调整 Main 方法以便与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]一起使用。

若要允许在C++项目中使用托管代码：右键单击 "win32clock 项目"，然后选择 "**属性**"。 在 "**常规**" 属性页（默认值）上，将 "公共语言运行时支持" 更改为 `/clr`。

接下来，添加对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]： PresentationCore、PresentationFramework、、WindowsBase、Uiautomationprovider.dll 和 Uiautomationtypes.dll 所需的 Dll 的引用。 （以下说明假定操作系统安装在 C: 驱动器上。）

1. 右键单击 "win32clock 项目"，然后选择 "**引用 ...** "，然后在该对话框中执行以下操作：

2. 右键单击 "win32clock 项目"，然后选择 "**引用 ...** "。

3. 单击 "**添加新引用**"，单击 "浏览" 选项卡，输入 C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll，然后单击 "确定"。

4. 对 PresentationFramework.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll。

5. 对 WindowsBase.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll。

6. 对 UIAutomationTypes.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll。

7. 对 UIAutomationProvider.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll。

8. 单击 "**添加新引用**"，选择 "系统"，然后单击 **"确定"** 。

9. 单击 **"确定"** 退出用于添加引用的 Win32clock 属性页。

 最后，将 `STAThreadAttribute` 添加到 `_tWinMain` 方法以便与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]一起使用：

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

此属性告知公共语言运行时（CLR）当初始化组件对象模型（COM）时，它应使用单线程单元模型（STA），这是 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] （和 Windows 窗体）所必需的。

## <a name="create-a-windows-presentation-framework-page"></a>创建 Windows Presentation Framework 页

接下来，创建一个定义 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>的 DLL。 通常最简单的方法是将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> 创建为独立应用程序，并以这种方式编写和调试 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 部分。 完成后，可以通过右键单击项目，单击 "**属性**"，转到 "应用程序"，并将 "输出类型" 更改为 "Windows 类库"，将该项目转换为 DLL。

然后，可以将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll 项目与 Win32 项目（一个包含两个项目的解决方案）结合在一起-右键单击解决方案，选择 " **Add\Existing 项目**"。

若要从 Win32 项目使用该 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll，需要添加引用：

1. 右键单击 "win32clock 项目"，然后选择 "**引用 ...** "。

2. 单击 "**添加新引用**"。

3. 单击 "**项目**" 选项卡。选择 "WPFClock"，然后单击 "确定"。

4. 单击 **"确定"** 退出用于添加引用的 Win32clock 属性页。

## <a name="hwndsource"></a>HwndSource

接下来，使用 <xref:System.Windows.Interop.HwndSource> 使 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> 外观类似于 HWND。 将此代码块添加到 C++ 文件中：

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;

    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
        HwndSource^ source = gcnew HwndSource(
            0, // class style
            WS_VISIBLE | WS_CHILD, // style
            0, // exstyle
            x, y, width, height,
            "hi", // NAME
            IntPtr(parent)        // parent window
            );

        UIElement^ page = gcnew WPFClock::Clock();
        source->RootVisual = page;
        return (HWND) source->Handle.ToPointer();
    }
}
}
```

 这是一长段代码，可以作一些解释。 第一部分是各种子句，无需完全限定所有调用：

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 然后定义一个函数，该函数创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容，在其周围放置 <xref:System.Windows.Interop.HwndSource> 并返回 HWND：

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

首先创建一个 <xref:System.Windows.Interop.HwndSource>，其参数与 CreateWindow 类似：

```cpp
HwndSource^ source = gcnew HwndSource(
    0, // class style
    WS_VISIBLE | WS_CHILD, // style
    0, // exstyle
    x, y, width, height,
    "hi", // NAME
    IntPtr(parent) // parent window
);
```

然后通过调用其构造函数创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类：

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

然后，将该页连接到 <xref:System.Windows.Interop.HwndSource>：

```cpp
source->RootVisual = page;
```

 在最后一行中，返回 <xref:System.Windows.Interop.HwndSource>的 HWND：

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a>放置 Hwnd

现在，你已具有包含 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟的 HWND，你需要将该 HWND 置于 Win32 对话框内。 如果只知道放置 HWND 的位置，只需将该大小和位置传递到前面定义的 `GetHwnd` 函数。 但是，由于已使用资源文件来定义对话框，因此你不完全确定任何 HWND 的放置位置。 你可以使用 Visual Studio 对话框编辑器将 Win32 静态控件放置在希望时钟进入的位置（"在此处插入时钟"），并使用它来定位 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟。

在其中处理 WM_INITDIALOG 的情况下，使用 `GetDlgItem` 检索占位符 STATIC 的 HWND：

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

然后，计算占位符的大小和位置，以便在该位置放置 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟：

RECT 矩形；

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

然后，你隐藏占位符 STATIC：

```cpp
ShowWindow(placeholder, SW_HIDE);
```

并在该位置创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟 HWND：

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

为了使本教程有趣，并生成真正的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟，此时需要创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟控件。 你可以在标记中执行大部分操作，代码隐藏中只有几个事件处理程序。 由于本教程介绍互操作性，而不是关于控件设计的，因此，此处提供了 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟的完整代码作为代码块提供，没有用于构建或每个部分所代表的单独说明。 随意尝试此代码来更改控件的外观或功能。

此处为标记：

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

以下是附带的代码隐藏：

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

最终结果如下所示：

!["最终结果日期和时间属性" 对话框](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

若要将最终结果与生成此屏幕截图的代码进行比较，请参阅[Win32 时钟互操作示例](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Interop.HwndSource>
- [WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)
- [Win32 时钟互操作示例](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)
