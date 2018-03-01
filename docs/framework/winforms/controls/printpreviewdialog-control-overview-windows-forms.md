---
title: "PrintPreviewDialog 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 01/08/2018
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1228a3cf39ea412cde341c4c4b8b83e0ab2f0299
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2018
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>PrintPreviewDialog 控件概述 （Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.PrintPreviewDialog>控件是一个预配置的对话框，用于显示如何[PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)打印时将显示。 中基于 Windows 的应用程序而不是配置自己对话框的简单解决方案，使用它。 该控件包含用于打印、放大、显示一页或多页以及关闭对话框的按钮。  
  
## <a name="key-properties-and-methods"></a>键属性和方法  
 控件的键属性是<xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>，这会设置要预览的文档。 文档必须是<xref:System.Drawing.Printing.PrintDocument>对象。 若要显示对话框中，您必须调用其<xref:System.Windows.Forms.Form.ShowDialog%2A>方法。 抗锯齿可以使文本显示生成更平滑的但它还可显示更慢;若要使用它，将设置<xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A>属性`true`。  
  
 某些属性均可通过<xref:System.Windows.Forms.PrintPreviewControl>，<xref:System.Windows.Forms.PrintPreviewDialog>包含。 (无需添加此<xref:System.Windows.Forms.PrintPreviewControl>到窗体; 它会自动包含在<xref:System.Windows.Forms.PrintPreviewDialog>向窗体添加对话框时。)可通过属性的示例<xref:System.Windows.Forms.PrintPreviewControl>是<xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>和<xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>属性，这些扩展名决定了水平和垂直显示在控件上的页面数。 你可以访问<xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>属性作为`PrintPreviewDialog1.PrintPreviewControl.Columns`中[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]，`printPreviewDialog1.PrintPreviewControl.Columns`中[!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]，或`printPreviewDialog1->PrintPreviewControl->Columns`中[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]。  
  
## <a name="printpreviewdialog-performance"></a>PrintPreviewDialog 性能

在以下情况下<xref:System.Windows.Forms.PrintPreviewDialog>控件非常缓慢初始化：

- 使用网络打印机。
- 修改此打印机，例如双工设置的用户首选项。
  
对于.NET Framework 4.5.2 上运行的应用，你可以添加到以下项\<appSettings > 你的配置文件以改进性能部分<xref:System.Windows.Forms.PrintPreviewDialog>控制初始化：

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
如果`EnablePrintPreviewOptimization`键设置为任何其他值，或如果该键不存在，则不会应用优化。

对于在.NET Framework 4.6 或更高版本上运行的应用程序，你可以添加以下切换到[ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)中的元素[\<运行时 >](../../configure-apps/file-schema/runtime/index.md)你的应用配置文件的部分内容：

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
如果交换机不存在，或者设置为任何其他值，则不会应用优化。 

如果你使用<xref:System.Drawing.Printing.PrintDocument.QueryPageSettings>要修改的打印机设置的性能事件<xref:System.Windows.Forms.PrintPreviewDialog>控件不会提高，即使设置优化配置开关。  

## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [PrintPreviewControl 控件概述](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [PrintPreviewDialog 控件](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [对话框控件和组件](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
