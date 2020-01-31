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
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="a6012-102">PrintPreviewDialog 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="a6012-102">PrintPreviewDialog control overview (Windows Forms)</span></span>

<span data-ttu-id="a6012-103">Windows 窗体 <xref:System.Windows.Forms.PrintPreviewDialog> 控件是一个预先配置的对话框，用于显示[PrintDocument](printdocument-component-windows-forms.md)在打印时的显示方式。</span><span class="sxs-lookup"><span data-stu-id="a6012-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="a6012-104">在基于 Windows 的应用程序中将其用作简单的解决方案，而不是配置自己的对话框。</span><span class="sxs-lookup"><span data-stu-id="a6012-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="a6012-105">该控件包含用于打印、放大、显示一页或多页以及关闭对话框的按钮。</span><span class="sxs-lookup"><span data-stu-id="a6012-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="a6012-106">键属性和方法</span><span class="sxs-lookup"><span data-stu-id="a6012-106">Key properties and methods</span></span>

<span data-ttu-id="a6012-107">控件的键属性为 <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>，这将设置要预览的文档。</span><span class="sxs-lookup"><span data-stu-id="a6012-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="a6012-108">文档必须是 <xref:System.Drawing.Printing.PrintDocument> 的对象。</span><span class="sxs-lookup"><span data-stu-id="a6012-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="a6012-109">若要显示该对话框，必须调用其 <xref:System.Windows.Forms.Form.ShowDialog%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="a6012-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="a6012-110">抗锯齿会使文本看起来更流畅，但也可以使显示速度变慢;若要使用它，请将 <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="a6012-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>

<span data-ttu-id="a6012-111">某些属性通过 <xref:System.Windows.Forms.PrintPreviewDialog> 包含的 <xref:System.Windows.Forms.PrintPreviewControl> 提供。</span><span class="sxs-lookup"><span data-stu-id="a6012-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="a6012-112">（无需将此 <xref:System.Windows.Forms.PrintPreviewControl> 添加到窗体中; 当您将对话框添加到窗体时，它将自动包含在 <xref:System.Windows.Forms.PrintPreviewDialog> 中。）通过 <xref:System.Windows.Forms.PrintPreviewControl> 提供的属性示例包括 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 和 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 属性，这些属性确定控件上水平和垂直显示的页数。</span><span class="sxs-lookup"><span data-stu-id="a6012-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="a6012-113">可以在 Visual Basic 中以 `PrintPreviewDialog1.PrintPreviewControl.Columns` 的形式访问 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 属性，`printPreviewDialog1.PrintPreviewControl.Columns` 在C#`printPreviewDialog1->PrintPreviewControl->Columns` 视觉对象中访问C++。</span><span class="sxs-lookup"><span data-stu-id="a6012-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span></span>

## <a name="printpreviewdialog-performance"></a><span data-ttu-id="a6012-114">PrintPreviewDialog 性能</span><span class="sxs-lookup"><span data-stu-id="a6012-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="a6012-115">在以下情况下，<xref:System.Windows.Forms.PrintPreviewDialog> 控件的初始化速度非常慢：</span><span class="sxs-lookup"><span data-stu-id="a6012-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="a6012-116">使用网络打印机。</span><span class="sxs-lookup"><span data-stu-id="a6012-116">A network printer is used.</span></span>
- <span data-ttu-id="a6012-117">此打印机的用户首选项（如双工设置）会被修改。</span><span class="sxs-lookup"><span data-stu-id="a6012-117">User preferences for this printer, such as duplex settings, are modified.</span></span>

<span data-ttu-id="a6012-118">对于在 .NET Framework 4.5.2 上运行的应用，你可以将以下项添加到配置文件的 \<appSettings > 部分，以提高 <xref:System.Windows.Forms.PrintPreviewDialog> 控件初始化的性能：</span><span class="sxs-lookup"><span data-stu-id="a6012-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

<span data-ttu-id="a6012-119">如果 `EnablePrintPreviewOptimization` 项设置为任何其他值，或者如果该键不存在，则不会应用优化。</span><span class="sxs-lookup"><span data-stu-id="a6012-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="a6012-120">对于在 .NET Framework 4.6 或更高版本上运行的应用，你可以将以下开关添加到应用配置文件的[\<运行时 >](../../configure-apps/file-schema/runtime/index.md)部分中的[\<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)元素：</span><span class="sxs-lookup"><span data-stu-id="a6012-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

<span data-ttu-id="a6012-121">如果此开关不存在或者设置为任何其他值，则不会应用优化。</span><span class="sxs-lookup"><span data-stu-id="a6012-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span>

<span data-ttu-id="a6012-122">如果使用 <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> 事件来修改打印机设置，即使设置了优化配置开关，<xref:System.Windows.Forms.PrintPreviewDialog> 控件的性能也不会提高。</span><span class="sxs-lookup"><span data-stu-id="a6012-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6012-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6012-123">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="a6012-124">PrintPreviewControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="a6012-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="a6012-125">PrintPreviewDialog 控件</span><span class="sxs-lookup"><span data-stu-id="a6012-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="a6012-126">对话框控件和组件</span><span class="sxs-lookup"><span data-stu-id="a6012-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
