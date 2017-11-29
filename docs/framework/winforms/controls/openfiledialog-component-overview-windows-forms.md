---
title: "OpenFileDialog 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35c947e3efbb9b2e5df775f83ffc6068e49c84e8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="openfiledialog-component-overview-windows-forms"></a>OpenFileDialog 组件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.OpenFileDialog> 组件是一个预配置的对话框。 相同**打开的文件**公开的 Windows 操作系统的对话框。 它继承自 <xref:System.Windows.Forms.CommonDialog> 类。  
  
## <a name="using-this-component"></a>使用此组件  
 将基于 Windows 的应用程序中的此组件作为简单的解决方案的文件选择替代配置自己对话框。 利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。 但是，应注意，当使用<xref:System.Windows.Forms.OpenFileDialog>组件，你必须编写打开文件的逻辑。  
  
 使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以在运行时显示的对话框。 你可以让用户选择多个文件以使用打开到<xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A>属性。 此外，你可以使用<xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A>属性来确定是否在对话框中显示只读复选框。 <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A>属性指示是否选定只读复选框。 最后，<xref:System.Windows.Forms.FileDialog.Filter%2A>属性设置当前文件名称筛选器字符串，用于确定在对话框中的"文件类型"框中出现的选择。  
  
 添加到窗体时<xref:System.Windows.Forms.OpenFileDialog>组件出现在 Windows 窗体设计器底部栏中。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [OpenFileDialog 组件](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
