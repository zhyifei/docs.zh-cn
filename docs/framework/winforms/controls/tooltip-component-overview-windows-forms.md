---
title: ToolTip 组件概述
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 731f7ad0ce6670000d8c3d3e901e1506f7ef470a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741901"
---
# <a name="tooltip-component-overview-windows-forms"></a>ToolTip 组件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.ToolTip> 组件在用户指向控件时显示文本。 ToolTip 可与任何控件关联。 此组件的示例用法：若要在窗体上节省空间，可以在按钮上显示小图标，并使用工具提示来解释该按钮的功能。  
  
## <a name="working-with-the-tooltip-component"></a>使用 ToolTip 组件  
 <xref:System.Windows.Forms.ToolTip> 组件为 Windows 窗体或其他容器上的多个控件提供 `ToolTip` 属性。 例如，如果您在窗体上放置一个 <xref:System.Windows.Forms.ToolTip> 组件，则可以在 "<xref:System.Windows.Forms.TextBox>" 控件中显示 "在此处键入您的名称"，并为 <xref:System.Windows.Forms.Button> 控件 "单击此处保存更改"。  
  
 <xref:System.Windows.Forms.ToolTip> 组件的关键方法 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 并 <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>。 您可以使用 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 方法设置为控件显示的工具提示。 有关详细信息，请参阅[如何：在设计时在 Windows 窗体上设置控件的工具提示](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)。 键属性是 <xref:System.Windows.Forms.ToolTip.Active%2A>的，必须将其设置为 `true` 以显示工具提示，并 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>，这将设置显示工具提示字符串的时间长度、用户必须指向控件以显示工具提示的时间，以及显示后续工具提示窗口所需的时间。 有关详细信息，请参阅[如何：更改 Windows 窗体 ToolTip 组件的延迟](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolTip>
- [如何：在设计时设置 Windows 窗体控件的工具提示](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [如何：更改 Windows 窗体 ToolTip 组件的延迟](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
