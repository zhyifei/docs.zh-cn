---
title: "ProgressBar 控件概述（Windows 窗体）"
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
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c5ca5fd908124b0f38643c7b2833ba591be3b980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="progressbar-control-overview-windows-forms"></a>ProgressBar 控件概述（Windows 窗体）
> [!IMPORTANT]
>  <xref:System.Windows.Forms.ToolStripProgressBar> 控件取代了 <xref:System.Windows.Forms.ProgressBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ProgressBar> 控件以实现向后兼容并供将来使用。  
  
 Windows 窗体<xref:System.Windows.Forms.ProgressBar>控件通过显示适当数量的矩形排列在水平条来指示过程的进度。 完成该过程时，栏被填满。 进度栏通常用于帮助用户了解等待进程完成;例如，当较大的文件正在加载。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ProgressBar>控件可以只能水平放置在窗体上。  
  
## <a name="key-properties-and-methods"></a>键属性和方法  
 键属性<xref:System.Windows.Forms.ProgressBar>控件<xref:System.Windows.Forms.ProgressBar.Value%2A>， <xref:System.Windows.Forms.ProgressBar.Minimum%2A>，和<xref:System.Windows.Forms.ProgressBar.Maximum%2A>。 <xref:System.Windows.Forms.ProgressBar.Minimum%2A>和<xref:System.Windows.Forms.ProgressBar.Maximum%2A>属性设置可以显示进度栏的最大和最小值。 <xref:System.Windows.Forms.ProgressBar.Value%2A>属性表示已完成该操作的进度。 显示的值在控件中显示的栏组成块，因为<xref:System.Windows.Forms.ProgressBar>控件仅仅是近似于<xref:System.Windows.Forms.ProgressBar.Value%2A>属性的当前值。 基于大小<xref:System.Windows.Forms.ProgressBar>控件，<xref:System.Windows.Forms.ProgressBar.Value%2A>属性确定何时将显示下一个块。  
  
 更新当前进度值的最常见方法是编写代码来设置<xref:System.Windows.Forms.ProgressBar.Value%2A>属性。 在加载较大的文件的示例中，你可能将最大值设置为千字节为单位中的文件的大小。 例如，如果<xref:System.Windows.Forms.ProgressBar.Maximum%2A>属性设置为 100，<xref:System.Windows.Forms.ProgressBar.Minimum%2A>属性设置为 10，和<xref:System.Windows.Forms.ProgressBar.Value%2A>属性设置为 50，将显示 5 个矩形。 这是数目的可以显示的一半。  
  
 但是，还有其他方式修改显示的值<xref:System.Windows.Forms.ProgressBar>控件，除了设置之外<xref:System.Windows.Forms.ProgressBar.Value%2A>直接属性。 <xref:System.Windows.Forms.ProgressBar.Step%2A>属性可以用于指定一个值，以递增<xref:System.Windows.Forms.ProgressBar.Value%2A>属性。 然后，调用<xref:System.Windows.Forms.ProgressBar.PerformStep%2A>方法将递增的值。 若要更改增量值，可以使用<xref:System.Windows.Forms.ProgressBar.Increment%2A>方法并指定具有要递增的值<xref:System.Windows.Forms.ProgressBar.Value%2A>属性。  
  
 以图形方式向用户通知有关当前操作的另一个控件是<xref:System.Windows.Forms.StatusBar>控件。  
  
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip>和<xref:System.Windows.Forms.ToolStripStatusLabel>控件替换，并将功能添加到<xref:System.Windows.Forms.StatusBar>和<xref:System.Windows.Forms.StatusBarPanel>控制; 但是，<xref:System.Windows.Forms.StatusBar>和<xref:System.Windows.Forms.StatusBarPanel>控件将保留用于向后兼容性和将来使用，如果你选择。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ProgressBar>  
 [ProgressBar 控件](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)
