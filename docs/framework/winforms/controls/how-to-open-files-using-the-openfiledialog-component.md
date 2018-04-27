---
title: 如何：使用 OpenFileDialog 组件打开文件
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7da2c660f09da74c84d29459cf283a021ed12c99
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a>如何：使用 OpenFileDialog 组件打开文件
<xref:System.Windows.Forms.OpenFileDialog>组件，用户可以浏览他们的计算机或网络上的任何计算机的文件夹并选择一个或多个要打开的文件。 对话框返回用户在对话框中所选的文件路径和名称。  
  
 用户选定要打开的文件后，可以使用两种机制来打开文件。 如果想要使用文件流，则可以创建的实例<xref:System.IO.StreamReader>类。 或者，可以使用<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法打开所选的文件。  
  
 下面的第一个示例涉及<xref:System.Security.Permissions.FileIOPermission>权限检查 （如在下面的"安全说明"中所述），但是，可以访问为文件名。 你可以在本地计算机、Intranet 以及 Internet 区域中使用这种技术。 第二种方法还执行<xref:System.Security.Permissions.FileIOPermission>权限检查，但适合更好地用于 Intranet 或 Internet 区域中的应用程序。  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a>使用 OpenFileDialog 组件以流形式打开文件  
  
1.  显示“打开文件”对话框，并调用方法来打开用户选择的文件。  
  
     一种方法是使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以显示打开文件对话框中，并使用的实例<xref:System.IO.StreamReader>类来打开文件。  
  
     下面的示例使用<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件处理程序来打开的实例<xref:System.Windows.Forms.OpenFileDialog>组件。 当用户选定某个文件并单击“确定”时，将打开对话框中所选的文件。 在这种情况下，内容会显示在一个消息框中，用于说明已经读取文件流。  
  
    > [!IMPORTANT]
    >  要获取或设置<xref:System.Windows.Forms.FileDialog.FileName%2A>属性，您的程序集需要特权级别授予通过<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>类。 如果在部分信任上下文中运行，该进程可能会因特权不足而引发异常。 有关详细信息，请参阅[代码访问安全性基础知识](../../../../docs/framework/misc/code-access-security-basics.md)。  
  
     该示例假定你的窗体具有<xref:System.Windows.Forms.Button>控件和<xref:System.Windows.Forms.OpenFileDialog>组件。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If OpenFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         Dim sr As New System.IO.StreamReader(OpenFileDialog1.FileName)  
         MessageBox.Show(sr.ReadToEnd)  
         sr.Close()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          System.IO.StreamReader sr = new   
             System.IO.StreamReader(openFileDialog1.FileName);  
          MessageBox.Show(sr.ReadToEnd());  
          sr.Close();  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             System::IO::StreamReader ^ sr = gcnew  
                System::IO::StreamReader(openFileDialog1->FileName);  
             MessageBox::Show(sr->ReadToEnd());  
             sr->Close();  
          }  
       }  
    ```  
  
     (Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数以注册事件处理程序。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  从文件流中读取有关的详细信息，请参阅<xref:System.IO.FileStream.BeginRead%2A>和<xref:System.IO.FileStream.Read%2A>。  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a>使用 OpenFileDialog 组件以文件形式打开文件  
  
1.  使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以显示对话框中和<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法打开该文件。  
  
     <xref:System.Windows.Forms.OpenFileDialog>组件的<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法返回的字节构成文件。 这些字节提供可从中读取的流。 在示例中， <xref:System.Windows.Forms.OpenFileDialog> "光标"筛选器，允许用户选择仅具有文件扩展名的文件与实例化组件`.cur`。 选择 `.cur` 文件后，窗体的光标将设置为所选光标。  
  
    > [!IMPORTANT]
    >  若要调用<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法，您的程序集需要特权级别授予通过<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>类。 如果在部分信任上下文中运行，该进程可能会因特权不足而引发异常。 有关详细信息，请参阅[代码访问安全性基础知识](../../../../docs/framework/misc/code-access-security-basics.md)。  
  
     该示例假定你的窗体具有<xref:System.Windows.Forms.Button>控件。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' Displays an OpenFileDialog so the user can select a Cursor.  
       Dim openFileDialog1 As New OpenFileDialog()  
       openFileDialog1.Filter = "Cursor Files|*.cur"  
       openFileDialog1.Title = "Select a Cursor File"  
  
       ' Show the Dialog.  
       ' If the user clicked OK in the dialog and   
       ' a .CUR file was selected, open it.  
       If openFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         ' Assign the cursor in the Stream to the Form's Cursor property.  
         Me.Cursor = New Cursor(openFileDialog1.OpenFile())  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // Displays an OpenFileDialog so the user can select a Cursor.  
       OpenFileDialog openFileDialog1 = new OpenFileDialog();  
       openFileDialog1.Filter = "Cursor Files|*.cur";  
       openFileDialog1.Title = "Select a Cursor File";  
  
       // Show the Dialog.  
       // If the user clicked OK in the dialog and  
       // a .CUR file was selected, open it.  
        if (openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          // Assign the cursor in the Stream to the Form's Cursor property.  
          this.Cursor = new Cursor(openFileDialog1.OpenFile());  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays an OpenFileDialog so the user can select a Cursor.  
          OpenFileDialog ^ openFileDialog1 = new OpenFileDialog();  
          openFileDialog1->Filter = "Cursor Files|*.cur";  
          openFileDialog1->Title = "Select a Cursor File";  
  
          // Show the Dialog.  
          // If the user clicked OK in the dialog and  
          // a .CUR file was selected, open it.  
          if (openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             // Assign the cursor in the Stream to  
             // the Form's Cursor property.  
             this->Cursor = gcnew  
                System::Windows::Forms::Cursor(  
                openFileDialog1->OpenFile());  
          }  
       }  
    ```  
  
     (Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数以注册事件处理程序。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [OpenFileDialog 组件](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
