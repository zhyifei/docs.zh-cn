---
title: PageSetupDialog 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744339"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>PageSetupDialog 구성 요소 개요(Windows Forms)

Windows 窗体 <xref:System.Windows.Forms.PageSetupDialog> 组件是一个预先配置的对话框，用于在基于 Windows 的应用程序中设置用于打印的页面详细信息。 在基于 Windows 的应用程序中使用它作为一种简单的解决方案，用户可以使用它来设置页面首选项，而不是配置自己的对话框。 可以让用户设置边框和边距调整、页眉和页脚以及纵向或横向方向。 표준 Windows 대화 상자를 사용하여 기본 기능이 사용자에게 익숙한 애플리케이션을 만듭니다.

## <a name="key-properties-and-methods"></a>键属性和方法

使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法可在运行时显示该对话框。 此组件具有与单页（<xref:System.Drawing.Printing.PrintDocument> 类）或任何文档（<xref:System.Drawing.Printing.PageSettings> 类）相关的属性。 此外，<xref:System.Windows.Forms.PageSetupDialog> 组件可用于确定存储在 <xref:System.Drawing.Printing.PrinterSettings> 类中的特定打印机设置。

将其添加到窗体时，<xref:System.Windows.Forms.PageSetupDialog> 组件会显示在 Visual Studio 中 Windows 窗体设计器底部的托盘中。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.PageSetupDialog>
- [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md)
