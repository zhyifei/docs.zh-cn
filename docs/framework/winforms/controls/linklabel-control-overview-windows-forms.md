---
title: LinkLabel 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 40326a9055ff51efae5f4c64744d0966870c6f6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535007"
---
# <a name="linklabel-control-overview-windows-forms"></a>LinkLabel 控件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.LinkLabel>控件，可将 Web 样式的链接添加到 Windows 窗体应用程序。 你可以使用<xref:System.Windows.Forms.LinkLabel>控件可以使用的所有操作都<xref:System.Windows.Forms.Label>控制; 也可以设置为文件、 文件夹或网页的链接的文本的一部分。  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>如何使用 LinkLabel 控件  
 除了所有属性、 方法和事件的<xref:System.Windows.Forms.Label>控件，<xref:System.Windows.Forms.LinkLabel>控件具有超链接和链接颜色的属性。 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>属性设置的激活链接的文本的区域。 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>， <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>，和<xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A>属性设置的链接的颜色。 <xref:System.Windows.Forms.LinkLabel.LinkClicked>事件确定当选中此链接文本时，会发生什么情况。  
  
 最简单用法<xref:System.Windows.Forms.LinkLabel>控件将显示单个链接使用<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>属性，但你还可以显示多个超链接使用<xref:System.Windows.Forms.LinkLabel.Links%2A>属性。 <xref:System.Windows.Forms.LinkLabel.Links%2A>属性使您能够访问的链接集合。 你还可以指定中的数据<xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>的每个单独的属性<xref:System.Windows.Forms.LinkLabel.Link>对象。 值<xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>属性可以用于存储到显示的文件的位置或 Web 站点的地址。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.LinkLabel>  
 [Label 控件概述](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [如何：使用 Windows 窗体 LinkLabel 控件链接到对象或网页](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [如何：更改 Windows 窗体 LinkLabel 控件的外观](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
