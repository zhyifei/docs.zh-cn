---
title: WPF 和 Windows 窗体互通
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 76d1e97c92946267aa1217f52c93594fb63d20de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187153"
---
# <a name="wpf-and-windows-forms-interoperation"></a>WPF 和 Windows 窗体互操作
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Windows 窗体提供了两种不同的体系结构来创建应用程序接口。 命名<xref:System.Windows.Forms.Integration?displayProperty=nameWithType>空间提供启用常见互操作方案的类。 实现互操作功能的两个关键类是<xref:System.Windows.Forms.Integration.WindowsFormsHost>和<xref:System.Windows.Forms.Integration.ElementHost>。 本主题介绍支持哪些互操作方案以及不支持哪些互操作方案。  
  
> [!NOTE]
> 关于*混合控件*方案，需要考虑一些特殊因素。 混合控件将一种技术中的控件嵌套于另一种技术中的控件。 这也称为*嵌套互操作*。 *多级混合控件*具有多个级别的混合控件嵌套。 多级嵌套互操作的示例是包含控件的 Windows 窗体控件，该控件包含[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]另一个 Windows 窗体控件。 不支持多级混合控件。  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>
## <a name="hosting-windows-forms-controls-in-wpf"></a>在 WPF 中承载 Windows 窗体控件  
 当控件承载 Windows 窗体控件时，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]支持以下操作间方案：  
  
- 该[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件可以使用 XAML 承载一个或多个 Windows 窗体控件。  
  
- 它可以使用代码承载一个或多个 Windows 窗体控件。  
  
- 它可以承载包含其他 Windows 窗体控件的 Windows 窗体容器控件。  
  
- 它可以承载主/详细信息的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]母版/详细信息。  
  
- 它可以承载具有 Windows 窗体主窗体和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]详细信息的主/详细信息窗体。  
  
- 它可以承载一个或多个 ActiveX 控件。  
  
- 它可以承载一个或多个复合控件。  
  
- 它可以使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 承载混合控件。  
  
- 它可以使用代码承载混合控件。  
  
### <a name="layout-support"></a>布局支持  
 以下列表描述<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素尝试将其托管 Windows 窗体控件集成到布局系统中时的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]已知限制。  
  
- 在某些情况下，Windows 窗体控件无法调整大小，或者只能调整到特定维度的大小。 例如，Windows 窗体<xref:System.Windows.Forms.ComboBox>控件仅支持单个高度，该高度由控件的字体大小定义。 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]动态布局中，假定元素可以垂直拉伸，托管<xref:System.Windows.Forms.ComboBox>控件不会按预期拉伸。  
  
- 无法旋转或倾斜 Windows 窗体控件。 例如，当您将用户界面旋转 90 度时，托管 Windows 窗体控件将保持其直立位置。  
  
- 在大多数情况下，Windows 窗体控件不支持比例缩放。 尽管该控件的整体尺寸将会缩放，但其子控件和组件元素可能不会按预期调整大小。 此限制取决于每个 Windows 窗体控件支持缩放的功能。  
  
- 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 用户界面中，可以更改元素的 z 顺序以控制重叠行为。 托管 Windows 窗体控件在单独的 HWND 中绘制，因此始终在元素上[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]绘制。  
  
- Windows 窗体控件支持根据字体大小进行自动缩放。 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 用户界面中，更改字号不会改变整个布局的大小，但是可动态调整单个元素的大小。  
  
### <a name="ambient-properties"></a>环境属性  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件的某些环境属性具有等效的 Windows 窗体。 这些环境属性传播到托管的 Windows 窗体控件，并作为控件上的<xref:System.Windows.Forms.Integration.WindowsFormsHost>公共属性公开。 该<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件将每个[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]环境属性转换为其 Windows 窗体等效项。  
  
 有关详细信息，请参阅 [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)。  
  
### <a name="behavior"></a>行为  
 下表介绍互操作行为。  
  
|行为|支持|不支持|  
|--------------|---------------|-------------------|  
|透明度|Windows 窗体控件呈现支持透明度。 父[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件的背景可以成为托管 Windows 窗体控件的背景。|某些 Windows 窗体控件不支持透明度。 例如，在<xref:System.Windows.Forms.TextBox>托管<xref:System.Windows.Forms.ComboBox>时， 和 控件将[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]不透明。|  
|Tab 键次序|托管 Windows 窗体控件的选项卡顺序与这些控件在基于 Windows 窗体的应用程序中托管时相同。<br /><br /> 使用 TAB[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]键和 SHIFT_TAB 键从控件到 Windows 窗体控件的 Tab 工作正常。<br /><br /> 当用户通过控件选项卡时，<xref:System.Windows.Forms.Control.TabStop%2A>具有 属性`false`值的 Windows 窗体控件不会接收焦点。<br /><br /> -<xref:System.Windows.Forms.Integration.WindowsFormsHost>每个控件都有<xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>一个值，该值<xref:System.Windows.Forms.Integration.WindowsFormsHost>确定该控件何时接收焦点。<br />- 包含在容器中的<xref:System.Windows.Forms.Integration.WindowsFormsHost>Windows 窗体控件遵循<xref:System.Windows.Forms.Control.TabIndex%2A>属性指定的顺序。 从最后一个 Tab 键索引使用 Tab 键切换会将焦点置于下一个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件上（若存在）。 如果没有其他可[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]聚焦控件，选项卡将返回到选项卡顺序中的第一个 Windows 窗体控件。<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>中控件的值<xref:System.Windows.Forms.Integration.WindowsFormsHost>与<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件中包含的同级 Windows 窗体控件相关。<br />-    按 Tab 键遵循特定于控件的行为。 例如，按<xref:System.Windows.Forms.TextBox>控件中的 TAB 键，该<xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A>控件的属性值为`true`"在文本框中输入选项卡，而不是移动焦点。|不适用。|  
|使用箭头键导航|-<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件中带有箭头键的导航与普通 Windows 窗体容器控件中的导航相同：向上箭头和左箭头键选择上一个控件，向下箭头和右箭头键选择下一个控件。<br />-<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件中包含的第一个控件的上箭头和 LEFT ARROW 键执行与 SHIFT_TAB 键盘快捷方式相同的操作。 如果存在可[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]聚焦控件，则焦点将移出<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件。 此行为不同于标准<xref:System.Windows.Forms.ContainerControl>行为，因为不会发生对最后一个控件的换行。 如果没有其他可[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]聚焦控件，则焦点将返回到选项卡顺序中的最后一个 Windows 窗体控件。<br />-<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件中包含的最后一个控件的向下箭头和右箭头键执行与 TAB 键相同的操作。 如果存在可[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]聚焦控件，则焦点将移出<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件。 此行为不同于标准<xref:System.Windows.Forms.ContainerControl>行为，因为未对第一个控件进行换行。 如果没有其他可[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]聚焦控件，则焦点将返回到选项卡顺序中的第一个 Windows 窗体控件。|不适用。|  
|加速键|加速键按常规方式工作，但“不支持”列中注明的情况除外。|跨多种技术的重复加速键与普通重复加速键的工作方式不同。 当跨技术复制加速器时，Windows 窗体控件中至少有一个，另一个[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]在控件上，Windows 窗体控件始终接收加速器。 当按重复加速键时，焦点不会在控件之间切换。|  
|快捷键|快捷键按常规方式工作，但“不支持”列中注明的情况除外。|- 在预处理阶段处理的 Windows 窗体快捷键始终优先于[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]快捷键。 例如，如果您有一个<xref:System.Windows.Forms.ToolStrip>定义了 CTRL_S 快捷键的控件，并且有一个[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]绑定到 CTRL_S 的命令<xref:System.Windows.Forms.ToolStrip>，则无论焦点如何，始终首先调用控件处理程序。<br />- 事件处理的<xref:System.Windows.Forms.Control.KeyDown>Windows 窗体快捷键在 中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]最后处理。 您可以通过重写 Windows 窗体控件<xref:System.Windows.Forms.Control.IsInputKey%2A>的方法或处理<xref:System.Windows.Forms.Control.PreviewKeyDown>事件来防止此行为。 从`true`<xref:System.Windows.Forms.Control.IsInputKey%2A>方法返回，或在<xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType>`true`<xref:System.Windows.Forms.Control.PreviewKeyDown>事件处理程序中将属性的值设置为。|  
|AcceptsReturn、AcceptsTab 以及其他特定于控件的行为|更改默认键盘行为的属性照常工作，假定 Windows 窗体控件重写要返回<xref:System.Windows.Forms.Control.IsInputKey%2A>`true`的方法。|Windows 窗体控件通过处理<xref:System.Windows.Forms.Control.KeyDown>事件更改默认键盘行为，最后在主机[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件中处理。 因为最后处理这些控件，所以它们可能产生意外行为。|  
|Enter 和 Leave 事件|当焦点不进入包含<xref:System.Windows.Forms.Integration.ElementHost>控件时，当焦点在单个<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件中更改时，将像往常一样引发 Enter 和 Leave 事件。|发生以下焦点更改时，不会引发 Enter 和 Leave 事件：<br /><br /> - 从内部到控制<xref:System.Windows.Forms.Integration.WindowsFormsHost>外部。<br />- 从外部到<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件内部。<br />- 在<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件之外<br />- 从托管在控件中的 Windows<xref:System.Windows.Forms.Integration.WindowsFormsHost>窗体控件<xref:System.Windows.Forms.Integration.ElementHost>到托管在同<xref:System.Windows.Forms.Integration.WindowsFormsHost>一控件中的控件。|  
|多线程处理|支持所有类型的多线程处理。|Windows 窗体[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和技术都假定为单线程并发模型。 调试期间，从其他线程调用框架对象会引发一个异常，以强制实施此要求。|  
|安全性|所有互操作方案都需要完全信任。|部分信任情况下，不允许任何互操作方案。|  
|可访问性|支持所有辅助功能方案。 辅助技术产品用于包含 Windows 窗体和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件的混合应用程序时，它们能够正常工作。|不适用。|  
|剪贴板|所有剪贴板操作按常规方式工作。 这包括在 Windows 窗体和控件之间进行剪切[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和粘贴。|不适用。|  
|拖放功能|所有拖放操作按常规方式工作。 这包括 Windows 窗体和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件之间的操作。|不适用。|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>
## <a name="hosting-wpf-controls-in-windows-forms"></a>在 Windows 窗体中承载 WPF 控件  
 当 Windows 窗体控件承载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件时，支持以下操作间方案：  
  
- 使用代码承载一个或多个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件。  
  
- 将属性表与一个或多个承载的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件关联。  
  
- 在窗体中承载一个或多个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页。  
  
- 启动 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 窗口。  
  
- 使用 Windows 窗体主窗体和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]详细信息托管主/详细信息窗体。  
  
- 使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]主窗体和 Windows 窗体详细信息托管主/详细信息窗体。  
  
- 承载自定义 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件。  
  
- 承载混合控件。  
  
### <a name="ambient-properties"></a>环境属性  
 Windows 窗体控件的某些环境属性具有[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]等效项。 这些环境属性传播到托管[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件，并作为控件上的<xref:System.Windows.Forms.Integration.ElementHost>公共属性公开。 该<xref:System.Windows.Forms.Integration.ElementHost>控件将每个 Windows 窗体环境属性转换为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]等效属性。  
  
 有关详细信息，请参阅 [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)。  
  
### <a name="behavior"></a>行为  
 下表介绍互操作行为。  
  
|行为|支持|不支持|  
|--------------|---------------|-------------------|  
|透明度|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件呈现支持透明度。 父 Windows 窗体控件的背景可以成为托管[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件的背景。|不适用。|  
|多线程处理|支持所有类型的多线程处理。|Windows 窗体[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和技术都假定为单线程并发模型。 调试期间，从其他线程调用框架对象会引发一个异常，以强制实施此要求。|  
|安全性|所有互操作方案都需要完全信任。|部分信任情况下，不允许任何互操作方案。|  
|可访问性|支持所有辅助功能方案。 辅助技术产品用于包含 Windows 窗体和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件的混合应用程序时，它们能够正常工作。|不适用。|  
|剪贴板|所有剪贴板操作按常规方式工作。 这包括在 Windows 窗体和控件之间进行剪切[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和粘贴。|不适用。|  
|拖放功能|所有拖放操作按常规方式工作。 这包括 Windows 窗体和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件之间的操作。|不适用。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [演练：在 WPF 中承载 Windows 窗体控件](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [演练：在 WPF 中承载 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)
