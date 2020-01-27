---
title: OpenFileDialog 组件概述
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: c519b373150a49ee41dbb0c503f7d5a4862477d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728435"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>OpenFileDialog 组件概述（Windows 窗体）

Windows 窗体 <xref:System.Windows.Forms.OpenFileDialog> 组件是一个预配置的对话框。 它与 Windows 操作系统公开的 "**打开文件**" 对话框相同。 它继承自 <xref:System.Windows.Forms.CommonDialog> 类。

## <a name="use-this-component"></a>使用此组件

在基于 Windows 的应用程序中使用此组件，就是一个用于选择文件的简单解决方案，而不是配置自己的对话框。 利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。 但请注意，在使用 <xref:System.Windows.Forms.OpenFileDialog> 组件时，必须编写自己的文件打开逻辑。

使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法可在运行时显示该对话框。 可以让用户使用 <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> 属性打开多选文件。 此外，您还可以使用 "<xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A>" 属性来确定对话框中是否显示了只读复选框。 <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> 属性指示是否选中只读复选框。 最后，<xref:System.Windows.Forms.FileDialog.Filter%2A> 属性设置当前文件名筛选器字符串，该字符串确定对话框中 "文件类型" 框中显示的选项。

将其添加到窗体时，<xref:System.Windows.Forms.OpenFileDialog> 组件会显示在 Visual Studio 中 Windows 窗体设计器底部的托盘中。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog 组件](openfiledialog-component-windows-forms.md)
