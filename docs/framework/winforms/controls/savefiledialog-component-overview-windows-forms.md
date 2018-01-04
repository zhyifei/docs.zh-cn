---
title: "SaveFileDialog 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1505e2bc31afb4f44f0d635b06624528cb16ba15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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
