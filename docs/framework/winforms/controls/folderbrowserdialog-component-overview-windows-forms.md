---
title: FolderBrowserDialog 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: ce449937b89c686c868dcf337f46f1816d08d191
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717657"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="52b25-102">FolderBrowserDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="52b25-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="52b25-103">Windows 窗体<xref:System.Windows.Forms.FolderBrowserDialog>组件是一个模式对话框，用于浏览和选择文件夹。</span><span class="sxs-lookup"><span data-stu-id="52b25-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="52b25-104">此外可以在创建新文件夹<xref:System.Windows.Forms.FolderBrowserDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="52b25-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52b25-105">若要选择文件，而不是文件夹，请使用[OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)组件。</span><span class="sxs-lookup"><span data-stu-id="52b25-105">To select files, instead of folders, use the [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="52b25-106"><xref:System.Windows.Forms.FolderBrowserDialog>组件，系统会在运行的时使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="52b25-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="52b25-107">设置<xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>属性来确定最顶层的文件夹，然后将对话框中的树视图中显示的任何子文件夹。</span><span class="sxs-lookup"><span data-stu-id="52b25-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="52b25-108">一旦已显示对话框中，可以使用<xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>属性以获取所选的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="52b25-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="52b25-109">添加到窗体时<xref:System.Windows.Forms.FolderBrowserDialog>组件在 Windows 窗体设计器底部的任务栏中显示。</span><span class="sxs-lookup"><span data-stu-id="52b25-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52b25-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="52b25-110">See also</span></span>
- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="52b25-111">如何：选择使用 Windows 窗体 FolderBrowserDialog 组件的文件夹</span><span class="sxs-lookup"><span data-stu-id="52b25-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="52b25-112">FolderBrowserDialog 组件</span><span class="sxs-lookup"><span data-stu-id="52b25-112">FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
