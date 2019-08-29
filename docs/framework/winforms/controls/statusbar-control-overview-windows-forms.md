---
title: StatusBar 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: bd58d4c70e3a3c88e57fe242957f669d1944fd71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964434"
---
# <a name="statusbar-control-overview-windows-forms"></a>StatusBar 控件概述（Windows 窗体）
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBar>和控件替换和添加了和控件的功能; 但是, 和<xref:System.Windows.Forms.StatusBarPanel>控件将保留以实现向后兼容性和将来使用, 前提是你<xref:System.Windows.Forms.ToolStripStatusLabel> <xref:System.Windows.Forms.StatusStrip>.  
  
 Windows 窗体[状态栏控件](statusbar-control-windows-forms.md)在窗体上用作区域, 通常显示在窗口底部, 应用程序可在窗口中显示各种类型的状态信息。 <xref:System.Windows.Forms.StatusBar>控件可在其上具有状态栏面板, 这些面板显示用于指示状态的文本或图标, 或动画中指示进程工作的一系列图标。例如, Microsoft Word 表明文档正在保存。  
  
## <a name="using-the-statusbar-control"></a>使用 "状态栏" 控件  
 当鼠标滚动到超链接上时, Internet Explorer 将使用状态栏来指示页面的 URL;Microsoft Word 提供了有关页面位置、分区位置和编辑模式 (如改写和修订跟踪) 的信息;Visual Studio 使用状态栏为上下文相关的信息, 如告诉您如何操作停靠或浮动的窗口。  
  
 您可以通过将<xref:System.Windows.Forms.StatusBar.ShowPanels%2A>属性设置为`false` ( <xref:System.Windows.Forms.StatusBar.Text%2A>默认值), 然后将状态栏的属性设置为要在状态栏中显示的文本, 在状态栏上显示一条消息。 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A>您可以通过将属性设置为`true` <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>并使用<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A>的方法, 将状态栏划分为多个面板以显示多种类型的信息。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [如何：确定单击 Windows 窗体状态栏控件中的哪个面板](determine-which-panel-wf-statusbar-control-was-clicked.md)
