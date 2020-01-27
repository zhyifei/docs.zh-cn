---
title: FontDialog 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745703"
---
# <a name="fontdialog-component-overview-windows-forms"></a>FontDialog 구성 요소 개요(Windows Forms)
Windows 窗体 <xref:System.Windows.Forms.FontDialog> 组件是一个预先配置的对话框，该对话框是标准的 Windows**字体**对话框，用于公开当前安装在系统中的字体。 在基于 Windows 的应用程序中使用它作为字体选择的简单解决方案，而不是配置自己的对话框。  
  
 默认情况下，该对话框将显示字体、字形和字号的列表框;用于效果的复选框，如删除线和下划线;脚本的下拉列表;以及字体显示方式的示例。 （脚本是指可用于给定字体的不同字符脚本，例如希伯来语或日语。）若要显示 "字体" 对话框，请调用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法。  
  
## <a name="key-properties"></a>키 속성  
 组件具有多个配置其外观的属性。 设置对话框选择的属性将 <xref:System.Windows.Forms.FontDialog.Font%2A> 和 <xref:System.Windows.Forms.FontDialog.Color%2A>。 <xref:System.Windows.Forms.FontDialog.Font%2A> 属性设置字体、样式、大小、脚本和效果;例如，`Arial, 10pt, style=Italic, Strikeout`。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.FontDialog>
- [FontDialog 구성 요소](fontdialog-component-windows-forms.md)
