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
ms.openlocfilehash: 3e8607644c858ae804e384c974b5e81c1786c6a1
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739517"
---
# <a name="linklabel-control-overview-windows-forms"></a>LinkLabel 控件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.LinkLabel>控件允许您向 Windows 窗体应用程序添加 Web 样式的链接。 您可以将控件<xref:System.Windows.Forms.LinkLabel>用于可用于<xref:System.Windows.Forms.Label>控件的所有内容;还可以将文本的一部分设置为指向文件、文件夹或网页的链接。  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>使用链接标签控件可以做什么  
 除了<xref:System.Windows.Forms.Label>控件的所有属性、方法和事件外，<xref:System.Windows.Forms.LinkLabel>控件还具有超链接和链接颜色的属性。 属性<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>设置激活链接的文本区域。 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A><xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A>和<xref:System.Windows.Forms.LinkLabel.LinkColor%2A>属性设置链接的颜色。 该<xref:System.Windows.Forms.LinkLabel.LinkClicked>事件确定选择链接文本时会发生什么情况。  
  
 控件最简单的用处<xref:System.Windows.Forms.LinkLabel>是使用 属性<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>显示单个链接，但也可以使用 属性<xref:System.Windows.Forms.LinkLabel.Links%2A>显示多个超链接。 该<xref:System.Windows.Forms.LinkLabel.Links%2A>属性使您能够访问链接的集合。 您还可以在每个单个<xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A><xref:System.Windows.Forms.LinkLabel.Link>对象的属性中指定数据。 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>属性的值可用于存储要显示的文件的位置或网站的地址。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.LinkLabel>
- [Label 控件概述](label-control-overview-windows-forms.md)
- [如何：使用 Windows 窗体 LinkLabel 控件链接到对象或 Web 页面](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [如何：更改 Windows 窗体 LinkLabel 控件的外观](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
