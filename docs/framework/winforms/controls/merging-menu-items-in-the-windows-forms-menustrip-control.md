---
title: "在 Windows 窗体 MenuStrip 控件中合并菜单项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cd54855f7ee618915fea4fcb8f465cc8c1a68164
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>在 Windows 窗体 MenuStrip 控件中合并菜单项
如果你有多文档界面 (MDI) 应用程序，你可以将菜单项或从子窗体的整个菜单合并到父窗体的菜单中。  
  
 本主题介绍与合并菜单项在 MDI 应用程序相关联的基本概念。  
  
## <a name="general-concepts"></a>常规概念  
 合并过程涉及的目标和源控件：  
  
-   目标是<xref:System.Windows.Forms.MenuStrip>到正在合并菜单项 main 的一个或多个 MDI 父窗体上控件。  
  
-   源是<xref:System.Windows.Forms.MenuStrip>上包含你想要合并到目标菜单的菜单项的 MDI 子窗体控件。  
  
 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>属性标识其下拉列表框将填充的标题的当前 MDI 父窗体的 MDI 子窗体的菜单项。 例如，您通常列出在当前打开的 MDI 子级**窗口**菜单。  
  
 <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A>属性标识该菜单项来自<xref:System.Windows.Forms.MenuStrip>MDI 子窗体上。  
  
 你可以手动或自动合并菜单项。 菜单项合并在相同的方式针对这两种方法，但合并激活方式不同，如本主题中后面的"手动合并"和"自动合并"节中所述。 在手动和自动合并时，每个合并操作会影响下一步的合并操作。  
  
 <xref:System.Windows.Forms.MenuStrip>合并菜单项移从一个<xref:System.Windows.Forms.ToolStrip>到另一个而不是克隆，因为这种情况<xref:System.Windows.Forms.MainMenu>。  
  
## <a name="mergeaction-values"></a>MergeAction 值  
 在源中的菜单项上设置的合并操作<xref:System.Windows.Forms.MenuStrip>使用<xref:System.Windows.Forms.MergeAction>属性。  
  
 下表描述了可用合并操作的含义和典型用法。  
  
|MergeAction 值|描述|典型用法|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|（默认值）将源项添加到目标项的集合的末尾。|激活该程序的某些部分时，请将菜单项添加到菜单的末尾。|  
|<xref:System.Windows.Forms.MergeAction.Insert>|将源项添加到目标项的集合，通过指定的位置中<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>在源项上设置属性。|激活该程序的某些部分时，请将菜单项添加到中间或菜单的开头。<br /><br /> 如果值<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>相同的两个菜单项，它们将被添加按相反的顺序。 设置<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>适当地保留原始顺序。|  
|<xref:System.Windows.Forms.MergeAction.Replace>|查找文本匹配项，或使用<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>时没有文本匹配找到，，然后将匹配的目标菜单项替换为源菜单项的值。|将替换源菜单项执行不同操作具有相同名称的目标菜单项。|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|查找文本匹配项，或使用<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>时没有文本匹配找到，，然后将所有的下拉列表项从源添加到目标的值。|生成的菜单结构，该插入或将菜单项添加到子菜单，或移除子菜单的菜单项。 例如，可以将菜单项从 MDI 子窗体添加到 main <xref:System.Windows.Forms.MenuStrip>**另存为**菜单。<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly>允许你导航菜单结构而不采取任何操作。 它提供了如何评估后续项。|  
|<xref:System.Windows.Forms.MergeAction.Remove>|查找文本匹配项，或使用<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>值没有文本匹配找到，然后从目标中移除的项。|从目标删除菜单项<xref:System.Windows.Forms.MenuStrip>。|  
  
## <a name="manual-merging"></a>手动合并  
 仅<xref:System.Windows.Forms.MenuStrip>自动合并参与控件。 要组合的项的其他控件，如<xref:System.Windows.Forms.ToolStrip>和<xref:System.Windows.Forms.StatusStrip>控件，你必须手动合并它们，通过调用<xref:System.Windows.Forms.ToolStripManager.Merge%2A>和<xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A>根据需要在代码中的方法。  
  
## <a name="automatic-merging"></a>自动合并  
 你可以使用自动合并对于 MDI 应用程序通过激活源窗体。 若要使用<xref:System.Windows.Forms.MenuStrip>MDI 应用程序，在设置<xref:System.Windows.Forms.Form.MainMenuStrip%2A>到目标属性<xref:System.Windows.Forms.MenuStrip>以便合并操作的源上执行<xref:System.Windows.Forms.MenuStrip>反映在目标<xref:System.Windows.Forms.MenuStrip>。  
  
 你可以触发自动合并通过激活<xref:System.Windows.Forms.MenuStrip>MDI 源。 在激活，源<xref:System.Windows.Forms.MenuStrip>合并到 MDI 目标。 当新的窗体变为活动状态时，合并还原最后一个窗体上，并触发新的窗体上。 你可以通过设置来控制此行为<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A>属性根据需要在每个上<xref:System.Windows.Forms.ToolStripItem>，并通过设置<xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>上每个属性<xref:System.Windows.Forms.MenuStrip>。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.MenuStrip>  
 [MenuStrip 控件](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [如何：使用 MenuStrip 创建 MDI 窗口列表](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)  
 [如何：为 MDI 应用程序设置自动菜单合并](../../../../docs/framework/winforms/controls/how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
