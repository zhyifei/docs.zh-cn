---
title: "TrackBar 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e62fc49a8a08c79138df080246b99b6fe891162e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="trackbar-control-overview-windows-forms"></a>TrackBar 控件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.TrackBar>（有时也称为"滑块"控件） 的控件用于浏览大量的信息或用于直观地调整数值设置。 <xref:System.Windows.Forms.TrackBar>控件具有两个部分： 滚动块，也称为滑块和刻度线。 滚动块是可以进行调整的一部分。 其位置对应于<xref:System.Windows.Forms.TrackBar.Value%2A>属性。 刻度线是定期间距的可视指示器。 Trackbar 指定和可以水平或垂直对齐的增量移动。 例如，可能会使用跟踪条以控制系统的光标闪烁速率或鼠标速度。  
  
## <a name="key-properties"></a>键属性  
 键属性<xref:System.Windows.Forms.TrackBar>控件<xref:System.Windows.Forms.TrackBar.Value%2A>， <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>， <xref:System.Windows.Forms.TrackBar.Minimum%2A>，和<xref:System.Windows.Forms.TrackBar.Maximum%2A>。 <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>是的刻度的间距。 <xref:System.Windows.Forms.TrackBar.Minimum%2A>和<xref:System.Windows.Forms.TrackBar.Maximum%2A>是可以表示跟踪条的最小和最大值。  
  
 其他两个重要属性都是<xref:System.Windows.Forms.TrackBar.SmallChange%2A>和<xref:System.Windows.Forms.TrackBar.LargeChange%2A>。 值<xref:System.Windows.Forms.TrackBar.SmallChange%2A>属性是滚动块移动到具有左或向右箭头键按下的响应中的位置数。 值<xref:System.Windows.Forms.TrackBar.LargeChange%2A>属性是的滚动块移动到具有 PAGE UP 或 PAGE DOWN 键按下的响应中或以响应鼠标单击跟踪条上滚动块的任何一侧上的位置数。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.TrackBar>  
 [TrackBar 控件](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)
