---
title: "FontDialog 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b1e00fc074148ddd53885bafbb490a3e3868fc0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="fontdialog-component-overview-windows-forms"></a>FontDialog 组件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.FontDialog>组件是一个预配置的对话框，这是标准的 Windows**字体**用于公开当前系统安装的字体的对话框。 替代配置自己对话框的字体选择基于 Windows 的应用程序作为简单的解决方案中使用它。  
  
 默认情况下，该对话框显示列表框字体，字体样式和大小;效果，例如删除线和下划线; 对应的复选框脚本; 下拉列表和的显示字体的外观示例。 （脚本引用不同的字符脚本可用于给定字体，例如，希伯来语或日语。）若要显示字体对话框中，调用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。  
  
## <a name="key-properties"></a>键属性  
 该组件具有多个配置其外观的属性。 设置对话框中选择的属性是<xref:System.Windows.Forms.FontDialog.Font%2A>和<xref:System.Windows.Forms.FontDialog.Color%2A>。 <xref:System.Windows.Forms.FontDialog.Font%2A>属性设置字体、 样式、 大小、 脚本和效果; 例如， `Arial, 10pt, style=Italic, Strikeout`。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.FontDialog>  
 [FontDialog 组件](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
