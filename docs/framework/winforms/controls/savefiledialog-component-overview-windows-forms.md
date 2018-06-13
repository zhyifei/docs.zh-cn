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
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="e23d7-102">SaveFileDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="e23d7-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="e23d7-103">Windows 窗体 <xref:System.Windows.Forms.SaveFileDialog> 组件是一个预配置的对话框。</span><span class="sxs-lookup"><span data-stu-id="e23d7-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="e23d7-104">它等同于标准**保存文件**Windows 使用的对话框。</span><span class="sxs-lookup"><span data-stu-id="e23d7-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="e23d7-105">它继承自 <xref:System.Windows.Forms.CommonDialog> 类。</span><span class="sxs-lookup"><span data-stu-id="e23d7-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="e23d7-106">使用 SaveFileDialog 组件</span><span class="sxs-lookup"><span data-stu-id="e23d7-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="e23d7-107">使用它作为简单的解决方案，使用户能够保存而不是配置对话框中的文件。</span><span class="sxs-lookup"><span data-stu-id="e23d7-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="e23d7-108">利用标准的 Windows 对话框，你创建的应用程序的基本功能可立即为用户熟悉。</span><span class="sxs-lookup"><span data-stu-id="e23d7-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="e23d7-109">但是，应注意，当使用<xref:System.Windows.Forms.SaveFileDialog>组件，你必须编写您自己的文件保存逻辑。</span><span class="sxs-lookup"><span data-stu-id="e23d7-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="e23d7-110">你可以使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以在运行时显示的对话框。</span><span class="sxs-lookup"><span data-stu-id="e23d7-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="e23d7-111">你可以打开一个文件中读/写模式下使用<xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e23d7-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="e23d7-112">添加到窗体时<xref:System.Windows.Forms.SaveFileDialog>组件出现在 Windows 窗体设计器底部栏中。</span><span class="sxs-lookup"><span data-stu-id="e23d7-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e23d7-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e23d7-113">See Also</span></span>  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [<span data-ttu-id="e23d7-114">SaveFileDialog 组件</span><span class="sxs-lookup"><span data-stu-id="e23d7-114">SaveFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
