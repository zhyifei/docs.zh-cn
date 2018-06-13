---
title: 如何：显示 PrintDialog 组件
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: d8765187522f8becf24b519434b7c170c1c755b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532182"
---
# <a name="how-to-display-the-printdialog-component"></a>如何：显示 PrintDialog 组件
<xref:System.Windows.Forms.PrintDialog>组件是很多用户都将熟悉的标准 Windows 打印对话框。 因为你的用户将立即熟悉它，它可能会对你要使用有用<xref:System.Windows.Forms.PrintDialog>组件。  
  
### <a name="to-display-the-printdialog-component"></a>显示 PrintDialog 组件  
  
-   调用<xref:System.Windows.Forms.Form.ShowDialog%2A>从你的应用程序的代码中的方法。  
  
     显示出该组件后，用户可以与之进行交互，设置打印作业的属性。 这些保存在<!--zz <xref:System.Drawing.Printing.PrinterSetting>-->`PrinterSetting`类 (与<xref:System.Drawing.Printing.PageSettings>类，如果用户访问[PageSetupDialog 组件](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)通过<xref:System.Windows.Forms.PrintDialog>组件) 与该打印作业关联。 然后可以调用它们所设置的属性以确定打印作业的细节。  
  
## <a name="see-also"></a>请参阅  
 [如何：创建标准的 Windows 窗体打印作业](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [如何：在运行时从 PrintDialog 中捕获用户输入](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [PrintPreviewDialog 控件](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [PrintDialog 组件](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 [Windows 窗体打印支持](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)
