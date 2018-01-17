---
title: "如何：将 ToolStrip 从 ToolStripContainer 移到窗体上"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: daa372397a3c85ef8359261c4816fbba664928bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>如何：将 ToolStrip 从 ToolStripContainer 移到窗体上
使用以下过程移动<xref:System.Windows.Forms.ToolStrip>外<xref:System.Windows.Forms.ToolStripContainer>拖到窗体。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>若要移动的 ToolStrip 从 toolstripcontainer 移到窗体外  
  
1.  选择 <xref:System.Windows.Forms.ToolStrip>。  
  
2.  剪切<xref:System.Windows.Forms.ToolStrip>通过按 CTRL + X，或右键单击<xref:System.Windows.Forms.ToolStrip>选择**剪切**从上下文菜单。  
  
3.  选择窗体。  
  
4.  粘贴<xref:System.Windows.Forms.ToolStrip>通过按 CTRL + V，或选择**粘贴**从**编辑**菜单。  
  
5.  设置<xref:System.Windows.Forms.ToolStrip.Dock%2A>属性<xref:System.Windows.Forms.ToolStrip>到**顶部**。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [ToolStrip 控件概述](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
