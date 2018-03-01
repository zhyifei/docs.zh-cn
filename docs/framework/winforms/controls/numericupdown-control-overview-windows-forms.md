---
title: "NumericUpDown 控件概述（Windows 窗体）"
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
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 067a8862ee991213e584819e1cf99eddde06e2bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="numericupdown-control-overview-windows-forms"></a>NumericUpDown 控件概述（Windows 窗体）
<xref:System.Windows.Forms.NumericUpDown>控件看起来像一对用户可以单击来调整值的箭头和一个文本框的组合。 该控件显示，并从一组固定数字值选项的设置的单个数值。 用户可以增加和减少的数量，通过单击向上和向下箭头，按向上和向下箭头键，或通过控件的文本框部分中键入一个数字。 单击向上箭头键移动朝着最大值; 数单击向下箭头键来移动朝着最小值的数量。  
  
 因为其通用的功能，而此控件的本质就是选择，例如，如果你想要创建音乐播放器应用程序的卷控件。 <xref:System.Windows.Forms.NumericUpDown>控件用于在许多 Windows 控制面板应用程序。  
  
## <a name="key-properties-and-methods"></a>键属性和方法  
 在控件的文本框中显示的数字可为各种格式，包括十六进制。 有关详细信息，请参阅[如何： 设置 Windows 窗体 NumericUpDown 控件的格式](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)。 控件的主要属性包括<xref:System.Windows.Forms.NumericUpDown.Value%2A>， <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> （默认值为 100）， <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> （默认值为 0） 和<xref:System.Windows.Forms.NumericUpDown.Increment%2A>（默认值为 1）。 <xref:System.Windows.Forms.NumericUpDown.Value%2A>属性设置在控件中选定的当前数目。 <xref:System.Windows.Forms.NumericUpDown.Increment%2A>属性设置为当用户单击向上或向下箭头，调整数的量。 当焦点移出该控件时，将根据最小和最大的数字值验证键入的输入。 你可以增加控件在用户连续按向上或向下箭头，在数字上移动的速度与<xref:System.Windows.Forms.NumericUpDown.Accelerations%2A>属性。 控件的主要方法是<xref:System.Windows.Forms.NumericUpDown.UpButton%2A>和<xref:System.Windows.Forms.NumericUpDown.DownButton%2A>。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.NumericUpDown>  
 [NumericUpDown 控件](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [如何：设置 Windows 窗体 NumericUpDown 控件的格式](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)  
 [TextBox 控件](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
