---
title: "PrintDialog 组件概述（Windows 窗体）"
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
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b90d94165de6985b43d47809ae57bfcae204f0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="b7f9d-102">PrintDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="b7f9d-102">PrintDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="b7f9d-103">Windows 窗体[PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)组件是一个预配置的对话框，用于选择打印机、 选择要打印的页以及确定基于 Windows 的应用程序中的其他与打印相关设置。</span><span class="sxs-lookup"><span data-stu-id="b7f9d-103">The Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="b7f9d-104">将该组件用作选择打印机和打印相关设置的简单解决方案，而不用配置你自己的对话框。</span><span class="sxs-lookup"><span data-stu-id="b7f9d-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="b7f9d-105">你可以使用户能够打印文档的很多部分： 全部打印、 打印选定的页范围或打印选定内容。</span><span class="sxs-lookup"><span data-stu-id="b7f9d-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="b7f9d-106">利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7f9d-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="b7f9d-107"><xref:System.Windows.Forms.PrintDialog>组件继承自<xref:System.Windows.Forms.CommonDialog>类。</span><span class="sxs-lookup"><span data-stu-id="b7f9d-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-component"></a><span data-ttu-id="b7f9d-108">使用该组件</span><span class="sxs-lookup"><span data-stu-id="b7f9d-108">Working with the Component</span></span>  
 <span data-ttu-id="b7f9d-109">使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以在运行时显示的对话框。</span><span class="sxs-lookup"><span data-stu-id="b7f9d-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="b7f9d-110">此组件具有与单个的打印作业的属性 (<xref:System.Drawing.Printing.PrintDocument>类) 或各个打印机的设置 (<xref:System.Drawing.Printing.PrinterSettings>类)。</span><span class="sxs-lookup"><span data-stu-id="b7f9d-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="b7f9d-111">其中一种，反过来，可能由多个打印机共享。</span><span class="sxs-lookup"><span data-stu-id="b7f9d-111">Either of these, in turn, may be shared by multiple printers.</span></span>  
  
 <span data-ttu-id="b7f9d-112">添加到窗体时<xref:System.Windows.Forms.PrintDialog>组件出现在 Windows 窗体设计器底部栏中。</span><span class="sxs-lookup"><span data-stu-id="b7f9d-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f9d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7f9d-113">See Also</span></span>  
 <xref:System.Windows.Forms.PrintDialog>  
 [<span data-ttu-id="b7f9d-114">PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="b7f9d-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
