---
title: PrintDocument 组件概述
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: a82cc0cdcb8cfae796c9c6bf60ab73873f85a291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728539"
---
# <a name="printdocument-component-overview-windows-forms"></a>PrintDocument 组件概述（Windows 窗体）

Windows 窗体 [PrintDocument](printdocument-component-windows-forms.md) 组件用于设置属性，这些属性描述在基于 Windows 的应用程序中要打印什么内容以及打印文档的能力。 此组件可与 [PrintDialog](printdialog-component-windows-forms.md) 组件一起使用，控制文档打印的各个方面。

## <a name="working-with-the-printdocument-component"></a>使用 PrintDocument 组件

涉及 <xref:System.Drawing.Printing.PrintDocument> 组件的两个主要方案是：

- 简单的打印作业，如打印单个文本文件。 在这种情况下，您需要将 <xref:System.Drawing.Printing.PrintDocument> 组件添加到 Windows 窗体中，然后添加在 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件处理程序中打印文件的编程逻辑。 编程逻辑应形成与 <xref:System.Drawing.Printing.PrintDocument.Print%2A> 方法一起打印文档。 此方法将包含在 <xref:System.Drawing.Printing.PrintPageEventArgs> 类的 <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> 属性中的 <xref:System.Drawing.Graphics> 对象发送到打印机。 有关演示如何使用 <xref:System.Drawing.Printing.PrintDocument> 组件打印文本文档的示例，请参阅[如何：在 Windows 窗体中打印多页文本文件](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)。

- 更复杂的打印作业，如想要重新使用已编写的打印逻辑的情况。 在这种情况下，你将从 <xref:System.Drawing.Printing.PrintDocument> 组件派生新的组件并重写（请参阅 Visual Basic 或[替代](../../../csharp/language-reference/keywords/override.md)的C#[替代](../../../visual-basic/language-reference/modifiers/overrides.md)） <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件。

将其添加到窗体时，<xref:System.Drawing.Printing.PrintDocument> 组件会显示在 Visual Studio 中 Windows 窗体设计器底部的托盘中。

## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Windows 窗体打印支持](../advanced/windows-forms-print-support.md)
- [PrintDocument 组件](printdocument-component-windows-forms.md)
