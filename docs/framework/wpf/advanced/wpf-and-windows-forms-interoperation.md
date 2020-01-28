---
title: WPF 和 Windows 窗体互操作
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 2dc2ea10ce8f723a0ee34c4774253e1357ba6afa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735116"
---
# <a name="wpf-and-windows-forms-interoperation"></a>WPF 和 Windows 窗体互操作
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 提供两种用于创建应用程序接口的不同体系结构。 <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> 命名空间提供用于启用常见互操作方案的类。 实现互操作功能的两个关键类 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 和 <xref:System.Windows.Forms.Integration.ElementHost>。 本主题介绍支持哪些互操作方案以及不支持哪些互操作方案。  
  
> [!NOTE]
> 关于*混合控件*方案，需要考虑一些特殊因素。 混合控件将一种技术中的控件嵌套于另一种技术中的控件。 这也称为*嵌套互操作*。 *多级混合控件*具有多个级别的混合控件嵌套。 多级嵌套互操作的一个示例是包含 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件，前者又包含另一个 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。 不支持多级混合控件。  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>   
## <a name="hosting-windows-forms-controls-in-wpf"></a>在 WPF 中承载 Windows 窗体控件  
 当 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件承载 Windows 窗体控件时，支持以下互操作方案：  
  
- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件可以使用 XAML 承载一个或多个 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。  
  
- 它可以使用代码承载一个或多个 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。  
  
- 它可以承载包含其他 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 容器控件。  
  
- 它可以承载具有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 母版和 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 详细信息的母版/详细信息窗体。  
  
- 它可以承载具有 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 母版和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 详细信息的母版/详细信息窗体。  
  
- 它可以承载一个或多个 ActiveX 控件。  
  
- 它可以承载一个或多个复合控件。  
  
- 它可以使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 承载混合控件。  
  
- 它可以使用代码承载混合控件。  
  
### <a name="layout-support"></a>布局支持  
 下面的列表介绍 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素尝试将其承载的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件集成到 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 布局系统时的已知限制。  
  
- 某些情况下，不能调整 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件的大小，或者大小只能调整为特定尺寸。 例如，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> 控件仅支持一个高度，该高度由控件的字号定义。 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的动态布局中（假定元素可垂直拉伸），承载的 <xref:System.Windows.Forms.ComboBox> 控件不会按预期拉伸。  
  
- 不能旋转或扭曲 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。 例如，将用户界面旋转 90 度时，所承载的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件将保持其垂直位置。  
  
- 大多数情况下，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件不支持按比例缩放。 尽管该控件的整体尺寸将会缩放，但其子控件和组件元素可能不会按预期调整大小。 此限制取决于每个 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件支持缩放的程度。  
  
- 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 用户界面中，可以更改元素的 z 顺序以控制重叠行为。 由于承载的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件是在单独的 HWND 中绘制的，所以始终在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素之上绘制它。  
  
- [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件支持基于字号的自动缩放。 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 用户界面中，更改字号不会改变整个布局的大小，但是可动态调整单个元素的大小。  
  
### <a name="ambient-properties"></a>环境属性  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件的某些环境属性具有 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 等效项。 这些环境属性传播到寄宿 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件，并作为 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件上的公共属性公开。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件将每个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 环境属性转换为其等效的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。  
  
 有关详细信息，请参阅 [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)。  
  
### <a name="behavior"></a>行为  
 下表介绍互操作行为。  
  
|行为|支持|不支持|  
|--------------|---------------|-------------------|  
|透明度|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件呈现支持透明度。 父 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件的背景可以成为所承载的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件的背景。|某些 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件不支持透明度。 例如，当通过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]承载时，<xref:System.Windows.Forms.TextBox> 和 <xref:System.Windows.Forms.ComboBox> 控件将不透明。|  
|Tab 键次序|所承载的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件的 Tab 键顺序与这些控件承载于基于 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 的应用程序中时是相同的。<br /><br /> 使用 Tab 键和 Shift+Tab 键从 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件切换到 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件将按常规方式工作。<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 具有 <xref:System.Windows.Forms.Control.TabStop%2A> 属性值 `false` 的控件在用户通过控件 tab 键时不会获得焦点。<br /><br /> -每个 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件都有一个 <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> 值，该值确定 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件将接收焦点的时间。<br />-   包含在 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 容器中 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件的顺序遵循 <xref:System.Windows.Forms.Control.TabIndex%2A> 属性指定的顺序。 从最后一个 Tab 键索引使用 Tab 键切换会将焦点置于下一个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件上（若存在）。 如果不存在其他可聚焦的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件，按 Tab 键将返回到 Tab 键顺序中的第一个 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。<br /><xref:System.Windows.Forms.Integration.WindowsFormsHost> 内控件 <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> 的 -   值相对于 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件中包含的同级 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。<br />-    按 Tab 键遵循特定于控件的行为。 例如，在 <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> 属性值为 `true` 的 <xref:System.Windows.Forms.TextBox> 控件中按 TAB 键会在文本框中输入一个选项卡，而不是移动焦点。|不适用。|  
|使用箭头键导航|-在 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件中使用箭头键进行导航与在普通的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 容器控件中相同：向上键和向左键选择上一个控件，向下键和向右键选择下一个控件。<br />-<xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件中包含的第一个控件的向上键和向左键将执行与 SHIFT + TAB 键盘快捷方式相同的操作。 如果有可获得焦点的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件，焦点将移到 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件之外。 此行为与标准 <xref:System.Windows.Forms.ContainerControl> 行为的不同之处在于，不会换行到最后一个控件。 如果不存在其他可聚焦的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件，焦点将返回到 Tab 键顺序中的最后一个 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。<br />-包含在 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件中的最后一个控件的向下箭头和向右箭头键执行的操作与 TAB 键相同。 如果有可获得焦点的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件，焦点将移到 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件之外。 此行为与标准 <xref:System.Windows.Forms.ContainerControl> 行为的不同之处在于，不会换行到第一个控件。 如果不存在其他可聚焦的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件，焦点将返回到 Tab 键顺序中的第一个 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。|不适用。|  
|加速键|加速键按常规方式工作，但“不支持”列中注明的情况除外。|跨多种技术的重复加速键与普通重复加速键的工作方式不同。 如果加速键跨多种技术复制，并且至少一个在 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件上，另一个在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件上，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件将始终收到此加速键。 当按重复加速键时，焦点不会在控件之间切换。|  
|快捷键|快捷键按常规方式工作，但“不支持”列中注明的情况除外。|在预处理阶段处理的 -   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 快捷键总是优先于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 快捷键。 例如，如果你有一个定义了 CTRL + S 快捷键的 <xref:System.Windows.Forms.ToolStrip> 控件，并且有一个绑定到 CTRL + S 的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 命令，则始终首先调用 <xref:System.Windows.Forms.ToolStrip> 控件处理程序，而不考虑焦点。<br />[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中最后处理 <xref:System.Windows.Forms.Control.KeyDown> 事件处理 -   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 快捷键。 可以通过重写 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件的 <xref:System.Windows.Forms.Control.IsInputKey%2A> 方法或处理 <xref:System.Windows.Forms.Control.PreviewKeyDown> 事件来防止此行为。 从 <xref:System.Windows.Forms.Control.IsInputKey%2A> 方法返回 `true`，或将 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> 属性的值设置为 <xref:System.Windows.Forms.Control.PreviewKeyDown> 事件处理程序中的 `true`。|  
|AcceptsReturn、AcceptsTab 以及其他特定于控件的行为|更改默认键盘行为的属性会像往常一样工作，假定 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件重写 <xref:System.Windows.Forms.Control.IsInputKey%2A> 方法以返回 `true`。|通过处理 <xref:System.Windows.Forms.Control.KeyDown> 事件来更改默认键盘行为 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件在主机 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件中最后处理。 因为最后处理这些控件，所以它们可能产生意外行为。|  
|Enter 和 Leave 事件|当焦点不转到包含 <xref:System.Windows.Forms.Integration.ElementHost> 控件时，在单个 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件中焦点更改时，Enter 和 Leave 事件会照常引发。|发生以下焦点更改时，不会引发 Enter 和 Leave 事件：<br /><br /> -从内部到 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件外。<br />-从外部到 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件。<br />-<xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件外。<br />-从 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件中承载的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件到托管在同一 <xref:System.Windows.Forms.Integration.WindowsFormsHost>中的 <xref:System.Windows.Forms.Integration.ElementHost> 控件。|  
|多线程|支持所有类型的多线程处理。|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 技术均采用单线程并发模型。 调试期间，从其他线程调用框架对象会引发一个异常，以强制实施此要求。|  
|安全性|所有互操作方案都需要完全信任。|部分信任情况下，不允许任何互操作方案。|  
|可访问性|支持所有辅助功能方案。 当辅助技术产品用于同时包含 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件的混合应用程序时，可正常工作。|不适用。|  
|剪贴板|所有剪贴板操作按常规方式工作。 这包括 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件之间的剪切和粘贴。|不适用。|  
|拖放功能|所有拖放操作按常规方式工作。 这包括 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件之间的操作。|不适用。|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>   
## <a name="hosting-wpf-controls-in-windows-forms"></a>在 Windows 窗体中承载 WPF 控件  
 当 Windows 窗体控件承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件时，支持以下互操作方案：  
  
- 使用代码承载一个或多个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件。  
  
- 将属性表与一个或多个承载的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件关联。  
  
- 在窗体中承载一个或多个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页。  
  
- 启动 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 窗口。  
  
- 承载具有 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 母版和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 详细信息的母版/详细信息窗体。  
  
- 承载具有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 母版和 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 详细信息的母版/详细信息窗体。  
  
- 承载自定义 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件。  
  
- 承载混合控件。  
  
### <a name="ambient-properties"></a>环境属性  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件的某些环境属性具有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 等效项。 这些环境属性传播到寄宿 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件，并作为 <xref:System.Windows.Forms.Integration.ElementHost> 控件上的公共属性公开。 <xref:System.Windows.Forms.Integration.ElementHost> 控件将每个 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 环境属性转换为其 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 等效的。  
  
 有关详细信息，请参阅 [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)。  
  
### <a name="behavior"></a>行为  
 下表介绍互操作行为。  
  
|行为|支持|不支持|  
|--------------|---------------|-------------------|  
|透明度|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件呈现支持透明度。 父 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件的背景可以成为所承载的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件的背景。|不适用。|  
|多线程|支持所有类型的多线程处理。|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 技术均采用单线程并发模型。 调试期间，从其他线程调用框架对象会引发一个异常，以强制实施此要求。|  
|安全性|所有互操作方案都需要完全信任。|部分信任情况下，不允许任何互操作方案。|  
|可访问性|支持所有辅助功能方案。 当辅助技术产品用于同时包含 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件的混合应用程序时，可正常工作。|不适用。|  
|剪贴板|所有剪贴板操作按常规方式工作。 这包括 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件之间的剪切和粘贴。|不适用。|  
|拖放功能|所有拖放操作按常规方式工作。 这包括 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件之间的操作。|不适用。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [演练：在 WPF 中承载 Windows 窗体控件](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [演练：在 WPF 中托管 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)
