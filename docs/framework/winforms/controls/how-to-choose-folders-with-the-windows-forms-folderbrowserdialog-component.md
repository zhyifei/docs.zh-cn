---
title: 选择具有 FolderBrowserDialog 组件的文件夹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: 313388442101f341cfed366143f3c9669fb45cbd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742227"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>如何：使用 Windows 窗体 FolderBrowserDialog 组件选择文件夹

通常，在创建的 Windows 应用程序内，需要提示用户选择文件夹，最常用于保存一组文件。 Windows 窗体 <xref:System.Windows.Forms.FolderBrowserDialog> 组件允许你轻松完成此任务。

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>使用 FolderBrowserDialog 组件选择文件夹

1. 在过程中，检查 <xref:System.Windows.Forms.FolderBrowserDialog> 组件的 <xref:System.Windows.Forms.Form.DialogResult%2A> 属性以查看对话框的关闭方式，并获取 <xref:System.Windows.Forms.FolderBrowserDialog> 组件 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 属性的值。

2. 如果需要设置将在对话框的树视图中显示的最顶层文件夹，请设置 <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> 属性，该属性采用 <xref:System.Environment.SpecialFolder> 枚举的成员。

3. 此外，还可以设置 <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> 属性，该属性指定在文件夹浏览器树视图顶部显示的文本字符串。

    在下面的示例中，<xref:System.Windows.Forms.FolderBrowserDialog> 组件用于选择文件夹，类似于在 Visual Studio 中创建项目时，系统会提示选择要保存的文件夹。 在此示例中，文件夹名称随后显示在窗体上的 <xref:System.Windows.Forms.TextBox> 控件中。 最好将该位置放置在可编辑的区域（如 <xref:System.Windows.Forms.TextBox> 控件）中，以便在出现错误或其他问题时，用户可以编辑其选择。 此示例假设窗体具有 <xref:System.Windows.Forms.FolderBrowserDialog> 组件和 <xref:System.Windows.Forms.TextBox> 控件。

    ```vb
    Public Sub ChooseFolder()
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then
            TextBox1.Text = FolderBrowserDialog1.SelectedPath
        End If
    End Sub
    ```

    ```csharp
    public void ChooseFolder()
    {
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)
        {
            textBox1.Text = folderBrowserDialog1.SelectedPath;
        }
    }
    ```

    ```cpp
    public:
       void ChooseFolder()
       {
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)
          {
             textBox1->Text = folderBrowserDialog1->SelectedPath;
          }
       }
    ```

    > [!IMPORTANT]
    > 若要使用此类，程序集需要 <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> 属性授予的特权级别，这是 <xref:System.Security.Permissions.FileIOPermissionAccess> 枚举的一部分。 如果在部分信任上下文中运行，该进程可能会因特权不足而引发异常。 有关详细信息，请参阅[代码访问安全性基础知识](../../misc/code-access-security-basics.md)。

有关如何保存文件的信息，请参阅[如何：使用 SaveFileDialog 组件保存文件](how-to-save-files-using-the-savefiledialog-component.md)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [FolderBrowserDialog 组件概述（Windows 窗体）](folderbrowserdialog-component-overview-windows-forms.md)
- [FolderBrowserDialog 组件](folderbrowserdialog-component-windows-forms.md)
