---
title: SaveFileDialog 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: ab8eb5409d017c6ea73a44e4e57ccec9cece4824
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631056"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="550a3-102">SaveFileDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="550a3-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="550a3-103">Windows 窗体 <xref:System.Windows.Forms.SaveFileDialog> 组件是一个预配置的对话框。</span><span class="sxs-lookup"><span data-stu-id="550a3-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="550a3-104">它是标准相同**保存文件**对话框中使用的 Windows。</span><span class="sxs-lookup"><span data-stu-id="550a3-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="550a3-105">它继承自 <xref:System.Windows.Forms.CommonDialog> 类。</span><span class="sxs-lookup"><span data-stu-id="550a3-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="550a3-106">使用 SaveFileDialog 组件</span><span class="sxs-lookup"><span data-stu-id="550a3-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="550a3-107">使用它作为一个简单的解决方案，使用户能够保存文件而不是配置你自己的对话框。</span><span class="sxs-lookup"><span data-stu-id="550a3-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="550a3-108">利用标准 Windows 对话框，您创建的应用程序的基本功能是立即为用户所熟悉。</span><span class="sxs-lookup"><span data-stu-id="550a3-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="550a3-109">但是，应注意，当使用<xref:System.Windows.Forms.SaveFileDialog>组件，您必须编写您自己保存文件的逻辑。</span><span class="sxs-lookup"><span data-stu-id="550a3-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="550a3-110">可以使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法，以便在运行时显示的对话框。</span><span class="sxs-lookup"><span data-stu-id="550a3-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="550a3-111">您可以打开文件中读/写模式下使用<xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="550a3-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="550a3-112">添加到窗体时<xref:System.Windows.Forms.SaveFileDialog>组件在 Windows 窗体设计器底部的任务栏中显示。</span><span class="sxs-lookup"><span data-stu-id="550a3-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="550a3-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="550a3-113">See also</span></span>
- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="550a3-114">SaveFileDialog 组件</span><span class="sxs-lookup"><span data-stu-id="550a3-114">SaveFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
