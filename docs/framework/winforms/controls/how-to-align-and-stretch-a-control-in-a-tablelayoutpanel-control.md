---
title: 如何：在 TableLayoutPanel 控件中对齐和拉伸控件
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210367"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a>如何：在 TableLayoutPanel 控件中对齐和拉伸控件

您可以对齐和拉伸控件中的<xref:System.Windows.Forms.TableLayoutPanel>与<xref:System.Windows.Forms.Control.Anchor%2A>和<xref:System.Windows.Forms.Control.Dock%2A>属性。

## <a name="align-and-stretch-a-control"></a>对齐和拉伸控件

1. 在 Visual Studio 中，拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。

2. 拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到的左上角单元格<xref:System.Windows.Forms.TableLayoutPanel>控件。 <xref:System.Windows.Forms.Button>控件居中单元格中。

3. 设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为`Left,Right`。 <xref:System.Windows.Forms.Button>控件将拉伸到匹配的单元格的宽度。

4. 设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为`Top,Bottom`。 <xref:System.Windows.Forms.Button>控件将拉伸到匹配的单元格的高度。

5. 设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Dock%2A>属性设置为<xref:System.Windows.Forms.DockStyle.Fill>。 <xref:System.Windows.Forms.Button>控件扩展以填充单元格。

6. 设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Dock%2A>属性设置为<xref:System.Windows.Forms.DockStyle.None>。 <xref:System.Windows.Forms.Button>控件返回到其原始大小，并将移动到单元格的左上角。 **Windows 窗体设计器**已设置<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为`Top, Left`。

7. 设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为`Bottom,Right`。 <xref:System.Windows.Forms.Button>控件移动到右下角的单元格。

8. 设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为<xref:System.Windows.Forms.AnchorStyles.None>。 <xref:System.Windows.Forms.Button>控件移动到单元格的中心。

## <a name="see-also"></a>请参阅

- [TableLayoutPanel 控件](tablelayoutpanel-control-windows-forms.md)
