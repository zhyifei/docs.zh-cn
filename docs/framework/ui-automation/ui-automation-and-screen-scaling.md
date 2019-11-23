---
title: UI 自动化和屏幕缩放
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scaling, screens
- screens, scaling
- UI (user interface), automation
- UI Automation
ms.assetid: 4380cad7-e509-448f-b9a5-6de042605fd4
ms.openlocfilehash: ceab7db1f9eeb47ec020e220ec702af8181855e2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442476"
---
# <a name="ui-automation-and-screen-scaling"></a>UI 自动化和屏幕缩放
> [!NOTE]
> 本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。  
  
Starting with Windows Vista, Windows enables users to change the dots per inch (dpi) setting so that most user interface (UI) elements on the screen appear larger. Although this feature has long been available in Windows, in previous versions the scaling had to be implemented by applications. Starting with Windows Vista, the Desktop Window Manager performs default scaling for all applications that do not handle their own scaling. UI 自动化客户端应用程序必须考虑到此功能。  
  
<a name="Scaling_in_Windows_Vista"></a>   
## <a name="scaling-in-windows-vista"></a>Windows Vista 中的缩放  
 The default dpi setting is 96, which means that 96 pixels occupy a width or height of one notional inch. “一英寸”的确切度量取决于监视器的大小和物理分辨率。 例如，在 12 英寸宽、水平分辨率为 1280 像素的监视器上，96 像素的水平线将扩展大约 9/10 英寸。  
  
 Changing the dpi setting is not the same as changing the screen resolution. With dpi scaling, the number of physical pixels on the screen remains the same. 但是，缩放将应用于 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 元素的大小和位置。 桌面窗口管理器 (DWM) 可以自动对桌面和未显式要求缩放的应用程序执行这种扩展。  
  
 In effect, when the user sets the scale factor to 120 dpi, a vertical or horizontal inch on the screen becomes bigger by 25 percent. 所有尺寸会相应缩放。 应用程序窗口距屏幕顶端和左边缘的偏移量将增大 25%。 If application scaling is enabled and the application is not dpi-aware, the size of the window increases in the same proportion, along with the offsets and sizes of all [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elements it contains.  
  
> [!NOTE]
> By default, the DWM does not perform scaling for non-dpi-aware applications when the user sets the dpi to 120, but does perform it when the dpi is set to a custom value of 144 or higher. 但是，用户可以重写默认行为。  
  
 屏幕缩放为以任何方式与屏幕坐标有关的应用程序带来了新的挑战。 屏幕现在包含两个坐标系：物理和逻辑。 点的物理坐标是距原点左上部的实际偏移量（以像素为单位）。 如果像素本身进行了缩放，则逻辑坐标为缩放后的偏移量。  
  
 假定你设计了一个对话框，其按钮位于坐标 (100, 48) 处。 When this dialog box is displayed at the default 96 dpi, the button is located at physical coordinates of (100, 48). At 120 dpi, it is located at physical coordinates of (125, 60). But the logical coordinates are the same at any dpi setting: (100, 48).  
  
 Logical coordinates are important, because they make the behavior of the operating system and applications consistent regardless of the dpi setting. 例如，正常情况下， <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> 将返回逻辑坐标。 If you move the cursor over an element in a dialog box, the same coordinates are returned regardless of the dpi setting. If you draw a control at (100, 100), it is drawn to those logical coordinates, and will occupy the same relative position at any dpi setting.  
  
<a name="Scaling_in_UI_Automation_Clients"></a>   
## <a name="scaling-in-ui-automation-clients"></a>UI 自动化客户端中的缩放  
 The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] API does not use logical coordinates. 下面的方法和属性将返回物理坐标或将其用作参数。  
  
- <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
- <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 By default, a UI Automation client application running in a non-96- dpi environment will not be able to obtain correct results from these methods and properties. 例如，由于光标的位置是逻辑坐标，客户端不能仅将这些坐标传递到 <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> 以获取光标下的元素。 此外，该应用程序不能正确将 Windows 放置在其客户端区域之外。  
  
 解决方法分两个部分。  
  
1. First, make the client application dpi-aware. 若要实现此目的，请在启动时调用 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] 函数 `SetProcessDPIAware` 。 在托管代码中，以下声明使得此函数可用。  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     This function makes the entire process dpi-aware, meaning that all windows that belong to the process are unscaled. In the [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter), for instance, the four windows that make up the highlight rectangle are located at the physical coordinates obtained from UI Automation, not the logical coordinates. If the sample were not dpi-aware, the highlight would be drawn at the logical coordinates on the desktop, which would result in incorrect placement in a non-96- dpi environment.  
  
2. 若要获取光标坐标，请调用 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] 函数 `GetPhysicalCursorPos`。 下面的示例演示如何声明和使用此函数。  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
> 请勿使用 <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>。 未定义此属性在扩展环境下客户端窗口以外的行为。  
  
 If your application performs direct cross-process communication with non- dpi-aware applications, you may have convert between logical and physical coordinates by using the [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] functions `PhysicalToLogicalPoint` and `LogicalToPhysicalPoint`.  
  
## <a name="see-also"></a>请参阅

- [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)
