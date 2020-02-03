---
title: ToolStrip 控件概述
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 931a6a0ea09f9b684b793c05cb1c3db8ee8fb7c7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741073"
---
# <a name="toolstrip-control-overview-windows-forms"></a>ToolStrip 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.ToolStrip> 控件及其关联的类提供一个公共框架，用于将用户界面元素合并到工具栏、状态栏和菜单中。 <xref:System.Windows.Forms.ToolStrip> 控件提供丰富的设计时体验，其中包括就地激活和编辑、自定义布局和漂浮（这是工具栏共享水平或垂直空间的能力）。  
  
 尽管 <xref:System.Windows.Forms.ToolStrip> 在早期版本中替换控件并添加功能，但如果需要，<xref:System.Windows.Forms.ToolBar> 会保留以实现向后兼容性和将来使用。  
  
## <a name="features-of-the-toolstrip-controls"></a>ToolStrip 控件的功能  
 使用 <xref:System.Windows.Forms.ToolStrip> 控件可以：  
  
- 跨容器显示公共用户界面。  
  
- 创建可轻松自定义的常用工具栏，它们支持高级用户界面和布局功能，如停靠、漂浮、带有文本和图像的按钮、下拉按钮和控件、溢出按钮以及对 <xref:System.Windows.Forms.ToolStrip> 项的运行时重新排序。  
  
- 支持溢出和运行时项重新排序。 当在 <xref:System.Windows.Forms.ToolStrip>中没有足够的空间来显示项时，溢出功能会将项移动到下拉菜单。  
  
- 通过常见的呈现模型支持操作系统的典型外观和行为。  
  
- 以一致的方式处理所有容器和包含项的事件，其方式与处理其他控件的事件的方式相同。  
  
- 将项从一个 <xref:System.Windows.Forms.ToolStrip> 拖动到另一个或 <xref:System.Windows.Forms.ToolStrip>中。  
  
- 在 <xref:System.Windows.Forms.ToolStripDropDown>中创建具有高级布局的下拉控件和用户界面类型编辑器。  
  
 使用 <xref:System.Windows.Forms.ToolStripControlHost> 类在 <xref:System.Windows.Forms.ToolStrip> 上使用其他控件，并为其获取 <xref:System.Windows.Forms.ToolStrip> 功能。  
  
 您可以使用 <xref:System.Windows.Forms.ToolStripRenderer>、<xref:System.Windows.Forms.ToolStripProfessionalRenderer>和 <xref:System.Windows.Forms.ToolStripManager> 以及 <xref:System.Windows.Forms.ToolStripRenderMode> 和 <xref:System.Windows.Forms.ToolStripManagerRenderMode> 枚举来扩展功能并修改外观和行为。  
  
 <xref:System.Windows.Forms.ToolStrip> 控件高度可配置且可扩展，并且提供了许多属性、方法和事件来自定义外观和行为。 下面是一些值得注意的成员：  
  
### <a name="important-toolstrip-members"></a>重要 ToolStrip 成员  
  
|名称|说明|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|获取或设置 <xref:System.Windows.Forms.ToolStrip> 停靠到的父容器的边缘。|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|获取或设置一个用于指示是否专门由 <xref:System.Windows.Forms.ToolStrip> 类处理拖放和项重新排序操作的值。|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|获取或设置一个值，该值指示 <xref:System.Windows.Forms.ToolStrip> 布局其项的方式。|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|获取或设置 <xref:System.Windows.Forms.ToolStripItem> 是附加到 <xref:System.Windows.Forms.ToolStrip> 还是 <xref:System.Windows.Forms.ToolStripOverflowButton>，或者是否可以在这两个之间浮动。|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|获取一个值，该值指示在单击 <xref:System.Windows.Forms.ToolStripItem> 时，<xref:System.Windows.Forms.ToolStripItem> 是否显示下拉列表中的其他项。|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|获取 <xref:System.Windows.Forms.ToolStripItem>，它是启用了溢出的 <xref:System.Windows.Forms.ToolStrip> 的“溢出”按钮。|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|获取或设置用于自定义 <xref:System.Windows.Forms.ToolStrip>的外观和行为（外观）的 <xref:System.Windows.Forms.ToolStripRenderer>。|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|获取或设置要应用于 <xref:System.Windows.Forms.ToolStrip> 的绘制样式。|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|在 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 属性更改时引发。|  
  
 通过使用多个伴生类来实现 <xref:System.Windows.Forms.ToolStrip> 控件的灵活性。 下面是一些最值得注意的事项：  
  
### <a name="important-toolstrip-companion-classes"></a>重要的 ToolStrip 伴生类  
  
|名称|说明|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|替换 <xref:System.Windows.Forms.MainMenu> 类并向其中添加功能。|  
|<xref:System.Windows.Forms.StatusStrip>|替换 <xref:System.Windows.Forms.StatusBar> 类并向其中添加功能。|  
|<xref:System.Windows.Forms.ContextMenuStrip>|替换 <xref:System.Windows.Forms.ContextMenu> 类并向其中添加功能。|  
|<xref:System.Windows.Forms.ToolStripItem>|用于管理 <xref:System.Windows.Forms.ToolStrip>、<xref:System.Windows.Forms.ToolStripControlHost>或 <xref:System.Windows.Forms.ToolStripDropDown> 可以包含的所有元素的事件和布局的抽象基类。|  
|<xref:System.Windows.Forms.ToolStripContainer>|提供一个容器，该容器在窗体的每一侧有一个面板，可通过多种方式排列控件。|  
|<xref:System.Windows.Forms.ToolStripRenderer>|处理 <xref:System.Windows.Forms.ToolStrip> 对象的绘制功能。|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|提供 Microsoft Office 样式的外观。|  
|<xref:System.Windows.Forms.ToolStripManager>|控制 <xref:System.Windows.Forms.ToolStrip> 的呈现和漂浮，以及 <xref:System.Windows.Forms.MenuStrip>、<xref:System.Windows.Forms.ToolStripDropDownMenu> 和 <xref:System.Windows.Forms.ToolStripMenuItem> 对象的合并。|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|指定应用于窗体中包含的多个 <xref:System.Windows.Forms.ToolStrip> 对象的绘制样式（自定义、Windows XP 或 Microsoft Office 专业版）。|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|指定应用于窗体中包含的一个 <xref:System.Windows.Forms.ToolStrip> 对象的绘制样式（自定义、Windows XP 或 Microsoft Office 专业版）。|  
|<xref:System.Windows.Forms.ToolStripControlHost>|承载并非专门 <xref:System.Windows.Forms.ToolStrip> 控件但要 <xref:System.Windows.Forms.ToolStrip> 功能的其他控件。|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|指定是在主 <xref:System.Windows.Forms.ToolStrip>上、在溢出 <xref:System.Windows.Forms.ToolStrip>上布局 <xref:System.Windows.Forms.ToolStripItem>，还是两者都是。|  
  
 有关详细信息，请参阅[Toolstrip 技术摘要](toolstrip-technology-summary.md)和[Toolstrip 控件体系结构](toolstrip-control-architecture.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
