---
title: 如何：将 ToolStrip 从 ToolStripContainer 移到窗体上
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 100e744e6e49fbf214488e9bbb796b5b6fb9591a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142358"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>如何：将 ToolStrip 从 ToolStripContainer 移到窗体上
使用以下过程将移<xref:System.Windows.Forms.ToolStrip>共<xref:System.Windows.Forms.ToolStripContainer>拖到窗体。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>若要将移动到窗体从 toolstripcontainer 移出 ToolStrip  
  
1.  选择 <xref:System.Windows.Forms.ToolStrip>。  
  
2.  剪切<xref:System.Windows.Forms.ToolStrip>通过按 CTRL + X，或右键单击<xref:System.Windows.Forms.ToolStrip>，然后选择**剪切**从上下文菜单。  
  
3.  选择窗体。  
  
4.  粘贴<xref:System.Windows.Forms.ToolStrip>通过按 CTRL + V，或选择**粘贴**从**编辑**菜单。  
  
5.  设置<xref:System.Windows.Forms.ToolStrip.Dock%2A>的属性<xref:System.Windows.Forms.ToolStrip>到**顶部**。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
