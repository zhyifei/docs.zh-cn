---
title: LinkLabel 控件概述
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 9837902bf56a402d623adbcf41558dcc568b7105
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745221"
---
# <a name="linklabel-control-overview-windows-forms"></a>LinkLabel 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.LinkLabel> 控件允许您将 Web 样式链接添加到 Windows 窗体应用程序。 您可以使用 <xref:System.Windows.Forms.LinkLabel> 控件来查找可对其使用 <xref:System.Windows.Forms.Label> 控件的所有内容;您还可以将部分文本设置为指向文件、文件夹或网页的链接。  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>可以对 LinkLabel 控件执行的操作  
 除了 <xref:System.Windows.Forms.Label> 控件的所有属性、方法和事件外，<xref:System.Windows.Forms.LinkLabel> 控件都具有用于超链接和链接颜色的属性。 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 属性设置激活链接的文本区域。 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>、<xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>和 <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> 属性设置链接的颜色。 <xref:System.Windows.Forms.LinkLabel.LinkClicked> 事件确定在选择链接文本后将发生的情况。  
  
 <xref:System.Windows.Forms.LinkLabel> 控件的最简单用法是使用 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 属性显示单个链接，但也可以使用 <xref:System.Windows.Forms.LinkLabel.Links%2A> 属性来显示多个超链接。 <xref:System.Windows.Forms.LinkLabel.Links%2A> 属性使你能够访问链接的集合。 您还可以在每个单独 <xref:System.Windows.Forms.LinkLabel.Link> 对象的 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 属性中指定数据。 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 属性的值可用于存储要显示的文件的位置或网站的地址。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.LinkLabel>
- [Label 控件概述](label-control-overview-windows-forms.md)
- [如何：使用 Windows 窗体 LinkLabel 控件链接到对象或网页](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [如何：更改 Windows 窗体 LinkLabel 控件的外观](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
