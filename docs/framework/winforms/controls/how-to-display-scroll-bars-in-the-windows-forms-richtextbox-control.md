---
title: "如何：在 Windows 窗体 RichTextBox 控件中显示滚动条"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b20c526b27eb185bf79eaf0ace47e5a9fded42a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>如何：在 Windows 窗体 RichTextBox 控件中显示滚动条
默认情况下，Windows 窗体<xref:System.Windows.Forms.RichTextBox>控件根据需要显示水平和垂直滚动条。 有七个可能值<xref:System.Windows.Forms.RichTextBox.ScrollBars%2A>属性<xref:System.Windows.Forms.RichTextBox>控件下, 表所述。  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>在 RichTextBox 控件中显示滚动条  
  
1.  将 <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 属性设置为 `true`。 如果没有任何类型的滚动条，包括水平，将显示<xref:System.Windows.Forms.RichTextBox.Multiline%2A>属性设置为`false`。  
  
2.  设置<xref:System.Windows.Forms.RichTextBox.ScrollBars%2A>为适当的值的属性<xref:System.Windows.Forms.RichTextBoxScrollBars>枚举。  
  
    |值|描述|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both>（默认值）|水平或垂直滚动条，或两个，仅当显示的文本超出宽度或的控件长度。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|永远不会显示任何类型的滚动条。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|显示水平滚动条仅当文本超过控件的宽度。 (若要执行，此<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>属性必须设置为`false`。)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|显示一个垂直滚动条仅当文本超过控件的高度。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|显示水平滚动条时<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>属性设置为`false`。 在文本未超过控件的宽度时，滚动条显示为灰色。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|始终显示垂直滚动条。 在文本未超过的控件长度时，滚动条显示为灰色。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|始终显示垂直滚动条。 显示水平滚动条时<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>属性设置为`false`。 滚动条显示为灰色，宽度或的控件长度不超过文本时。|  
  
3.  将 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 属性设置为适当的值。  
  
    |值|描述|  
    |-----------|-----------------|  
    |`false`|控件中的文本不自动调整以适应该控件的宽度，所以它将向右滚动，直到到达一个分行符。 如果您在上面选择和 / 或水平滚动条，请使用此值。|  
    |`true`（默认值）|控件中的文本自动调整以适应控件的宽度。 水平滚动条将不会出现。 如果选择垂直滚动条或无、 更高版本，以显示一个或多个段落，请使用此值。|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox 控件](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
