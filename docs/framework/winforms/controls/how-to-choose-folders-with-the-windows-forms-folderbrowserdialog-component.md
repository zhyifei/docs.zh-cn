---
title: 如何：使用 Windows 窗体 FolderBrowserDialog 组件选择文件夹
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
ms.openlocfilehash: 657aad6efa195ec3d9741f4f91d4e01af4a54a19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>如何：使用 Windows 窗体 FolderBrowserDialog 组件选择文件夹
通常，在创建的 Windows 应用程序内，需要提示用户选择文件夹，最常用于保存一组文件。 Windows 窗体<xref:System.Windows.Forms.FolderBrowserDialog>组件允许你轻松地完成此任务。  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>使用 FolderBrowserDialog 组件选择文件夹  
  
1.  在过程中，检查<xref:System.Windows.Forms.FolderBrowserDialog>组件的<xref:System.Windows.Forms.Form.DialogResult%2A>属性，请参阅对话框中如何关闭并获取的值<xref:System.Windows.Forms.FolderBrowserDialog>组件的<xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>属性。  
  
2.  如果需要将对话框中的树视图中显示的组最顶层文件夹，将设置<xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>属性，采用的成员<xref:System.Environment.SpecialFolder>枚举。  
  
3.  此外，你可以设置<xref:System.Windows.Forms.FolderBrowserDialog.Description%2A>属性，用于指定文本字符串，将显示在文件夹浏览器树视图的顶部。  
  
     在示例中，<xref:System.Windows.Forms.FolderBrowserDialog>组件用于选择一个文件夹中，类似于你在 Visual Studio 中创建一个项目并提示您选择要将其保存在的文件夹。 在此示例中，文件夹名称然后显示在<xref:System.Windows.Forms.TextBox>窗体上的控件。 它是一个好办法位置放置在可编辑区域中，如<xref:System.Windows.Forms.TextBox>控制，以便用户可以编辑它们的选择发生错误或其他问题。 此示例假定的窗体具有<xref:System.Windows.Forms.FolderBrowserDialog>组件和<xref:System.Windows.Forms.TextBox>控件。  
  
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
    >  若要使用此类，您的程序集需要权限级别授予由<xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>属性，它是一部分的<xref:System.Security.Permissions.FileIOPermissionAccess>枚举。 如果在部分信任上下文中运行，该进程可能会因特权不足而引发异常。 有关详细信息，请参阅[代码访问安全性基础知识](../../../../docs/framework/misc/code-access-security-basics.md)。  
  
 有关如何保存文件的信息，请参阅[如何：使用 SaveFileDialog 组件保存文件](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [FolderBrowserDialog 组件概述（Windows 窗体）](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)  
 [FolderBrowserDialog 组件](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
