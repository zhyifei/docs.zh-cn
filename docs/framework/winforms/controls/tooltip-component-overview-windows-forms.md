---
title: "ToolTip 组件概述（Windows 窗体）"
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
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fce1cb5750197e52461b4883f1238325fa10fc5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="tooltip-component-overview-windows-forms"></a>ToolTip 组件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.ToolTip> 组件在用户指向控件时显示文本。 ToolTip 可与任何控件关联。 此组件的一个用法示例： 若要在窗体上节省空间，可以在按钮上显示一个小图标，并使用 ToolTip 来解释按钮的功能。  
  
## <a name="working-with-the-tooltip-component"></a>使用工具提示组件  
 A<xref:System.Windows.Forms.ToolTip>组件提供`ToolTip`到 Windows 窗体或其他容器上的多个控件的属性。 例如，如果您将某个<xref:System.Windows.Forms.ToolTip>窗体上的组件，可以显示"键入你在本文中的名称"<xref:System.Windows.Forms.TextBox>控制和"单击此处以保存更改"为<xref:System.Windows.Forms.Button>控件。  
  
 主要方法<xref:System.Windows.Forms.ToolTip>组件<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>和<xref:System.Windows.Forms.ToolTip.GetToolTip%2A>。 你可以使用<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>方法以设置控件显示的工具提示。 有关详细信息，请参阅[如何： 在设计时的 Windows 窗体上的控件设置工具提示](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)。 主要属性包括<xref:System.Windows.Forms.ToolTip.Active%2A>，其必须设置为`true`的工具提示显示，和<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>，这会设置的工具提示字符串会显示的时间长度，多长时间，用户必须指向控件的工具提示显示，以及如何长它将显示后续工具提示窗口。 有关详细信息，请参阅[如何： 更改 Windows 窗体 ToolTip 组件的延迟](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolTip>  
 [如何：在设计时设置 Windows 窗体控件的工具提示](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [如何：更改 Windows 窗体 ToolTip 组件的延迟](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
