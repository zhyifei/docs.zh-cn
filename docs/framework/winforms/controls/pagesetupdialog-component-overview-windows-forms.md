---
title: "PageSetupDialog 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd2162cd2b538b5c6277991fab0ce40762f6c07d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>PageSetupDialog 组件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.PageSetupDialog>组件是一个预配置的对话框，用于在基于 Windows 的应用程序中设置用于打印的页面详细信息。 用于基于 Windows 的应用程序中作为简单的解决方案的用户设置替代配置自己对话框的页首选项。 你可以使用户能够设置边框和边距调整、 页眉和页脚和纵向或横向朝方向。 利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。  
  
## <a name="key-properties-and-methods"></a>键属性和方法  
 使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以在运行时显示的对话框。 此组件有的属性可以设置与单个页面 (<xref:System.Drawing.Printing.PrintDocument>类) 或任何文档 (<xref:System.Drawing.Printing.PageSettings>类)。 此外，<xref:System.Windows.Forms.PageSetupDialog>组件可以用于确定特定的打印机设置，它们将存储在<xref:System.Drawing.Printing.PrinterSettings>类。  
  
 添加到窗体时<xref:System.Windows.Forms.PageSetupDialog>组件出现在 Windows 窗体设计器底部栏中。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [PageSetupDialog 组件](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
