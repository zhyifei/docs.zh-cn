---
title: PrintPreviewDialog 控件概述
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: 6fb971493336cda1e04c720dd09147e650918c3a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741409"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>PrintPreviewDialog 控件概述（Windows 窗体）

Windows 窗体 <xref:System.Windows.Forms.PrintPreviewDialog> 控件是一个预先配置的对话框，用于显示[PrintDocument](printdocument-component-windows-forms.md)在打印时的显示方式。 在基于 Windows 的应用程序中将其用作简单的解决方案，而不是配置自己的对话框。 该控件包含用于打印、放大、显示一页或多页以及关闭对话框的按钮。

## <a name="key-properties-and-methods"></a>键属性和方法

控件的键属性为 <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>，这将设置要预览的文档。 文档必须是 <xref:System.Drawing.Printing.PrintDocument> 的对象。 若要显示该对话框，必须调用其 <xref:System.Windows.Forms.Form.ShowDialog%2A> 方法。 抗锯齿会使文本看起来更流畅，但也可以使显示速度变慢;若要使用它，请将 <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> 属性设置为 `true`。

某些属性通过 <xref:System.Windows.Forms.PrintPreviewDialog> 包含的 <xref:System.Windows.Forms.PrintPreviewControl> 提供。 （无需将此 <xref:System.Windows.Forms.PrintPreviewControl> 添加到窗体中; 当您将对话框添加到窗体时，它将自动包含在 <xref:System.Windows.Forms.PrintPreviewDialog> 中。）通过 <xref:System.Windows.Forms.PrintPreviewControl> 提供的属性示例包括 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 和 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 属性，这些属性确定控件上水平和垂直显示的页数。 可以在 Visual Basic 中以 `PrintPreviewDialog1.PrintPreviewControl.Columns` 的形式访问 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 属性，`printPreviewDialog1.PrintPreviewControl.Columns` 在C#`printPreviewDialog1->PrintPreviewControl->Columns` 视觉对象中访问C++。

## <a name="printpreviewdialog-performance"></a>PrintPreviewDialog 性能

在以下情况下，<xref:System.Windows.Forms.PrintPreviewDialog> 控件的初始化速度非常慢：

- 使用网络打印机。
- 此打印机的用户首选项（如双工设置）会被修改。

对于在 .NET Framework 4.5.2 上运行的应用，你可以将以下项添加到配置文件的 \<appSettings > 部分，以提高 <xref:System.Windows.Forms.PrintPreviewDialog> 控件初始化的性能：

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

如果 `EnablePrintPreviewOptimization` 项设置为任何其他值，或者如果该键不存在，则不会应用优化。

对于在 .NET Framework 4.6 或更高版本上运行的应用，你可以将以下开关添加到应用配置文件的[\<运行时 >](../../configure-apps/file-schema/runtime/index.md)部分中的[\<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)元素：

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

如果此开关不存在或者设置为任何其他值，则不会应用优化。

如果使用 <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> 事件来修改打印机设置，即使设置了优化配置开关，<xref:System.Windows.Forms.PrintPreviewDialog> 控件的性能也不会提高。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [PrintPreviewControl 控件概述](printpreviewcontrol-control-overview-windows-forms.md)
- [PrintPreviewDialog 控件](printpreviewdialog-control-windows-forms.md)
- [对话框控件和组件](dialog-box-controls-and-components-windows-forms.md)
