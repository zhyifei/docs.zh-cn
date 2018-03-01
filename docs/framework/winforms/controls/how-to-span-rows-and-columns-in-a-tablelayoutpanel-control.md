---
title: "如何：在 TableLayoutPanel 控件中跨行和跨列"
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
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 24b281e6e1ab56e2c7387435bf2429e7e107c4b8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>如何：在 TableLayoutPanel 控件中跨行和跨列
中的控件<xref:System.Windows.Forms.TableLayoutPanel>控件可以跨越相邻的行和列。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-span-columns-and-rows"></a>跨列和行  
  
1.  拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。  
  
2.  拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到的左上角单元格中<xref:System.Windows.Forms.TableLayoutPanel>控件。  
  
3.  设置<xref:System.Windows.Forms.Button>控件的**ColumnSpan**属性**2**。 请注意，<xref:System.Windows.Forms.Button>控件跨的第一个和第二个列。  
  
4.  设置<xref:System.Windows.Forms.Button>控件的**RowSpan**属性**2**。 请注意，<xref:System.Windows.Forms.Button>控件跨的第一个和第二个行。  
  
5.  设置<xref:System.Windows.Forms.Button>控件的**ColumnSpan**属性**1**。 请注意，<xref:System.Windows.Forms.Button>控制会移动到第一列和跨越的第一个和第二个行。  
  
## <a name="see-also"></a>请参阅  
 [TableLayoutPanel 控件](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
