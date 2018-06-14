---
title: PrintDialog 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0b0e516364277133efc83e7324345ccea8328690
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535484"
---
# <a name="printdialog-component-overview-windows-forms"></a>PrintDialog 组件概述（Windows 窗体）
Windows 窗体[PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)组件是一个预配置的对话框，用于选择打印机、 选择要打印的页以及确定基于 Windows 的应用程序中的其他与打印相关设置。 将该组件用作选择打印机和打印相关设置的简单解决方案，而不用配置你自己的对话框。 你可以使用户能够打印文档的很多部分： 全部打印、 打印选定的页范围或打印选定内容。 利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。 <xref:System.Windows.Forms.PrintDialog>组件继承自<xref:System.Windows.Forms.CommonDialog>类。  
  
## <a name="working-with-the-component"></a>使用该组件  
 使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以在运行时显示的对话框。 此组件具有与单个的打印作业的属性 (<xref:System.Drawing.Printing.PrintDocument>类) 或各个打印机的设置 (<xref:System.Drawing.Printing.PrinterSettings>类)。 其中一种，反过来，可能由多个打印机共享。  
  
 添加到窗体时<xref:System.Windows.Forms.PrintDialog>组件出现在 Windows 窗体设计器底部栏中。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.PrintDialog>  
 [PrintDialog 组件](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
