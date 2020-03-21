---
title: 如何：使用 OpenFileDialog 组件打开文件
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: ca69de19ab1b9ae387002898145fe99e35a7b6b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182133"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>如何：使用打开文件对话框打开文件

组件<xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType>将打开用于浏览和选择文件的 Windows 对话框。 要打开和读取所选文件，可以使用 方法<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType>或创建类的<xref:System.IO.StreamReader?displayProperty=nameWithType>实例。 以下示例显示了这两种方法。

在 .NET 框架中，要获取<xref:System.Windows.Forms.FileDialog.FileName%2A>或设置该属性需要<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>类授予的权限级别。 这些示例运行<xref:System.Security.Permissions.FileIOPermission>权限检查，如果在部分信任上下文中运行，则由于权限不足，可能会引发异常。 有关详细信息，请参阅[代码访问安全基础知识](../../misc/code-access-security-basics.md)。

可以从 C# 或 Visual Basic 命令行生成和运行这些示例为 .NET 框架应用。 有关详细信息，请参阅使用[csc.exe 的命令行构建](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)或[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。

从 .NET Core 3.0 开始，您还可以从具有 .NET 核心 Windows 窗体*\<文件夹名称>.csproj*项目文件的文件夹中生成并运行 Windows .NET Core 应用示例。

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>示例：使用流阅读器将文件作为流读取  
  
下面的示例使用 Windows 窗体<xref:System.Windows.Forms.Button>控件<xref:System.Windows.Forms.Control.Click>的事件处理程序打开 方法 。 <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 用户选择文件并选择 **"确定"** 后，<xref:System.IO.StreamReader>类的实例读取该文件并在窗体的文本框中显示其内容。 有关从文件流读取的详细信息，请参阅<xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType>和<xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>。  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>示例：使用 OpenFile 从筛选的选择中打开文件

下面的示例使用<xref:System.Windows.Forms.Button>控件<xref:System.Windows.Forms.Control.Click>的事件处理程序<xref:System.Windows.Forms.OpenFileDialog>打开 仅显示文本文件的筛选器。 用户选择文本文件并选择 **"确定"** 后，<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>该方法将用于在记事本中打开该文件。

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.OpenFileDialog>
- [打开文件对话组件](openfiledialog-component-windows-forms.md)
