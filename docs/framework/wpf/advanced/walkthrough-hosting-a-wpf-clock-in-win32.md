---
title: 演练：在 Win32 中承载 WPF 时钟
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 79f79e42652ca51c409fabb12a572485ad734b35
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744896"
---
# <a name="walkthrough-host-a-wpf-clock-in-win32"></a>演练：在 Win32 中承载 WPF 时钟

若要将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 放入 Win32 应用程序中，请使用 <xref:System.Windows.Interop.HwndSource>，它提供包含 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的 HWND。 首先创建 <xref:System.Windows.Interop.HwndSource>，并为其提供类似于 CreateWindow 的参数。 然后，告诉 <xref:System.Windows.Interop.HwndSource> 所需的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容。 最后，获取 <xref:System.Windows.Interop.HwndSource>中的 HWND。 本演练演示如何在重新实现 "操作系统**日期和时间属性**" 对话框的 Win32 应用程序中创建混合 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。

## <a name="prerequisites"></a>先决条件

请参阅[WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)。

## <a name="how-to-use-this-tutorial"></a>이 자습서의 사용 방법

이 자습서는 상호 운용 애플리케이션을 생성하는 중요한 단계에 대해 중점적으로 설명합니다. 本教程通过示例[Win32 时钟互操作示例](https://go.microsoft.com/fwlink/?LinkID=160051)进行了支持，但该示例反射了最终产品。 本教程介绍的步骤如下所示：从自己的现有 Win32 项目开始（可能是预先存在的项目），并向应用程序添加托管的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 可以将最终产品与[Win32 时钟互操作示例](https://go.microsoft.com/fwlink/?LinkID=160051)进行比较。

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Win32 내에서 Windows Presentation Framework의 연습(HwndSource)

다음 그래픽에서는 이 자습서의 의도된 최종 제품을 보여 줍니다.

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

接下来，添加对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]： PresentationCore、PresentationFramework、、WindowsBase、Uiautomationprovider.dll 和 Uiautomationtypes.dll 所需的 Dll 的引用。 다음 지침에서는 운영 체제가 C: 드라이브에 설치되어 있다고 가정합니다.

1. 右键单击 "win32clock 项目"，然后选择 "**引用 ...** "，然后在该对话框中执行以下操作：

2. 右键单击 "win32clock 项目"，然后选择 "**引用 ...** "。

3. 单击 "**添加新引用**"，单击 "浏览" 选项卡，输入 C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll，然后单击 "确定"。

4. PresentationFramework.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll)에 대해 반복합니다.

5. WindowsBase.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll)에 대해 반복합니다.

6. UIAutomationTypes.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll)에 대해 반복합니다.

7. UIAutomationProvider.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll)에 대해 반복합니다.

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

此属性告知公共语言运行时（CLR）当初始化组件对象模型（COM）时，它应使用单线程单元模型（STA），这是 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] （和 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]）所必需的。

## <a name="create-a-windows-presentation-framework-page"></a>Windows Presentation Framework 페이지 만들기

接下来，创建一个定义 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>的 DLL。 通常最简单的方法是将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> 创建为独立应用程序，并以这种方式编写和调试 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 部分。 完成后，可以通过右键单击项目，单击 "**属性**"，转到 "应用程序"，并将 "输出类型" 更改为 "Windows 类库"，将该项目转换为 DLL。

然后，可以将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll 项目与 Win32 项目（一个包含两个项目的解决方案）结合在一起-右键单击解决方案，选择 " **Add\Existing 项目**"。

若要从 Win32 项目使用该 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll，需要添加引用：

1. 右键单击 "win32clock 项目"，然后选择 "**引用 ...** "。

2. 单击 "**添加新引用**"。

3. 单击 "**项目**" 选项卡。选择 "WPFClock"，然后单击 "确定"。

4. 单击 **"确定"** 退出用于添加引用的 Win32clock 属性页。

## <a name="hwndsource"></a>HwndSource

接下来，使用 <xref:System.Windows.Interop.HwndSource> 使 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> 外观类似于 HWND。 다음 코드 블록을 C++ 파일에 추가합니다.

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

 다음은 약간의 설명이 필요할 수 있는 긴 코드 조각입니다. 첫 번째 부분은 다양한 절이어서 모든 호출을 정규화할 필요가 없습니다.

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

## <a name="positioning-the-hwnd"></a>Hwnd 위치 지정

现在，你已具有包含 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟的 HWND，你需要将该 HWND 置于 Win32 对话框内。 如果只知道放置 HWND 的位置，只需将该大小和位置传递到前面定义的 `GetHwnd` 函数。 그러나 리소스 파일을 사용하여 대화 상자를 정의했으므로 HWND를 배치할 위치를 정확하게 알 수 없습니다. 你可以使用 Visual Studio 对话框编辑器将 Win32 静态控件放置在希望时钟进入的位置（"在此处插入时钟"），并使用它来定位 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟。

在其中处理 WM_INITDIALOG 的情况下，使用 `GetDlgItem` 检索占位符 STATIC 的 HWND：

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

然后，计算占位符的大小和位置，以便在该位置放置 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟：

RECT 사각형의 경우입니다.

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

그런 다음 자리 표시자 STATIC을 숨깁니다.

```cpp
ShowWindow(placeholder, SW_HIDE);
```

并在该位置创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟 HWND：

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

为了使本教程有趣，并生成真正的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟，此时需要创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟控件。 코드 숨김에서 몇 개의 이벤트 처리기만 사용하여 태그에서 거의 모든 작업을 수행할 수 있습니다. 由于本教程介绍互操作性，而不是关于控件设计的，因此，此处提供了 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟的完整代码作为代码块提供，没有用于构建或每个部分所代表的单独说明。 이 코드를 자유롭게 사용하여 컨트롤의 모양과 느낌 또는 기능을 변경해 보세요.

다음은 태그입니다.

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

다음은 함께 제공되는 코드 숨김입니다.

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

최종 결과는 다음과 같습니다.

!["最终结果日期和时间属性" 对话框](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

若要将最终结果与生成此屏幕截图的代码进行比较，请参阅[Win32 时钟互操作示例](https://go.microsoft.com/fwlink/?LinkID=160051)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Interop.HwndSource>
- [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)
- [Win32 시계 상호 운용 샘플](https://go.microsoft.com/fwlink/?LinkID=160051)
