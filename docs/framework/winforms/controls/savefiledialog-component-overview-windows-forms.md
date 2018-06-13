---
title: SaveFileDialog 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: be5f70e2e8b0d5143ef387819689ce95564a72d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537442"
---
# <a name="savefiledialog-component-overview-windows-forms"></a>SaveFileDialog 组件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.SaveFileDialog> 组件是一个预配置的对话框。 它等同于标准**保存文件**Windows 使用的对话框。 它继承自 <xref:System.Windows.Forms.CommonDialog> 类。  
  
## <a name="working-with-the-savefiledialog-component"></a>使用 SaveFileDialog 组件  
 使用它作为简单的解决方案，使用户能够保存而不是配置对话框中的文件。 利用标准的 Windows 对话框，你创建的应用程序的基本功能可立即为用户熟悉。 但是，应注意，当使用<xref:System.Windows.Forms.SaveFileDialog>组件，你必须编写您自己的文件保存逻辑。  
  
 你可以使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以在运行时显示的对话框。 你可以打开一个文件中读/写模式下使用<xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>方法。  
  
 添加到窗体时<xref:System.Windows.Forms.SaveFileDialog>组件出现在 Windows 窗体设计器底部栏中。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [SaveFileDialog 组件](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
