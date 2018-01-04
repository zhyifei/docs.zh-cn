---
title: "FolderBrowserDialog 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26d2b6294a503edd25b499da2ab67739cdf87174
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="7d821-102">FolderBrowserDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="7d821-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="7d821-103">Windows 窗体<xref:System.Windows.Forms.FolderBrowserDialog>组件是模式对话框，用于浏览和选择文件夹。</span><span class="sxs-lookup"><span data-stu-id="7d821-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="7d821-104">此外可以在创建新文件夹<xref:System.Windows.Forms.FolderBrowserDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="7d821-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d821-105">若要选择文件，而不是文件夹，使用[OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)组件。</span><span class="sxs-lookup"><span data-stu-id="7d821-105">To select files, instead of folders, use the [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="7d821-106"><xref:System.Windows.Forms.FolderBrowserDialog>组件显示在运行的时使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="7d821-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="7d821-107">设置<xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>属性来确定最顶层文件夹，然后将显示对话框中的树视图中的任何子文件夹。</span><span class="sxs-lookup"><span data-stu-id="7d821-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="7d821-108">已显示对话框中之后, 你可以使用<xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>属性来获取所选的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="7d821-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="7d821-109">添加到窗体时<xref:System.Windows.Forms.FolderBrowserDialog>组件出现在 Windows 窗体设计器底部栏中。</span><span class="sxs-lookup"><span data-stu-id="7d821-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d821-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d821-110">See Also</span></span>  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [<span data-ttu-id="7d821-111">如何：使用 Windows 窗体 FolderBrowserDialog 组件选择文件夹</span><span class="sxs-lookup"><span data-stu-id="7d821-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)  
 [<span data-ttu-id="7d821-112">FolderBrowserDialog 组件</span><span class="sxs-lookup"><span data-stu-id="7d821-112">FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
