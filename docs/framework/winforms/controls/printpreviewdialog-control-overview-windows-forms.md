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
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="c49cb-102">PrintPreviewDialog 控件概述 （Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="c49cb-102">PrintPreviewDialog control overview (Windows Forms)</span></span>
<span data-ttu-id="c49cb-103">Windows 窗体<xref:System.Windows.Forms.PrintPreviewDialog>控件是一个预配置的对话框，用于显示如何[PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)打印时将显示。</span><span class="sxs-lookup"><span data-stu-id="c49cb-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="c49cb-104">中基于 Windows 的应用程序而不是配置自己对话框的简单解决方案，使用它。</span><span class="sxs-lookup"><span data-stu-id="c49cb-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="c49cb-105">该控件包含用于打印、放大、显示一页或多页以及关闭对话框的按钮。</span><span class="sxs-lookup"><span data-stu-id="c49cb-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="c49cb-106">键属性和方法</span><span class="sxs-lookup"><span data-stu-id="c49cb-106">Key properties and methods</span></span>  
 <span data-ttu-id="c49cb-107">控件的键属性是<xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>，这会设置要预览的文档。</span><span class="sxs-lookup"><span data-stu-id="c49cb-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="c49cb-108">文档必须是<xref:System.Drawing.Printing.PrintDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="c49cb-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="c49cb-109">若要显示对话框中，您必须调用其<xref:System.Windows.Forms.Form.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="c49cb-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="c49cb-110">抗锯齿可以使文本显示生成更平滑的但它还可显示更慢;若要使用它，将设置<xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="c49cb-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="c49cb-111">某些属性均可通过<xref:System.Windows.Forms.PrintPreviewControl>，<xref:System.Windows.Forms.PrintPreviewDialog>包含。</span><span class="sxs-lookup"><span data-stu-id="c49cb-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="c49cb-112">(无需添加此<xref:System.Windows.Forms.PrintPreviewControl>到窗体; 它会自动包含在<xref:System.Windows.Forms.PrintPreviewDialog>向窗体添加对话框时。)可通过属性的示例<xref:System.Windows.Forms.PrintPreviewControl>是<xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>和<xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>属性，这些扩展名决定了水平和垂直显示在控件上的页面数。</span><span class="sxs-lookup"><span data-stu-id="c49cb-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="c49cb-113">你可以访问<xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>属性作为`PrintPreviewDialog1.PrintPreviewControl.Columns`中[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]，`printPreviewDialog1.PrintPreviewControl.Columns`中[!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]，或`printPreviewDialog1->PrintPreviewControl->Columns`中[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c49cb-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], or `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span></span>  
  
## <a name="printpreviewdialog-performance"></a><span data-ttu-id="c49cb-114">PrintPreviewDialog 性能</span><span class="sxs-lookup"><span data-stu-id="c49cb-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="c49cb-115">在以下情况下<xref:System.Windows.Forms.PrintPreviewDialog>控件非常缓慢初始化：</span><span class="sxs-lookup"><span data-stu-id="c49cb-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="c49cb-116">使用网络打印机。</span><span class="sxs-lookup"><span data-stu-id="c49cb-116">A network printer is used.</span></span>
- <span data-ttu-id="c49cb-117">修改此打印机，例如双工设置的用户首选项。</span><span class="sxs-lookup"><span data-stu-id="c49cb-117">User preferences for this printer, such as duplex settings, are modified.</span></span>
  
<span data-ttu-id="c49cb-118">对于.NET Framework 4.5.2 上运行的应用，你可以添加到以下项\<appSettings > 你的配置文件以改进性能部分<xref:System.Windows.Forms.PrintPreviewDialog>控制初始化：</span><span class="sxs-lookup"><span data-stu-id="c49cb-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
<span data-ttu-id="c49cb-119">如果`EnablePrintPreviewOptimization`键设置为任何其他值，或如果该键不存在，则不会应用优化。</span><span class="sxs-lookup"><span data-stu-id="c49cb-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="c49cb-120">对于在.NET Framework 4.6 或更高版本上运行的应用程序，你可以添加以下切换到[ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)中的元素[\<运行时 >](../../configure-apps/file-schema/runtime/index.md)你的应用配置文件的部分内容：</span><span class="sxs-lookup"><span data-stu-id="c49cb-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
<span data-ttu-id="c49cb-121">如果交换机不存在，或者设置为任何其他值，则不会应用优化。</span><span class="sxs-lookup"><span data-stu-id="c49cb-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span> 

<span data-ttu-id="c49cb-122">如果你使用<xref:System.Drawing.Printing.PrintDocument.QueryPageSettings>要修改的打印机设置的性能事件<xref:System.Windows.Forms.PrintPreviewDialog>控件不会提高，即使设置优化配置开关。</span><span class="sxs-lookup"><span data-stu-id="c49cb-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c49cb-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="c49cb-123">See also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [<span data-ttu-id="c49cb-124">PrintPreviewControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="c49cb-124">PrintPreviewControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="c49cb-125">PrintPreviewDialog 控件</span><span class="sxs-lookup"><span data-stu-id="c49cb-125">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="c49cb-126">对话框控件和组件</span><span class="sxs-lookup"><span data-stu-id="c49cb-126">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
