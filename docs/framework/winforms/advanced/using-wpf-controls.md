---
title: 使用 WPF 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 8dcf79d449a8f8443774b133904e819dfd925288
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526599"
---
# <a name="using-wpf-controls"></a>使用 WPF 控件
在基于 Windows 窗体的应用程序，可以使用 Windows Presentation Foundation (WPF) 控件。 尽管这些是两个不同的视图技术，则它们顺利互操作。  
  
 Windows 窗体设计器提供用于承载 Windows Presentation Foundation 控件的可视设计环境。 由名为的特殊 Windows 窗体控件承载 WPF 控件<xref:System.Windows.Forms.Integration.ElementHost>。 此控件启用 WPF 控件将参与窗体的布局以及接收键盘和鼠标的消息。 在设计时，可以排列<xref:System.Windows.Forms.Integration.ElementHost>控制就像任何 Windows 窗体控件。  
  
 此外可以基于 WPF 的应用程序中使用 Windows 窗体控件。 有关详细信息，请参阅[WPF 设计器](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：在设计时复制并粘贴 ElementHost 控件](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 演示如何将 Windows 窗体上的 Windows Presentation Foundation 控件复制。  
  
 [演练：在设计时在 Windows 窗体上排列 WPF 内容](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 演示如何使用 Windows 窗体布局功能，例如锚定和对齐线，排列 Windows Presentation Foundation 控件。  
  
 [演练：在设计时更改托管 WPF 元素的属性](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 显示 Windows 窗体设计器之间的工作流和[!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]更改 WPF 控件的属性。  
  
 [演练：在设计时在 Windows 窗体上新建 WPF 内容](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 演示如何在基于 Windows 窗体的应用程序中创建使用 Windows Presentation Foundation 控件。  
  
 [演练：将 ElementHost 控件复制并粘贴到各个 Windows 窗体中](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 演示如何将 Windows Presentation Foundation 控件从一个 Windows 窗体复制到另一个。  
  
 [演练：在设计时在 Windows 窗体上分配 WPF 内容](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 演示如何选择你想要在窗体上显示的 Windows Presentation Foundation 控件类型。  
  
 [演练：设置 WPF 内容的样式](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 显示 Windows 窗体设计器之间的工作流和[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]用于将样式应用到 Windows Presentation Foundation 控件。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 介绍可以在基于 Windows 窗体的应用程序中使用到的主机 Windows Presentation Foundation 控件的类。  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 介绍可以在基于 Windows Presentation Foundation 的应用程序中使用主机 Windows 窗体控件的类。  
  
## <a name="related-sections"></a>相关章节  
 [迁移和互操作性](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 介绍 Windows Presentation Foundation 和 Windows 窗体技术之间的互操作。  
  
 [WPF 设计器](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 描述如何设计 Visual Studio 中的 Windows Presentation Foundation 控件。
