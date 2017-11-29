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
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="dc0cf-102">OpenFileDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="dc0cf-102">OpenFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="dc0cf-103">Windows 窗体 <xref:System.Windows.Forms.OpenFileDialog> 组件是一个预配置的对话框。</span><span class="sxs-lookup"><span data-stu-id="dc0cf-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="dc0cf-104">相同**打开的文件**公开的 Windows 操作系统的对话框。</span><span class="sxs-lookup"><span data-stu-id="dc0cf-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="dc0cf-105">它继承自 <xref:System.Windows.Forms.CommonDialog> 类。</span><span class="sxs-lookup"><span data-stu-id="dc0cf-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="using-this-component"></a><span data-ttu-id="dc0cf-106">使用此组件</span><span class="sxs-lookup"><span data-stu-id="dc0cf-106">Using this Component</span></span>  
 <span data-ttu-id="dc0cf-107">将基于 Windows 的应用程序中的此组件作为简单的解决方案的文件选择替代配置自己对话框。</span><span class="sxs-lookup"><span data-stu-id="dc0cf-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="dc0cf-108">利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。</span><span class="sxs-lookup"><span data-stu-id="dc0cf-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="dc0cf-109">但是，应注意，当使用<xref:System.Windows.Forms.OpenFileDialog>组件，你必须编写打开文件的逻辑。</span><span class="sxs-lookup"><span data-stu-id="dc0cf-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>  
  
 <span data-ttu-id="dc0cf-110">使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以在运行时显示的对话框。</span><span class="sxs-lookup"><span data-stu-id="dc0cf-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="dc0cf-111">你可以让用户选择多个文件以使用打开到<xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="dc0cf-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="dc0cf-112">此外，你可以使用<xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A>属性来确定是否在对话框中显示只读复选框。</span><span class="sxs-lookup"><span data-stu-id="dc0cf-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="dc0cf-113"><xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A>属性指示是否选定只读复选框。</span><span class="sxs-lookup"><span data-stu-id="dc0cf-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="dc0cf-114">最后，<xref:System.Windows.Forms.FileDialog.Filter%2A>属性设置当前文件名称筛选器字符串，用于确定在对话框中的"文件类型"框中出现的选择。</span><span class="sxs-lookup"><span data-stu-id="dc0cf-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>  
  
 <span data-ttu-id="dc0cf-115">添加到窗体时<xref:System.Windows.Forms.OpenFileDialog>组件出现在 Windows 窗体设计器底部栏中。</span><span class="sxs-lookup"><span data-stu-id="dc0cf-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc0cf-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc0cf-116">See Also</span></span>  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [<span data-ttu-id="dc0cf-117">OpenFileDialog 组件</span><span class="sxs-lookup"><span data-stu-id="dc0cf-117">OpenFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
