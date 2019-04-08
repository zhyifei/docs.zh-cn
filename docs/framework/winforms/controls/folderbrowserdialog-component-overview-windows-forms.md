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
ms.openlocfilehash: aae18167b29c71ad692cc6ba447457cd079374b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074126"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="9b1bf-102">FolderBrowserDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="9b1bf-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="9b1bf-103">Windows 窗体<xref:System.Windows.Forms.FolderBrowserDialog>组件是一个模式对话框，用于浏览和选择文件夹。</span><span class="sxs-lookup"><span data-stu-id="9b1bf-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="9b1bf-104">此外可以在创建新文件夹<xref:System.Windows.Forms.FolderBrowserDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="9b1bf-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b1bf-105">若要选择文件，而不是文件夹，请使用[OpenFileDialog](openfiledialog-component-windows-forms.md)组件。</span><span class="sxs-lookup"><span data-stu-id="9b1bf-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="9b1bf-106"><xref:System.Windows.Forms.FolderBrowserDialog>组件，系统会在运行的时使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="9b1bf-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="9b1bf-107">设置<xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>属性来确定最顶层的文件夹，然后将对话框中的树视图中显示的任何子文件夹。</span><span class="sxs-lookup"><span data-stu-id="9b1bf-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="9b1bf-108">一旦已显示对话框中，可以使用<xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>属性以获取所选的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="9b1bf-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="9b1bf-109">添加到窗体时<xref:System.Windows.Forms.FolderBrowserDialog>组件在 Windows 窗体设计器底部的任务栏中显示。</span><span class="sxs-lookup"><span data-stu-id="9b1bf-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b1bf-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b1bf-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="9b1bf-111">如何：使用 Windows 窗体 FolderBrowserDialog 组件选择文件夹</span><span class="sxs-lookup"><span data-stu-id="9b1bf-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="9b1bf-112">FolderBrowserDialog 组件</span><span class="sxs-lookup"><span data-stu-id="9b1bf-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
