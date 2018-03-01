---
title: "PageSetupDialog 组件概述（Windows 窗体）"
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
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dd2162cd2b538b5c6277991fab0ce40762f6c07d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="c9458-102">PageSetupDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="c9458-102">PageSetupDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="c9458-103">Windows 窗体<xref:System.Windows.Forms.PageSetupDialog>组件是一个预配置的对话框，用于在基于 Windows 的应用程序中设置用于打印的页面详细信息。</span><span class="sxs-lookup"><span data-stu-id="c9458-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="c9458-104">用于基于 Windows 的应用程序中作为简单的解决方案的用户设置替代配置自己对话框的页首选项。</span><span class="sxs-lookup"><span data-stu-id="c9458-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="c9458-105">你可以使用户能够设置边框和边距调整、 页眉和页脚和纵向或横向朝方向。</span><span class="sxs-lookup"><span data-stu-id="c9458-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="c9458-106">利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c9458-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="c9458-107">键属性和方法</span><span class="sxs-lookup"><span data-stu-id="c9458-107">Key Properties and Methods</span></span>  
 <span data-ttu-id="c9458-108">使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以在运行时显示的对话框。</span><span class="sxs-lookup"><span data-stu-id="c9458-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="c9458-109">此组件有的属性可以设置与单个页面 (<xref:System.Drawing.Printing.PrintDocument>类) 或任何文档 (<xref:System.Drawing.Printing.PageSettings>类)。</span><span class="sxs-lookup"><span data-stu-id="c9458-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="c9458-110">此外，<xref:System.Windows.Forms.PageSetupDialog>组件可以用于确定特定的打印机设置，它们将存储在<xref:System.Drawing.Printing.PrinterSettings>类。</span><span class="sxs-lookup"><span data-stu-id="c9458-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>  
  
 <span data-ttu-id="c9458-111">添加到窗体时<xref:System.Windows.Forms.PageSetupDialog>组件出现在 Windows 窗体设计器底部栏中。</span><span class="sxs-lookup"><span data-stu-id="c9458-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9458-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9458-112">See Also</span></span>  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [<span data-ttu-id="c9458-113">PageSetupDialog 组件</span><span class="sxs-lookup"><span data-stu-id="c9458-113">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
