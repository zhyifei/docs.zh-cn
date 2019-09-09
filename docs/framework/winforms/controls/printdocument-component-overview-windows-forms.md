---
title: PrintDocument 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 16a7f3a34ccb280f7bf91c52e29b20edc22130b9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928975"
---
# <a name="printdocument-component-overview-windows-forms"></a>PrintDocument 组件概述（Windows 窗体）

Windows 窗体 [PrintDocument](printdocument-component-windows-forms.md) 组件用于设置属性，这些属性描述在基于 Windows 的应用程序中要打印什么内容以及打印文档的能力。 此组件可与 [PrintDialog](printdialog-component-windows-forms.md) 组件一起使用，控制文档打印的各个方面。

## <a name="working-with-the-printdocument-component"></a>使用 PrintDocument 组件

涉及<xref:System.Drawing.Printing.PrintDocument>组件的两个主要方案是：

- 简单的打印作业，如打印单个文本文件。 在这种情况下，您需要<xref:System.Drawing.Printing.PrintDocument>将组件添加到 Windows 窗体中，然后添加<xref:System.Drawing.Printing.PrintDocument.PrintPage>在事件处理程序中打印文件的编程逻辑。 编程逻辑应形成<xref:System.Drawing.Printing.PrintDocument.Print%2A>用于打印文档的方法。 此方法将包含<xref:System.Drawing.Graphics> <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>在<xref:System.Drawing.Printing.PrintPageEventArgs>类的属性中的对象发送到打印机。 有关演示如何使用<xref:System.Drawing.Printing.PrintDocument>组件打印文本文档的示例，请参阅[如何：在 Windows 窗体](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)中打印多页文本文件。

- 更复杂的打印作业，如想要重新使用已编写的打印逻辑的情况。 在这种<xref:System.Drawing.Printing.PrintDocument>情况下，你将从组件派生新组件并重写（请[参阅对的](../../../visual-basic/language-reference/modifiers/overrides.md)Visual Basic 或[重写](../../../csharp/language-reference/keywords/override.md) C#） <xref:System.Drawing.Printing.PrintDocument.PrintPage>事件。

将该组件添加到窗体时， <xref:System.Drawing.Printing.PrintDocument>该组件将出现在 Visual Studio 中 Windows 窗体设计器底部的托盘中。

## <a name="see-also"></a>请参阅

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Windows 窗体打印支持](../advanced/windows-forms-print-support.md)
- [PrintDocument 组件](printdocument-component-windows-forms.md)
