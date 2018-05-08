---
title: TableLayoutPanel 控件中的自动调整大小行为
ms.date: 03/30/2017
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
ms.openlocfilehash: 497991106d151cfe1f3944977828e9c77c27e526
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a>TableLayoutPanel 控件中的自动调整大小行为
## <a name="distinct-autosize-behaviors"></a>非重复 AutoSize 行为  
 <xref:System.Windows.Forms.TableLayoutPanel>控件支持自动调整大小行为通过以下方式：  
  
-   通过<xref:System.Windows.Forms.Control.AutoSize%2A>属性;  
  
-   通过<xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>属性<xref:System.Windows.Forms.TableLayoutPanel>控件的列和行样式。  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a>具有行和列样式的 AutoSize 属性  
 下表描述了之间的交互<xref:System.Windows.Forms.Control.AutoSize%2A>属性和<xref:System.Windows.Forms.TableLayoutPanel>控件的列和行样式。  
  
|AutoSize 设置|样式交互|  
|----------------------|-----------------------|  
|`false`|<xref:System.Windows.Forms.TableLayoutPanel>控件将继续从左到右，并为列或行或按以下顺序分配空间。<br /><br /> 1.如果<xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>属性设置为<xref:System.Windows.Forms.SizeType.Absolute>，由指定的像素数<xref:System.Windows.Forms.ColumnStyle.Width%2A>或<xref:System.Windows.Forms.RowStyle.Height%2A>分配。<br />2.如果<xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>属性设置为<xref:System.Windows.Forms.SizeType.AutoSize>，返回的子控件的像素数<xref:System.Windows.Forms.Control.GetPreferredSize%2A>分配方法。<br />3.所有的空格后面<xref:System.Windows.Forms.SizeType.Absolute>和<xref:System.Windows.Forms.SizeType.AutoSize>列或行已分配，任何列或行与<xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>设置为<xref:System.Windows.Forms.SizeType.Percent>用于按比例分配的剩余可用空间|  
|`true`|类似于前面的交互，出现异常，<xref:System.Windows.Forms.SizeType.Percent>列或行获取自动调整大小方面。<br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>控件扩展的列或行以创建足够的可用空间，以便任何列或行<xref:System.Windows.Forms.SizeType.Percent>样式剪裁掉其内容。 <xref:System.Windows.Forms.TableLayoutPanel>控件分配根据到按比例的新空间<xref:System.Windows.Forms.ColumnStyle.Width%2A>或<xref:System.Windows.Forms.RowStyle.Height%2A>属性。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [TableLayoutPanel 控件概述](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)
