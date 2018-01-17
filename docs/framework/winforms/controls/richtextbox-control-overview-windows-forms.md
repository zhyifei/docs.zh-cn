---
title: "RichTextBox 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6ed04ab478cc6c20d88ec97934f5e45528558c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="richtextbox-control-overview-windows-forms"></a>RichTextBox 控件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.RichTextBox>控件用于显示、 输入和操作具有格式的文本。 <xref:System.Windows.Forms.RichTextBox>控件的作用的所有内容<xref:System.Windows.Forms.TextBox>控件的作用，但它还可以显示字体、 颜色和链接; 从文件; 加载文本和嵌入的图像并查找指定的字符。 <xref:System.Windows.Forms.RichTextBox>控件通常用于文本操作，并显示类似于 Microsoft Word 等文字处理应用程序的功能。 如<xref:System.Windows.Forms.TextBox>控件，<xref:System.Windows.Forms.RichTextBox>控件可以显示滚动条; 但与<xref:System.Windows.Forms.TextBox>控件，其默认设置是显示水平和垂直滚动条，根据需要并包含其他滚动条设置。  
  
## <a name="working-with-the-richtextbox-control"></a>使用 RichTextBox 控件  
 与<xref:System.Windows.Forms.TextBox>控件，显示的文本设置<xref:System.Windows.Forms.RichTextBox.Text%2A>属性。 <xref:System.Windows.Forms.RichTextBox>控件具有大量的属性，用于设置文本格式。 有关这些属性的详细信息，请参阅[如何：为 Windows 窗体 RichTextBox 控件设置字体特性](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)和[如何：在 Windows 窗体 RichTextBox 控件中设置缩进、悬挂缩进和带项目符号的段落](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)。 若要处理文件，<xref:System.Windows.Forms.RichTextBox.LoadFile%2A>和<xref:System.Windows.Forms.RichTextBox.SaveFile%2A>方法可以显示和写入多个文件格式，包括纯文本、 Unicode 纯文本和格式 RTF (丰富文本)。 中列出了可能的文件格式<xref:System.Windows.Forms.RichTextBoxStreamType>。 你可以使用<xref:System.Windows.Forms.RichTextBox.Find%2A>方法若要查找的文本或特定的字符的字符串。  
  
 你还可以使用<xref:System.Windows.Forms.RichTextBox>Web 样式的链接，通过设置的控件<xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>属性`true`编写代码来处理<xref:System.Windows.Forms.RichTextBox.LinkClicked>事件。 有关详细信息，请参阅[如何：使用 Windows 窗体 RichTextBox 控件显示 Web 样式的链接](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)。 你可以防止用户通过设置操作的部分或全部控件中的文本<xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A>属性`true`。  
  
 可以撤消和重做中的大多数编辑操作<xref:System.Windows.Forms.RichTextBox>通过调用控件<xref:System.Windows.Forms.TextBoxBase.Undo%2A>和<xref:System.Windows.Forms.RichTextBox.Redo%2A>方法。 <xref:System.Windows.Forms.RichTextBox.CanRedo%2A>方法使您能够确定是否可以重新撤消了用户的上一个操作应用于控件。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox 控件](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [TextBox 控件概述](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
