---
title: "FolderBrowserDialog 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 26d2b6294a503edd25b499da2ab67739cdf87174
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>FolderBrowserDialog 组件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.FolderBrowserDialog>组件是模式对话框，用于浏览和选择文件夹。 此外可以在创建新文件夹<xref:System.Windows.Forms.FolderBrowserDialog>组件。  
  
> [!NOTE]
>  若要选择文件，而不是文件夹，使用[OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)组件。  
  
 <xref:System.Windows.Forms.FolderBrowserDialog>组件显示在运行的时使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。 设置<xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>属性来确定最顶层文件夹，然后将显示对话框中的树视图中的任何子文件夹。 已显示对话框中之后, 你可以使用<xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>属性来获取所选的文件夹的路径。  
  
 添加到窗体时<xref:System.Windows.Forms.FolderBrowserDialog>组件出现在 Windows 窗体设计器底部栏中。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [如何：使用 Windows 窗体 FolderBrowserDialog 组件选择文件夹](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)  
 [FolderBrowserDialog 组件](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
