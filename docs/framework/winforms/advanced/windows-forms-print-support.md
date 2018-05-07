---
title: Windows 窗体打印支持
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: 4ea04d0b6bb8ffa7182d5166ebd66b809adeed34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-print-support"></a>Windows 窗体打印支持
在 Windows 窗体中的打印主要由使用[PrintDocument 组件](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)组件，使用户能够打印，和[PrintPreviewDialog 控件](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)控件， [PrintDialog组件](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)和[PageSetupDialog 组件](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)组件以向熟悉 Windows 操作系统的用户提供熟悉的图形界面。  
  
 通常，你创建的新实例<xref:System.Drawing.Printing.PrintDocument>组件，设置描述打印使用内容的属性<xref:System.Drawing.Printing.PrinterSettings>和<xref:System.Drawing.Printing.PageSettings>类，并调用<xref:System.Drawing.Printing.PrintDocument.Print%2A>方法来实际打印文档。  
  
 从基于 Windows 的应用程序，打印过程<xref:System.Drawing.Printing.PrintDocument>组件将向警报用户事实指出正在进行打印并允许打印作业要取消显示中止打印对话框。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：创建标准的 Windows 窗体打印作业](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 说明如何使用<xref:System.Drawing.Printing.PrintDocument>组件从 Windows 窗体进行打印。  
  
 [如何：在运行时从 PrintDialog 中捕获用户输入](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 说明如何修改所选的打印选项，以编程方式使用<xref:System.Windows.Forms.PrintDialog>组件。  
  
 [如何：在 Windows 窗体中选择用户计算机连接的打印机](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 介绍更改打印机来打印到使用<xref:System.Windows.Forms.PrintDialog>在运行时组件。  
  
 [如何：在 Windows 窗体中打印图形](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 描述发送到打印机的图形。  
  
 [如何：打印 Windows 窗体中的多页文本文件](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 描述发送到打印机的文本。  
  
 [如何：完成 Windows 窗体打印作业](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 说明如何通知用户打印作业的完成。  
  
 [如何：打印 Windows 窗体](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 演示如何打印一份当前窗体。  
  
 [如何：使用打印预览在 Windows 窗体中进行打印](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 演示如何使用<xref:System.Windows.Forms.PrintPreviewDialog>打印文档。  
  
## <a name="related-sections"></a>相关章节  
 [PrintDocument 组件](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 说明使用<xref:System.Drawing.Printing.PrintDocument>组件。  
  
 [PrintDialog 组件](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 说明使用<xref:System.Windows.Forms.PrintDialog>组件。  
  
 [PrintPreviewDialog 控件](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 说明使用<xref:System.Windows.Forms.PrintPreviewDialog>控件。  
  
 [PageSetupDialog 组件](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 说明使用<xref:System.Windows.Forms.PageSetupDialog>组件。  
  
 <xref:System.Drawing.Printing>  
 描述中的类<xref:System.Drawing.Printing>命名空间。
