---
title: PageSetupDialog 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: 702e9a40652e00cc2f93dd52af29a61a50c90ae0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715797"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="3ab0c-102">PageSetupDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="3ab0c-102">PageSetupDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="3ab0c-103">Windows 窗体<xref:System.Windows.Forms.PageSetupDialog>组件是一个预配置的对话框，用于在基于 Windows 的应用程序中设置用于打印的页详细信息。</span><span class="sxs-lookup"><span data-stu-id="3ab0c-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="3ab0c-104">用于在基于 Windows 的应用程序中作为一个简单的解决方案为用户设置首选项而不是配置您自己的对话框。</span><span class="sxs-lookup"><span data-stu-id="3ab0c-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="3ab0c-105">可以使用户能够设置边框和边距调整、 页眉和页脚和纵向或横向布局。</span><span class="sxs-lookup"><span data-stu-id="3ab0c-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="3ab0c-106">利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3ab0c-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="3ab0c-107">键属性和方法</span><span class="sxs-lookup"><span data-stu-id="3ab0c-107">Key Properties and Methods</span></span>  
 <span data-ttu-id="3ab0c-108">使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法，以便在运行时显示对话框。</span><span class="sxs-lookup"><span data-stu-id="3ab0c-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="3ab0c-109">此组件具有可以设置与单个页面的属性 (<xref:System.Drawing.Printing.PrintDocument>类) 或任何文档 (<xref:System.Drawing.Printing.PageSettings>类)。</span><span class="sxs-lookup"><span data-stu-id="3ab0c-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="3ab0c-110">此外，<xref:System.Windows.Forms.PageSetupDialog>组件可用于确定特定的打印机设置，它们将存储在<xref:System.Drawing.Printing.PrinterSettings>类。</span><span class="sxs-lookup"><span data-stu-id="3ab0c-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>  
  
 <span data-ttu-id="3ab0c-111">添加到窗体时<xref:System.Windows.Forms.PageSetupDialog>组件在 Windows 窗体设计器底部的任务栏中显示。</span><span class="sxs-lookup"><span data-stu-id="3ab0c-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab0c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ab0c-112">See also</span></span>
- <xref:System.Windows.Forms.PageSetupDialog>
- [<span data-ttu-id="3ab0c-113">PageSetupDialog 组件</span><span class="sxs-lookup"><span data-stu-id="3ab0c-113">PageSetupDialog Component</span></span>](pagesetupdialog-component-windows-forms.md)
