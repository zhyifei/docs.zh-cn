---
title: 如何：使用 OpenFileDialog 组件打开文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: d7e1ebb319576aa7a38d55d8cb9f3652626966b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542270"
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a><span data-ttu-id="33ce5-102">如何：使用 OpenFileDialog 组件打开文件</span><span class="sxs-lookup"><span data-stu-id="33ce5-102">How to: Open Files Using the OpenFileDialog Component</span></span>
<span data-ttu-id="33ce5-103"><xref:System.Windows.Forms.OpenFileDialog>组件，用户可以浏览他们的计算机或网络上的任何计算机的文件夹并选择一个或多个要打开的文件。</span><span class="sxs-lookup"><span data-stu-id="33ce5-103">The <xref:System.Windows.Forms.OpenFileDialog> component allows users to browse the folders of their computer or any computer on the network and select one or more files to open.</span></span> <span data-ttu-id="33ce5-104">对话框返回用户在对话框中所选的文件路径和名称。</span><span class="sxs-lookup"><span data-stu-id="33ce5-104">The dialog box returns the path and name of the file the user selected in the dialog box.</span></span>  
  
 <span data-ttu-id="33ce5-105">用户选定要打开的文件后，可以使用两种机制来打开文件。</span><span class="sxs-lookup"><span data-stu-id="33ce5-105">Once the user has selected the file to be opened, there are two approaches to the mechanism of opening the file.</span></span> <span data-ttu-id="33ce5-106">如果想要使用文件流，则可以创建的实例<xref:System.IO.StreamReader>类。</span><span class="sxs-lookup"><span data-stu-id="33ce5-106">If you prefer to work with file streams, you can create an instance of the <xref:System.IO.StreamReader> class.</span></span> <span data-ttu-id="33ce5-107">或者，可以使用<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法打开所选的文件。</span><span class="sxs-lookup"><span data-stu-id="33ce5-107">Alternately, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open the selected file.</span></span>  
  
 <span data-ttu-id="33ce5-108">下面的第一个示例涉及<xref:System.Security.Permissions.FileIOPermission>权限检查 （如在下面的"安全说明"中所述），但是，可以访问为文件名。</span><span class="sxs-lookup"><span data-stu-id="33ce5-108">The first example below involves a <xref:System.Security.Permissions.FileIOPermission> permission check (as described in the "Security Note" below), but gives you access to the filename.</span></span> <span data-ttu-id="33ce5-109">你可以在本地计算机、Intranet 以及 Internet 区域中使用这种技术。</span><span class="sxs-lookup"><span data-stu-id="33ce5-109">You can use this technique from the Local Machine, Intranet, and Internet zones.</span></span> <span data-ttu-id="33ce5-110">第二种方法还执行<xref:System.Security.Permissions.FileIOPermission>权限检查，但适合更好地用于 Intranet 或 Internet 区域中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="33ce5-110">The second method also does a <xref:System.Security.Permissions.FileIOPermission> permission check, but is better suited for applications in the Intranet or Internet zones.</span></span>  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a><span data-ttu-id="33ce5-111">使用 OpenFileDialog 组件以流形式打开文件</span><span class="sxs-lookup"><span data-stu-id="33ce5-111">To open a file as a stream using the OpenFileDialog component</span></span>  
  
1.  <span data-ttu-id="33ce5-112">显示“打开文件”对话框，并调用方法来打开用户选择的文件。</span><span class="sxs-lookup"><span data-stu-id="33ce5-112">Display the **Open File** dialog box and call a method to open the file selected by the user.</span></span>  
  
     <span data-ttu-id="33ce5-113">一种方法是使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以显示打开文件对话框中，并使用的实例<xref:System.IO.StreamReader>类来打开文件。</span><span class="sxs-lookup"><span data-stu-id="33ce5-113">One approach is to use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the Open File dialog box, and use an instance of the <xref:System.IO.StreamReader> class to open the file.</span></span>  
  
     <span data-ttu-id="33ce5-114">下面的示例使用<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件处理程序来打开的实例<xref:System.Windows.Forms.OpenFileDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="33ce5-114">The example below uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open an instance of the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="33ce5-115">当用户选定某个文件并单击“确定”时，将打开对话框中所选的文件。</span><span class="sxs-lookup"><span data-stu-id="33ce5-115">When a file is chosen and the user clicks **OK**, the file selected in the dialog box opens.</span></span> <span data-ttu-id="33ce5-116">在这种情况下，内容会显示在一个消息框中，用于说明已经读取文件流。</span><span class="sxs-lookup"><span data-stu-id="33ce5-116">In this case, the contents are displayed in a message box, just to show that the file stream has been read.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="33ce5-117">要获取或设置<xref:System.Windows.Forms.FileDialog.FileName%2A>属性，您的程序集需要特权级别授予通过<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="33ce5-117">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="33ce5-118">如果在部分信任上下文中运行，该进程可能会因特权不足而引发异常。</span><span class="sxs-lookup"><span data-stu-id="33ce5-118">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="33ce5-119">有关详细信息，请参阅[代码访问安全性基础知识](../../../../docs/framework/misc/code-access-security-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="33ce5-119">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="33ce5-120">该示例假定你的窗体具有<xref:System.Windows.Forms.Button>控件和<xref:System.Windows.Forms.OpenFileDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="33ce5-120">The example assumes your form has a <xref:System.Windows.Forms.Button> control and an <xref:System.Windows.Forms.OpenFileDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="33ce5-121">(Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="33ce5-121">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="33ce5-122">从文件流中读取有关的详细信息，请参阅<xref:System.IO.FileStream.BeginRead%2A>和<xref:System.IO.FileStream.Read%2A>。</span><span class="sxs-lookup"><span data-stu-id="33ce5-122">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A> and <xref:System.IO.FileStream.Read%2A>.</span></span>  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a><span data-ttu-id="33ce5-123">使用 OpenFileDialog 组件以文件形式打开文件</span><span class="sxs-lookup"><span data-stu-id="33ce5-123">To open a file as a file using the OpenFileDialog component</span></span>  
  
1.  <span data-ttu-id="33ce5-124">使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以显示对话框中和<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法打开该文件。</span><span class="sxs-lookup"><span data-stu-id="33ce5-124">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open the file.</span></span>  
  
     <span data-ttu-id="33ce5-125"><xref:System.Windows.Forms.OpenFileDialog>组件的<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法返回的字节构成文件。</span><span class="sxs-lookup"><span data-stu-id="33ce5-125">The <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method returns the bytes that compose the file.</span></span> <span data-ttu-id="33ce5-126">这些字节提供可从中读取的流。</span><span class="sxs-lookup"><span data-stu-id="33ce5-126">These bytes give you a stream to read from.</span></span> <span data-ttu-id="33ce5-127">在示例中， <xref:System.Windows.Forms.OpenFileDialog> "光标"筛选器，允许用户选择仅具有文件扩展名的文件与实例化组件`.cur`。</span><span class="sxs-lookup"><span data-stu-id="33ce5-127">In the example below, an <xref:System.Windows.Forms.OpenFileDialog> component is instantiated with a "cursor" filter on it, allowing the user to choose only files with the file name extension`.cur`.</span></span> <span data-ttu-id="33ce5-128">选择 `.cur` 文件后，窗体的光标将设置为所选光标。</span><span class="sxs-lookup"><span data-stu-id="33ce5-128">If a`.cur` file is chosen, the form's cursor is set to the selected cursor.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="33ce5-129">若要调用<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法，您的程序集需要特权级别授予通过<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="33ce5-129">To call the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="33ce5-130">如果在部分信任上下文中运行，该进程可能会因特权不足而引发异常。</span><span class="sxs-lookup"><span data-stu-id="33ce5-130">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="33ce5-131">有关详细信息，请参阅[代码访问安全性基础知识](../../../../docs/framework/misc/code-access-security-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="33ce5-131">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="33ce5-132">该示例假定你的窗体具有<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="33ce5-132">The example assumes your form has a <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
     <span data-ttu-id="33ce5-133">(Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="33ce5-133">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="33ce5-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="33ce5-134">See Also</span></span>  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [<span data-ttu-id="33ce5-135">OpenFileDialog 组件</span><span class="sxs-lookup"><span data-stu-id="33ce5-135">OpenFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
