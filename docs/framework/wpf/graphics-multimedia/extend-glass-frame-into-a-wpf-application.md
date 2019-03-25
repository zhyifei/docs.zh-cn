---
title: 将玻璃框扩展到 WPF 应用程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], extending glass frames into
- graphics [WPF], extending glass frames into applications
- extending glass frames into applications [WPF]
- glass frames [WPF], extending into applications
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
ms.openlocfilehash: 8da1f49bf5b7d3daf6319906fb49390c008d209c
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412209"
---
# <a name="extend-glass-frame-into-a-wpf-application"></a><span data-ttu-id="e26df-102">将玻璃框扩展到 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="e26df-102">Extend Glass Frame Into a WPF Application</span></span>

<span data-ttu-id="e26df-103">本主题演示如何扩展[!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]到 Windows Presentation Foundation (WPF) 应用程序的客户端区域的玻璃框。</span><span class="sxs-lookup"><span data-stu-id="e26df-103">This topic demonstrates how to extend the [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] glass frame into the client area of a Windows Presentation Foundation (WPF) application.</span></span>

> [!NOTE]
> <span data-ttu-id="e26df-104">此示例仅在运行已启用玻璃效果的桌面窗口管理器 (DWM) 的 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] 计算机上才起作用。</span><span class="sxs-lookup"><span data-stu-id="e26df-104">This example will only work on a [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] machine running the Desktop Window Manager (DWM) with glass enabled.</span></span> [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] <span data-ttu-id="e26df-105">家庭普通版不支持透明玻璃效果。</span><span class="sxs-lookup"><span data-stu-id="e26df-105">Home Basic edition does not support the transparent glass effect.</span></span> <span data-ttu-id="e26df-106">在 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] 的其他版本上通常使用透明玻璃效果呈现的区域呈现为不透明。</span><span class="sxs-lookup"><span data-stu-id="e26df-106">Areas that would typically render with the transparent glass effect on other editions of [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] are rendered opaque.</span></span>

## <a name="example"></a><span data-ttu-id="e26df-107">示例</span><span class="sxs-lookup"><span data-stu-id="e26df-107">Example</span></span>

<span data-ttu-id="e26df-108">下图阐释了玻璃框扩展到地址栏的 Internet Explorer 7:</span><span class="sxs-lookup"><span data-stu-id="e26df-108">The following image illustrates the glass frame extended into the address bar of Internet Explorer 7:</span></span>

![扩展到 IE7 地址栏后的屏幕截图显示玻璃框。](./media/extend-glass-frame-into-a-wpf-application/internet-explorer-glass-frame-extended-address-bar.png)

<span data-ttu-id="e26df-110">若要在 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序上扩展玻璃框，需要访问非托管 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e26df-110">To extend the glass frame on a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application, access to unmanaged [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] is needed.</span></span> <span data-ttu-id="e26df-111">以下代码示例针对将框扩展到工作区所需的两个 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 执行平台调用 (pinvoke)。</span><span class="sxs-lookup"><span data-stu-id="e26df-111">The following code example does a Platform Invoke (pinvoke) for the two [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] needed to extend the frame into the client area.</span></span> <span data-ttu-id="e26df-112">其中每一个 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 都在名为 **NonClientRegionAPI** 的类中声明。</span><span class="sxs-lookup"><span data-stu-id="e26df-112">Each of these [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] are declared in a class called **NonClientRegionAPI**.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential)]
public struct MARGINS
{
    public int cxLeftWidth;      // width of left border that retains its size
    public int cxRightWidth;     // width of right border that retains its size
    public int cyTopHeight;      // height of top border that retains its size
    public int cyBottomHeight;   // height of bottom border that retains its size
};

[DllImport("DwmApi.dll")]
public static extern int DwmExtendFrameIntoClientArea(
    IntPtr hwnd,
    ref MARGINS pMarInset);
```

```vb
<StructLayout(LayoutKind.Sequential)>
Public Structure MARGINS
    Public cxLeftWidth As Integer ' width of left border that retains its size
    Public cxRightWidth As Integer ' width of right border that retains its size
    Public cyTopHeight As Integer ' height of top border that retains its size
    Public cyBottomHeight As Integer ' height of bottom border that retains its size
End Structure

<DllImport("DwmApi.dll")>
Public Shared Function DwmExtendFrameIntoClientArea(ByVal hwnd As IntPtr, ByRef pMarInset As MARGINS) As Integer
End Function
```

<span data-ttu-id="e26df-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) 是将框扩展到工作区的 DWM 函数。</span><span class="sxs-lookup"><span data-stu-id="e26df-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) is the DWM function that extends the frame into the client area.</span></span> <span data-ttu-id="e26df-114">它采用两个参数：一个窗口句柄和一个 [MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) 结构。</span><span class="sxs-lookup"><span data-stu-id="e26df-114">It takes two parameters; a window handle and a [MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) structure.</span></span> <span data-ttu-id="e26df-115">[MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) 用于告知 DWM 应向工作区扩展多少额外框。</span><span class="sxs-lookup"><span data-stu-id="e26df-115">[MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) is used to tell the DWM how much extra the frame should be extended into the client area.</span></span>

## <a name="example"></a><span data-ttu-id="e26df-116">示例</span><span class="sxs-lookup"><span data-stu-id="e26df-116">Example</span></span>

<span data-ttu-id="e26df-117">若要使用 [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) 函数，必须获取窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="e26df-117">To use the [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) function, a window handle must be obtained.</span></span> <span data-ttu-id="e26df-118">在中[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]，可以从获取窗口句柄<xref:System.Windows.Interop.HwndSource.Handle%2A>属性的<xref:System.Windows.Interop.HwndSource>。</span><span class="sxs-lookup"><span data-stu-id="e26df-118">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], the window handle can be obtained from the <xref:System.Windows.Interop.HwndSource.Handle%2A> property of an <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="e26df-119">在以下示例中，框扩展到工作区上<xref:System.Windows.FrameworkElement.Loaded>窗口的事件。</span><span class="sxs-lookup"><span data-stu-id="e26df-119">In the following example, the frame is extended into the client area on the <xref:System.Windows.FrameworkElement.Loaded> event of the window.</span></span>

```csharp
void OnLoaded(object sender, RoutedEventArgs e)
{
   try
   {
      // Obtain the window handle for WPF application
      IntPtr mainWindowPtr = new WindowInteropHelper(this).Handle;
      HwndSource mainWindowSrc = HwndSource.FromHwnd(mainWindowPtr);
      mainWindowSrc.CompositionTarget.BackgroundColor = Color.FromArgb(0, 0, 0, 0);

      // Get System Dpi
      System.Drawing.Graphics desktop = System.Drawing.Graphics.FromHwnd(mainWindowPtr);
      float DesktopDpiX = desktop.DpiX;
      float DesktopDpiY = desktop.DpiY;

      // Set Margins
      NonClientRegionAPI.MARGINS margins = new NonClientRegionAPI.MARGINS();

      // Extend glass frame into client area
      // Note that the default desktop Dpi is 96dpi. The  margins are
      // adjusted for the system Dpi.
      margins.cxLeftWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));
      margins.cxRightWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));
      margins.cyTopHeight = Convert.ToInt32(((int)topBar.ActualHeight + 5) * (DesktopDpiX / 96));
      margins.cyBottomHeight = Convert.ToInt32(5 * (DesktopDpiX / 96));

      int hr = NonClientRegionAPI.DwmExtendFrameIntoClientArea(mainWindowSrc.Handle, ref margins);
      //
      if (hr < 0)
      {
         //DwmExtendFrameIntoClientArea Failed
      }
   }
   // If not Vista, paint background white.
   catch (DllNotFoundException)
   {
      Application.Current.MainWindow.Background = Brushes.White;
   }
}
```

## <a name="example"></a><span data-ttu-id="e26df-120">示例</span><span class="sxs-lookup"><span data-stu-id="e26df-120">Example</span></span>

<span data-ttu-id="e26df-121">以下示例演示一个简单的窗口，在该窗口中框扩展到工作区。</span><span class="sxs-lookup"><span data-stu-id="e26df-121">The following example shows a simple window in which the frame is extended into the client area.</span></span> <span data-ttu-id="e26df-122">框扩展背后的上边框的包含两个<xref:System.Windows.Controls.TextBox>对象。</span><span class="sxs-lookup"><span data-stu-id="e26df-122">The frame is extended behind the top border that contains the two <xref:System.Windows.Controls.TextBox> objects.</span></span>

```xaml
<Window x:Class="SDKSample.Window1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    Title="Extended Glass in WPF" Height="300" Width="400"
    Loaded="OnLoaded" Background="Transparent"
    >
  <Grid ShowGridLines="True">
    <DockPanel Name="mainDock">
      <!-- The border is used to compute the rendered height with margins.
           topBar contents will be displayed on the extended glass frame.-->
      <Border Name="topBar" DockPanel.Dock="Top" >
        <Grid Name="grid">
          <Grid.ColumnDefinitions>
            <ColumnDefinition MinWidth="100" Width="*"/>
            <ColumnDefinition Width="Auto"/>
          </Grid.ColumnDefinitions>
          <TextBox Grid.Column="0" MinWidth="100" Margin="0,0,10,5">Path</TextBox>
          <TextBox Grid.Column="1" MinWidth="75" Margin="0,0,0,5">Search</TextBox>
        </Grid>
      </Border>
      <Grid DockPanel.Dock="Top" >
        <Grid.ColumnDefinitions>
          <ColumnDefinition/>
        </Grid.ColumnDefinitions>
        <TextBox Grid.Column="0" AcceptsReturn="True"/>
      </Grid>
    </DockPanel>
  </Grid>
</Window>
```

<span data-ttu-id="e26df-123">下图阐释了玻璃框扩展到[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]应用程序：</span><span class="sxs-lookup"><span data-stu-id="e26df-123">The following image illustrates the glass frame extended into a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application:</span></span>

![显示玻璃框扩展到 WPF 应用程序的屏幕截图。](./media/extend-glass-frame-into-a-wpf-application/glass-frame-extended-wpf-application.png)

## <a name="see-also"></a><span data-ttu-id="e26df-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="e26df-125">See also</span></span>

- [<span data-ttu-id="e26df-126">桌面窗口管理器概述</span><span class="sxs-lookup"><span data-stu-id="e26df-126">Desktop Window Manager Overview</span></span>](/windows/desktop/dwm/dwm-overview)
- [<span data-ttu-id="e26df-127">桌面窗口管理器模糊概述</span><span class="sxs-lookup"><span data-stu-id="e26df-127">Desktop Window Manager Blur Overview</span></span>](/windows/desktop/dwm/blur-ovw)
- [<span data-ttu-id="e26df-128">DwmExtendFrameIntoClientArea</span><span class="sxs-lookup"><span data-stu-id="e26df-128">DwmExtendFrameIntoClientArea</span></span>](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)
