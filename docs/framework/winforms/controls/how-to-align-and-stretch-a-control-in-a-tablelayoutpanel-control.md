---
title: "如何：在 TableLayoutPanel 控件中对齐和拉伸控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bfc1c64bc0bd9cbebad44193fb5adbe529877487
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a>如何：在 TableLayoutPanel 控件中对齐和拉伸控件
您可以对齐和拉伸控件中的<xref:System.Windows.Forms.TableLayoutPanel>与<xref:System.Windows.Forms.Control.Anchor%2A>和<xref:System.Windows.Forms.Control.Dock%2A>属性。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-align-and-stretch-a-control"></a>若要对齐和拉伸控件  
  
1.  拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。  
  
2.  拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到的左上角单元格中<xref:System.Windows.Forms.TableLayoutPanel>控件。 <xref:System.Windows.Forms.Button>控件居中的单元格中。  
  
3.  设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性`Left,Right`。 <xref:System.Windows.Forms.Button>控件将拉伸到匹配的单元格的宽度。  
  
4.  设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性`Top,Bottom`。 <xref:System.Windows.Forms.Button>控件将拉伸到匹配的单元格的高度。  
  
5.  设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.Fill>。 <xref:System.Windows.Forms.Button>控件扩展以填充单元格。  
  
6.  设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.None>。 <xref:System.Windows.Forms.Button>控件返回到其原始大小，并将移动到单元格的左上角。 **Windows 窗体设计器**已设置<xref:System.Windows.Forms.Control.Anchor%2A>属性`Top, Left`。  
  
7.  设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性`Bottom,Right`。 <xref:System.Windows.Forms.Button>控件移动到单元格右下角。  
  
8.  设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性<xref:System.Windows.Forms.AnchorStyles.None>。 <xref:System.Windows.Forms.Button>控件将移动到单元格的中心。  
  
## <a name="see-also"></a>请参阅  
 [TableLayoutPanel 控件](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
