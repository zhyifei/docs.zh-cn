---
title: PrintPreviewDialog 控件概述（Windows 窗体）
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aad8673051b22db1df6d525094394dd2a43285ca
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711273"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="3aafb-102">PrintPreviewDialog 控件概述 （Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="3aafb-102">PrintPreviewDialog control overview (Windows Forms)</span></span>
<span data-ttu-id="3aafb-103">Windows 窗体<xref:System.Windows.Forms.PrintPreviewDialog>控件是一个预配置的对话框，用于显示如何[PrintDocument](printdocument-component-windows-forms.md)打印时的显示。</span><span class="sxs-lookup"><span data-stu-id="3aafb-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="3aafb-104">为简单的解决方案，而不是配置你自己的对话框在基于 Windows 的应用程序中使用它。</span><span class="sxs-lookup"><span data-stu-id="3aafb-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="3aafb-105">该控件包含用于打印、放大、显示一页或多页以及关闭对话框的按钮。</span><span class="sxs-lookup"><span data-stu-id="3aafb-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="3aafb-106">键属性和方法</span><span class="sxs-lookup"><span data-stu-id="3aafb-106">Key properties and methods</span></span>  
 <span data-ttu-id="3aafb-107">控件的关键属性是<xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>，用于设置要预览的文档。</span><span class="sxs-lookup"><span data-stu-id="3aafb-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="3aafb-108">文档必须是<xref:System.Drawing.Printing.PrintDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="3aafb-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="3aafb-109">为了显示对话框中，您必须调用其<xref:System.Windows.Forms.Form.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="3aafb-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="3aafb-110">抗锯齿功能可以使文本显示更加顺利，但它还可以显示更慢;若要使用它，将设置<xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="3aafb-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="3aafb-111">某些属性是可通过<xref:System.Windows.Forms.PrintPreviewControl>的<xref:System.Windows.Forms.PrintPreviewDialog>包含。</span><span class="sxs-lookup"><span data-stu-id="3aafb-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="3aafb-112">(无需添加这<xref:System.Windows.Forms.PrintPreviewControl>向窗体; 它会自动包含在<xref:System.Windows.Forms.PrintPreviewDialog>向窗体添加对话框时。)可通过属性的示例<xref:System.Windows.Forms.PrintPreviewControl>都<xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>和<xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>属性，确定在控件上显示水平和垂直方向的页面数。</span><span class="sxs-lookup"><span data-stu-id="3aafb-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="3aafb-113">您可以访问<xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>属性设置为`PrintPreviewDialog1.PrintPreviewControl.Columns`在 Visual Basic`printPreviewDialog1.PrintPreviewControl.Columns`视觉对象中C#，或`printPreviewDialog1->PrintPreviewControl->Columns`中[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3aafb-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span></span>  
  
## <a name="printpreviewdialog-performance"></a><span data-ttu-id="3aafb-114">PrintPreviewDialog 性能</span><span class="sxs-lookup"><span data-stu-id="3aafb-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="3aafb-115">在以下情况下<xref:System.Windows.Forms.PrintPreviewDialog>控件初始化非常缓慢：</span><span class="sxs-lookup"><span data-stu-id="3aafb-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="3aafb-116">使用网络打印机。</span><span class="sxs-lookup"><span data-stu-id="3aafb-116">A network printer is used.</span></span>
- <span data-ttu-id="3aafb-117">修改此打印机，如双面打印设置的用户首选项。</span><span class="sxs-lookup"><span data-stu-id="3aafb-117">User preferences for this printer, such as duplex settings, are modified.</span></span>
  
<span data-ttu-id="3aafb-118">对于.NET Framework 4.5.2 上运行的应用程序，可以添加的以下关键\<appSettings > 配置文件来提高的性能的部分<xref:System.Windows.Forms.PrintPreviewDialog>控制初始化：</span><span class="sxs-lookup"><span data-stu-id="3aafb-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
<span data-ttu-id="3aafb-119">如果`EnablePrintPreviewOptimization`键设置为任何其他值，或如果密钥不存在，则不会应用优化。</span><span class="sxs-lookup"><span data-stu-id="3aafb-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="3aafb-120">对于.NET Framework 4.6 或更高版本上运行的应用程序，您可以添加到以下开关[ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)中的元素[\<运行时 >](../../configure-apps/file-schema/runtime/index.md)应用程序配置文件的部分：</span><span class="sxs-lookup"><span data-stu-id="3aafb-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
<span data-ttu-id="3aafb-121">如果交换机不存在，或者设置为任何其他值，则不会应用优化。</span><span class="sxs-lookup"><span data-stu-id="3aafb-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span> 

<span data-ttu-id="3aafb-122">如果您使用<xref:System.Drawing.Printing.PrintDocument.QueryPageSettings>要修改的打印机设置的性能事件<xref:System.Windows.Forms.PrintPreviewDialog>控件不会提高，即使设置优化配置开关。</span><span class="sxs-lookup"><span data-stu-id="3aafb-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3aafb-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="3aafb-123">See also</span></span>
- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="3aafb-124">PrintPreviewControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="3aafb-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="3aafb-125">PrintPreviewDialog 控件</span><span class="sxs-lookup"><span data-stu-id="3aafb-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="3aafb-126">对话框控件和组件</span><span class="sxs-lookup"><span data-stu-id="3aafb-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
